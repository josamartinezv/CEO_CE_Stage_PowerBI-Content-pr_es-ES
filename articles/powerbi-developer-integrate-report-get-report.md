<properties
   pageTitle="Obtener un informe de Power BI"
   description="Tutorial para integrar un informe en una aplicación - obtener un informe de Power BI"
   services="powerbi"
   documentationCenter=""
   authors="guyinacube"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="monitoring"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="get-started-article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/23/2016"
   ms.author="asaxton"/>

# Paso 2: Obtener un informe

## Introducción

En **paso 1** de integración de un informe en una aplicación [registrar una aplicación web con Azure AD](powerbi-developer-integrate-report-register.md), registrar una aplicación web para que la aplicación pueda autenticar a **Azure Active Directory**. En este paso, usará un **token de acceso**, y el **Power BI** API para obtener un informe.

![](media\powerbi-developer-integrate-report\integrate-report-get-report.png)

Para obtener un **Power BI** de informes, utiliza el [obtener informes](https://msdn.microsoft.com/library/mt634543.aspx) operación que obtiene una lista de **Power BI** informes. En la lista de informes, puede obtener un informe **embedUrl**. Una vez que tenga un informe **embedUrl**, puede cargar un informe en un **IFrame**.

Para poder llamar el [obtener informes](https://msdn.microsoft.com/library/mt634543.aspx) operación o cualquier otro **Power BI** operación, debe obtener un Azure Active Directory **token de acceso de autenticación** (token de acceso). Un **token de acceso** se utiliza para permitir que su aplicación acceso a **Power BI** informes. Para obtener más información acerca de Azure Active Directory **token de acceso** flujo, consulte [flujo de concesión de código de autorización de AD Azure](https://msdn.microsoft.com/library/azure/dn645542.aspx). La sección siguiente muestra cómo obtener un **token de acceso** en una aplicación web.

<a name="get-token"/>
## Obtener un acceso de autenticación token

Aquí se muestra cómo obtener un token de acceso de autenticación para llamar a un **Power BI** operación.

-   
            **Paso 1:** [obtener un código de autorización de Azure AD](#auth-code)
-   
            **Paso 2:** [obtener un acceso token del código de autorización](#access-token)

<a name="auth-code"/>
### Paso 1: Obtener un código de autorización de Azure AD

El primer paso para obtener un **token de acceso** consiste en obtener un código de autorización de **Azure AD**. Para ello, cree una cadena de consulta con las siguientes propiedades y redirigir a **Azure AD**.


**Cadena de consulta del código de autorización**

```
var @params = new NameValueCollection
{
    //Azure AD will return an authorization code.
    {"response_type", "code"},

    //Client ID is used by the application to identify themselves to the users that they are requesting permissions from.
    //You get the client id when you register your Azure app.
    {"client_id", Settings.Default.ClientID},

    //Resource uri to the Power BI resource to be authorized
    //The resource uri is hard-coded for sample purposes
    {"resource", "https://analysis.windows.net/powerbi/api"},

    //After app authenticates, Azure AD will redirect back to the web app. In this sample, Azure AD redirects back
    //to Default page (Default.aspx).
    { "redirect_uri", Settings.Default.RedirectUri}
};
```

Después de construir una cadena de consulta, redirige a **Azure AD** para obtener un **código de autorización**.  A continuación se muestra un método C# completando para construir un **código de autorización** la cadena de consulta y redirigir a **Azure AD**. En el paso siguiente, obtendrá un **token de acceso** utilizando la **código de autorización**.

**Obtener código de autorización**

```
public void GetAuthorizationCode()
{
    //NOTE: Values are hard-coded for sample purposes.
    //Create a query string
    //Create a sign-in NameValueCollection for query string
    var @params = new NameValueCollection
    {
        //Azure AD will return an authorization code.
        {"response_type", "code"},

        //Client ID is used by the application to identify themselves to the users that they are requesting permissions from.
        //You get the client id when you register your Azure app.
        {"client_id", Settings.Default.ClientID},

        //Resource uri to the Power BI resource to be authorized
        //The resource uri is hard-coded for sample purposes
        {"resource", "https://analysis.windows.net/powerbi/api"},

        //After app authenticates, Azure AD will redirect back to the web app. In this sample, Azure AD redirects back
        //to Default page (Default.aspx).
        { "redirect_uri", Settings.Default.RedirectUri}
    };

    //Create sign-in query string
    var queryString = HttpUtility.ParseQueryString(string.Empty);
    queryString.Add(@params);

    //Redirect to Azure AD Authority
    //  Authority Uri is an Azure resource that takes a client id and client secret to get an Access token
    //  QueryString contains
    //      response_type of "code"
    //      client_id that identifies your app in Azure AD
    //      resource which is the Power BI API resource to be authorized
    //      redirect_uri which is the uri that Azure AD will redirect back to after it authenticates

    //Redirect to Azure AD to get an authorization code
    Response.Redirect(String.Format("https://login.windows.net/common/oauth2/authorize?{0}", queryString));
}
```

<a name="access-token"/>
### Paso 2: Obtener un token de acceso del código de autorización

En el paso 1 para obtener un acceso de autenticación token, obtendrá un **código de autorización** de Azure AD. Una vez **Azure AD** redirecciones hacia su aplicación web con un **código de autorización**, utiliza la **código de autorización** para obtener un token de acceso. A continuación se muestra un método de C# para obtener un **token de acceso**. En la sección siguiente, obtendrá un **informe** mediante un **token de acceso**.

**Obtener token de acceso**

```
public string GetAccessToken(string authorizationCode, string clientID, string clientSecret, string redirectUri)
{
    //Redirect uri must match the redirect_uri used when requesting Authorization code.
    //Note: If you use a redirect back to Default, as in this sample, you need to add a forward slash
    //such as http://localhost:13526/

    // Get auth token from auth code       
    TokenCache TC = new TokenCache();

    //Values are hard-coded for sample purposes
    string authority = "https://login.windows.net/common/oauth2/authorize";
    AuthenticationContext AC = new AuthenticationContext(authority, TC);
    ClientCredential cc = new ClientCredential(clientID, clientSecret);

    //Set token from authentication result
    return AC.AcquireTokenByAuthorizationCode(
        authorizationCode,
        new Uri(redirectUri), cc).AccessToken;
}
```

## Obtener el token con acceso de informe

Ahora que tiene un **token de acceso**, puede llamar a la [obtener informes](https://msdn.microsoft.com/library/mt634543.aspx) operación. El [obtener informes](https://msdn.microsoft.com/library/mt634543.aspx) operación devuelve una lista de informes. Puede obtener un informe de la lista de informes. A continuación se muestra un método C# completo para obtener un informe. Una vez que tenga una **informe**, se pueden cargar en un **IFrame**. Consulte [paso 3: cargar un informe de Power BI en un IFrame](powerbi-developer-integrate-report-load-report-iframe.md).

**Obtener informe**

```
protected void GetReport(int index)
{
    //Configure Reports request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}/Reports",
        baseUri)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get Reports response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBIReports Reports = JsonConvert.DeserializeObject<PBIReports>(reader.ReadToEnd());

            //Sample assumes at least one Report.
            //You could write an app that lists all Reports
            if (Reports.value.Length > 0)
                ReportEmbedUrl.Text = Reports.value[index].embedUrl;
        }
    }
}

//Power BI Reports used to deserialize the Get Reports response.
public class PBIReports
{
    public PBIReport[] value { get; set; }
}
public class PBIReport
{
    public string id { get; set; }
    public string name { get; set; }
    public string webUrl { get; set; }
    public string embedUrl { get; set; }
}
```

## Paso siguiente

Para integrar un informe en una aplicación, cargue un informe en un IFrame. En el paso siguiente, aprenderá cómo [cargar un informe en un IFrame](powerbi-developer-integrate-report-load-report-iframe.md).

[Siguiente paso >](powerbi-developer-integrate-report-load-report-iframe.md)

## Consulte también

[Registrarse para Power BI](powerbi-admin-free-with-custom-azure-directory.md)  
[Integrar un informe en un tutorial de la aplicación](powerbi-developer-integrate-report.md)  
[Integrar un informe de ejemplo](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-report-web-app)  
[Configurar la integración de un informe de ejemplo](powerbi-developer-integrate-report-register.md#configure-sample)  
[Flujo de concesión de código de autorización de Azure AD](https://msdn.microsoft.com/library/azure/dn645542.aspx)  
[Operación de informes de obtención de](https://msdn.microsoft.com/library/mt634543.aspx)  
[Paso 3: Cargar un informe de Power BI en un IFrame](powerbi-developer-integrate-report-load-report-iframe.md)  
¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
<properties
   pageTitle="Un panel de Power BI"
   description="Tutorial para integrar un mosaico en una aplicación - obtener un panel de Power BI"
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

# Paso 2: Obtener un panel

## Introducción

En **paso 1** de integración de un mosaico en una aplicación [registrar una aplicación web con Azure AD](powerbi-developer-integrate-tile-register.md), registrar una aplicación web para que la aplicación pueda autenticar a **Azure Active Directory**. En este paso, usará un **token de acceso**, y el **Power BI** API para obtener un panel. Después de obtener un panel, puede obtener un **Power BI** en mosaico.

![](media\powerbi-developer-integrate-tile\integrate-tile-get-dashboard.png)

Para obtener un **Power BI** panel, use la [paneles obtener](https://msdn.microsoft.com/library/mt465739.aspx) operación que obtiene una lista de **Power BI** paneles. En la lista de paneles, puede obtener un identificador del panel. Una vez que tenga un identificador del panel, puede obtener un **Power BI** en mosaico.

Para poder llamar el [obtener paneles](https://msdn.microsoft.com/library/mt465739.aspx) operación o cualquier otro **Power BI** operación, debe obtener un Azure Active Directory **token de acceso de autenticación** (token de acceso). Un **token de acceso** se utiliza para permitir que su aplicación acceso a **Power BI** paneles y mosaicos. Para obtener más información acerca de Azure Active Directory **token de acceso** flujo, consulte [flujo de concesión de código de autorización de AD Azure](https://msdn.microsoft.com/library/azure/dn645542.aspx). La sección siguiente muestra cómo obtener un **token de acceso** en una aplicación web.

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

En el paso 1 para obtener un acceso de autenticación token, obtendrá un **código de autorización** de Azure AD. Una vez **Azure AD** redirecciones hacia su aplicación web con un **código de autorización**, utiliza la **código de autorización** para obtener un token de acceso. A continuación se muestra un método de C# para obtener un **token de acceso**. En la sección siguiente, obtendrá un **panel** mediante un **token de acceso**.

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

## Obtener el token con acceso de escritorio

Ahora que tiene un **token de acceso**, puede llamar a la [paneles obtener](https://msdn.microsoft.com/library/mt465739.aspx) operación. El [obtener paneles](https://msdn.microsoft.com/library/mt465739.aspx) operación devuelve una lista de paneles. Puede obtener un panel de la lista de paneles. A continuación se muestra un método C# completo a un panel. Una vez que tenga una **panel**, puede obtener una **icono**. Consulte [paso 3: obtener un mosaico de Power BI]( powerbi-developer-integrate-tile-get-tile.md).

**Panel**

```
//Get a dashboard id.
protected string GetDashboard(int index)
{
    string dashboardId = string.Empty;

    //Configure tiles request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}Dashboards",
        baseUri)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get dashboards response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBIDashboards dashboards = JsonConvert.DeserializeObject<PBIDashboards>(reader.ReadToEnd());

            //Sample assumes at least one Dashboard with one Tile.
            //You could write an app that lists all tiles in a dashboard
            dashboardId = dashboards.value[index].id;
        }
    }

    return dashboardId;
}

//Power BI Dashboards used to deserialize the Get Dashboards response.
public class PBIDashboards
{
    public PBIDashboard[] value { get; set; }
}
public class PBIDashboard
{
    public string id { get; set; }
    public string displayName { get; set; }
}
```

## Paso siguiente

Para integrar un mosaico en una aplicación, debe obtener un mosaico. En el paso siguiente, aprenderá cómo [obtener un mosaico de Power BI](powerbi-developer-integrate-tile-get-tile.md).

[Siguiente paso >](powerbi-developer-integrate-tile-get-tile.md)

## Consulte también

[Registrarse para Power BI](powerbi-admin-free-with-custom-azure-directory.md)  
[Integrar un mosaico en un tutorial de la aplicación](powerbi-developer-integrate-tile.md)  
[Integrar un mosaico de ejemplo](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app)  
[Configurar la integración de un mosaico de ejemplo](powerbi-developer-integrate-tile-register.md#configure-sample)  
[Flujo de concesión de código de autorización de Azure AD](https://msdn.microsoft.com/library/azure/dn645542.aspx)  
[Paneles de la operación de obtención](https://msdn.microsoft.com/library/mt465739.aspx)  
[Paso 3: Obtener un mosaico de Power BI](powerbi-developer-integrate-tile-get-tile.md)  
¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
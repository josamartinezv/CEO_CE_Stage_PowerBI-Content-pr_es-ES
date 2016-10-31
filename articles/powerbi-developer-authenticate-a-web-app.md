<properties
   pageTitle="Autenticar una aplicación web"
   description="Autenticar una aplicación web"
   services="powerbi"
   documentationCenter=""
   authors="guyinacube"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="no"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/23/2016"
   ms.author="asaxton"/>

# Autenticar una aplicación web


            [Descargue el ejemplo de aplicación web](http://go.microsoft.com/fwlink/?LinkId=619279) | Ver el código en GitHub: [Default.aspx.cs](https://github.com/Microsoft/PowerBI-CSharp/blob/master/samples/webforms/get-started-web-app-asp.net/PBIWebApp/Default.aspx.cs) | [Redirect.aspx.cs](https://github.com/Microsoft/PowerBI-CSharp/blob/master/samples/webforms/get-started-web-app-asp.net/PBIWebApp/redirect.aspx.cs)

Este artículo muestra cómo autenticar una aplicación web de Power BI. Incluye ejemplos de C#; Sin embargo, el proceso de autenticación es el mismo para otro lenguajes de programación web. Hay un [ejemplo de aplicación web en GitHub](http://go.microsoft.com/fwlink/?LinkId=619279). Para obtener información sobre cómo ejecutar el ejemplo, vea [ejemplo de aplicación Web](https://msdn.microsoft.com/library/mt186158.aspx).

Aplicaciones web de Power BI usan Active Directory (AAD) para autenticar a los usuarios y proteger aplicaciones. La autenticación es el proceso de identificar una aplicación o usuario. Para identificar la aplicación web en AAD, registre la aplicación con AAD. Al registrar una aplicación web en AAD, concede a la aplicación acceso a los recursos de la API de REST de Power BI. Para obtener información sobre cómo registrar su aplicación web de Power BI, consulte [registrar una aplicación web](powerbi-developer-register-a-web-app.md).

Para obtener más información acerca del flujo de autorización de Azure Active Directory (Azure AD), consulte [flujo de concesión de código de autorización](https://msdn.microsoft.com/library/azure/dn645542.aspx).


            **NOTA** para Power BI, se crean aplicaciones como aplicaciones de varios inquilinos mediante el Portal de administración.

## Lo que necesita para autenticar una aplicación web de Power BI
Estos son los pasos para autenticar una aplicación web de Power BI y realizar una solicitud web REST. Estos pasos se aplican a una aplicación web ASP.NET; Sin embargo, los pasos se aplican a otras plataformas. Para obtener más información sobre OAuth 2.0 en Azure AD, consulte [OAuth 2.0 en Azure AD](https://msdn.microsoft.com/library/azure/dn645545.aspx).
<a name="register"/>
### Paso 1: registrar la aplicación web
Al registrar una aplicación web en Azure Active Directory, concede a la aplicación acceso a los recursos de la API de REST de Power BI. Para registrar una aplicación web de Power BI, consulte [registrar una aplicación web](powerbi-developer-register-a-web-app.md).
<a name="configure"/>
### Paso 2: configurar las opciones de Power BI para autenticarse con Azure AD
Esta es la configuración que necesita para autenticar una aplicación web de Power BI con Azure AD.

|Setting|Descripción|Valor|
|:--|:--|:--|
|Identificador de cliente|Id. de cliente se utiliza la aplicación para identificarse ante los usuarios que están solicitando permisos.|Para obtener un identificador de cliente de aplicación de Power BI, vea [cómo obtener un identificador de la aplicación cliente](powerbi-developer-register-a-web-app.md#clientID).|
|Secreto del cliente|La clave secreta de cliente se envía junto con un identificador de cliente para autenticar a Azure AD para llamar a una API web.|Para obtener un Power BI clave secreta de cliente de aplicación, vea [cómo obtener un cliente clave secreta](powerbi-developer-register-a-web-app.md#clientSecret).|
|Uri de recurso|El Uri de recurso para el recurso de Power BI a autorizar. Debe utilizar este Uri exacto.|https://Analysis.Windows.NET/powerbi/API|
|Uri de la entidad|La autoridad de Uri es un recurso de Azure que toma un identificador de cliente para obtener un token de acceso.|https://Login.Windows.NET/Common/oauth2/Authorize|
|Dirección Url de redireccionamiento|Una dirección Url de redireccionamiento para la url de la aplicación web. El servicio de Azure AD redirige a la dirección url de aplicación web con un código de autenticación.|Ejemplo: 13526/Redirect|

<a name="create"/>
### Paso 3: crear una cadena de consulta para obtener el código de autorización de Azure AD
Para autenticar una aplicación web de Power BI, primero hay que crear una cadena de consulta de dirección url para redirigir al servicio de autenticación de Azure AD. Después de proporcionar credenciales válidas, Azure AD devuelve un código de autorización. El siguiente es un ejemplo de una url de AD de Azure completo con cadena de consulta. Utilice una dirección url similar a la siguiente para obtener un código de autorización de Azure AD. Use **Response.Redirect**() para redirigir al servicio de Azure AD que devolverá un código de autorización de Azure AD. Use el código de autorización en el paso 4 para adquirir un token de acceso mediante código de autorización.

    https://login.windows.net/common/oauth2/authorize
      ?response_type=code
      &client_id=1861585d...9a79c296
      &resource= https://analysis.windows.net/powerbi/api
      &redirect_uri= http://localhost:13526/Redirect

**Configuración de la cadena de consulta de autenticación de Power BI**

|Setting|Descripción|
|:--|:--|
|response_type = código|Azure AD devuelve un código de autorización.|
|client_id = d 1861585... 9a79c296|Id. de cliente se utiliza la aplicación para identificarse ante los usuarios que están solicitando permisos. Obtiene el identificador de cliente al registrar la aplicación de Azure.|
|recurso = https://analysis.windows.net/powerbi/api|Uri de recurso para el recurso de Power BI a autorizar. Debe utilizar este Uri exacto.|
|URI de redireccionamiento = 13526/Redirect|Una vez que se autentica el usuario, Azure AD redirigirá a la aplicación web.|

Este es un ejemplo de código de C# para crear una dirección url de autorización de Azure AD con una cadena de consulta y redirigir al servicio de autoridad de Azure AD.

**Por ejemplo: C# de inicio de sesión**

        protected void signInButton_Click(object sender, EventArgs e)
        {
            //Create a query string
            //Create a sign-in NameValueCollection for query string
            var @params = new NameValueCollection
            {
                //Azure AD will return an authorization code.
                //See the Redirect class to see how "code" is used to AcquireTokenByAuthorizationCode
                {"response_type", "code"},

                //Client ID is used by the application to identify themselves to the users that they are requesting permissions from.
                //You get the client id when you register your Azure app.
                {"client_id", Properties.Settings.Default.ClientID},

                //Resource uri to the Power BI resource to be authorized
                {"resource", "https://analysis.windows.net/powerbi/api"},

                //After user authenticates, Azure AD will redirect back to the web app
                {"redirect_uri", "http://localhost:13526/Redirect"}
            };

            //Create sign-in query string
            var queryString = HttpUtility.ParseQueryString(string.Empty);
            queryString.Add(@params);

            //Redirect authority
            //Authority Uri is an Azure resource that takes a client id to get an Access token
            string authorityUri = "https://login.windows.net/common/oauth2/authorize/";
            Response.Redirect(String.Format("{0}?{1}", authorityUri, queryString));       
        }
<a name="acquire"/>
### Paso 4: adquirir un token de acceso de Azure AD con código de autorización

Para realizar una solicitud de datos en el servicio REST de Power BI, deberá suministrar un token de acceso. En una aplicación web. NET, se utiliza el [biblioteca de autenticación de Azure AD para paquete de nuget de .NET](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) para obtener un token de acceso. Si no tiene la biblioteca de autenticación de Windows Azure (AAL), vea [cómo agregar biblioteca de autenticación de Azure Active Directory](#add).

Después de la aplicación redirige a la autoridad de Azure AD Uri y adquiere un código de autorización, la aplicación obtiene un token por código de autorización. Aquí es cómo puede obtener el código de autorización y obtener un token de acceso de la aplicación: **en redirigir clase**:

1.  Obtiene el código de autenticación de Azure AD que se devuelve de Azure AD.

    ```
    string code = Request.Params.GetValues(0)[0];
    ```
2.  Crear un **AuthenticationContext** pasando el uri de la entidad y un TokenCache.

    ```
    TokenCache TC = new TokenCache();

    AuthenticationContext AC = new AuthenticationContext(authorityUri, TC);
    ```

3.  Crear un **ClientCredential** pasa la aplicación de Azure **Id. de cliente** y aplicación de Azure **secreto de cliente**.

    ```
    ClientCredential cc = new ClientCredential(Properties.Settings.Default.ClientID, Properties.Settings.Default.ClientSecretKey);
    ```

4.  Obtener un token por código de autorización pasando la **código de autenticación** devuelto por Azure AD y un **dirección url de redireccionamiento**.

    ```
    AuthenticationResult AR = AC.AcquireTokenByAuthorizationCode(code, new Uri(redirectUri), cc);
    ```

5.  Redireccionar a default.aspx.

    ```
    Response.Redirect("/Default.aspx");
    ```

6.  Establecer una cadena de índice "authResult" de sesión en AuthenticationResult para que pueda usar el resultado en la página default.aspx.

    ```
    Session["authResult"] = AR;
    ```


            **En una página Default.aspx**:

1.  Obtener un **AuthenticationResult** de la sesión. En el paso 4, use la **AuthenticationResult** para obtener una autorización **AccessToken**.

    ```
    AuthenticationResult authResult = (AuthenticationResult)Session["authResult"];
    ```

Este es el código completo para adquirir un token de acceso de Azure por código de autorización y redireccione a default.aspx.


            **Nota** el Uri de redireccionamiento debe coincidir con el URI de redireccionamiento usada para solicitar el código de autorización.

    public partial class Redirect : System.Web.UI.Page
    {
      protected void Page_Load(object sender, EventArgs e)
      {
          //Redirect uri must match the redirect_uri used when requesting Authorization code.
          string redirectUri = "http://localhost:13526/Redirect";
          string authorityUri = "https://login.windows.net/common/oauth2/authorize/";

          // Get the auth code
          string code = Request.Params.GetValues(0)[0];

          // Get auth token from auth code       
          TokenCache TC = new TokenCache();

          AuthenticationContext AC = new AuthenticationContext(authorityUri, TC);
          ClientCredential cc = new ClientCredential
              (Properties.Settings.Default.ClientID,
              Properties.Settings.Default.ClientSecret);

          AuthenticationResult AR = AC.AcquireTokenByAuthorizationCode(code, new Uri(redirectUri), cc);

          //Set Session "authResult" index string to the AuthenticationResult
          Session["authResult"] = AR;

          //Redirect back to Default.aspx
          Response.Redirect("/Default.aspx");
      }
    }

    public partial class _Default : Page
    {
      public AuthenticationResult authResult { get; set; }
      string baseUri = "https://api.powerbi.com/beta/myorg/";

      protected void Page_Load(object sender, EventArgs e)
      {

          //Test for AuthenticationResult
          if (Session["authResult"] != null)
          {
              //Get the authentication result from the session
              authResult = (AuthenticationResult)Session["authResult"];

              //Show Power BI Panel
              signInStatus.Visible = true;

              //Set user and token from authentication result
              userLabel.Text = authResult.UserInfo.DisplayableId;
              accessTokenTextbox.Text = authResult.AccessToken;
          }
      }

      ...
    }

<a name="use"/>
### Paso 5: token de acceso usar Azure AD para llamar a una operación de Power BI

Llamadas de API de REST de BI de energía se realizan en nombre de un usuario autenticado pasando un token de acceso adquirido a través de Azure Active Directory, en el encabezado "Autorización". Después de obtener un token de acceso de Active Directory (AAD), use el token para realizar una solicitud web en la API de REST de Power BI.

Una vez establecida una **AuthenticationResult** al adquirir un token por código de autorización (**AcquireTokenByAuthorizationCode**), obtener un acceso de Azure token obteniendo el **AccessToken** propiedad de **AuthenticationResult**.
Este es el código para obtener Power BI **conjuntos de datos**.  El ejemplo de código se crea un **WebRequest** y deserializa la cadena de respuesta a un conjunto de datos.
Para obtener acceso a la API de REST de Power BI, cree un encabezado de solicitud estableciendo "Autorización" en "Portador {AccessToken}":

    request.Headers.Add("Authorization", String.Format("Bearer {0}", authResult.AccessToken));

**Ejemplo de C#: obtener conjuntos de datos de BI de energía**

        protected void getDatasetsButton_Click(object sender, EventArgs e)
        {
            string responseContent = string.Empty;

            //The resource Uri to the Power BI REST API resource
            string datasetsUri = "https://api.powerbi.com/v1.0/myorg/datasets";

            //Configure datasets request
            System.Net.WebRequest request = System.Net.WebRequest.Create(datasetsUri) as System.Net.HttpWebRequest;
            request.Method = "GET";
            request.ContentLength = 0;
            request.Headers.Add("Authorization", String.Format("Bearer {0}", authResult.AccessToken));

            //Get datasets response from request.GetResponse()
            using (var response = request.GetResponse() as System.Net.HttpWebResponse)
            {
                //Get reader from response stream
                using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
                {
                    responseContent = reader.ReadToEnd();

                    //Deserialize JSON string
                    //JavaScriptSerializer class is in System.Web.Script.Serialization
                    JavaScriptSerializer json = new JavaScriptSerializer();
                    Datasets datasets = (Datasets)json.Deserialize(responseContent, typeof(Datasets));

                    resultsTextbox.Text = string.Empty;
                    //Get each Dataset from
                    foreach (dataset ds in datasets.value)
                    {
                        resultsTextbox.Text += String.Format("{0}\t{1}\n", ds.Id, ds.Name);
                    }
                }
            }
        }

    public class Datasets
    {
        public dataset[] value { get; set; }
    }

    public class dataset
    {
        public string Id { get; set; }
        public string Name { get; set; }
    }

<a name="add"/>
## Cómo agregar la biblioteca de autenticación de Azure Active Directory
En una aplicación de cliente. NET, se utiliza **AuthenticationContext** en la biblioteca de autenticación de Active Directory para adquirir un token de acceso de Azure. Puede instalar el paquete de NuGet de biblioteca de autenticación de Active Directory desde Visual Studio. Cuando se instala un paquete de NuGet, Visual Studio crea una referencia a los ensamblados necesarios.

1. Haga clic una solución.
2. Elija Administrar paquetes de NuGet.
3. Búsqueda de la biblioteca de autenticación de Active Directory.
4. Elija la biblioteca de autenticación de Active Directory en la lista de paquetes y haga clic en instalar.

## Consulte también

[Biblioteca de autenticación de Azure AD para paquete de nuget de .NET](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)  
[Autenticación de Active Directory Library (ADAL) v1 para .NET](http://www.cloudidentity.com/blog/2013/09/12/active-directory-authentication-library-adal-v1-for-net-general-availability/)  
[OAuth 2.0 en Azure AD](https://msdn.microsoft.com/library/azure/dn645545.aspx)  
[Flujo de concesión de códigos de autorización](https://msdn.microsoft.com/library/azure/dn645542.aspx)  
[Escenarios de autenticación en Azure AD](https://msdn.microsoft.com/library/azure/dn499820.aspx)  
¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)

<properties
   pageTitle="Autenticar una aplicación cliente"
   description="Autenticar una aplicación cliente"
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

# Autenticar una aplicación cliente


            [Descargue el ejemplo de aplicación de cliente .NET](http://go.microsoft.com/fwlink/?LinkId=619280) | [Ver el código de GitHub](http://go.microsoft.com/fwlink/?LinkId=619429)

En este artículo se muestra cómo autenticar una aplicación de cliente de Power BI. Incluye ejemplos de C#; Sin embargo, el proceso de autenticación es el mismo para otros lenguajes de programación.

Para un completo ejemplo de C# que muestra cómo autenticar una aplicación de cliente de Power BI, consulte [ejemplo de aplicación de cliente](https://msdn.microsoft.com/library/mt186159.aspx).

Uso de aplicaciones de cliente de BI de energía **Azure Active Directory** (AAD) para autenticar a los usuarios y proteger las aplicaciones. La autenticación es el proceso de identificar una aplicación o usuario. Para identificar la aplicación cliente en AAD, registre la aplicación con AAD. Al registrar una aplicación cliente en AAD, concede a la aplicación acceso a las API de Power BI. Para obtener información sobre cómo registrar la aplicación de cliente de Power BI, consulte [registrar una aplicación de cliente](powerbi-developer-register-a-client-app.md).

Llamadas de API de REST de BI de energía se realizan en nombre de un usuario autenticado pasando un token en el encabezado "Autorización" de la solicitud. El token se adquiere a través de Azure Active Directory.


            **Nota** para Power BI Preview privada, se crean aplicaciones como aplicaciones de varios inquilinos mediante el Portal de administración.

<a name="What"></a>
## Lo que necesita para autenticar una aplicación de cliente de Power BI
Para autenticar una aplicación de cliente de Power BI y realizar una solicitud web REST, necesitará:

1. 
            **Registrar la aplicación cliente** : para registrar una aplicación de cliente de Power BI, consulte [registrar una aplicación de cliente](powerbi-developer-register-a-client-app.md).   Al registrar una aplicación cliente en **Azure Active Directory**, concede a la aplicación acceso a la API de Power BI.
2. 
            **Asignar el identificador de cliente para la aplicación** : para obtener el identificador de cliente para la aplicación, consulte [cómo obtener un identificador de la aplicación cliente](powerbi-developer-register-a-client-app.md#clientID). El identificador de cliente se utiliza la aplicación para identificarse ante los usuarios que están solicitando permisos.
    - En el código de la aplicación cliente, asigne el **clientID** variable al identificador de cliente de la aplicación de Azure.
3. 
            **Asignar el Uri de redireccionamiento** -para una aplicación cliente, un uri de redireccionamiento da a AAD más detalles acerca de la aplicación específica que autenticará. Un identificador uniforme de recursos (URI) es un valor para identificar un nombre de un recurso.
    - En el código de aplicación cliente, asigne el **redirectUri** a "https://login.live.com/oauth20_desktop.srf". Puesto que una aplicación cliente no tiene un servicio externo para redirigir a, este identificador URI es el marcador de posición estándar para las aplicaciones cliente.

4. 
            **Asignar el Uri de recurso para la API de Power BI** : el Uri de recurso identifica el recurso de la API de Power BI.
    - En el código de aplicación cliente, asigne el **resourceUri** a "https://analysis.windows.net/powerbi/api".
5. 
            **Asignar el uri de autoridad OAuth2** : el Uri de autoridad identifica el recurso de autoridad OAuth2.
    - En el código de la aplicación cliente, asigne un Uri de la entidad a "https://login.windows.net/common/oauth2/authorize".
6. 
            **Asignar el Uri del conjunto de datos para los conjuntos de datos de la API de Power BI** -los conjuntos de datos Uri identifican el recurso de conjuntos de datos de la API de Power BI.
    - En el código de aplicación cliente, asigne el **datasetsUri** a "https://api.powerbi.com/v1.0/myorg/datasets".

Para realizar una solicitud de datos en el servicio REST de Power BI, deberá suministrar un token de acceso. En una aplicación de cliente. NET, se utiliza el [biblioteca de autenticación de Azure AD para paquete de nuget de .NET](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) para obtener un token de acceso. Este es el proceso. A continuación se muestra un ejemplo **AccessToken()** método.

Si no tiene la biblioteca de autenticación de Windows Azure (AAL), vea [cómo agregar biblioteca de autenticación de Azure Active Directory](#Library).


            **Importante** para autenticar una aplicación cliente, debe agregar una referencia a **Microsoft.IdentityModel.Clients.ActiveDirectory** que se incluye en la biblioteca de autenticación de Windows Azure (ADAL).

## Pasos para obtener un token de acceso
1. 
            **Cree una instancia de AuthenticationContext** -AuthenticationContext es la clase principal que representa el token de emisión de autoridad para recursos de Azure AD. El constructor toma:
    - Un authorityUri OAuth2

    ```
            //OAuth2 authority Uri
            string authorityUri = "https://login.windows.net/common/oauth2/authorize";
    AuthenticationContext  authContext = new AuthenticationContext(authorityUri);
    ```
2. 
            **Llame a authenticationcontext.acquiretoken () para obtener un token** -el método toma:
    - Power BI API resourceUri
    - El clientID de aplicación Power BI
    - Su redirectUri de aplicación Power BI

    ```
    string token = authContext.AcquireToken(resourceUri, clientId, new Uri(redirectUri), PromptBehavior.RefreshSession).AccessToken;
    ```

Para obtener más información acerca de qué AuthenticationContext para obtener un token, consulte [flujo de contexto de autenticación de Azure](#Flow).

## Ejemplo de C#: token de acceso Get

En una aplicación de cliente. NET, se utiliza **AuthenticationContext** para obtener un token de acceso.

```
      static string AccessToken()
      {
            //Get access token:
            // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
            // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
            // To install the Active Directory Authentication Library NuGet package in Visual Studio,
            //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

            //Resource Uri for Power BI API
            string resourceUri = "https://analysis.windows.net/powerbi/api";

            string clientId = {clientIDFromAzureAppRegistration};

            //A redirect uri gives AAD more details about the specific application that it will authenticate.
            //Since a client app does not have an external service to redirect to, this Uri is the standard placeholder for a client app.
            string redirectUri = "https://login.live.com/oauth20_desktop.srf";

            // Create an instance of AuthenticationContext to acquire an Azure access token
            // OAuth2 authority Uri
            string authorityUri = "https://login.windows.net/common/oauth2/authorize";
            AuthenticationContext authContext = new AuthenticationContext(authorityUri);

            // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
            //  AcquireToken takes a Client Id that Azure AD creates when you register your client app.
            //  To learn how to register a client app and get a Client ID, see https://msdn.microsoft.com/library/dn877542(Azure.100).aspx   
            string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

            return token;
      }
```
<a name="Datarequest"></a>
## Realizar una solicitud de datos a la API de REST de Power BI utilizando un token

Después de obtener un token de acceso de Active Directory (AAD), use el token para realizar una solicitud web en la API de REST de Power BI. Para crear una solicitud web de REST de Power BI, agregar un token de acceso para el encabezado de solicitud como:


```
request.Headers.Add("Authorization", String.Format("Bearer {0}", AccessToken()));
```


## Ejemplo de C#: solicitud de datos de la API de REST de Power BI mediante un token

Para un completo ejemplo de C# que muestra cómo autenticar una aplicación de cliente de Power BI y llamar a todas las operaciones de REST de Power BI, consulte [ejemplo de aplicación cliente](https://msdn.microsoft.com/library/mt186159.aspx) o [Ver el código en GitHub](http://go.microsoft.com/fwlink/?LinkId=619429).

```
        static dataset[] GetDatasets()
        {
            //This is sample code to illustrate a Power BI operation.
            //In a production application, refactor code into specific methods and use appropriate exception handling.

            //Power BI Datasets Url
            string powerBIApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";

            //Get Azure AD access token (see above)
            string token = AccessToken();

            //GET web request to list all datasets.
            //To get a datasets in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
            HttpWebRequest request = System.Net.WebRequest.Create(powerBIApiUrl) as System.Net.HttpWebRequest;
            request.KeepAlive = true;
            request.Method = "GET";
            request.ContentLength = 0;
            request.ContentType = "application/json";

            //Add access token to Request header
            request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

            //Get HttpWebResponse from GET request
            using (HttpWebResponse httpResponse = request.GetResponse() as System.Net.HttpWebResponse)
            {
                //Get StreamReader that holds the response stream
                using (StreamReader reader = new System.IO.StreamReader(httpResponse.GetResponseStream()))
                {
                    string responseContent = reader.ReadToEnd();

                    JavaScriptSerializer jsonSerializer = new JavaScriptSerializer();
                    Datasets datasets = (Datasets)jsonSerializer.Deserialize(responseContent, typeof(Datasets));

                    return datasets.value;
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

```
<a name="Flow"></a>
## Flujo de contexto de autenticación de Azure
En una aplicación de cliente. NET, se utiliza **AuthenticationContext** para adquirir un token de acceso de Azure. 
            **AuthenticationContext** es la clase principal que representa el token de emisión de autoridad para recursos de Azure AD. 
            **AuthenticationContext** hace lo siguiente:

1. AuthenticationContext inicia el flujo redirigiendo el agente de usuario para el extremo de autorización de Azure Active Directory. El usuario se autentica y da su consentimiento, si este se requiere.

2. El extremo de autorización de Azure Active Directory redirige al usuario a AuthenticationContext con un código de autorización. El agente de usuario, devuelve un código de autorización al URI de redireccionamiento de la aplicación cliente.

3. AuthenticationContext solicita un token de acceso desde el extremo de emisión de tokens de Azure Active Directory. Presenta el código de autorización para demostrar que el usuario ha dado su consentimiento.

4. El extremo de emisión de tokens de Azure Active Directory devuelve un token de acceso.

5. La aplicación cliente usa el token de acceso para autenticar la API web.

6. Después de autenticar la aplicación cliente, la API de REST de Power BI devuelve los datos solicitados.


Para obtener más información acerca del flujo de autorización de Azure Active Directory (Azure AD), consulte [flujo de concesión de código de autorización](https://msdn.microsoft.com/library/azure/dn645542.aspx).

<a name="Library"></a>
## Cómo agregar la biblioteca de autenticación de Azure Active Directory

En una aplicación de cliente. NET, se utiliza **AuthenticationContext** en el **biblioteca de autenticación de Active Directory** para adquirir un token de acceso de Azure. Puede instalar el **biblioteca de autenticación de Active Directory** paquete de NuGet desde Visual Studio. Cuando se instala un paquete de NuGet, Visual Studio crea una referencia a los ensamblados necesarios.

1. Haga clic una solución.

2. Elija **Administrar paquetes de NuGet**.

3. Buscar **biblioteca de autenticación de Active Directory**.

4. Elija **biblioteca de autenticación de Active Directory** en la lista de paquetes y haga clic en **instalar**.

## Consulte también

[Biblioteca de autenticación de Azure AD para paquete de nuget de .NET](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)  
[Autenticación de Active Directory Library (ADAL) v1 para .NET](http://www.cloudidentity.com/blog/2013/09/12/active-directory-authentication-library-adal-v1-for-net-general-availability/)  
[OAuth 2.0 en Azure AD](https://msdn.microsoft.com/library/azure/dn645545.aspx)  
[Flujo de concesión de códigos de autorización](https://msdn.microsoft.com/library/azure/dn645542.aspx)  
[Escenarios de autenticación en Azure AD](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-scenarios/)  
¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
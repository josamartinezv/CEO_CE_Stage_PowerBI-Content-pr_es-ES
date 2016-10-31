<properties
   pageTitle="Autenticar el servicio Power BI"
   description="Autenticar el servicio Power BI"
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

# Autenticar el servicio Power BI

Este artículo es una introducción a la autenticación en Power BI y cómo obtener un token de acceso mediante un identificador de cliente. Para empezar a crear una aplicación Power BI, consulte [empezar a crear una aplicación Power BI](powerbi-developer-steps-to-create-a-power-bi-app.md).

La API de Power BI proporciona acceso mediante programación a los recursos del panel como conjuntos de datos, tablas y filas. Estos recursos están protegidos por **Azure Active Directory** (Azure AD). Para obtener acceso a **Power BI** recursos, se autentica la aplicación con **Azure AD**.

<a name="intro"/>
## Introducción a la autenticación en Power BI
Aplicaciones de Power BI se integran con **Azure Active Directory** (Azure AD) para proporcionar el inicio de sesión seguro y autorización para la aplicación. Para integrar una aplicación Power BI con Azure AD, registre los detalles acerca de la aplicación con Azure AD mediante el Portal de administración de Azure. Al registrar una aplicación en Azure Active Directory, la aplicación externaliza la autenticación a Azure AD. Registro de la aplicación implica informar a Azure AD acerca de la aplicación incluida la dirección URL donde se encuentra, la dirección URL para enviar respuestas después de la autenticación y el URI que identifica la aplicación. Al registrar una aplicación cliente o aplicación web en Azure AD, concede a la aplicación acceso a la API de REST de Power BI.

Una aplicación Power BI usa un **Id. de cliente** para identificarse a Azure AD. Consulte [identificador de cliente de aplicación de Azure](#clientID). Para una aplicación Web, también necesita una clave secreta de cliente. Consulte [clave secreta del cliente de aplicación web de Azure](#clientSecret).

Para obtener información sobre cómo registrar y autenticar una aplicación Power BI:

- 
            **Aplicación de cliente de Power BI**: consulte [registrar una aplicación cliente](powerbi-developer-register-a-client-app.md) y [autenticar una aplicación de cliente de Power BI](powerbi-developer-authenticate-a-client-app.md).

- 
            **Aplicación web de Power BI**: consulte [registrar una aplicación web](powerbi-developer-register-a-web-app.md) y [autenticar una aplicación web de Power BI](powerbi-developer-authenticate-a-web-app.md).

- Para aprender a usar la autenticación de Azure en distintas plataformas: la [bibliotecas de autenticación de Azure](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-libraries/) están disponibles en distintas plataformas para ayudar a los desarrolladores a autenticar a los usuarios en la nube o en Active Directory (AD) local para obtener tokens de acceso para proteger las llamadas de API. Este tema contiene una guía sobre las bibliotecas de autenticación disponibles en distintas plataformas y sobre recursos útiles para cada una de ellas, incluidos ejemplos y código fuente.

<a name="clientID"/>
## Identificador de cliente de aplicación de Azure
Una aplicación de Azure tiene un **Id. de cliente** que se utiliza la aplicación para identificarse ante los usuarios que están solicitando permisos. Utiliza un **Id. de cliente** para obtener un token de autenticación. Para obtener una Azure **Id. de cliente**, vea [cómo obtener un identificador de la aplicación cliente](powerbi-developer-register-a-client-app.md#clientID).

Para obtener un ejemplo completo de cómo usar una **Id. de cliente** para autenticar una aplicación de cliente, consulte [autenticar una aplicación cliente](powerbi-developer-authenticate-a-client-app.md).

Por ejemplo, el siguiente código de C# utiliza un identificador de cliente de aplicación de Azure para obtener un token de acceso.

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
            //  To learn how to register a client app and get a Client ID, see https://msdn.microsoft.com/en-US/library/dn877542(Azure.100).aspx   
            string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

            return token;
      }

<a name="clientSecret"/>
## Clave secreta del cliente de aplicación web de Azure
Al registrar una aplicación web, recibirá un secreto de cliente **clave**. El secreto del cliente **clave** se utiliza la aplicación web para identificarse de forma segura a los **servicio Power BI**. Para obtener un secreto de cliente de Azure **clave**, vea [cómo obtener un cliente clave secreta](powerbi-developer-register-a-web-app.md#clientSecret).

Para obtener un ejemplo completo de cómo usar una **Id. de cliente** y el secreto del cliente **clave** para autenticar una aplicación web, consulte [autenticar una aplicación web](powerbi-developer-authenticate-a-web-app.md).

## Consulte también

[Empezar a crear una aplicación Power BI](powerbi-developer-steps-to-create-a-power-bi-app.md)  
[Cómo obtener a un inquilino de Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-howto-tenant/)  
[Crear a un inquilino de Azure Active Directory](powerbi-developer-create-an-azure-active-directory-tenant.md)  
[Registrar una aplicación cliente](powerbi-developer-register-a-client-app.md)  
[Registrar una aplicación web](powerbi-developer-register-a-web-app.md)  
¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
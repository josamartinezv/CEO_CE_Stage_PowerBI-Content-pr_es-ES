<properties
   pageTitle="Obtener un acceso de autenticación token"
   description="Tutorial para insertar datos - obtener un acceso de autenticación token"
   services="powerbi"
   documentationCenter=""
   authors="guyinacube"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="monitoring"
   qualityDate="04/15/2016"/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="get-started-article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/23/2016"
   ms.author="asaxton"/>

# Paso 2: Obtener un acceso de autenticación token

Este artículo forma parte de un tutorial paso a paso para [Insertar datos en un panel](powerbi-developer-walkthrough-push-data.md).

En **paso 1** de insertar datos en un panel [registrar la aplicación con Azure AD](powerbi-developer-walkthrough-push-data-register-app-with-azure-ad.md), que ha registrado una aplicación cliente en Azure AD. En este paso, obtener un autenticación token de acceso. Aplicaciones de Power BI se integran con **Azure AD** para proporcionar el inicio de sesión seguro y autorización para la aplicación. Usar un token para autenticarse en **Azure AD** y tener acceso a recursos de Power BI.

Aquí se muestra cómo obtener un acceso de autenticación token.

## Obtener un acceso de autenticación token

>
            **NOTA**: antes de comenzar, asegúrese de que ha seguido los pasos anteriores en el [Insertar datos en un panel](powerbi-developer-walkthrough-push-data.md) tutorial.

1. En Visual Studio 2015, cree un **aplicación de consola** proyecto.
2. Instalar el [biblioteca de autenticación de Azure AD para el paquete NuGet de .NET](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/). Para obtener una seguridad de autenticación token en una aplicación. NET, use este paquete. Aquí se muestra cómo instalar el paquete:

     a. En Visual Studio 2015, elija **herramientas** > **Administrador de paquetes de NuGet** > **Package Manager Console**.

     b. En **Package Manager Console**, escriba Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory-versión 2.21.301221612.

3. Agregue el código siguiente a la clase Program {...}.
4. Reemplazar "{ClientID}", con el **Id. de cliente** que obtuvo al registrar la aplicación. Consulte [registrar la aplicación con Azure AD](powerbi-developer-walkthrough-push-data-register-app-with-azure-ad.md).
5. Después de instalar el paquete de Microsoft.IdentityModel.Clients.ActiveDirectory, agregue **utilizando Microsoft.IdentityModel.Clients.ActiveDirectory;** en Program.cs.
6. Ejecutar la aplicación de consola e inicie sesión en su cuenta de Power BI. Debería ver una cadena de token en la ventana de consola.

**Código de ejemplo para obtener tokens de seguridad de autenticación**

Agregue este código al programa {...}.

- Una variable de token para llamar a operaciones:

  ```
  private static string token = string.Empty;

  static void Main(string[] args)
  {
  }
  ```

- En static void Main (string [] args):

  ```
  static void Main(string[] args)
  {
    //Get an authentication access token
    token = GetToken();
  }
  ```

- Agregue un método GetToken():

```
       #region Get an authentication access token
       private static string GetToken()
       {
           // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
           // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

           //The client id that Azure AD created when you registered your client app.
           string clientID = "{Client_ID}";

           //RedirectUri you used when you register your app.
           //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
           // You can use this redirect uri for your client app
           string redirectUri = "https://login.live.com/oauth20_desktop.srf";

           //Resource Uri for Power BI API
           string resourceUri = "https://analysis.windows.net/powerbi/api";

           //OAuth2 authority Uri
           string authorityUri = "https://login.windows.net/common/oauth2/authorize";

           //Get access token:
           // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
           // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
           // To install the Active Directory Authentication Library NuGet package in Visual Studio,
           //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

           // AcquireToken will acquire an Azure access token
           // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
           AuthenticationContext authContext = new AuthenticationContext(authorityUri);
           string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

           Console.WriteLine(token);
           Console.ReadLine();

           return token;
       }

       #endregion
```

Después de obtener un token de autenticación, puede llamar a cualquier operación de Power BI. El paso siguiente muestra cómo llamar a la [Crear conjunto de datos](https://msdn.microsoft.com/library/mt203562.aspx) operación para crear un conjunto de datos para insertar datos en un panel.

El paso siguiente muestra cómo a [crear un conjunto de datos en un panel de Power BI](powerbi-developer-walkthrough-push-data-create-dataset.md).

A continuación se muestra la [código completo](#code).

[Siguiente paso >](powerbi-developer-walkthrough-push-data-create-dataset.md)

## Consulte también
- [Crear un conjunto de datos en un panel de Power BI](powerbi-developer-walkthrough-push-data-create-dataset.md)
- [Registrar una aplicación con Azure AD](powerbi-developer-walkthrough-push-data-register-app-with-azure-ad.md)
- [Biblioteca de autenticación de Azure AD para el paquete NuGet de .NET](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)
- [Insertar datos en un panel de Power BI](powerbi-developer-walkthrough-push-data.md)
- [Información general sobre la API de REST de Power BI](powerbi-developer-overview-of-power-bi-rest-api.md)
- [Referencia de API de REST de BI de energía](https://msdn.microsoft.com/library/mt147898.aspx)

<a name="code"/>
## Lista de código completa

    using System;
    using Microsoft.IdentityModel.Clients.ActiveDirectory;

    namespace walkthrough_push_data
    {
        class Program
        {
            private static string token = string.Empty;

            static void Main(string[] args)
            {

                //Get an authentication access token
                token = GetToken();

            }

            #region Get an authentication access token
            private static string GetToken()
            {
                // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
                // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

                //The client id that Azure AD created when you registered your client app.
                string clientID = "{Client_ID}";

                //RedirectUri you used when you register your app.
                //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
                // You can use this redirect uri for your client app
                string redirectUri = "https://login.live.com/oauth20_desktop.srf";

                //Resource Uri for Power BI API
                string resourceUri = "https://analysis.windows.net/powerbi/api";

                //OAuth2 authority Uri
                string authorityUri = "https://login.windows.net/common/oauth2/authorize";

                //Get access token:
                // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
                // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
                // To install the Active Directory Authentication Library NuGet package in Visual Studio,
                //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

                // AcquireToken will acquire an Azure access token
                // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
                AuthenticationContext authContext = new AuthenticationContext(authorityUri);
                string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

                Console.WriteLine(token);
                Console.ReadLine();

                return token;
            }

            #endregion

        }
    }

¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
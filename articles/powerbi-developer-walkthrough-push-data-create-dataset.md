<properties
   pageTitle="Crear un conjunto de datos"
   description="Tutorial: insertar datos en un panel: crear un conjunto de datos en un panel de Power BI"
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

# Paso 3: Crear un conjunto de datos en un panel de Power BI

Este artículo forma parte de un tutorial paso a paso para [Insertar datos en un panel](powerbi-developer-walkthrough-push-data.md).

En **paso 2** de insertar datos en un panel [obtener un acceso de autenticación token](powerbi-developer-walkthrough-push-data-get-token.md), obtuvo un token para autenticarse en **Azure AD**. En este paso, se utiliza el token para llamar la [Crear conjunto de datos](https://msdn.microsoft.com/library/mt203562.aspx) operación.

Para realizar una llamada a un recurso REST, utilice una dirección url que localiza el recurso y enviar una cadena de JavaScript Object Notation (JSON), que describe el conjunto de datos, para el recurso del servicio Power BI. Un recurso REST identifica la parte de la que desea trabajar con el servicio de Power BI. Para insertar datos en el panel, el recurso de destino es un **conjunto de datos del panel**. La dirección URL que identifica un conjunto de datos es https://api.PowerBI.com/v1.0/myorg/datasets. Si va a insertar datos de un grupo, la dirección url es https://api.PowerBI.com/v1.0/myorg/groups/ {group_id} / conjuntos de datos.

Para autenticar una operación de REST de Power BI, agregará el token que obtuvo en [obtener un acceso de autenticación token](powerbi-developer-walkthrough-push-data-get-token.md) a un encabezado de solicitud:

Cuando se llama a la [Crear conjunto de datos](https://msdn.microsoft.com/library/mt203562.aspx) operación, se crea un nuevo conjunto de datos en el panel.

![](media/powerbi-developer-walkthrough-push-data/powerbi-developer-create-dataset.png)

A continuación le mostramos cómo crear un conjunto de datos en un panel de Power BI.

## Crear un conjunto de datos en un panel de Power BI

>
            **NOTA**: antes de comenzar, asegúrese de que ha seguido los pasos anteriores en el [Insertar datos en un panel](powerbi-developer-walkthrough-push-data.md) tutorial.

1. En la aplicación de consola de proyecto que creó en [paso 2: obtener un token de acceso de autenticación](powerbi-developer-walkthrough-push-data-get-token.md), agregue **using System.Net;**, y **using System.IO;** en Program.cs.
2. En Program.cs, agregue el código siguiente.
3. Ejecutar la aplicación de consola e inicie sesión en su cuenta de Power BI. Debería ver **creó el conjunto de datos** en la ventana de consola. Además, puede iniciar sesión en el panel para ver el nuevo conjunto de datos.

**Insertar datos en un panel de ejemplo**

Agregue este código en Program.cs.

- En static void Main (string [] args):

    ```
    static void Main(string[] args)
    {
        //Get an authentication access token
        token = GetToken();

        //Create a dataset in a Power BI dashboard
        CreateDataset();
    }
    ```

- Agregue un método CreateDataset():

    ```
    #region Create a dataset in a Power BI dashboard
    private static void CreateDataset()
    {
        //TODO: Add using System.Net and using System.IO

        //Push data into a Power BI dashboard

        string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
        //POST web request to create a dataset.
        //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
        HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
        request.KeepAlive = true;
        request.Method = "POST";
        request.ContentLength = 0;
        request.ContentType = "application/json";

        //Add token to the request header
        request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

        //Create dataset JSON for POST request
        string datasetJson = "{\"name\": \"SalesMarketing\", \"tables\": " +
            "[{\"name\": \"Product\", \"columns\": " +
            "[{ \"name\": \"ProductID\", \"dataType\": \"Int64\"}, " +
            "{ \"name\": \"Name\", \"dataType\": \"string\"}, " +
            "{ \"name\": \"Category\", \"dataType\": \"string\"}," +
            "{ \"name\": \"IsCompete\", \"dataType\": \"bool\"}," +
            "{ \"name\": \"ManufacturedOn\", \"dataType\": \"DateTime\"}" +
            "]}]}";

        //POST web request
        byte[] byteArray = System.Text.Encoding.UTF8.GetBytes(datasetJson);
        request.ContentLength = byteArray.Length;

        //Write JSON byte[] into a Stream
        using (Stream writer = request.GetRequestStream())
        {
            writer.Write(byteArray, 0, byteArray.Length);

            var response = (HttpWebResponse)request.GetResponse();

            Console.WriteLine(string.Format("Dataset {0}", response.StatusCode.ToString()));

            Console.ReadLine();
        }
    }
    #endregion
    ```

El paso siguiente muestra cómo al [obtener un conjunto de datos para agregar filas a una tabla de Power BI](powerbi-developer-walkthrough-push-data-get-datasets.md).

A continuación se muestra la [código completo](#code).

[Siguiente paso >](powerbi-developer-walkthrough-push-data-get-datasets.md)

## Consulte también
- [Obtiene un conjunto de datos para agregar filas a una tabla de Power BI](powerbi-developer-walkthrough-push-data-get-datasets.md)
- [Obtener un acceso de autenticación token](powerbi-developer-walkthrough-push-data-get-token.md)
- [Crear conjunto de datos](https://msdn.microsoft.com/library/mt203562.aspx)
- [Insertar datos en un panel de Power BI](powerbi-developer-walkthrough-push-data.md)
- [Información general sobre la API de REST de Power BI](powerbi-developer-overview-of-power-bi-rest-api.md)
- [Referencia de API de REST de BI de energía](https://msdn.microsoft.com/library/mt147898.aspx)

<a name="code"/>
## Lista de código completa

    using System;
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    using System.Net;
    using System.IO;

    namespace walkthrough_push_data
    {
        class Program
        {
            private static string token = string.Empty;

            static void Main(string[] args)
            {

                //Get an authentication access token
                token = GetToken();

                //Create a dataset in a Power BI dashboard
                CreateDataset();

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


            #region Create a dataset in a Power BI dashboard
            private static void CreateDataset()
            {
                //TODO: Add using System.Net and using System.IO

                //Push data into a Power BI dashboard

                string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
                //POST web request to create a dataset.
                //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
                HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
                request.KeepAlive = true;
                request.Method = "POST";
                request.ContentLength = 0;
                request.ContentType = "application/json";

                //Add token to the request header
                request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

                //Create dataset JSON for POST request
                string datasetJson = "{\"name\": \"SalesMarketing\", \"tables\": " +
                    "[{\"name\": \"Product\", \"columns\": " +
                    "[{ \"name\": \"ProductID\", \"dataType\": \"Int64\"}, " +
                    "{ \"name\": \"Name\", \"dataType\": \"string\"}, " +
                    "{ \"name\": \"Category\", \"dataType\": \"string\"}," +
                    "{ \"name\": \"IsCompete\", \"dataType\": \"bool\"}," +
                    "{ \"name\": \"ManufacturedOn\", \"dataType\": \"DateTime\"}" +
                    "]}]}";

                //POST web request
                byte[] byteArray = System.Text.Encoding.UTF8.GetBytes(datasetJson);
                request.ContentLength = byteArray.Length;

                //Write JSON byte[] into a Stream
                using (Stream writer = request.GetRequestStream())
                {
                    writer.Write(byteArray, 0, byteArray.Length);

                    var response = (HttpWebResponse)request.GetResponse();

                    Console.WriteLine(string.Format("Dataset {0}", response.StatusCode.ToString()));

                    Console.ReadLine();
                }
            }
            #endregion
        }
    }

¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
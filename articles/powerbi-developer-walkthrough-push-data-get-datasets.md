<properties
   pageTitle="Obtiene un conjunto de datos para agregar filas"
   description="Tutorial para insertar datos - obtener un conjunto de datos para agregar filas a una tabla de Power BI"
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

# Paso 4: Obtener un conjunto de datos para agregar filas a una tabla de Power BI

Este artículo forma parte de un tutorial paso a paso para [Insertar datos en un panel](powerbi-developer-walkthrough-push-data.md).

En **paso 3** de insertar datos en un panel [crear un conjunto de datos en un panel de Power BI](powerbi-developer-walkthrough-push-data-create-dataset.md), se llamó la [Crear conjunto de datos](https://msdn.microsoft.com/library/mt203562.aspx) operación para crear un conjunto de datos en un panel. En este paso, usará el [obtener conjuntos de datos](https://msdn.microsoft.com/library/mt203567.aspx) operación y Newtonsoft.Json para obtener un identificador de conjunto de datos. Utilice el identificador de conjunto de datos en el paso 4 para agregar filas a un conjunto de datos.

Para insertar datos en un panel de Power BI, debe hacer referencia a la tabla del conjunto de datos. Para hacer referencia a una tabla en un conjunto de datos, primero debe obtener un **identificador de conjunto de datos**. Obtendrá un **identificador de conjunto de datos** mediante la [obtener el conjunto de datos](https://msdn.microsoft.com/library/mt203567.aspx) operación. El **obtener el conjunto de datos** operación devuelve una cadena JSON que contiene una lista de todos los conjuntos de datos en un panel de Power BI. Es la manera recomendada para deserializar una cadena JSON con [Newtonsoft.Json](http://www.newtonsoft.com/json).

Aquí es cómo obtener un conjunto de datos.

## Obtiene un conjunto de datos de Power BI

>
            **NOTA**: antes de comenzar, asegúrese de que ha seguido los pasos anteriores en el [Insertar datos en un panel](powerbi-developer-walkthrough-push-data.md) tutorial.

1. En el proyecto de aplicación de consola creó en el paso 2: tutorial para insertar datos, [obtener un acceso de autenticación token](powerbi-developer-walkthrough-push-data-get-token.md), instale el paquete Newtonsoft.Json NuGet. Aquí se muestra cómo instalar el paquete:

     a. En Visual Studio 2015, elija **herramientas** > **Administrador de paquetes de NuGet** > **Package Manager Console**.

     b. En **Package Manager Console**, escriba Install-Package Newtonsoft.Json.

2. Después de instala el paquete, agregar **utilizando Newtonsoft.Json;** en Program.cs.

3. En Program.cs, agregue el código siguiente para obtener un **identificador de conjunto de datos**.

4. Ejecutar la aplicación de consola e inicie sesión en su cuenta de Power BI. Debería ver **identificador de conjunto de datos:** seguido de un identificador en la ventana de consola.

**Get de ejemplo de un conjunto de datos**

Agregue este código en Program.cs.

- En static void Main (string [] args):

  ```
  static void Main(string[] args)
  {

    //Get an authentication access token
    token = GetToken();

    //Create a dataset in a Power BI dashboard
    CreateDataset();

    //Get a dataset to add rows into a Power BI table
    string datasetId = GetDataset();
  }
  ```

- Agregue un método GetDatset():

  ```
    #region Get a dataset to add rows into a Power BI table
    private static string GetDataset()
    {
        string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
        //POST web request to create a dataset.
        //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
        HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
        request.KeepAlive = true;
        request.Method = "GET";
        request.ContentLength = 0;
        request.ContentType = "application/json";

        //Add token to the request header
        request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

        string datasetId = string.Empty;
        //Get HttpWebResponse from GET request
        using (HttpWebResponse httpResponse = request.GetResponse() as System.Net.HttpWebResponse)
        {
            //Get StreamReader that holds the response stream
            using (StreamReader reader = new System.IO.StreamReader(httpResponse.GetResponseStream()))
            {
                string responseContent = reader.ReadToEnd();

                //TODO: Install NuGet Newtonsoft.Json package: Install-Package Newtonsoft.Json
                //and add using Newtonsoft.Json
                var results = JsonConvert.DeserializeObject<dynamic>(responseContent);

                //Get the first id
                datasetId = results["value"][0]["id"];

                Console.WriteLine(String.Format("Dataset ID: {0}", datasetId));
                Console.ReadLine();

                return datasetId;
            }
        }
    }
    #endregion
```

El paso siguiente muestra cómo a [Agregar filas a una tabla de Power BI](powerbi-developer-walkthrough-push-data-add-rows.md).

A continuación se muestra la [código completo](#code).

[Siguiente paso >](powerbi-developer-walkthrough-push-data-add-rows.md)

## Consulte también
- [Agregar filas a una tabla de Power BI](powerbi-developer-walkthrough-push-data-add-rows.md)
- [Newtonsoft.Json](http://www.newtonsoft.com/json)
- [Obtener conjuntos de datos](https://msdn.microsoft.com/library/mt203567.aspx)
- [Insertar datos en un panel de Power BI](powerbi-developer-walkthrough-push-data.md)
- [Información general sobre la API de REST de Power BI](powerbi-developer-overview-of-power-bi-rest-api.md)
- [Referencia de API de REST de BI de energía](https://msdn.microsoft.com/library/mt147898.aspx)

<a name="code"/>
## Lista de código completa

    using System;
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    using System.Net;
    using System.IO;
    using Newtonsoft.Json;

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

                //Get a dataset to add rows into a Power BI table
                string datasetId = GetDataset();

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

            #region Get a dataset to add rows into a Power BI table
            private static string GetDataset()
            {
                string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
                //POST web request to create a dataset.
                //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
                HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
                request.KeepAlive = true;
                request.Method = "GET";
                request.ContentLength = 0;
                request.ContentType = "application/json";

                //Add token to the request header
                request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

                string datasetId = string.Empty;
                //Get HttpWebResponse from GET request
                using (HttpWebResponse httpResponse = request.GetResponse() as System.Net.HttpWebResponse)
                {
                    //Get StreamReader that holds the response stream
                    using (StreamReader reader = new System.IO.StreamReader(httpResponse.GetResponseStream()))
                    {
                        string responseContent = reader.ReadToEnd();

                        //TODO: Install NuGet Newtonsoft.Json package: Install-Package Newtonsoft.Json
                        //and add using Newtonsoft.Json
                        var results = JsonConvert.DeserializeObject<dynamic>(responseContent);

                        //Get the first id
                        datasetId = results["value"][0]["id"];

                        Console.WriteLine(String.Format("Dataset ID: {0}", datasetId));
                        Console.ReadLine();

                        return datasetId;
                    }
                }
            }
            #endregion
        }
    }

¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
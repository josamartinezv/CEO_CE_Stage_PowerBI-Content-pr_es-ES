<properties
   pageTitle="Create a dataset"
   description="Walkthrough - Push data into a dashboard - Create a dataset in a Power BI dashboard"
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

# Step 3: Create a dataset in a Power BI dashboard

This article is part of a step-by-step walkthrough to <bpt id="p1">[</bpt>push data into a dashboard<ept id="p1">](powerbi-developer-walkthrough-push-data.md)</ept>.

In <bpt id="p1">**</bpt>step 2<ept id="p1">**</ept> of Push data into a dashboard, <bpt id="p2">[</bpt>Get an authentication access token<ept id="p2">](powerbi-developer-walkthrough-push-data-get-token.md)</ept>, you got a token to authenticate to <bpt id="p3">**</bpt>Azure AD<ept id="p3">**</ept>. In this step, you use the token to call the <bpt id="p1">[</bpt>Create Dataset<ept id="p1">](https://msdn.microsoft.com/library/mt203562.aspx)</ept> operation.

To make a call to a REST resource, you use a url that locates the resource, and you send a JavaScript Object Notation (JSON) string, which describes the dataset, to the Power BI service resource. A REST resource identifies the part of the Power BI service you want to work with. To push data into the dashboard, the target resource is a <bpt id="p1">**</bpt>Dashboard Dataset<ept id="p1">**</ept>. The URL that identifies a dataset is https://api.PowerBI.com/v1.0/myorg/datasets. If you are pushing data within a group, the url is https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets.

To authenticate a Power BI REST operation, you add the token you got in <bpt id="p1">[</bpt>Get an authentication access token<ept id="p1">](powerbi-developer-walkthrough-push-data-get-token.md)</ept> to a request header:

When you call the <bpt id="p1">[</bpt>Create Dataset<ept id="p1">](https://msdn.microsoft.com/library/mt203562.aspx)</ept> operation, a new dataset is created in your dashboard.

![](media/powerbi-developer-walkthrough-push-data/powerbi-developer-create-dataset.png)

Here's how to create a dataset in a Power BI dashboard.

## Create a dataset in a Power BI dashboard

><bpt id="p1">**</bpt>NOTE<ept id="p1">**</ept>: Before you get started, make sure you have followed the previous steps in the <bpt id="p2">[</bpt>push data into a dashboard<ept id="p2">](powerbi-developer-walkthrough-push-data.md)</ept> walkthrough.

1. In the Console Application project you created in <bpt id="p1">[</bpt>Step 2 - Get an authentication access token<ept id="p1">](powerbi-developer-walkthrough-push-data-get-token.md)</ept>, add <bpt id="p2">**</bpt>using System.Net;<ept id="p2">**</ept>, and <bpt id="p3">**</bpt>using System.IO;<ept id="p3">**</ept> to Program.cs.
2. In Program.cs, add the code below.
3. Run the Console App, and login to your Power BI account. You should see <bpt id="p1">**</bpt>Dataset Created<ept id="p1">**</ept> in the Console Window. Also, you can login to your dashboard to see the new dataset.

**Sample push data into a dashboard**

Add this code into Program.cs.

- In static void Main(string[] args):

    ```
    static void Main(string[] args)
    {
        //Get an authentication access token
        token = GetToken();

        //Create a dataset in a Power BI dashboard
        CreateDataset();
    }
    ```

- Add a CreateDataset() method:

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

The next step shows you how to <bpt id="p1">[</bpt>get a dataset to add rows into a Power BI table<ept id="p1">](powerbi-developer-walkthrough-push-data-get-datasets.md)</ept>.

Below is the <bpt id="p1">[</bpt>complete code listing<ept id="p1">](#code)</ept>.

[Next Step &gt;](powerbi-developer-walkthrough-push-data-get-datasets.md)

## Consulte también
- [Get a dataset to add rows into a Power BI table](powerbi-developer-walkthrough-push-data-get-datasets.md)
- [Get an authentication access token](powerbi-developer-walkthrough-push-data-get-token.md)
- [Create Dataset](https://msdn.microsoft.com/library/mt203562.aspx)
- [Push data into a Power BI Dashboard](powerbi-developer-walkthrough-push-data.md)
- [Overview of Power BI REST API](powerbi-developer-overview-of-power-bi-rest-api.md)
- [Power BI REST API reference](https://msdn.microsoft.com/library/mt147898.aspx)

<a name="code"/>
## Complete code listing

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

More questions? [Try the Power BI Community](http://community.powerbi.com/)
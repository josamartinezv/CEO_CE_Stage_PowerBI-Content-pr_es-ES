<properties
   pageTitle="Authenticate a web app"
   description="Authenticate a web app"
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

# Authenticate a web app

<bpt id="p1">[</bpt>Download the web app sample<ept id="p1">](http://go.microsoft.com/fwlink/?LinkId=619279)</ept> | View the code on GitHub: <bpt id="p2">[</bpt>Default.aspx.cs<ept id="p2">](https://github.com/Microsoft/PowerBI-CSharp/blob/master/samples/webforms/get-started-web-app-asp.net/PBIWebApp/Default.aspx.cs)</ept><ph id="ph1"> | </ph><bpt id="p3">[</bpt>Redirect.aspx.cs<ept id="p3">](https://github.com/Microsoft/PowerBI-CSharp/blob/master/samples/webforms/get-started-web-app-asp.net/PBIWebApp/redirect.aspx.cs)</ept>

This article shows you how to authenticate a Power BI web app. It includes examples in C#; however, the authentication process is the same for other web programming languages. There is a <bpt id="p1">[</bpt>web app sample on GitHub<ept id="p1">](http://go.microsoft.com/fwlink/?LinkId=619279)</ept>. To learn how to run the sample, see <bpt id="p1">[</bpt>Web app sample<ept id="p1">](https://msdn.microsoft.com/library/mt186158.aspx)</ept>.

Power BI web apps use Active Directory (AAD) to authenticate users and protect applications. Authentication is the process of identifying an app or user. To identify your web app in AAD, you register your app with AAD. When you register a web app in AAD, you give your app access to the Power BI REST API resources. To learn how to register your Power BI web app, see <bpt id="p1">[</bpt>Register a web app<ept id="p1">](powerbi-developer-register-a-web-app.md)</ept>.

To learn more about Azure Active Directory (Azure AD) authorization flow, see <bpt id="p1">[</bpt>Authorization Code Grant Flow<ept id="p1">](https://msdn.microsoft.com/library/azure/dn645542.aspx)</ept>.

<bpt id="p1">**</bpt>NOTE<ept id="p1">**</ept> For Power BI, apps are created as multi-tenant apps using the Azure Management Portal.

## What you need to authenticate a Power BI web app
Here are the steps to authenticate a Power BI web app and perform a REST web request. These steps apply to an ASP.NET web app; however, the steps apply to other platforms. To learn more about OAuth 2.0 in Azure AD, see <bpt id="p1">[</bpt>OAuth 2.0 in Azure AD<ept id="p1">](https://msdn.microsoft.com/library/azure/dn645545.aspx)</ept>.
<a name="register"/>
### Step 1 - Register your web app
When you register a web app in Azure Active Directory, you give your app access to the Power BI REST API resources. To register a Power BI web app, see <bpt id="p1">[</bpt>Register a web app<ept id="p1">](powerbi-developer-register-a-web-app.md)</ept>.
<a name="configure"/>
### Step 2 - Configure Power BI settings to authenticate with Azure AD
Here are the settings you need to authenticate a Power BI web app with Azure AD.

|Setting|Descripción|Valor|
|:--|:--|:--|
|Identificador de cliente|Client ID is used by the application to identify themselves to the users that they are requesting permissions from.|To get a Power BI app client id, see <bpt id="p1">[</bpt>How to get a client app id<ept id="p1">](powerbi-developer-register-a-web-app.md#clientID)</ept>.|
|Secreto del cliente|The client secret key is sent along with a Client ID when authenticating to Azure AD to call a web API.|To get a Power BI app client secret key, see <bpt id="p1">[</bpt>How to get a client secret key<ept id="p1">](powerbi-developer-register-a-web-app.md#clientSecret)</ept>.|
|Resource Uri|The resource Uri to the Power BI resource to be authorized. You must use this exact Uri.|https://analysis.windows.net/powerbi/api|
|Authority Uri|The authority Uri is an Azure resource that takes a client id to get an access token.|https://login.windows.net/common/oauth2/authorize|
|Redirect Url|A Redirect Url for the web app url. The Azure AD service redirects back to the web app url with an authentication code.|Example: http://localhost:13526/Redirect|

<a name="create"/>
### Step 3 - Create a query string to get authorization code from Azure AD
To authenticate a Power BI web app, you first create a url query string to redirect to the Azure AD authentication service. After providing valid credentials, Azure AD returns an authorization code. The following is an example of a fully qualified Azure AD url with query string. You use a url similar to this to get an authorization code from Azure AD. Use <bpt id="p1">**</bpt>Response.Redirect<ept id="p1">**</ept>() to redirect to the Azure AD service that will return an authorization code from Azure AD. You use the authorization code in step 4 to acquire an access token by authorization code.

    https://login.windows.net/common/oauth2/authorize
      ?response_type=code
      &client_id=1861585d...9a79c296
      &resource= https://analysis.windows.net/powerbi/api
      &redirect_uri= http://localhost:13526/Redirect

**Power BI authentication query string settings**

|Setting|Descripción|
|:--|:--|
|response_type=code|Azure AD returns an authorization code.|
|client_id=1861585d...9a79c296|Client ID is used by the application to identify themselves to the users that they are requesting permissions from. You get the client id when you register your Azure app.|
|resource= https://analysis.windows.net/powerbi/api|Resource uri to the Power BI resource to be authorized. You must use this exact Uri.|
|redirect_uri= http://localhost:13526/Redirect|After user authenticates, Azure AD will redirect back to the web app.|

Here’s a C# code sample to create an Azure AD authorization url with a query string, and redirect to the Azure AD authority service.

**Example – C# sign in**

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
### Step 4 – Acquire an Azure AD access token using authorization code

To make a data request to the Power BI REST service, you need to supply an access token. In a .NET web app, you use the <bpt id="p1">[</bpt>Azure AD Authentication Library for .NET nuget package<ept id="p1">](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)</ept> to get an access token. If you do not have Windows Azure Authentication Library (ADAL), see <bpt id="p1">[</bpt>How to add Azure Active Directory Authentication Library<ept id="p1">](#add)</ept>.

After your app redirects to the Azure AD authority Uri and acquires an authorization code, your app gets a token by authorization code. Here’s how your app can get the authorization code and get an access token: <bpt id="p1">**</bpt>In a Redirect class<ept id="p1">**</ept>:

1.  Get the Azure AD auth code that is returned from Azure AD.

    ```
    string code = Request.Params.GetValues(0)[0];
    ```
2.  Create an <bpt id="p1">**</bpt>AuthenticationContext<ept id="p1">**</ept> passing the authority uri and a TokenCache.

    ```
    TokenCache TC = new TokenCache();

    AuthenticationContext AC = new AuthenticationContext(authorityUri, TC);
    ```

3.  Create a <bpt id="p1">**</bpt>ClientCredential<ept id="p1">**</ept> passing the Azure App <bpt id="p2">**</bpt>Client ID<ept id="p2">**</ept> and Azure App <bpt id="p3">**</bpt>Client Secret<ept id="p3">**</ept>.

    ```
    ClientCredential cc = new ClientCredential(Properties.Settings.Default.ClientID, Properties.Settings.Default.ClientSecretKey);
    ```

4.  Get a token by authorization code passing the <bpt id="p1">**</bpt>authentication code<ept id="p1">**</ept> returned by Azure AD and a <bpt id="p2">**</bpt>redirect url<ept id="p2">**</ept>.

    ```
    AuthenticationResult AR = AC.AcquireTokenByAuthorizationCode(code, new Uri(redirectUri), cc);
    ```

5.  Redirect back to default.aspx.

    ```
    Response.Redirect("/Default.aspx");
    ```

6.  Set a session "authResult" index string to the AuthenticationResult so that you can use the result in the default.aspx page.

    ```
    Session["authResult"] = AR;
    ```

<bpt id="p1">**</bpt>In a Default.aspx page<ept id="p1">**</ept>:

1.  Get an <bpt id="p1">**</bpt>AuthenticationResult<ept id="p1">**</ept> from the Session. In Step 4, you use the <bpt id="p1">**</bpt>AuthenticationResult<ept id="p1">**</ept> to get an authorization <bpt id="p2">**</bpt>AccessToken<ept id="p2">**</ept>.

    ```
    AuthenticationResult authResult = (AuthenticationResult)Session["authResult"];
    ```

Here’s the complete code to acquire an Azure access token by authorization code and redirect back to default.aspx.

<bpt id="p1">**</bpt>Note<ept id="p1">**</ept> The Redirect Uri must match the redirect_uri used when requesting Authorization code.

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
### Step 5 – Use Azure AD access token to call a Power BI operation

Power BI REST API calls are made on behalf of an authenticated user by passing an access token acquired through Azure Active Directory, in the “Authorization” header. After you get an access token from Active Directory (AAD), you use the token to make a web request to the Power BI REST API.

Once you set an <bpt id="p1">**</bpt>AuthenticationResult<ept id="p1">**</ept> by acquiring a token by authorization code (<bpt id="p2">**</bpt>AcquireTokenByAuthorizationCode<ept id="p2">**</ept>), you get an Azure access token by getting the <bpt id="p3">**</bpt>AccessToken<ept id="p3">**</ept> property of <bpt id="p4">**</bpt>AuthenticationResult<ept id="p4">**</ept>.
Here’s the code to get Power BI <bpt id="p1">**</bpt>Datasets<ept id="p1">**</ept>.  The code sample creates a <bpt id="p1">**</bpt>WebRequest<ept id="p1">**</ept> and deserializes the response string to a Dataset.
To access the Power BI REST API, you create a request header setting “Authorization” to "Bearer {AccessToken}":

    request.Headers.Add("Authorization", String.Format("Bearer {0}", authResult.AccessToken));

**C# sample – Get Power BI Datasets**

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
## How to add Azure Active Directory Authentication Library
In a .NET client app, you use <bpt id="p1">**</bpt>AuthenticationContext<ept id="p1">**</ept> in the Active Directory Authentication Library to acquire an Azure access token. You can install the Active Directory Authentication Library NuGet package from Visual Studio. When you install a NuGet package, Visual Studio creates a reference to the required assemblies.

1. Right click a solution.
2. Choose Manage NuGet Packages.
3. Search for Active Directory Authentication Library.
4. Choose Active Directory Authentication Library in the list of packages, and click Install.

## Consulte también

[Azure AD Authentication Library for .NET nuget package](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)  
[Active Directory Authentication Library (ADAL) v1 for .NET](http://www.cloudidentity.com/blog/2013/09/12/active-directory-authentication-library-adal-v1-for-net-general-availability/)  
[OAuth 2.0 en Azure AD](https://msdn.microsoft.com/library/azure/dn645545.aspx)  
[Flujo de concesión de códigos de autorización](https://msdn.microsoft.com/library/azure/dn645542.aspx)  
[Escenarios de autenticación en Azure AD](https://msdn.microsoft.com/library/azure/dn499820.aspx)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)

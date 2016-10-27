<properties
   pageTitle="Register a web app with Azure AD"
   description="Register a web app with Azure AD"
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

# Step 1: Register a web app with Azure AD

## Introducción

In this step of the <bpt id="p1">[</bpt>Integrate a tile into an app walkthrough<ept id="p1">](powerbi-developer-integrate-tile.md)</ept>, you register your app in <bpt id="p2">**</bpt>Azure Active Directory (AD)<ept id="p2">**</ept>. You need to do this first so that you have a <bpt id="p1">**</bpt>Client ID<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Client Secret<ept id="p2">**</ept> that identifies your web app in Azure AD. Without a <bpt id="p1">**</bpt>Client ID<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Client Secret<ept id="p2">**</ept>, Azure AD cannot authenticate your web app. If you downloaded the <bpt id="p1">[</bpt>Integrate a tile sample<ept id="p1">](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app)</ept>, you use the <bpt id="p2">**</bpt>Client ID<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Client Secret<ept id="p3">**</ept> you get after registration to configure the sample so that the sample can authenticate to Azure AD.

![](media\powerbi-developer-integrate-tile\integrate-tile-step1a.png)

><bpt id="p1">**</bpt>NOTE<ept id="p1">**</ept>: Before you register a web app for <bpt id="p2">**</bpt>Power BI<ept id="p2">**</ept>, you need to <bpt id="p3">[</bpt>Sign up for Power BI<ept id="p3">](powerbi-admin-free-with-custom-azure-directory.md)</ept>.

Here are the steps to register a web app in Azure AD.

## Register a web app in Azure AD

1. Go to dev.powerbi.com/apps.
2. Click <bpt id="p1">**</bpt>Sign in with your existing account<ept id="p1">**</ept>, and sign into your Power BI account.
3. Enter an <bpt id="p1">**</bpt>App Name<ept id="p1">**</ept>. For this walkthrough, enter <bpt id="p1">**</bpt>Integrate a tile sample<ept id="p1">**</ept>.
4. For <bpt id="p1">**</bpt>App Type<ept id="p1">**</ept>, choose <bpt id="p2">**</bpt>Server-side Web app<ept id="p2">**</ept>.
5. Enter a <bpt id="p1">**</bpt>Redirect URL<ept id="p1">**</ept>. For this walkthrough, Azure AD redirects back to the default page, so enter http://localhost:13526. Azure Active Directory (AD) will redirect to this page with an <bpt id="p1">**</bpt>Authorization Code<ept id="p1">**</ept>. To learn how to acquire an <bpt id="p1">**</bpt>Access Token<ept id="p1">**</ept> to access <bpt id="p2">**</bpt>Power BI<ept id="p2">**</ept> tiles using an <bpt id="p3">**</bpt>Authorization Code<ept id="p3">**</ept>, see <bpt id="p4">[</bpt>Get an authentication access token<ept id="p4">](powerbi-developer-integrate-tile-get-dashboard.md#get-token)</ept>.
6. Enter a <bpt id="p1">**</bpt>Home Page<ept id="p1">**</ept>. For this walkthrough, enter http://localhost:13526 which is the home page for the sample.
7. For <bpt id="p1">**</bpt>Choose APIs to access<ept id="p1">**</ept>, choose <bpt id="p2">**</bpt>Read All Dashboards (preview)<ept id="p2">**</ept>. For all Power BI app permissions, see <bpt id="p1">[</bpt>App permissions<ept id="p1">](powerbi-developer-power-bi-permissions.md)</ept>.
7. Click <bpt id="p1">**</bpt>Register app<ept id="p1">**</ept>, and save the <bpt id="p2">**</bpt>Client ID<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Client Secret<ept id="p3">**</ept> that was generated. A <bpt id="p1">**</bpt>Client ID<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Client Secret<ept id="p2">**</ept> identifies the app in Azure AD. To configure the <bpt id="p1">[</bpt>Integrate a tile sample<ept id="p1">](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app)</ept> to use the <bpt id="p2">**</bpt>Client ID<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Client Secret<ept id="p3">**</ept> to authenticate, see <bpt id="p4">[</bpt>Configure the integrate a tile sample<ept id="p4">](powerbi-developer-integrate-tile-register.md#configure-sample)</ept>.

Here's how your <bpt id="p1">**</bpt>Register an Application for Power BI<ept id="p1">**</ept> page should look:

![](media\powerbi-developer-integrate-tile\register-app.png)

Now that you have registered your web app with <bpt id="p1">**</bpt>Azure AD<ept id="p1">**</ept>, you can get an authorization access token from <bpt id="p2">**</bpt>Azure AD<ept id="p2">**</ept> to access <bpt id="p3">**</bpt>Power BI<ept id="p3">**</ept> dashboards and tiles.

![](media\powerbi-developer-integrate-tile\integrate-tile-step1b.png)

After you have a <bpt id="p1">**</bpt>Client ID<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Client Secret<ept id="p2">**</ept>, you can configure your web app, such as the <bpt id="p3">[</bpt>Integrate a tile sample<ept id="p3">](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app)</ept>, to be able to access <bpt id="p4">**</bpt>Power BI<ept id="p4">**</ept> tiles. The next section shows you how to configure the sample.

<a name="configure-sample"/>
## Configure the Integrate a tile sample
If you downloaded the <bpt id="p1">[</bpt>Integrate a tile sample<ept id="p1">](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app)</ept>, you use the <bpt id="p2">**</bpt>Client ID<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Client Secret<ept id="p3">**</ept> you get after registration so that the sample can authenticate to Azure AD. To configure the sample, change the <bpt id="p1">**</bpt>Client ID<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Client Secret<ept id="p2">**</ept> in web.config. To learn more about how to authenticate to Azure AD, see <bpt id="p1">[</bpt>Step 2: Get a Power BI dashboard<ept id="p1">](powerbi-developer-integrate-tile-get-dashboard.md)</ept>.

## Paso siguiente

To integrate a tile into an app, you need to get a tile which is in a dashboard. In the next step, you learn how to <bpt id="p1">[</bpt>Get a Power BI dashboard<ept id="p1">](powerbi-developer-integrate-tile-get-dashboard.md)</ept>. In step 3, you learn how to get a tile from a dashboard.

[Next Step &gt;](powerbi-developer-integrate-tile-get-dashboard.md)

## Consulte también

[Sign up for Power BI](powerbi-admin-free-with-custom-azure-directory.md)  
[Integrate a tile into an app walkthrough](powerbi-developer-integrate-tile.md)  
[Integrate a tile sample](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app)  
[Configure the integrate a tile sample](powerbi-developer-integrate-tile-register.md#configure-sample)  
[Get an authentication access token](powerbi-developer-integrate-tile-get-dashboard.md#get-token)  
[Permisos de aplicación](powerbi-developer-power-bi-permissions.md)  
[Step 2: Get a Power BI dashboard](powerbi-developer-integrate-tile-get-dashboard.md)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)
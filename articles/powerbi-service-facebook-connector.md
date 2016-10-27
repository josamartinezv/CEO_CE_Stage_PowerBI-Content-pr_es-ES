<properties
   pageTitle="Third-party service: Facebook connector for Power BI Desktop"
   description="Third-party service: Facebook connector for Power BI Desktop"
   services="powerbi"
   documentationCenter=""
   authors="davidiseminger"
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
   ms.date="09/29/2016"
   ms.author="davidi"/>
# Third-party service: Facebook connector for Power BI Desktop

The Facebook connector in Power BI Desktop relies on the Facebook Graph API. As such, features and availability may vary over time.

You can see a <bpt id="p1">[</bpt>tutorial about the Facebook Connector for Power BI Desktop<ept id="p1">](powerbi-desktop-tutorial-facebook-analytics.md)</ept>.

Facebook expired v1.0 of its Graph API on April 30<ph id="ph1">&lt;sup&gt;</ph>th<ph id="ph2">&lt;/sup&gt;</ph> 2015. Power BI uses the Graph API behind the scenes for the Facebook connector, allowing you to connect to your data and analyze it.

Queries that were built before April 30<ph id="ph1">&lt;sup&gt;</ph>th<ph id="ph2">&lt;/sup&gt;</ph> 2015 may no longer work or return less data. Subsequent to April 30<ph id="ph1">&lt;sup&gt;</ph>th<ph id="ph2">&lt;/sup&gt;</ph> 2015, Power BI leverages v2.2 in all calls to the Facebook API. If your query was built prior to April 30, 2015 and you have not used it since, you’ll likely need to authenticate again, to approve the new set of permissions that we’ll ask for.

Although we attempt to release updates in accordance with any changes, the API may change in a way that affects the results of the queries we generate. In some cases, certain queries may no longer be supported. Due to this dependency we cannot guarantee the results of your queries when using this connector.

More details on the change in the Facebook API are available <bpt id="p1">[</bpt>here<ept id="p1">](https://developers.facebook.com/docs/apps/changelog#v2_0)</ept>.

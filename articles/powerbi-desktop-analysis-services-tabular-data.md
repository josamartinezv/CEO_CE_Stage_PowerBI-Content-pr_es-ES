<properties
   pageTitle="Analysis Services Tabular data in Power BI Desktop"
   description="Analysis Services Tabular data in Power BI Desktop"
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
# Analysis Services Tabular data in Power BI Desktop

With Power BI Desktop, there are two ways you can connect to and get data from your SQL Server Analysis Services Tabular models: Explore by using a live connection or Select items and import into Power BI Desktop.

Let’s take a closer look.

<bpt id="p1">**</bpt>Explore by using a live connection<ept id="p1">**</ept> – When using a live connection, items in your Tabular model or perspective, like tables, columns, and measures appear in your Power BI Desktop Fields list. You can use Power BI Desktop’s advanced visualization and report tools to explore your Tabular model in new, highly interactive ways.

When connecting live, no data from the Tabular model is imported into Power BI Desktop. Each time you interact with a visualization, Power BI Desktop queries the Tabular model and calculates the results you see. You’re always looking at the latest data. Keep in-mind, Tabular models are highly secure. Items that appear in Power BI Desktop depend on your permissions for the Tabular model you’re connected to.

When you’ve created dynamic reports in Power BI Desktop, you can share them by publishing to your Power BI site. When you publish a Power BI Desktop file with a live connection to a Tabular model to your Power BI site, an On-premises Data Gateway must be installed and configured by an administrator. To learn more, see <bpt id="p1">[</bpt>On-premises Data Gateway<ept id="p1">](powerbi-gateway-onprem.md)</ept>.

<bpt id="p1">**</bpt>Select items and import into Power BI Desktop<ept id="p1">**</ept> – When you connect with this option, you can select items like tables, columns, and measures in your Tabular model or perspective and load them into a Power BI Desktop model. You can use Power BI Desktop’s advanced Query Editor to further shape what you want. You can use Power BI Desktop’s modeling features to further model the data. No live connection between Power BI Desktop and the Tabular model is maintained. You can then explore your Power BI Desktop model offline or publish to your Power BI site.

## To connect to a Tabular model

1. In Power BI Desktop, on the <bpt id="p1">**</bpt>Home<ept id="p1">**</ept> tab, click <bpt id="p2">﻿**</bpt>Get Data<ept id="p2">**</ept>.

 ![](media/powerbi-desktop-analysis-services-tabular-data/PBID_SQLAS_GetData.png)

2. Click <bpt id="p1">**</bpt>SQL Server Analysis Services Database<ept id="p1">**</ept>, then click <bpt id="p2">**</bpt>Connect<ept id="p2">**</ept>.

 ![](media/powerbi-desktop-analysis-services-tabular-data/PBID_SQLAS_GetData_AS.png)

3. Enter the Server name and select a connection mode. 

 ![](media/powerbi-desktop-analysis-services-tabular-data/PBID_SQLAS_GetData_AS_server.png)

4. This step depends on the connection mode you selected:

-   If you’re connecting live, in Navigator, select a Tabular model or perspective.

    ![](media/powerbi-desktop-analysis-services-tabular-data/PBID_SQLAS_GetData_AS_Live.png)

-   If you chose Select items and get data, in Navigator, select a Tabular model or perspective. You can further select only particular tables or columns to load. To shape your data before loading, click Edit to open Query Editor. When you’re ready, click Load to import the data into Power BI Desktop.
>  ![](media/powerbi-desktop-analysis-services-tabular-data/PBID_SQLAS_GetData_AS_Select.png)

## Preguntas más frecuentes

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> Do I need an On-premises Data Gateway?

<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> It depends. If you use Power BI Desktop to connect live to a Tabular model, but have no intention on publishing to your Power BI site, you do not need a gateway. On the other hand, if you do intend on publishing to your Power BI site, a data gateway is necessary to ensure secure communication between the Power BI service and your on-premises Analysis Services server. Be sure to talk to your Analysis Services server administrator before installing a data gateway.

If you choose select items and get data, you’re importing Tabular model data right into your Power BI Desktop file, so no gateway is necessary.

 

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> What’s the difference between connecting live to a Tabular model from the Power BI service versus connecting live from Power BI Desktop?

<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> When connecting live to a Tabular model from your site in the Power BI service to an Analysis Services database on-premises in your organization, an On-premises Data Gateway is required to secure communications between them. When connecting live to a Tabular model from Power BI Desktop, a gateway is not required because both Power BI Desktop and the Analysis Services server you’re connecting to are both running on-premises in your organization. However, if you publish your Power BI Desktop file to your Power BI site, a gateway is required.

 

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> If I created a live connection, can I connect to another data source in the same Power BI Desktop file?

<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> No. You cannot explore live data and connect to another type of data source in the same file. If you’ve already imported data or connected to a different data source in a Power BI Desktop file, you’ll need to create a new file to explore live.

 

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> If I created a live connection, can I edit the model or query in Power BI Desktop?

<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> No. All of the query and modeling features in Power BI Desktop are disabled when exploring live data.

 

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> If I created a live connection, is it secure?

<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> Yes. Your current Windows credentials are used to connect to the Analysis Services server. You cannot use Basic or stored credentials in either the Power BI service or Power BI Desktop when exploring live.

 

<bpt id="p1">**</bpt>Question:<ept id="p1">**</ept> In Navigator, I see a model and a perspective. What’s the difference?

<bpt id="p1">**</bpt>Answer:<ept id="p1">**</ept> A perspective is a particular view of a Tabular model. It might include only particular tables, columns, or measures depending on a unique data analysis need. A Tabular model always contains at least one perspective, which could include everything in the model. If you’re unsure which you should select, check with your administrator.


## To change the server name after initial connection

Once you create a Power BI Desktop file with an explore live connection, there might be some cases where you want to switch the connection to a different server. For example, if you created your Power BI Desktop file when connecting to a development server, and before publishing to the Power BI service, you want to switch the connection to production server.

1. Select <bpt id="p1">**</bpt>Edit Queries<ept id="p1">**</ept> from the Ribbon.

 ![](media/powerbi-desktop-analysis-services-tabular-data/PBID_SQLAS_ChName_EditQuery.png)

2. Enter the new server name.

 ![](media/powerbi-desktop-analysis-services-tabular-data/PBID_SQLAS_ChName_Dialog.png)

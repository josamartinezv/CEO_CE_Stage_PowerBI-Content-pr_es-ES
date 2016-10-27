<properties
   pageTitle="Data refresh in Power BI"
   description="Data refresh in Power BI"
   services="powerbi"
   documentationCenter=""
   authors="guyinacube"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="complete"
   qualityDate="03/31/2016"/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="09/21/2016"
   ms.author="asaxton"/>

# Data refresh in Power BI  

Making sure you’re always getting the latest data is often critical in making the right decisions. You’ve probably already used Get Data in Power BI to connect to and upload some data, created some reports and a dashboard. Now, you want to make sure your data really is the latest and greatest.

In many cases, you don’t need to do anything at all. Some data, like from a Salesforce or Marketo content pack is automatically refreshed for you. If your connection makes use of a live connection or DirectQuery, the data will be update to date. But, in other cases, like with an Excel workbook or Power BI Desktop file that connects to an external online or on-premises data source, you’ll need to refresh manually or setup a refresh schedule so Power BI can refresh the data in your reports and dashboards for you.

This article, along with a few others, are meant to help you understand how data refresh in Power BI really works, whether or not you need to setup a refresh schedule, and what needs to be in-place to refresh your data successfully.

## Data refresh by subscription type 
 
Before we go any further, it’s important to know how data refresh works depending on your Power BI subscription type. There are two different types of user subscriptions, Power BI (free) and Power BI Pro. Power BI Pro provides additional refresh frequency and capacity.

|**Data Refresh**|**Power BI (free)**|**Power BI Pro**|
|---|---|---|
|Datasets scheduled to refresh|A diario|Hourly*|
|Streaming data in your dashboards and reports using Microsoft Power BI REST API or Microsoft Stream Analytics.|10k rows/hour|1M rows/hour|
|Live/DirectQuery on-premises data sources with full interactivity via the On-premises Data Gateway| | ![](media/powerbi-refresh-data/checkmark.png)|
|Live cloud data sources with full interactivity (Azure SQL Database, Azure SQL Data Warehouse, Spark on HDInsight)| | ![](media/powerbi-refresh-data/checkmark.png)|
|On-premises data sources requiring a Power BI Gateway - Personal and/or the On-premises Data Gateway.| | ![](media/powerbi-refresh-data/checkmark.png)|

\* Up to eight times (hours) per day.

## Understanding data refresh  
Before setting up refresh, it’s important to understand what it is you’re refreshing and where you’re getting your data.

A <bpt id="p1">*</bpt>data source<ept id="p1">*</ept> is where the data you explore in your reports and dashboards really comes from; for example, an online service like Google Analytics or QuickBooks, a database in the cloud like Azure SQL Database, or a database or file on a local computer or server in your own organization. These are all data sources. The type of data source determines how data from it is refreshed. We’ll go into refresh for each type of data source a little later in the <bpt id="p1">[</bpt>What can be refreshed?<ept id="p1">](#what-can-be-refreshed)</ept> section.

A <bpt id="p1">*</bpt>dataset<ept id="p1">*</ept> is automatically created in Power BI when you use Get Data to connect to and upload data from a content pack, file, or you connect to a live data source. In Power BI Desktop and Excel 2016, you can also publish your file right to the Power BI service, which is just like using Get Data.

In each case, a dataset is created and appears in the My Workspace, or Group, containers in the Power BI service. When you select the <bpt id="p1">**</bpt>ellipse (...)<ept id="p1">**</ept> for a dataset, you can explore the data in a report, edit settings, and setup refresh.
  
![](media/powerbi-refresh-data/dataset-menu.png)

A dataset can get data from one or more data sources. For example, you can use Power BI Desktop to get data from a SQL Database in your organization, and get other data from an OData feed online. Then, when you publish the file to Power BI, a single dataset is created, but it will have data sources for both the SQL Database and the OData feed.

A dataset contains information about the data sources, data source credentials, and in most cases, a sub-set of data copied from the data source. When you create visualizations in reports and dashboards, you’re looking at data in the dataset, or in the case of a live connection like Azure SQL Database, the dataset defines the data you see right from the data source. For a live connection to Analysis Services, the dataset definition comes from Analysis Services directly.

> *When you refresh data, you are updating the data in the dataset that is stored in Power BI from your data source. This refresh is a full refresh and not incremental.* 

Whenever you refresh data in a dataset, whether by using Refresh Now or by setting up a refresh schedule, Power BI uses information in the dataset to connect to the data sources defined for it, query for updated data, and then loads the updated data into the dataset. Any visualizations in your reports or dashboards based on the data are updated automatically.

Before we go any further, there’s something else that's very important to understand: 

> *Regardless of how often you refresh the dataset, or how often you look at live data, it is the data at the data source that must be up-to-date first.*

Most organizations process their data once a day, usually in the evening. If you schedule refresh for a dataset created from a Power BI Desktop file that connects to an on-premises database, and your IT department runs processing on that SQL database once in the evening, then you only need to setup scheduled refresh to run once-a-day. For example, after processing on the database happens, but before you come into work. Of course, this isn’t always the case. Power BI provides many ways to connect to data sources that are updated frequently or even real-time.

## Types of refresh

There are four main types of refresh that happen within Power BI. Package refresh, model/data refresh, tile refresh and visual container refresh.

### Package refresh

This synchronizes your Power BI Desktop, or Excel, file between the Power BI service and OneDrive, or SharePoint Online. This does not pull data from the original data source. The dataset in Power BI will only be updated with what is in the file within OneDrive, or SharePoint Online.

![](media/powerbi-refresh-data/package-refresh.png)

### Model/data refresh

This is referring to refreshing the dataset, within the Power BI service, with data from the original data source. This is done by either using scheduled refresh, or refresh now. This requires a gateway for on-premises data sources.

### Tile refresh

Tile refresh updates the cache for tile visuals, on the dashboard, once data changes. This happens about every fifteen minutes. You can also force a tile refresh by selecting the <bpt id="p1">**</bpt>ellipse (...)<ept id="p1">**</ept> in the upper right of a dashboard and selecting <bpt id="p2">**</bpt>Refresh dashboard tiles<ept id="p2">**</ept>.

![](media/powerbi-refresh-data/dashboard-tile-refresh.png)

For details around common tile refresh errors, see <bpt id="p1">[</bpt>Troubleshooting tile errors<ept id="p1">](powerbi-refresh-troubleshooting-tile-errors.md)</ept>.

### Visual container refresh

Refreshing the visual container updates the cached report visuals, within a report, once the data changes.

## What can be refreshed?

In Power BI, you’ll typically use Get Data to import data from a file on a local drive, OneDrive or SharePoint Online, publish a report from Power BI Desktop, or connect directly to a database in the cloud in your own organization. Just about any data in Power BI can be refreshed, but whether or not you need to depends on how your dataset was created from and the data sources it connects to. Let’s look at how each of these refresh data.

Before we go further, here are some important definitions to understand:

<bpt id="p1">**</bpt>Automatic refresh<ept id="p1">**</ept>  - This means no user configuration is necessary in order for the dataset to be refreshed on a regular basis. Data refresh settings are configured for you by Power BI. For online service providers, refresh usually occurs once-a-day. For files loaded from OneDrive, automatic refresh occurs about every hour for data that does not come from an external data source. While you can configure different schedule refresh settings and manually refresh, you probably don’t need to.

<bpt id="p1">**</bpt>User configured manual or scheduled refresh<ept id="p1">**</ept> – This means you can manually refresh a dataset by using Refresh Now or setup a refresh schedule by using Schedule Refresh in a dataset’s settings. This type of refresh is required for Power BI Desktop files and Excel workbooks that connect to external online and on-premises data sources.

> [AZURE.NOTE] When you configure a time for scheduled refresh, there can be a delay of up to one hour before it begins.

<bpt id="p1">**</bpt>Live/DirectQuery<ept id="p1">**</ept> – This means there is a live connection between Power BI and the data source. For on-premises data sources, Admins will need to have a data source configured within an enteprise gateway, but user interaction may not be needed.

## Local files and files on OneDrive or SharePoint Online

Data refresh is supported for Power BI Desktop files and Excel workbooks that connect to external online or on-premises data sources. This will only refresh the data for the dataset within the Power BI service. It will not update your local file.

Keeping your files on OneDrive, or SharePoint Online, and connecting to them from Power BI, provides a great amount of flexibility. But with all that flexibility, it also makes it one of the most challenging to understand. Scheduled refresh for files stored in OneDrive, or SharePoint Online, are different from package refresh. You can learn more in the <bpt id="p1">[</bpt>Types of refresh<ept id="p1">](#types-of-refresh)</ept> section.

### Power BI Desktop file

|**Origen de datos**|**Automatic refresh**|**User configured manual or scheduled refresh**|**Gateway required**|
|---|---|---|---|
|Get Data (on the ribbon) is used to connect to and query data from any listed online data source.|No|Sí|No|
|Get Data is used to connect to and explore a live Analysis Services database.|Sí|No|Sí|
|Get Data is used to connect to and explore a supported on-premises DirectQuery data source.|Sí|No|Sí|
|Get Data is used to connect to and query data from an Azure SQL Database, Azure SQL Data Warehouse, Azure HDInsight Spark.|Yes (hourly)|Sí|No|
|Get Data is used to connect to and query data from any listed  on-premises data source except for Hadoop file (HDFS) and Microsoft Exchange.|No|Sí|Sí|

For details, see <bpt id="p1">[</bpt>Refresh a dataset created from a Power BI Desktop file on OneDrive<ept id="p1">](powerbi-refresh-desktop-file-onedrive.md)</ept>.

### Excel workbook

|**Origen de datos**|**Automatic refresh**|**User configured manual or scheduled refresh**|**Gateway required**|
|---|---|---|---|
|Tables of data in a worksheet not loaded into the Excel data model.|Yes, hourly <bpt id="p1">*</bpt>(OneDrive/SharePoint Online only)<ept id="p1">*</ept>|Manual only <bpt id="p1">*</bpt>(OneDrive/SharePoint Online only)<ept id="p1">*</ept>|No|
|Tables of data in a worksheet linked to a table in the Excel data model (linked tables).|Yes, hourly <bpt id="p1">*</bpt>(OneDrive/SharePoint Online only)<ept id="p1">*</ept>|Manual only <bpt id="p1">*</bpt>(OneDrive/SharePoint Online only)<ept id="p1">*</ept>|No|
|Power Query* is used to connect to and query data from any listed online data source and load data into the Excel data model.|No|Sí|No|
|Power Query* is used to connect to and query data from any listed on-premises data source except for Hadoop file (HDFS) and Microsoft Exchange and load data into the Excel data model.|No|Sí|Sí|
|Power Pivot is used to connect to and query data from any listed online data source and load data into the Excel data model.|No|Sí|No|
|Power Pivot is used to connect to and query data from any listed on-premises data source and load data into the Excel data model.|No|Sí|Sí|

*\* Power Query is known as Get &amp; Transform Data in Excel 2016.*

For more detailed information, see <bpt id="p1">[</bpt>Refresh a dataset created from an Excel workbook on OneDrive<ept id="p1">](powerbi-refresh-excel-file-onedrive.md)</ept>.

### Comma separated value (.csv) file on OneDrive or SharePoint Online

|**Origen de datos**|**Automatic refresh**|**User configured manual or scheduled refresh**|**Gateway required**|
|---|---|---|---|
|Simple comma separated value|Yes, hourly|Manual only|No|

For more detailed information, see <bpt id="p1">[</bpt>Refresh a dataset created from a comma separated value (.csv) file on OneDrive<ept id="p1">](powerbi-refresh-csv-file-onedrive.md)</ept>.

## Content packs  
There are two types of content packs in Power BI:

<bpt id="p1">**</bpt>Content packs from online services<ept id="p1">**</ept>: like Adobe Analytics, SalesForce, and Dynamics CRM Online. Datasets created from online services are refreshed automatically once a day. While it’s probably not necessary, you can manually refresh or setup a refresh schedule. Because online services are in the cloud, a gateway is not required.

<bpt id="p1">**</bpt>Organizational content packs<ept id="p1">**</ept>: created and shared by users in your own organization. Content pack consumers cannot setup a refresh schedule or manually refresh. Only the content pack creator can setup refresh for the datasets in the content pack. Refresh settings are inherited with the dataset.

### Content packs from online services

|**Origen de datos**|**Automatic refresh**|**User configured manual or scheduled refresh**|**Gateway required**|
|---|---|---|---|
|Online services in Get Data <ph id="ph1">&amp;gt;</ph> Services|Sí|Sí|No|

### Organizational content packs

Refresh capabilities for a dataset included within an organization content pack depends on the dataset. See information above in relation to local files, OneDrive or SharePoint Online.

To learn more, see <bpt id="p1">[</bpt>Introduction to organizational content packs<ept id="p1">](powerbi-service-organizational-content-packs-introduction.md)</ept>.

## Live connections and DirectQuery to on-premises data sources 
With the On-premises Data Gateway, you can issue queries from Power BI to your on-premises data sources. When you interact with a visualization, queries are sent from Power BI directly to the database. Updated data is then returned and visualizations are updated. Because there is a direct connection between Power BI and the database, there is no need to schedule refresh. 

When you configure a data source with the On-premises Data Gateway, you can use that data source as the scheduled refresh option. This would be instead of using the personal gateway.

> [AZURE.NOTE] If your dataset is configured for a live or DirectQuery connection, you will not have the option to use scheduled refresh. Scheduled refresh is only available for imported datasets.

|**Origen de datos**|**Live/DirectQuery**|**User configured manual or scheduled refresh**|**Gateway required**|
|---|---|---|---|
|Analysis Services Tabular|Sí|Sí|Sí|
|Analysis Services Multidimensional|Sí|Sí|Sí|
|SQL Server|Sí|Sí|Sí|
|SAP HANA|Sí|Sí|Sí|
|Oracle|Sí|Sí|Sí|
|Teradata|Sí|Sí|Sí|

To learn more, see <bpt id="p1">[</bpt>On-premises Data Gateway<ept id="p1">](powerbi-gateway-onprem.md)</ept>

## Databases in the cloud  

With DirectQuery, there is a direct connection between Power BI and the database in the cloud. When you interact with a visualization, queries are sent from Power BI directly to the database. Updated data is then returned and visualizations are updated. If there is no user interaction in a visualization, like in a dashboard, data is refreshed automatically about every fifteen minutes. Because there is a direct connection between Power BI and the database, there is no need to manually refresh or setup a refresh schedule for the dataset. And, because both the Power BI service and the data source are in the cloud, there is no need for a Personal Gateway.

|**Origen de datos**|**Live/DirectQuery**|**User configured manual or scheduled refresh**|**Gateway required**|
|---|---|---|---|
|SQL Azure Data Warehouse|Sí|No|No|
|Spark on HDInsight|Sí|No|No|

To learn more, see <bpt id="p1">[</bpt>Azure and Power BI<ept id="p1">](powerbi-azure-and-power-bi.md)</ept>.

## Real-time dashboards  

Real-time dashboards use the Microsoft Power BI REST API, or Microsoft Stream Analytics, to make sure the data is up-to-date. Since real time dashboards do not require users to configure refresh, they are outside the scope of this article.

|**Origen de datos**|**Automático**|**User configured manual or scheduled refresh**|**Gateway required**|
|---|---|---|---|
|Custom apps developed with the Power BI Rest API or Microsoft Stream Analytics|Yes, live streaming|No|No|

To learn more, see <bpt id="p1">[</bpt>Create a real-time dashboard in Power BI<ept id="p1">](https://msdn.microsoft.com/library/mt267603.aspx)</ept>.

## Configure scheduled refresh

To learn how to configure scheduled refresh, see <bpt id="p1">[</bpt>Configure scheduled refresh<ept id="p1">](powerbi-refresh-scheduled-refresh.md)</ept>

## Common data refresh scenarios  

Sometimes the best way to learn about data refresh in Power BI to look at examples. Here are some of the more common data refresh scenarios:

### Excel workbook with tables of data  

You have an Excel workbook with several tables of data, but none of them are loaded into the Excel data model. You use Get Data to upload the workbook file from your local drive into Power BI, and create a dashboard. But, now you’ve made some changes to a couple of the workbook’s tables on your local drive, and you want to update your dashboard in Power BI with the new data.

Unfortunately, refresh is not supported in this scenario. In order to refresh the dataset for your dashboard, you will have to re-upload the workbook. However, there’s a really great solution: Put your workbook file on OneDrive, or SharePoint Online!

When you connect to a file on OneDrive, or SharePoint Online, your reports and dashboards will show data as it is in the file. In this case, your Excel workbook. Power BI automatically checks the file, about every hour, for updates. If you make changes to the workbook (stored in OneDrive or SharePoint Online), those changes are reflected in your dashboard and reports within an hour. You don’t need to setup refresh at all. However, if you need to see your updates in Power BI immediately, you can manually refresh the dataset by using Refresh Now.

To learn more, see <bpt id="p1">[</bpt>Excel data in Power BI<ept id="p1">](powerbi-service-excel-data.md)</ept>,<bpt id="p2">[</bpt>Replace an Excel, Power BI Desktop, or CSV file in Power BI<ept id="p2">](powerbi-replace-an-excel-power-bi-desktop-or-csv-file.md)</ept>, <bpt id="p3">[</bpt>Refresh a dataset created from an Excel workbook on OneDrive<ept id="p3">](powerbi-refresh-excel-file-onedrive.md)</ept>.

### Excel workbook connects to a SQL database in your company  

Let’s say you have an Excel workbook named SalesReport.xlsx on your local computer. Power Query in Excel was used to connect to a SQL database on a server in your company and query for sales data that is loaded into the data model. Each morning, you open the workbook and hit Refresh to update your PivotTables.

Now you want to explore your sales data in Power BI, so you use Get Data to connect to and upload the SalesReport.xlsx workbook from your local drive.

In this case, you can manually refresh the data in the SalesReport.xlsx dataset or setup a refresh schedule. Because the data really comes from the SQL database in your company, you’ll need to download and install a gateway. Once you’ve installed and configured the gateway, you’ll need to go into the SalesReport dataset’s settings and sign in to the data source; but you’ll only have to do this once. You can then setup a refresh schedule so Power BI automatically connects to the SQL database and gets updated data. Your reports and dashboards will also be updated automatically.

> [AZURE.NOTE] This will only update the data within the dataset in the Power BI service. Your local file will not be updated as part of the refresh.

To learn more, see  <bpt id="p1">[</bpt>Excel data in Power BI<ept id="p1">](powerbi-service-excel-data.md)</ept>, <bpt id="p2">[</bpt>Power BI Gateway - Personal<ept id="p2">](powerbi-personal-gateway.md)</ept>, <bpt id="p3">[</bpt>On-premises Data Gateway<ept id="p3">](powerbi-gateway-onprem.md)</ept>, <bpt id="p4">[</bpt>Refresh a dataset created from an Excel workbook on a local drive<ept id="p4">](powerbi-refresh-excel-file-local-drive.md)</ept>.

### Power BI Desktop file with data from an OData feed  
In this case, you use Get Data in Power BI Desktop to connect to and import census data from an OData feed.  You create several reports in Power BI Desktop, then name the file WACensus and save it on a share in your company. You then publish the file to the Power BI service.

In this case, you can manually refresh the data in the WACensus dataset or setup a refresh schedule. Because the data in the data source comes from an OData feed online, you do not need to install a gateway, but you will need to go into the WACensus dataset’s settings and sign in to the OData data source. You can then setup a refresh schedule so Power BI automatically connects to the OData feed and gets updated data. Your reports and dashboards will also be updated automatically.

To learn more, see <bpt id="p1">[</bpt>Publish from Power BI Desktop<ept id="p1">](powerbi-desktop-upload-desktop-files.md)</ept>, <bpt id="p2">[</bpt>Refresh a dataset created from a Power BI Desktop file on a local drive<ept id="p2">](powerbi-refresh-desktop-file-local-drive.md)</ept>, <bpt id="p3">[</bpt>Refresh a dataset created from a Power BI Desktop file on OneDrive<ept id="p3">](powerbi-refresh-desktop-file-onedrive.md)</ept>.

### Shared content pack from another user in your organization  

You’ve connected to an organizational content pack. It includes a dashboard, several reports, and a dataset.

In this scenario, you cannot setup refresh for the dataset. The data analyst who created the content pack is responsible for making sure the dataset is refreshed, depending on the data sources used.

If your dashboards and reports from the content pack aren’t updating, you’ll want to talk to the data analyst who created the content pack.

To learn more, see <bpt id="p1">[</bpt>Introduction to organizational content packs<ept id="p1">](powerbi-service-organizational-content-packs-introduction.md)</ept>, <bpt id="p2">[</bpt>Work with organizational content packs<ept id="p2">](powerbi-service-organizational-content-packs-use-and-work-with.md)</ept>.

### Content pack from an online service provider like Salesforce  

In Power BI you used Get Data to connect to and import your data from an online service provider like Salesforce. Well, not much to do here. Your Salesforce data set is automatically scheduled to refresh once a day. 

Like most online service providers, Salesforce updates data once a day, usually at night. You can manually refresh your Salesforce dataset, or setup a refresh schedule, but it’s not necessary because Power BI will automatically refresh the dataset and your reports and dashboards will be updated too.

To learn more, see <bpt id="p1">[</bpt>Salesforce content pack for Power BI<ept id="p1">](powerbi-content-pack-salesforce.md)</ept>.

## Solucionar problemas  

When things go wrong, it’s usually because Power BI can’t sign into data sources, or the dataset connects to an on-premises data source and the gateway is offline. Make sure Power BI can sign into data sources. If a password you use to sign into a data source changes, or Power BI gets signed out from a data source, be sure to try signing into your data sources again in Data Source Credentials.

For more information about troubleshooting, see <bpt id="p1">[</bpt>Tools for troubleshooting refresh issues<ept id="p1">](powerbi-refresh-tools-for-troubleshooting-issues.md)</ept> and <bpt id="p2">[</bpt>Troubleshooting refresh scenarios<ept id="p2">](powerbi-refresh-troubleshooting-refresh-scenarios.md)</ept>.

## Consulte también

[Tools for troubleshooting refresh issues](powerbi-refresh-tools-for-troubleshooting-issues.md)  
[Troubleshooting refresh scenarios](powerbi-refresh-troubleshooting-refresh-scenarios.md)  
[Power BI Gateway - Personal](powerbi-personal-gateway.md)  
[On-premises Data Gateway](powerbi-gateway-onprem.md)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)
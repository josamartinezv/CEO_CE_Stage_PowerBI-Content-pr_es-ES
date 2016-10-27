<properties
   pageTitle="Refresh a dataset created from an Excel workbook - local"
   description="Refresh a dataset created from an Excel workbook on a local drive"
   services="powerbi"
   documentationCenter=""
   authors="guyinacube"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="complete"
   qualityDate="04/01/2016"/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/15/2016"
   ms.author="asaxton"/>

# Refresh a dataset created from an Excel workbook on a local drive

## What’s supported?  
In Power BI, Refresh Now and Schedule Refresh is supported for datasets created from Excel workbooks imported from a local drive where Power Query (Get &amp; Transform data in Excel 2016) or Power Pivot is used to connect to any of the following data sources and load data into the Excel data model:  

### Power BI Gateway - Personal

-   All online data sources shown in Power Query.
-   All on-premises data sources shown in Power Query except for Hadoop file (HDFS) and Microsoft Exchange.
-   All online data sources shown in Power Pivot.\*
-   All on-premises data sources shown in Power Pivot except for Hadoop file (HDFS) and Microsoft Exchange.

<!-- Refresh Data sources-->
[AZURE.INCLUDE [refresh-datasources](../includes/refresh-datasources.md)]

>**Notas:**  
>- A gateway must be installed and running in order for Power BI to connect to on-premises data sources and refresh the dataset.
>
>- When using Excel 2013, make sure you’ve updated Power Query to the latest version.
>
>- Refresh is not supported for Excel workbooks imported from a local drive where data exists only in  worksheets or linked tables. Refresh is supported for worksheet data if it is stored and imported from OneDrive. To learn more, see <bpt id="p1">[</bpt>Refresh a dataset created from an Excel workbook on OneDrive, or SharePoint Online<ept id="p1">](powerbi-refresh-excel-file-onedrive.md)</ept>.
>
>- When you refresh a dataset created from an Excel workbook imported from a local drive, only the data queried from data sources is refreshed. If you change the structure of the data model in Excel or Power Pivot; for example, create a new measure or change the name of a column, those changes will not be copied to the dataset. If you make such changes, you’ll need to re-upload or re-publish the workbook. If you expect to make regular changes to the structure of your workbook and you want those to be reflected in the dataset in Power BI without having to re-upload, consider putting your workbook on OneDrive. Power BI automatically refreshes both the structure and worksheet data from workbooks stored and imported from OneDrive.

## How do I make sure data is loaded to the Excel data model?  
When you use Power Query (Get &amp; Transform data in Excel 2016) to connect to a data source, you have several options where to load the data. To make sure you load data into the data model, you must select the <bpt id="p1">**</bpt>Add this data to the Data Model<ept id="p1">**</ept> option in the <bpt id="p2">**</bpt>Load To<ept id="p2">**</ept> dialog box.

> [AZURE.NOTE] The images here show Excel 2016.

In <bpt id="p1">**</bpt>Navigator<ept id="p1">**</ept>, click <bpt id="p2">**</bpt>Load To…<ept id="p2">**</ept>  
    ![](media/powerbi-refresh-excel-file-local-drive/Refresh_LoadToDM_1.png)

Or, If you click <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept> in Navigator, you’ll open the Query Editor. There you can click <bpt id="p1">**</bpt>Close &amp; Load To….<ept id="p1">**</ept>  
    ![](media/powerbi-refresh-excel-file-local-drive/Refresh_LoadToDM_2.png)

Then in <bpt id="p1">**</bpt>Load To<ept id="p1">**</ept>, make sure you select <bpt id="p2">**</bpt>Add this data to the Data Model<ept id="p2">**</ept>.  
    ![](media/powerbi-refresh-excel-file-local-drive/Refresh_LoadToDM_3.png)

### What if I use Get External Data in Power Pivot?  
No problem. Whenever you use Power Pivot to connect to and query data from an on-premises or online data source, the data is automatically loaded to the data model.

## How do I schedule refresh?  
When you setup a refresh schedule, Power BI will connect directly to the data sources using connection information and credentials in the dataset to query for updated data, then load the updated data into the dataset. Any visualizations in reports and dashboards based on that dataset in the Power BI service are also updated.

For details on how to setup schedule refresh, see <bpt id="p1">[</bpt>Configure Schedule Refresh<ept id="p1">](powerbi-refresh-scheduled-refresh.md)</ept>.

## When things go wrong  
When things go wrong, it’s usually because Power BI can’t sign into data sources, or if the dataset connects to an on-premises data source, the gateway is offline. Make sure Power BI can sign into data sources. If a password you use to sign into a data source changes, or Power BI gets signed out from a data source, be sure to try signing into your data sources again in Data Source Credentials.

Be sure to leave the <bpt id="p1">**</bpt>Send refresh failure notification email to me checked<ept id="p1">**</ept>. You’ll want to know right away if a scheduled refresh fails.

## Important notes  
\* Refresh is not supported for OData feeds connected to and queried from Power Pivot. When using an OData feed as a data source, use Power Query.

## Solucionar problemas

Sometimes refreshing data may not go as expected. Typically this will be an issue connected with a gateway. Take a look at the gateway troubleshooting articles for tools and known issues.

[Troubleshooting the On-premises Data Gateway](powerbi-gateway-onprem-tshoot.md)

[Troubleshooting the Power BI Gateway - Personal](powerbi-admin-troubleshooting-power-bi-personal-gateway.md)

More questions? [Try the Power BI Community](http://community.powerbi.com/)

<properties
   pageTitle="Refresh a dataset created from a Power BI Desktop file - local"
   description="Refresh a dataset created from a Power BI Desktop file on a local drive"
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

# Refresh a dataset created from a Power BI Desktop file on a local drive  

## What’s supported?  
In Power BI, Refresh Now and Schedule Refresh is supported for datasets created from Power BI Desktop files imported from a local drive where Get Data/Query Editor is used to connect to and load data from any of the following data sources:  

### Power BI Gateway - Personal
-   All online data sources shown in Power BI Desktop’s Get Data and Query Editor.
-   All on-premises data sources shown in Power BI Desktop’s Get Data and Query Editor except for Hadoop file (HDFS) and Microsoft Exchange.

<!-- Refresh Data sources-->
[AZURE.INCLUDE [refresh-datasources](../includes/refresh-datasources.md)]

> [AZURE.NOTE] A gateway must be installed and running in order for Power BI to connect to on-premises data sources and refresh the dataset.

You can perform a one-time, manual refresh right in Power BI Desktop by selecting Refresh on the Home ribbon. When you select Refresh here, the data in the <bpt id="p1">*</bpt>file’s<ept id="p1">*</ept> model is refreshed with updated data from the original data source. This kind of refresh, entirely from within the Power BI Desktop application itself, is different from manual or scheduled refresh in Power BI, and it’s important to understand the distinction.

![](media/powerbi-refresh-desktop-file-local-drive/pbix-refresh.png)

When you import your Power BI Desktop file from a local drive, data, along with other information about the model is loaded into a dataset in the Power BI service. In the Power BI service, not Power BI Desktop, you want to refresh data in the dataset because that is what your reports, in the Power BI service, are based on. Because the data sources are external, you can manually refresh the dataset by using <bpt id="p1">**</bpt>Refresh now<ept id="p1">**</ept> or you can setup a refresh schedule by using <bpt id="p2">**</bpt>Schedule Refresh<ept id="p2">**</ept>.

When you refresh the dataset, Power BI does not connect to the file on the local drive to query for updated data. It uses information in the dataset to connect directly to the data sources to query for updated data it then loads into the dataset. 

> [AZURE.NOTE] Refreshed data in the dataset is not synchronized back to the file on the local drive.

## How do I schedule refresh?  
When you setup a refresh schedule, Power BI will connect directly to the data sources using connection information and credentials in the dataset to query for updated data, then load the updated data into the dataset. Any visualizations in reports and dashboards based on that dataset in the Power BI service are also updated.

For details on how to setup schedule refresh, see <bpt id="p1">[</bpt>Configure Schedule Refresh<ept id="p1">](powerbi-refresh-scheduled-refresh.md)</ept>.

## When things go wrong  
When things go wrong, it’s usually because Power BI can’t sign into data sources, or if the dataset connects to an on-premises data source, the gateway is offline. Make sure Power BI can sign into data sources. If a password you use to sign into a data source changes, or Power BI gets signed out from a data source, be sure to try signing into your data sources again in Data Source Credentials.

Be sure to leave the <bpt id="p1">**</bpt>Send refresh failure notification email to me<ept id="p1">**</ept> checked. You’ll want to know right away if a scheduled refresh fails.

## Solucionar problemas

Sometimes refreshing data may not go as expected. Typically this will be an issue connected with a gateway. Take a look at the gateway troubleshooting articles for tools and known issues.

[Troubleshooting the On-premises Data Gateway](powerbi-gateway-onprem-tshoot.md)

[Troubleshooting the Power BI Gateway - Personal](powerbi-admin-troubleshooting-power-bi-personal-gateway.md)

More questions? [Try the Power BI Community](http://community.powerbi.com/)
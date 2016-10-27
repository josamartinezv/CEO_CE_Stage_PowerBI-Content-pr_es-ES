<properties
pageTitle="On-premises data gateway"
description="This is an overview of the On-premises data gateway for Power BI. You can use this gateway to work with DirectQuery data sources. You can also use this gateway to refresh cloud datasets with on-premises data."
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
ms.tgt_pltfrm="na"
ms.workload="powerbi"
ms.date="10/12/2016"
ms.author="asaxton"/>
# On-premises data gateway

The on-premises data gateway acts as a bridge, providing quick and secure data transfer between on-premises data (data that is not in the cloud) and the Power BI, Microsoft Flow, Logic Apps, and PowerApps services.

You can use a single gateway with different services at the same time. If you are using Power BI, as well as PowerApps, a single gateway and be used for both. It is dependent on the account you sign in with.

<!-- Shared Requirements Include -->
[AZURE.INCLUDE [gateway-onprem-requirements-include](../includes/gateway-onprem-requirements-include.md)]

### Limitations of Analysis Services live connections

You can use a live connection against tabular or multidimensional instances.

|**Server version**|**Required SKU**|
|---|---|
|2012 SP1 CU4 or later|Business Intelligence and Enterprise SKU|
|2014|Business Intelligence and Enterprise SKU|
|2016|Standard SKU or higher|

- Cell level Formatting and translation features are not supported.
- Actions and Named Sets are not exposed to Power BI, but you can still connect to multidimensional cubes that also contain Actions or Named sets and create visuals and reports.

<!-- Shared Install steps Include -->
[AZURE.INCLUDE [gateway-onprem-datasources-include](../includes/gateway-onprem-datasources-include.md)]
 
## Download and install the On-premises data gateway

To download the gateway, select <bpt id="p1">**</bpt>Data Gateway<ept id="p1">**</ept> under the Downloads menu. Download the <bpt id="p1">[</bpt>On-premises data gateway<ept id="p1">](http://go.microsoft.com/fwlink/?LinkID=820925)</ept>.

![](media/powerbi-gateway-onprem/powerbi-download-data-gateway.png)

<!-- Shared Install steps Include -->
[AZURE.INCLUDE [gateway-onprem-install-include](../includes/gateway-onprem-install-include.md)]

## Install the gateway in personal mode 

> [AZURE.NOTE] Personal will only work with Power BI.

After the personal gateway is installed, you will need to launch the <bpt id="p1">**</bpt>Power BI Gateway - Personal Configuration Wizard<ept id="p1">**</ept>.

![](media/powerbi-gateway-onprem/personal-gateway-launch-configuration.png)

You will then need to sign into Power BI to register the gateway with the cloud service.

![](media/powerbi-gateway-onprem/personal-gateway-signin.png)

You will also need to supply the windows user name and password that the windows service will run as. You can specify a different Windows account from your own. The gateway service will run using this account.

![](media/powerbi-gateway-onprem/personal-gateway-windows-service.png)

After the installation is complete, you will need to go to your datasets within Power BI and make sure credentials are entered for your on-premises data sources.

<a name="credentials">
## Storing encrypted credentials in the cloud

When you add a data source to the gateway, you need to provide credentials for that data source. All queries to the data source will run using these credentials. The credentials are encrypted securely, using asymmetric encryption so that they cannot be decrypted in the cloud, before they are stored in the cloud. The credentials are sent to the machine, running the gateway, on-premises where they are decrypted when the data sources are accessed.

<!-- Account and Port information -->
[AZURE.INCLUDE [gateway-onprem-accounts-ports-more](../includes/gateway-onprem-accounts-ports-more.md)]

<!-- How the gateway works -->
[AZURE.INCLUDE [gateway-onprem-how-it-works-include](../includes/gateway-onprem-how-it-works-include.md)]

## Solucionar problemas

If you’re having trouble when installing and configuring a gateway, be sure to see <bpt id="p1">[</bpt>Troubleshooting the Power BI Gateway - Enterprise<ept id="p1">](powerbi-gateway-enterprise-tshoot.md)</ept>. If you think you are having an issue with your firewall, see the <bpt id="p1">[</bpt>firewall or proxy<ept id="p1">](powerbi-gateway-enterprise-tshoot.md#firewall-or-proxy)</ept> section in the troubleshooting article.

If you think you are encountering proxy issues, with the gateway, see <bpt id="p1">[</bpt>Configuring proxy settings for the Power BI Gateways<ept id="p1">](powerbi-gateway-proxy.md)</ept>.

## Consulte también

[Manage your data source - Analysis Services](powerbi-gateway-enterprise-manage-ssas.md)  
[Manage your data source - SAP HANA](powerbi-gateway-enterprise-manage-sap.md)  
[Manage your data source - SQL Server](powerbi-gateway-enterprise-manage-sql.md)  
[Manage your data source - Oracle](powerbi-gateway-onprem-manage-oracle.md)  
[Manage your data source - Import/Scheduled refresh](powerbi-gateway-enterprise-manage-scheduled-refresh.md)  
[On-premises Data Gateway in-depth](powerbi-gateway-onprem-indepth.md)  
[Troubleshooting the On-premises Data Gateway](powerbi-gateway-onprem-tshoot.md)  
[Configuring proxy settings for the On-Premises Data Gateway](powerbi-gateway-proxy.md)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)

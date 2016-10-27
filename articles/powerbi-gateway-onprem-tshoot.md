<properties
pageTitle="Troubleshooting the On-Premises Data Gateway"
description="This article provides ways for you to troubleshoot issues you are having with the On-Premises Data Gateway. It provides potential workarounds to known issues, as well as tools to assist you."
services="powerbi"
documentationCenter=""
authors="guyinacube"
manager="erikre"
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
ms.date="09/21/2016"
ms.author="asaxton"/>
# Troubleshooting the On-Premises Data Gateway

The following goes through some common issues you may encounter when using the On-premises Data Gateway. 

<!-- Shared Community & support links Include -->
[AZURE.INCLUDE [gateway-onprem-tshoot-support-links-include](../includes/gateway-onprem-tshoot-support-links-include.md)]

<!-- Shared Troubleshooting Install Include -->
[AZURE.INCLUDE [gateway-onprem-tshoot-install-include](../includes/gateway-onprem-tshoot-install-include.md)]

## Configuración

### How to restart the gateway

The gateway runs as a Windows service, so you can start and stop it in multiple ways. For example, you can open a command prompt with elevated permissions on the machine where the gateway is running and then run either of these commands:

- To stop the service, run this command:

    '''   net stop PBIEgwService   '''
    
- To start the service, run this command:

    '''   net start PBIEgwService   '''

### Error: Failed to create gateway. Inténtelo de nuevo.

All of the details are available, but the call to the Power BI service returned an error. The error, and an activity id, will be displayed. This could happen for different reasons. You can collect, and review, the logs, as mentioned below, to get more details. 

This could also be due to proxy configuration issues. The user interface does now allow for proxy configuration. You can learn more about making <bpt id="p1">[</bpt>proxy configuration changes<ept id="p1">](powerbi-gateway-proxy.md)</ept>

### Error: Failed to update gateway details.  Inténtelo de nuevo.

Information was received from the Power BI service, to the gateway. The information was passed onto the local windows service, but it failed to return. Or, a symmetric key generation failed. The inner exception will be displayed under <bpt id="p1">**</bpt>Show details<ept id="p1">**</ept>. You can collect, and review, the logs, as mentioned below, to get more details. 

### Error: Power BI service reported local gateway as unreachable. Please restart the gateway and try again.

At the end of configuration, the Power BI service will be called again to validate the gateway. The Power BI service does not report the gateway as <bpt id="p1">*</bpt>live<ept id="p1">*</ept>. Restarting the windows service may allow the communication to be successful. You can collect, and review, the logs, as mentioned below, to get more details. 

### Script error during sign into Power BI

You may receive a script error when signing into Power BI as part of the enterprise gateway configuration. Installing the following security update should resolve the issue. This can be installed via Windows Update.

[MS16-051: Security update for Internet Explorer: May 10, 2016 (KB 3154070)](https://support.microsoft.com/kb/3154070)

### Gateway configuration failed with a null reference exception

You may encounter an error similar to the following.

        Failed to update gateway details.  Please try again.
        Error updating gateway configuration.

This will include a stack trace, and that stack trace will may include the following.

        Microsoft.PowerBI.DataMovement.Pipeline.Diagnostics.CouldNotUpdateGatewayConfigurationException: Error updating gateway configuration. ----> System.ArgumentNullException: Value cannot be null.
        Parameter name: serviceSection

If you are upgrading from an older gateway, we preserve the config file. There may be a section that is missing. When the gateway tries to read it, we will get the above null reference exception.

To correct this, do the following.

1. Uninstall the gateway.

2. Delete the following folder.

        c:\Program Files\on-premises data gateway

3. Reinstall the gateway.

4. Optionally apply the recovery key to restore an existing gateway.

## Orígenes de datos

### Error: Unable to Connect. Details: "Invalid connection credentials"

Within <bpt id="p1">**</bpt>Show details<ept id="p1">**</ept>, it should display the error message received from the data source. For SQL Server, you should see something like the following.

    Login failed for user 'username'.

Verify that you have the correct username and password. Also verify that those credentials can successfully connect to the data source. Make sure the account being used matches the <bpt id="p1">**</bpt>Authentication Method<ept id="p1">**</ept>.

### Error: Unable to Connect. Details: "Cannot connect to the database"

We were able to connect to the server, but not to the database supplied. Verify the name of the database, and that the user credential as the proper permission to access that database.

Within <bpt id="p1">**</bpt>Show details<ept id="p1">**</ept>, it should display the error message received from the data source. For SQL Server, you should see something like the following.

    Cannot open database "AdventureWorks" requested by the login. The login failed. Login failed for user 'username'.

### Error: Unable to Connect. Details: "Unknown error in enterprise gateway"

This error could occur for different reasons. Be sure to validate that you can connect to the data source from the machine hosting the gateway. This could be the result of the server not being accessible.

Within <bpt id="p1">**</bpt>Show details<ept id="p1">**</ept>, you will see an error code of <bpt id="p2">**</bpt>DM_GWPipeline_UnknownError<ept id="p2">**</ept>.

You can also look in the Event Logs &gt; <bpt id="p1">**</bpt>Applications and Services Logs<ept id="p1">**</ept><ph id="ph1"> &gt; </ph><bpt id="p2">**</bpt>Power BI Enterprise Gateway Service<ept id="p2">**</ept> for more details.

### Error: We encountered an error while trying to connect to <ph id="ph1">&lt;server&gt;</ph>. Details: "We reached the enterprise gateway, but the gateway can't access the on-premises data source."

We were unable to connect to the specified data source. Be sure to validate the information provided for that data source.

Within <bpt id="p1">**</bpt>Show details<ept id="p1">**</ept>, you will see an error code of <bpt id="p2">**</bpt>DM_GWPipeline_Gateway_DataSourceAccessError<ept id="p2">**</ept>. 

If the underlying error message is similar to the following, this means that the account you are using for the data source is not a server admin for that Analysis Services instance. [Obtener más información](powerbi-gateway-onprem-manage-ssas.md#add-a-data-source)

    The 'CONTOSO\account' value of the 'EffectiveUserName' XML for Analysis property is not valid.

If the underlying error message is similar to the following, it could mean that the service account for Analysis Services may be missing the <bpt id="p1">[</bpt>token-groups-global-and-universal<ept id="p1">](https://msdn.microsoft.com/library/windows/desktop/ms680300.aspx)</ept> (TGGAU) directory attribute.

    The user name or password is incorrect.

Domains with Pre-Windows 2000 compatibility access will have the TGGAU attribute enabled. However, most newly created domains will not enable this attribute by default. You can read more about this <bpt id="p1">[</bpt>here<ept id="p1">](https://support.microsoft.com/kb/331951)</ept>.

You can confirm this by doing the following.

1. Connect to the Analysis Services machine within SQL Server Management Studio. Within the Advanced connection properties, include EffectiveUserName for the user in question and see if this reproduces the error.

2. You can use the dsacls Active Directory tool to validate whether the attribute is listed. This is tool is normally found on a domain controller. You will need to know what the distinguished domain name is for the account and pass that to the tool.

        dsacls "CN=John Doe,CN=UserAccounts,DC=contoso,DC=com"
    
    You want to see something similar to the following in the results.

            Allow BUILTIN\Windows Authorization Access Group
                                          SPECIAL ACCESS for tokenGroupsGlobalAndUniversal
                                          READ PROPERTY

To correct this issue, you will need to enable TGGAU on account used for the Analysis Services windows service.

**Another possibility for user name or password incorrect**

This error could also be caused if the Analysis Services server is in a different domain than the users and there is not a two-way trust established.

You will need to work with your domain administrators to verify the trust relationship between domains.

**Unable to see enterprise gateway data sources in the 'Get Data' experience for Analysis Services from the Power BI service**

Make sure that your account is listed in the <bpt id="p1">**</bpt>Users<ept id="p1">**</ept> tab of the data source within the gateway configuration. If you don't have access to the gateway, check with the administrator of the gateway and ask them to verify. Only accounts in the <bpt id="p1">**</bpt>Users<ept id="p1">**</ept> list will see the data source listed in the Analysis Services list.

## Conjuntos de datos

### Error: There is not enough space for this row.

This will occur if you have a single row greater than 4 MB in size. You will need to determine what the row is from your data source and attempt to filter it out or reduce the size for that row.

## Reports

### Report could not access the data source because you do not have access to our data source via an enterprise gateway.

This is usually caused by one of the following. 

1. The data source information does not match what is in the underlying dataset. The server and database name need to match between the data source defined for the on-premises data gateway and what you supply within Power BI Desktop. If you use an IP Address in Power BI Desktop, the data source, for the on-premises data gateway, needs to use an IP Address as well.

2. There is not a data source available on any gateway within your organization. You can configure the data source on a new, or existing, on-premises data gateway.

### Error: Data source access error. Please contact the gateway administrator.

If this report is making use of a live Analysis Services connection, you could be encountering an issue with a value being passed to EffectiveUserName that is either not valid, or doesn't have permissions on the Analysis Services machine. Typically, an authentication issue is due to the fact that the value being passed for EffectiveUserName doesn't match a local user principal name (UPN).

To confirm this, you can do the following.

1. Find the effective username within the <bpt id="p1">[</bpt>gateway logs<ept id="p1">](#logs)</ept>.

2. Once you have the value being passed, validate that it is correct. If it is your user, you can use the following command from a command prompt to see what the UPN should be. The UPN will look like an email address.

        whoami /upn

Optionally, you can see what Power BI gets from Azure Active Directory.

1. Browse to <bpt id="p1">[</bpt>https://graphexplorer.cloudapp.net<ept id="p1">](https://graphexplorer.cloudapp.net)</ept>.

2. Select <bpt id="p1">**</bpt>Sign in<ept id="p1">**</ept> in the upper right.

3. Run the following query. You will see a rather large JSON response.

        https://graph.windows.net/me?api-version=1.5

4. Look for <bpt id="p1">**</bpt>userPrincipalName<ept id="p1">**</ept>. 


If your Azure Active Directory UPN doesn't match your local Active Directory UPN, you can use the <bpt id="p1">[</bpt>Map user names<ept id="p1">](powerbi-gateway-enterprise-manage-ssas.md#map-user-names)</ept> feature to replace it with a valid value. Or you can work with either your tenant admin, or local Active Directory admin, to get your UPN changed.

<!-- Shared Troubleshooting Firewall/Proxy Include -->
[AZURE.INCLUDE [gateway-onprem-tshoot-firewall-include](../includes/gateway-onprem-tshoot-firewall-include.md)]

You can find the data center region you are in by doing the following:

1. Select the <bpt id="p1">**</bpt>?<ept id="p1">**</ept> in the upper right of the Power BI service.

2. Select <bpt id="p1">**</bpt>About Power BI<ept id="p1">**</ept>.

3. Your data region will be listed in <bpt id="p1">**</bpt>Your data is stored in<ept id="p1">**</ept>.

    ![](media/powerbi-gateway-onprem-tshoot/power-bi-data-region.png)

If you are still not getting anywhere, you could try getting a network trace using a tool like <bpt id="p1">[</bpt>fiddler<ept id="p1">](#fiddler)</ept> or netsh, although these are advanced collection methods and you may need assistance in analyzing the collected data. You can contact <bpt id="p1">[</bpt>support<ept id="p1">](https://support.microsoft.com)</ept> for assistance.

## Pruebas

<iframe width="560" height="315" src="https://www.youtube.com/embed/IJ_DJ30VNk4?showinfo=0" frameborder="0" allowfullscreen></iframe>

### Contadores de rendimiento

There are a number of performance counters that can be used to gauge the activities for the gateway. These can be helfup to understanding if we have a large load of activity and may need to make a new gateway. These counters will not reflect how long something takes.

These counters can be access through the Windows Performance Monitor tool.

![](media/powerbi-gateway-onprem-tshoot/gateway-perfmon.png)

There are general groupings of these counters.

|Counter Type|Descripción|
|---|---|
|ADO.NET|This is used for any DirectQuery connection.|
|ADOMD|This is used for Analysis Services 2014 and earlier.|
|OLEDB|This is used by certain data sources. This includes SAP HANA and Analysis Service 2016 or later.|
|Mashup|This includes any imported data source. If you are scheduling refresh or doing an on-demand refresh, it will go through the mashup engine.|

Here is a listing of the available performance counters.

|Contador|Descripción|
|---|---|
|# of ADO.NET open connection executed / sec|Number of ADO.NET open connection actions executed per second (succeeded or failed).|
|# of ADO.NET open connection failed / sec|Number of ADO.NET open connections actions failed per second.|
|# of ADO.NET queries executed / sec|Number of ADO.NET queries executed per second (succeeded or failed).|
|# of ADO.NET queries failed / sec|Number of ADO.NET failed queries executed per second.|
|# of ADOMD open connection executed / sec|Number of ADOMD open connection actions executed per second (succeeded or failed).|
|# of ADOMD open connection failed / sec|Number of ADOMD open connection actions failed per second.|
|# of ADOMD queries executed / sec|Number of ADOMD queries executed per second (succeeded or failed).|
|# of ADOMD queries failed / sec|Number of ADOMD failed queries executed per second.|
|# of all open connection executed / sec|Number of open connection actions executed per second (succeeded or failed).|
|# of all open connection failed / sec|Number of failed open connection actions executed per second.|
|# of all queries executed / sec|Number of queries executed per second (succeeded or failed).|
|# of items in the ADO.NET connection pool|Number of items in the ADO.NET connection pool.|
|# of items in the OLEDB connection pool|Number of items in the OLEDB connection pool.|
|# of items in the Service Bus pool|Number of items in the Service Bus pool.|
|# of Mashup open connection executed / sec|Number of Mashup open connection actions executed per second (succeeded or failed).|
|# of Mashup open connection failed / sec|Number of Mashup open connection actions failed per second.|
|# of Mashup queries executed / sec|Number of Mashup queries executed per second (succeeded or failed).|
|# of Mashup queries failed / sec|Number of Mashup failed queries executed per second|
|# of multiple result set OLEDB queries failed / sec|Number of multiple resultset OLEDB failed queries executed per second.|
|# of OLEDB multiple resultset queries executed / sec|Number of OLEDB multiple resultset queries executed per second (succeeded or failed).|
|# of OLEDB open connection executed / sec|Number of OLEDB open connection actions executed per second (succeeded or failed).|
|# of OLEDB open connection failed / sec|Number of OLEDB open connection actions failed per second.|
|# of OLEDB queries executed / sec|Number of OLEDB multiple resultset queries executed per second (succeeded or failed).|
|# of OLEDB queries failed / sec|Number of OLEDB mutiple resultset failed queries executed per second.|
|# of OLEDB single resultset queries executed / sec|Number of OLEDB single resultset queries executed per second (succeeded or failed).|
|# of queries failed / sec|Number of failed queries executed per second.|
|# of single result set OLEDB queries failed / sec|Number of single resultset OLEDB failed queries executed per second.|

### Reviewing slow performing queries

You may find that response through the gateway is slow. This could be for DirectQuery queries or when refreshing your imported dataset. You can enable additional logging to output queries and their timings to help understand what is performing slow. When you find a long running query, it may require additional modification on your data source to tune query performance. For example, adjusting indexes for a SQL Server query.

You will need to modify two configuration files to determine the duration of a query. 

#### Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config

Within the <bpt id="p1">*</bpt>Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config<ept id="p1">*</ept> file, change the <ph id="ph1">`EmitQueryTraces`</ph> value from <ph id="ph2">`False`</ph> to <ph id="ph3">`True`</ph>. This file is located, by default, at <bpt id="p1">*</bpt>C:\Program Files\On-premises data gateway<ept id="p1">*</ept>. Enabling <ph id="ph1">`EmitQueryTraces`</ph> will begin to log queries that are sent from the gateway to a data source.

> [AZURE.IMPORTANT] Enabling EmitQueryTraces could increase the log size significantly depending on gateway usage. Once you are done reviewing the logs, you will want to set EmitQueryTraces to False. It is not recommended to leave this setting enabled long term.

```
<setting name="EmitQueryTraces" serializeAs="String">
    <value>True</value>
</setting>
```

**Example query entry**

```
DM.EnterpriseGateway Information: 0 : 2016-09-15T16:09:27.2664967Z DM.EnterpriseGateway 4af2c279-1f91-4c33-ae5e-b3c863946c41    d1c77e9e-3858-4b21-3e62-1b6eaf28b176    MGEQ    c32f15e3-699c-4360-9e61-2cc03e8c8f4c    FF59BC20 [DM.GatewayCore] Executing query (timeout=224) "<pi>
SELECT 
TOP (1000001) [t0].[ProductCategoryName],[t0].[FiscalYear],SUM([t0].[Amount])
 AS [a0]
FROM 
(
(select [$Table].[ProductCategoryName] as [ProductCategoryName],
    [$Table].[ProductSubcategory] as [ProductSubcategory],
    [$Table].[Product] as [Product],
    [$Table].[CustomerKey] as [CustomerKey],
    [$Table].[Region] as [Region],
    [$Table].[Age] as [Age],
    [$Table].[IncomeGroup] as [IncomeGroup],
    [$Table].[CalendarYear] as [CalendarYear],
    [$Table].[FiscalYear] as [FiscalYear],
    [$Table].[Month] as [Month],
    [$Table].[OrderNumber] as [OrderNumber],
    [$Table].[LineNumber] as [LineNumber],
    [$Table].[Quantity] as [Quantity],
    [$Table].[Amount] as [Amount]
from [dbo].[V_CustomerOrders] as [$Table])
)
 AS [t0]
GROUP BY [t0].[ProductCategoryName],[t0].[FiscalYear] </pi>"
```

#### Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config

Within the <bpt id="p1">*</bpt>Microsoft.PowerBI.DataMovement.Pipeline.Diagnostics.dll.config<ept id="p1">*</ept> file, change the <ph id="ph1">`TraceVerbosity`</ph> value from <ph id="ph2">`4`</ph> to <ph id="ph3">`5`</ph>. This file is located, by default, at <bpt id="p1">*</bpt>C:\Program Files\On-premises data gateway<ept id="p1">*</ept>. Changing this setting will begin to log verbose entries to the gateway log. This includes entries that show duration.

> [AZURE.IMPORTANT] Enabling TraceVerbosity 5 could increase the log size significantly depending on gateway usage. Once you are done reviewing the logs, you will want to set EmitQueryTraces to <ph id="ph1">`4`</ph>. It is not recommended to leave this setting enabled long term.

```
<setting name="TracingVerbosity" serializeAs="String">
    <value>5</value>
</setting>
```

<a name="activities"></a>
#### Activity Types

|Activty Type|Descripción|
|---|---|
|MGEQ|Queries executed over ADO.NET. This includes DirectQuery data sources.|
|MGEO|Queries executed over OLEDB. This includes SAB HANA and Analysis Services 2016.|
|MGEM|Queries executed from the Mashup engine. This is used with imported datasets that use scheduled refresh or refresh on-demand.|

#### Determine the duration of a query

To determine the time it took to query the data source, you can do the following.

1. Open the gateway log.

2. Search for an <bpt id="p1">[</bpt>Activity Type<ept id="p1">](#activities)</ept> to find the query. An example of this would be MGEQ.

3. Make note of the second GUID as this is the request id. 

4. Continue to search for MGEQ until you find the FireActivityCompletedSuccessfullyEvent entry with the duration. You can verify the entry has the same request id. Duration will be in milliseconds.

        DM.EnterpriseGateway Verbose: 0 : 2016-09-26T23:08:56.7940067Z DM.EnterpriseGateway baf40f21-2eb4-4af1-9c59-0950ef11ec4a    5f99f566-106d-c8ac-c864-c0808c41a606    MGEQ    21f96cc4-7496-bfdd-748c-b4915cb4b70c    B8DFCF12 [DM.Pipeline.Common.TracingTelemetryService] Event: FireActivityCompletedSuccessfullyEvent (duration=5004)
    
    > [AZURE.NOTE] FireActivityCompletedSuccessfullyEvent is a verbose entry. This entry will not be logged unless TraceVerbosity is at level 5.

<!-- Shared Troubleshooting tools Include -->
[AZURE.INCLUDE [gateway-onprem-tshoot-tools-include](../includes/gateway-onprem-tshoot-tools-include.md)]

### Refresh History

When using the gateway for scheduled refresh, <bpt id="p1">**</bpt>Refresh History<ept id="p1">**</ept> can help you see what errors have occurred, as well as provide useful data if you should need to create a support request. You can view both scheduled, as well as on demand, refreshes. Here is how you can get to the <bpt id="p1">**</bpt>Refresh History<ept id="p1">**</ept>.

1. In the Power BI navigation pane, in <bpt id="p1">**</bpt>Datasets<ept id="p1">**</ept>, select a dataset <ph id="ph1">&amp;gt;</ph> Open Menu <ph id="ph2">&amp;gt;</ph> <bpt id="p2">**</bpt>Schedule Refresh<ept id="p2">**</ept>.

    ![](media/powerbi-gateway-onprem-tshoot/scheduled-refresh.png)

2.  

    ![](media/powerbi-gateway-onprem-tshoot/scheduled-refresh-2.png)

    ![](media/powerbi-gateway-onprem-tshoot/refresh-history.png)

## Consulte también

[Configuring proxy settings for the Power BI Gateways](powerbi-gateway-proxy.md)  
[On-premises Data Gateway](powerbi-gateway-onprem.md)  
[On-premises Data Gateway - in-depth](powerbi-gateway-onprem-indepth.md)  
[Manage your data source - Analysis Services](powerbi-gateway-enterprise-manage-ssas.md)  
[Manage your data source - SAP HANA](powerbi-gateway-enterprise-manage-sap.md)  
[Manage your data source - SQL Server](powerbi-gateway-enterprise-manage-sql.md)  
[Manage your data source - Import/Scheduled refresh](powerbi-gateway-enterprise-manage-scheduled-refresh.md)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)
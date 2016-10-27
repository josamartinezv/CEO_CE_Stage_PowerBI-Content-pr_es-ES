<properties
pageTitle="Troubleshooting tile errors"
description="Common errors that may be encountered when a tile tries to refresh"
services="powerbi"
documentationCenter=""
authors="guyinacube"
manager="mblythe"
backup=""
editor=""
tags=""
qualityFocus="monitoring"
qualityDate="06/13/2016"/>

<tags
ms.service="powerbi"
ms.devlang="NA"
ms.topic="article"
ms.tgt_pltfrm="na"
ms.workload="powerbi"
ms.date="08/15/2016"
ms.author="asaxton"/>
# Troubleshooting tile errors

Below are the common errors you may encounter with tiles along with an explanation.

> [AZURE.NOTE] If you encounter an error that is not listed below, and it is causing you issues, you can ask for further assistance on the <bpt id="p1">[</bpt>community site<ept id="p1">](http://community.powerbi.com/)</ept>, or you can create a <bpt id="p2">[</bpt>support ticket<ept id="p2">](https://powerbi.microsoft.com/support/)</ept>.

## errores

**Power BI encountered an unexpected error while loading the model. Vuelva a intentarlo más tarde.**
 

We weren't able to access your data because the data source wasn't reachable. This could happen if the data source was removed, renamed, moved, offline, or permissions have changed. Check that the source is still in the location we are pointing to and you still have permission to access it. If that isn't the issue, the source may be slow. Try again later during a time when the load on the source is smaller. If it is an on-premise source, the data source owner may be able to provide more information. 

**You don’t have permission to view this tile or open the workbook.**

Please contact the dashboard owner to make sure the data sources and model exist and are accessible for your account.

**Data shapes must contain at least one group or calculation that outputs data. Please contact the dashboard owner.**

We don't have any data to display because the query is empty. Try adding some fields from the field list to your visual and repinning it.

**Can't display the data because Power BI can't determine the relationship between two or more fields.**

You are trying to use two or more fields from tables that are not related. You need to remove the unrelated fields from the visual and then create a relationship between the tables. Once you have done this, you can add the fields back to the visual. This can be done in Power BI Desktop or Power Pivot for Excel. [Obtener más información](powerbi-desktop-create-and-manage-relationships.md)

**The groups in the primary axis and the secondary axis overlap. Groups in the primary axis can't have the same keys as groups in the secondary axis.**

This is usually a transient issue. This will typically happen when you are moving groups from rows to columns. In this case, the error should disappear when you finish moving all the groups. If you still see the message, try switching fields between the rows and columns or the axis legend or removing fields from the visual.  

**This visual has exceeded the available resources. Try filtering to decrease the amount of data displayed.**

Your visual has attempted to query too much data for us to complete the result with the available resources. Try filtering the visual to reduce the amount of data in the result.

**We are not able to identify the following fields: {0}. Please update the visual with fields that exist in the dataset.**

The field was likely deleted or renamed. You can remove the broken field from the visual, add a different field, and repin it.

**Couldn't retrieve the data for this visual. Vuelva a intentarlo más tarde.**

This is usually a transient issue. If you try again later and you still see this message, please contact support.

## Póngase en contacto con el soporte técnico.

If you are still having an issue, please <bpt id="p1">[</bpt>contact support<ept id="p1">](https://support.powerbi.com)</ept> to investigate further.

## Consulte también

[Troubleshooting the On-premises Data Gateway](powerbi-gateway-onprem-tshoot.md)  
[Troubleshooting Power BI Personal Gateway](powerbi-admin-troubleshooting-power-bi-personal-gateway.md)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)
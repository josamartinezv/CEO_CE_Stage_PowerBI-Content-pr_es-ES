<properties
pageTitle="Row-level security (RLS) with Power BI Desktop"
description="How to configure row-level security for imported datasets, and DirectQuery, within Power BI Desktop."
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
ms.date="09/21/2016"
ms.author="asaxton"/>
# Row-level security (RLS) with Power BI Desktop

Row-level security (RLS) with Power BI Desktop can be used to restrict data access for given users. Filters restrict data at the row level. You can define filters within roles.

> [AZURE.NOTE] RLS is a Pro feature. You can read more about what <bpt id="p1">[</bpt>Pro content<ept id="p1">](powerbi-power-bi-pro-content-what-is-it.md)</ept> is.

You can now configure RLS for data models imported into Power BI with Power BI Desktop. You can also configure RLS on datasets that are using DirectQuery, such as SQL Server. Previously, you were only able to implement RLS within on-premises Analysis Services models outside of Power BI. For Analysis Services live connections, you configure Row-level security on the on-premises model. The security option will not show up for live connection datasets.

> [AZURE.IMPORTANT] If you defined roles/rules within the Power BI service, you will need to recreate those roles within Power BI Desktop and publish the report to the service.

Learn more about options for <bpt id="p1">[</bpt>RLS within the Power BI Service<ept id="p1">](powerbi-admin-rls.md)</ept>.

[AZURE.INCLUDE [include-short-name](../includes/rls-desktop-define-roles.md)]

[AZURE.INCLUDE [include-short-name](../includes/rls-desktop-view-as-roles.md)]

[AZURE.INCLUDE [include-short-name](../includes/rls-limitations.md)]

[AZURE.INCLUDE [include-short-name](../includes/rls-faq.md)]

## Consulte también

[Row-level security (RLS) with the Power BI service](powerbi-admin-rls.md)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)
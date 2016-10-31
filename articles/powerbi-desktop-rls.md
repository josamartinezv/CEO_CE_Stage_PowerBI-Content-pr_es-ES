<properties
pageTitle="Seguridad de nivel de fila (RLS) con Power BI Desktop"
description="Cómo configurar la seguridad de nivel de fila de los conjuntos de datos importados y DirectQuery en Power BI Desktop."
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
# Seguridad de nivel de fila (RLS) con Power BI Desktop

Seguridad de nivel de fila (RLS) con Power BI Desktop puede usarse para restringir el acceso a datos para los usuarios. Los filtros restringen los datos en el nivel de fila. Puede definir filtros en roles.

> [AZURE.NOTE] RLS no es una característica de Pro. Puede leer más sobre qué [contenido Pro](powerbi-power-bi-pro-content-what-is-it.md) es.

Ahora puede configurar RLS para modelos de datos importados en Power BI con Power BI Desktop. También puede configurar RLS en conjuntos de datos que utilizan DirectQuery, como SQL Server. Anteriormente, podía sólo implementar RLS dentro de modelos de Analysis Services local fuera de Power BI. Para las conexiones en directo de Analysis Services, configurar la seguridad de nivel de fila en el modelo en local. La opción de seguridad no mostrará los conjuntos de datos de la conexión activa.

> [AZURE.IMPORTANT] Si define las funciones o las reglas dentro del servicio Power BI, necesitará volver a crear esos roles dentro de Power BI Desktop y publicar el informe en el servicio.

Más información acerca de las opciones de [RLS dentro del servicio Power BI](powerbi-admin-rls.md).

[AZURE.INCLUDE [include-short-name](../includes/rls-desktop-define-roles.md)]

[AZURE.INCLUDE [include-short-name](../includes/rls-desktop-view-as-roles.md)]

[AZURE.INCLUDE [include-short-name](../includes/rls-limitations.md)]

[AZURE.INCLUDE [include-short-name](../includes/rls-faq.md)]

## Consulte también

[Seguridad de nivel de fila (RLS) con el servicio Power BI](powerbi-admin-rls.md)  
¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
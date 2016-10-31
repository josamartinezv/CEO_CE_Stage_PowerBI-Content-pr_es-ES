<properties
   pageTitle="Servicio de terceros: conector de Facebook para Power BI Desktop"
   description="Servicio de terceros: conector de Facebook para Power BI Desktop"
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
# Servicio de terceros: conector de Facebook para Power BI Desktop

El conector de Facebook en Power BI Desktop se basa en la API de Facebook. Como tal, características y la disponibilidad pueden variar con el tiempo.

Puede ver un [tutorial acerca del conector de Facebook para Power BI Desktop](powerbi-desktop-tutorial-facebook-analytics.md).

Facebook caducado v1.0 de su API de Graph el 30 de abril de<sup>th</sup> 2015. Power BI usa la API Graph en segundo plano para el conector de Facebook, lo que le permite conectarse a los datos y analizarlos.

Las consultas que se crearon antes del 30 de abril<sup>th</sup> 2015 ya no se puede trabajar o devolver menos datos. Después del 30 de abril<sup>th</sup> 2015, Power BI aprovecha v2.2 en todas las llamadas a la API de Facebook. Si la consulta se creó antes del 30 de abril de 2015 y no ha utilizado desde, probablemente necesitará volver a autenticarse, para aprobar el nuevo conjunto de permisos que te preguntaremos.

Aunque intentamos publicar actualizaciones de acuerdo con los cambios, la API puede cambiar de manera que afecta a los resultados de las consultas que se genera. En algunos casos, ya no pueden admitirse determinadas consultas. Debido a esta dependencia no podemos garantizar los resultados de las consultas cuando se utiliza este conector.

Hay disponible más información sobre el cambio en la API de Facebook [aquí](https://developers.facebook.com/docs/apps/changelog#v2_0).

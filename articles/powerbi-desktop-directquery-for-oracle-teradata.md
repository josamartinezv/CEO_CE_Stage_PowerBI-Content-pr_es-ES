<properties
   pageTitle="DirectQuery para las bases de datos de Oracle y Teradata"
   description="DirectQuery para las bases de datos de Oracle y Teradata"
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

# DirectQuery para Oracle y bases de datos Teradata

Con Power BI Desktop puede conectarse a bases de datos Oracle y Teradata directamente mediante DirectQuery.

En esta versión, puede elegir conectarse a bases de datos Oracle o Teradata utilizando **importación** o **DirectQuery**:

-   Si se conecta mediante **DirectQuery**, se importan o copian en Power BI Desktop ningún dato. Crear o interactuar con una visualización, Power BI Desktop consulta el origen de datos subyacente para obtener los datos necesarios para responder a la interacción, lo que significa que siempre está viendo los datos actuales. Consulte [DirectQuery de uso en Power BI Desktop](powerbi-desktop-use-directquery.md) para obtener una descripción de DirectQuery.

-   Si se conecta con **importación**, importar datos a Power BI Desktop tras la conexión a la base de datos y la interacción con los datos se basa en lo que se importó.

DirectQuery para las bases de datos de Oracle y Teradata está disponible para Power BI Desktop y para el servicio Power BI.

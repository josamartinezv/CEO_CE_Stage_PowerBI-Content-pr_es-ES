<properties
   pageTitle="Datos activos de SQL Server Analysis Services en Power BI"
   description="Datos de SQL Server Analysis Services en directo en Power BI. Esto se realiza mediante un origen de datos que se ha configurado para una puerta de enlace de la empresa."
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
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="09/21/2016"
   ms.author="asaxton"/>
# Datos activos de SQL Server Analysis Services en Power BI

En Power BI, hay dos maneras de que conectarse a un servidor activo de SQL Server Analysis Services. En obtener datos, puede conectarse a un servidor SQL Server Analysis Services o puede conectarse a un [archivo de Power BI Desktop](powerbi-service-powerbi-desktop-files.md), o [libro de Excel](powerbi-service-excel-data.md), que ya está conectado a un servidor de Analysis Services. 

 ![](media/powerbi-sql-server-analysis-services-tabular-data/importantIcon.png) **Importante:**

-   Para conectarse a un servidor de Analysis Services en vivo, una puerta de enlace de datos local debe estar instalada y configurada por un administrador. Para obtener más información, consulte [puerta de enlace de datos local](powerbi-gateway-onprem.md).

-   Cuando se utiliza la puerta de enlace, los datos permanecen en local.  Los informes que cree se basan en que los datos se guardan en el servicio Power BI. 

-   
            [Preguntas y respuestas una consulta de lenguaje natural](powerbi-service-q-and-a-direct-query.md) está en vista previa para Analysis Services conexiones activas.

> [AZURE.NOTE] Trabajar con servicios de análisis en vivo, junto con grupos, los servidores son características de Pro. [Obtener más información](powerbi-power-bi-pro-content-what-is-it.md)

## Para conectarse a un modelo de datos de Get

1.  En **Mi área de trabajo**, seleccione **obtener datos**. También puede cambiar a un área de grupo, si está disponible.

    ![](media/powerbi-sql-server-analysis-services-tabular-data/ConnectToAS_GetDataButton.png)

2.  Seleccione **bases de datos y más**.

    ![](media/powerbi-sql-server-analysis-services-tabular-data/ConnectToAS_GetData_1.png)

3.  Seleccione **SQL Server Analysis Services** > **Conectar**. 

    ![](media/powerbi-sql-server-analysis-services-tabular-data/ConnectToAS_GetData_2.png)

4.  Seleccione un servidor. Si no ve los servidores enumerados aquí, significa que no se configuran una puerta de enlace y el origen de datos, o la cuenta no aparece en el **usuarios** ficha del origen de datos, en la puerta de enlace. Consulte con su administrador.

5.  Seleccione el modelo que desea conectarse. Esto podría ser Tabular o Multidimensional.

Después de conectarse al modelo, aparecerá en el sitio de Power BI de **Mi área de trabajo y conjuntos**. Si estaba swtiched al área de trabajo de un grupo, el conjunto de datos aparecerá dentro del grupo.

![](media/powerbi-sql-server-analysis-services-tabular-data/ConnectToAS_Dataset_5.png)

Si ancla objetos visuales de un informe en el panel, los iconos anclados se actualizan automáticamente cada 10 minutos. Si se actualizan los datos en el servidor de Analysis Services local, los mosaicos obtiene se actualiza automáticamente después de 10 minutos.

## Consulte también

[Puerta de enlace de datos local](powerbi-gateway-onprem.md)  
[Administrar orígenes de datos de Analysis Services](powerbi-gateway-enterprise-manage-ssas.md)  
[Solución de problemas de la puerta de enlace de datos local](powerbi-gateway-onprem-tshoot.md)  
¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
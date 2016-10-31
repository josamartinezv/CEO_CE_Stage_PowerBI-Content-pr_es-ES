<properties
   pageTitle="Elementos visuales KPI"
   description="crear KPI en power bi"
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   featuredVideoId="xmja6EpqaO0"
   qualityFocus="no"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/23/2016"
   ms.author="mihart"/>

# KPI en Power BI

Un indicador clave de rendimiento (KPI) es una indicación visual que comunica el incremento del progreso realizado hacia un objetivo cuantificable. Para obtener más información acerca de los KPI, vea [Microsoft Developer Network](https://msdn.microsoft.com/library/hh272050).

##  Cuándo usar un KPI
Los KPI son una excelente opción:

-   para medir el progreso (¿voy adelantado o retrasado?)

-   para medir la distancia a un objetivo (cómo adelanto o retraso am I?)   

##  Requisitos de visual de KPI
Un indicador clave de rendimiento (KPI) se basa en una medida específica y está diseñado para ayudarle a evaluar el valor actual y el estado de una métrica con respecto a un destino definido. Por lo tanto, se requiere un objeto visual KPI un *base* medida que se evalúa como un valor y un *destino* medida o de valor y un umbral u objetivo.

>[AZURE.NOTE] Actualmente, un conjunto de datos KPI debe contener valores de objetivo de un KPI. Esto puede hacerse mediante la adición de una hoja de excel con los objetivos para el modelo de datos o el archivo PBIX.

##  Cómo crear un KPI  

Para continuar, inicie sesión Power BI y seleccione **obtener datos > Muestras > ejemplo de análisis de venta**. Vamos a crear un KPI que mide el progreso que hemos hecho para lograr un objetivo de ventas.

O inspección le mostrará cómo crear elementos visuales de métrica únicos: medidores, tarjetas y KPI.
<iframe width="560" height="315" src="https://www.youtube.com/embed/xmja6EpqaO0?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1.  Seleccione **ventas > Total de unidades de este año**.  Se trata del indicador.

2.  Agregar **tiempo > mes**.  Esto se representará la tendencia.

2. Convertir el objeto visual a un KPI seleccionando el icono KPI en el panel de visualización.

    ![](media/powerbi-service-tutorial-kpi/kpi-icon.png)

3. Agregar un objetivo. Agregar ventas últimos años como objetivo. Arrastre **el año pasado unidades Total** a la **objetivos de destino** campo.

    ![](media/powerbi-service-tutorial-kpi/kpi-new.png)

4.  Opcionalmente, formato de KPI, seleccione el icono de pincel para abrir el panel de formato.

    -   
            **Indicador** -controla las unidades de visualización del indicador y decimales.

    -   
            **Eje de tendencia** -cuando se establece en **en**, se muestra el eje de tendencia como el fondo del objeto visual KPI.  

    -   
            **Objetivos** -cuando se establece en **en**, el objeto visual muestra el objetivo y la distancia desde el objetivo como un porcentaje.

    -   
            **Estado** : algunos KPI se consideran *mejor* para valores mayor y algunas se consideran *mejor* con valores más bajos. Por ejemplo, las ganancias VS. tiempo de espera. Normalmente un valor mayor de ingresos es mejor en comparación con un valor más alto de tiempo de espera, que normalmente se considera como algo peor. Esta opción permite la selección de un comportamiento KPI. El estado de la opción predeterminada es **alto es mejor**.

6.  Cuando tenga el KPI como desee, [Anclar a un panel](powerbi-service-pin-a-tile-to-a-dashboard-from-a-report.md).


KPI también están disponibles en los dispositivos móviles: mantiene su siempre conectados a su latido de empresas



##  Consulte también

[Informes de Power BI](powerbi-service-reports.md)

[Visualizaciones en informes de Power BI](powerbi-service-visualizations-for-reports.md)

[Power BI: conceptos básicos](powerbi-service-basic-concepts.md)

¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)

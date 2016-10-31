<properties
   pageTitle="Tutorial: Gráficos cascada en Power BI"
   description="Tutorial: Gráficos cascada en Power BI"
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   featuredVideoId="maTzOJSRB3g"
   qualityFocus="no"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="10/07/2016"
   ms.author="mihart"/>
# Tutorial: gráficos cascada en Power BI

Un gráfico en cascada muestra un total acumulativo conforme se agregan o se restan valores. Es útil para comprender cómo afecta un valor inicial (por ejemplo, los ingresos netos) a una serie de cambios positivos y negativos.

Las columnas están codificados de forma que puede saber rápidamente aumenta y disminuye con colores. La inicial y las columnas de valor final a menudo [Iniciar en el eje horizontal](https://support.office.com/article/Create-a-waterfall-chart-in-Office-2016-for-Windows-8de1ece4-ff21-4d37-acd7-546f5527f185#BKMK_Float "Iniciar en el eje horizontal"), mientras que los valores intermedios flotante columnas. Debido a esta "búsqueda", gráficos de cascada también se denominan gráficos de puente.

<iframe width="560" height="315" src="https://www.youtube.com/embed/maTzOJSRB3g?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## Cuándo usar un gráfico en cascada

Gráficos de cascada son una excelente opción:

-   Cuando haya cambios para la medida entre las distintas categorías o de series temporales

-   Para auditar los cambios más importantes que contribuyen al valor total

-   para trazar beneficio anual de su compañía, mostrando varias fuentes de ingresos y llegar a la ganancia total (o pérdida).

-   Para ilustrar el principio y final del número de empleados de su empresa en un año

-   para visualizar la cantidad de dinero realiza y pasar cada mes y el saldo de ejecución de su cuenta. 

## Crear un gráfico en cascada

Para continuar, inicie sesión Power BI y seleccione **obtener datos \> ejemplos \> ejemplo de análisis de venta**. 

1. En el panel "Ejemplo de análisis de venta", seleccione la **Total almacenes** icono para abrir el informe "Ejemplo de análisis de venta directa".

2. Seleccione **Editar informe** para abrir el informe en la vista de edición.

3. 
            [Agregar una nueva página de informe](powerbi-service-add-a-page-to-a-report.md).

4. Crear un gráfico en cascada que muestra el objetivo de este año de ventas y ventas por mes.

  - Desde el **campos** panel, seleccione **ventas \> Total de ventas de varianza**.

    - Convertir el gráfico a un **cascada**. 

        ![](media/powerbi-service-tutorial-waterfall-charts/convertWaterfall.png)

    - Si **Total de ventas de varianza** no está en el **eje Y** área, lo arrastra.

    - Seleccione **tiempo** \> **FiscalMonth** para agregarlo a la **categoría** bien. 

    ![](media/powerbi-service-tutorial-waterfall-charts/first_new.png)

## Resaltado y filtrado cruzado

Para obtener información acerca de cómo utilizar el panel de filtros, consulte [Agregar un filtro a un informe](powerbi-service-add-a-filter-to-a-report.md).

Filtros en resaltando una columna en un gráfico en cascada entre las otras visualizaciones en la página de informe... y viceversa. Sin embargo, la columna Total desencadenar resaltado o responder a filtro cruzado.

## Consulte también

[Informes de Power BI](powerbi-service-reports.md)

[Tipos de visualización en Power BI](powerbi-service-visualization-types-for-reports-and-q-and-a.md)

[Visualizaciones en informes de Power BI](powerbi-service-visualizations-for-reports.md)

[Power BI: conceptos básicos](powerbi-service-basic-concepts.md)

¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)

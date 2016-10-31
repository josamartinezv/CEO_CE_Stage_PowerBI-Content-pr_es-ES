<properties
   pageTitle="Cambiar cómo interactúan los objetos visuales en un informe"
   description="Documentación sobre cómo establecer las interacciones Visual en un informe de Microsoft Power BI."
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   featuredVideoId="N_xYsCbyHPw"
   qualityFocus="no"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/25/2016"
   ms.author="mihart"/>

# Interacciones de visualización en un informe de Power BI

De forma predeterminada, visualizaciones en una página de informe pueden utilizarse para filtro cruzado y resaltan las otras visualizaciones en la página.
Por ejemplo, la selección de un estado de visualización de mapa resalta el gráfico de columnas y filtra el gráfico de líneas para mostrar sólo los datos que se aplica a ese estado de una.
Consulte [acerca del filtrado y resaltado](powerbi-service-about-filters-and-highlighting-in-reports.md).

Para cambiar este comportamiento predeterminado, utilice el **elementos visuales interacción** control.

>[AZURE.NOTE] Los términos *filtro entre* y *resaltan* se utilizan para distinguir el comportamiento descrito aquí de lo que sucede cuando se utiliza el **filtros** panel para filtrar y resaltar visualizaciones.  

<iframe width="560" height="315" src="https://www.youtube.com/embed/N_xYsCbyHPw?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1.  Seleccionar una visualización para activarlo.  

2. Activar **interacciones Visual** seleccionándola en la barra de menús superior. Observe que el filtro y resaltar los iconos que aparecen encima de las otras visualizaciones en la página del informe.

    ![](media/powerbi-service-visual-interactions/pbi-visual-interaction-icon.png)

2.  Determinar el impacto que tendrá la visualización seleccionada en las otras.  

    -   Si debe filtro cruzado la otra visualización, seleccione la **filtro** icono ![](media/powerbi-service-visual-interactions/pbi-filter-icon-outlined.png).

    -   Si debe realzado transversal de visualización, seleccione la **resaltar** icono ![](media/powerbi-service-visual-interactions/pbi-highlight-icon-outlined.png).

    -   Seleccione si debería tener ningún impacto, la **ningún impacto** icono ![](media/powerbi-service-visual-interactions/pbi-noimpact-icon-outlined.png).

3.  Repita para todas las otras visualizaciones en la página del informe.

## Consulte también

 [Cómo usar filtros de informe](powerbi-service-how-to-use-a-report-filter.md)

[Filtros y resaltado en informes](powerbi-service-about-filters-and-highlighting-in-reports.md)

[Power BI: conceptos básicos](powerbi-service-basic-concepts.md)

¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)

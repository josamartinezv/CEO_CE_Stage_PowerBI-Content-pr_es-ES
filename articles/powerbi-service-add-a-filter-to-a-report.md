<properties
   pageTitle="Agregar un filtro a un informe en Power BI"
   description="Agregar un filtro a un informe en Power BI"
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="monitoring"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/21/2016"
   ms.author="mihart"/>

# Agregar un filtro a un informe de Power BI (en la vista de edición)

>
            **SUGERENCIA**: se recomienda leer primero [sobre los filtros y resaltado en informes de Power BI](powerbi-service-about-filters-and-highlighting-in-reports.md).


##  ¿Cuál es la diferencia entre los filtros de informe en la vista de edición frente a la vista de lectura

Existen dos modos para interactuar con los informes: [vista lectura](powerbi-service-interact-with-a-report-in-reading-view.md) y [vista de edición de](powerbi-service-interact-with-a-report-in-editing-view.md).  Y las capacidades de filtrado disponibles dependen de qué modo se encuentra en.

-   En la vista de edición, puede agregar informes, página y filtros visuales. Al guardar el informe, los filtros se guardan con él. Examinando el informe en la vista de lectura puedan interactuar con los filtros que ha agregado, pero no guardar sus cambios.

-   En la vista de lectura, puede interactuar con cualquier página y filtros visuales que ya existen en el informe, pero no podrá guardar los cambios del filtro.


            **NOTA:**  este artículo describe cómo crear filtros de informe **vista de edición de**.  Para obtener más información acerca de los filtros en la vista de lectura, consulte [interactuar con los filtros en la vista de lectura informe](powerbi-service-interact-with-a-report-in-reading-view.md).

##  Filtros visuales, página filtros y filtros de informe
Un **filtro de página** se aplica a todos los elementos visuales en la página del informe. Un **filtro visual** se aplica a un único objeto visual en una página del informe. Y un **filtro de informe** se aplica a todas las páginas del informe.

![](media/powerbi-service-add-a-filter-to-a-report/power-bi-add-filter-reading-view.png)

## Agregar un filtro a una visualización específica (también conocido como filtro visual)

### Mediante el filtrado de los campos en el gráfico

1.  Abra su [informes en la vista de edición de](powerbi-service-go-from-reading-view-to-editing-view.md).

2.  Abra el panel de visualizaciones y los filtros y el panel de campos (si no está ya abiertos).

3.  Seleccione un elemento visual para activarlo. Todos los campos que se utiliza el objeto visual se identifican en la **campos** panel y también aparece en el **filtros** panel, en el **filtros de nivel Visual** encabezado.

4.  Seleccione el campo que desea agregar como un nuevo filtro de nivel visual y arrástrelo al área de filtros de nivel Visual.  Establecer **básica** o **avanzadas** controles de filtrado (consulte [cómo usar filtros de informe](powerbi-service-how-to-use-a-report-filter.md)).

    ![](media/powerbi-service-add-a-filter-to-a-report/vizFilter.png)

El visual cambia para reflejar el nuevo filtro. Si guarda el informe con el filtro, los lectores de informes pueden interactuar con el filtro en la vista de lectura, activando o desactivando valores.

## Agregar un filtro a una página completa (también conocido como filtro de vista de página)

1.  Abra su [informes en la vista de edición de](powerbi-service-go-from-reading-view-to-editing-view.md).

2.  Abra el panel de visualizaciones y los filtros y el panel de campos (si no está ya abiertos).

3.  Seleccione un campo en la lista de campos en el informe y arrástrelo por debajo **filtros de nivel de página**.

4.  Seleccione los valores que desea filtrar y establecer  **básica** o **avanzadas** controles de filtrado (consulte [cómo usar filtros de informe](powerbi-service-how-to-use-a-report-filter.md)).

    Los cambios de visualización para reflejar el nuevo filtro. 

    ![](media/powerbi-service-add-a-filter-to-a-report/filterPage.gif)

Si guarda el informe con el filtro, los lectores de informes pueden interactuar con el filtro en la vista de lectura, activando o desactivando valores.

## Agregar un filtro a un informe completo (también conocido como filtro de informe)

1. Abra su [informes en la vista de edición de](powerbi-service-go-from-reading-view-to-editing-view.md).

2. Abra el panel de visualizaciones y los filtros y el panel de campos (si no está ya abiertos).

3. Seleccione un campo en la lista de campos y arrástrelo por debajo **filtros de nivel de informe**.

4. Seleccione los valores que desea filtrar (vea [cómo usar filtros de informe](powerbi-service-how-to-use-a-report-filter.md)).

Los elementos visuales en la página activa y en todas las páginas del informe cambia para reflejar el nuevo filtro. Si guarda el informe con el filtro, los lectores de informes pueden interactuar con el filtro en la vista de lectura, activando o desactivando valores.

##  Solucionar problemas

### ¿Por qué el filtro nivel visual a un filtro y la página de nivel puede devolver resultados diferentes

Al agregar un filtro de nivel visual, Power BI filtros en los resultados agregados.  La agregación predeterminada es la suma, pero puede [cambiar el tipo de agregación](powerbi-service-aggregates.md).  

Al agregar un filtro de nivel de página, filtros de Power BI sin agregación.  Esto consigue porque una página puede tener muchos elementos visuales que pueden utilizar los tipos de agregación diferente cada uno.  Por lo que el filtro se aplica en cada fila de datos.


## Consulte también

 [Cómo usar filtros de informe](powerbi-service-how-to-use-a-report-filter.md)

  [Filtros y resaltado en informes](powerbi-service-about-filters-and-highlighting-in-reports.md)

[Interactuar con los filtros y resaltado en la vista de lectura de informe](powerbi-service-interact-with-a-report-in-reading-view.md)

[Cambiar elementos visuales de informe filtro cruzado y resaltan entre sí](powerbi-service-visual-interactions.md)

Obtenga más información sobre [informes de Power BI](powerbi-service-reports.md)

[Power BI: conceptos básicos](powerbi-service-basic-concepts.md)

¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)

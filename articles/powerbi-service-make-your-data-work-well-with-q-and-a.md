<properties
   pageTitle="Hacer que los datos funcionen bien con preguntas y respuestas en Power BI"
   description="Hacer que los datos funcionen bien con preguntas y respuestas en Power BI"
   services="powerbi"
   documentationCenter=""
   authors="mihart"
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
   ms.date="10/05/2016"
   ms.author="mihart"/>

# Hacer que los datos funcionen bien con preguntas y respuestas en Power BI  

Si eres una persona que crea modelos de datos o compilaciones de libros de Excel que se utilizará con Power BI, siga leyendo...

En Power BI, preguntas y respuestas pueden buscar datos estructurados y elegir la visualización correcta para la pregunta, que es lo que hace una herramienta atractiva.   

Preguntas y respuestas pueden trabajar en cualquier Excel archivo cargado que contiene tablas, rangos, o un modelo de PowerPivot, pero las optimizaciones más y lo hace, la limpieza de datos el más sólido Q & es de un rendimiento. 

## Funcionamiento de preguntas y respuestas  
Preguntas y respuestas tiene un conjunto de capacidades de descripción de lenguaje natural de núcleo que funcionan en los datos. Tiene la búsqueda de palabra clave dependiente del contexto para la tabla, columna y nombres de los campos calculados de Excel. En segundo lugar, tiene conocimiento integrado acerca de cómo filtrar, ordenar, agregado, grupo y mostrar datos. 

Por ejemplo, en una tabla de Excel denominada "Ventas", con las columnas "Product", "Mes", "Unidades vendidas", "Ventas brutas" y "Beneficios", se podría preguntar sobre cualquiera de esas entidades.  Puede solicitar mostrar las ventas, total de beneficios por mes, los productos están ordenados por unidades vendidas y muchos otros. Obtenga más información sobre la [tipos de preguntas que pueden](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-1.aspx), y [preguntas con una plantilla de pregunta](powerbi-service-q-and-a.md) y [tipos de visualización puede especificar en una consulta de preguntas y respuestas](powerbi-service-visualization-types-for-reports-and-q-and-a.md).

## Preparar un libro para preguntas y respuestas  
Preguntas y respuestas se basa en los nombres de tablas, columnas, y campos calculados para responder a preguntas específicas de datos, lo que significa que lo que se llama a las entidades en el libro es importante!

Estas son algunas sugerencias para realizar la mayoría de las preguntas y respuestas en el libro.

-   Asegúrese de que los datos están en una tabla de Excel. Aquí es [cómo crear una tabla de Excel](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-e81aa349-b006-4f8a-9806-5af9df0ac664?ui=en-US&rs=en-US&ad=US).

-   Asegúrese de que los nombres de sus tablas, columnas y campos calculados tienen sentido en inglés.

    Por ejemplo, si tiene una tabla con datos de ventas, llame a la tabla "Ventas". Nombres de columna como "Year", "Producto", "Representante de ventas" y "Cantidad" funcionarán bien con preguntas y respuestas.

>[AZURE.NOTE]  Si el libro tiene un modelo de datos de PowerPivot, puede hacer incluso más optimizaciones. Obtenga más información sobre [Desmitificación de Power BI Q & A parte 2](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-2.aspx) de nuestro equipo interno de expertos en lenguaje natural.

## Consulte también  
[Preguntas y respuestas en Power BI](powerbi-service-q-and-a.md)  
[Tutorial: Introducción a Power BI Q & A](powerbi-service-tutorial-introduction-to-q-and-a.md)  
[Obtener datos (Power BI)](powerbi-service-get-data.md)  
[Power BI: conceptos básicos](powerbi-service-basic-concepts.md)

¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)

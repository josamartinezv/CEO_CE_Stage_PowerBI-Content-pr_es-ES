<properties
   pageTitle="Tutorial: Introducción a Power BI Q & A"
   description="Tutorial: Introducción a Power BI Q & A con el ejemplo de análisis de venta directa"
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
   ms.date="10/05/2016"
   ms.author="mihart"/>
# Tutorial: usar Power BI Q & A con el ejemplo de análisis de venta directa

A veces, la forma más rápida de obtener una respuesta de los datos es formular una pregunta con lenguaje natural.  En este tutorial analizaremos 2 distintas formas de crear la misma visualización: creación de un informe y formular una pregunta con preguntas y respuestas.  

## Método 1: usar el editor de informes
1. En el área de trabajo de Power BI, seleccione **obtener datos** \> **ejemplos** \> **ejemplo de análisis de venta directa** > **Conectar**.

    ![](media/powerbi-service-tutorial-introduction-to-q-and-a/gnaTutorial_1.png)

2. El panel contiene un título de gráfico de área para "Ventas del último año y las ventas de este año."  Seleccione este icono. 

    -   Si este icono se creó con preguntas y respuestas, seleccione el icono abrirá preguntas y respuestas. 

    -   Pero este icono se creó en un informe, por lo que el informe se abre en la página que contiene esta visualización.

3. Abra el informe en la vista de edición seleccionando **Editar informe**.

    ![](media/powerbi-service-tutorial-introduction-to-q-and-a/gnaTutorial_2.png)

4. Seleccione el gráfico de áreas y revise la configuración de la **campos** panel.  El creador del informe genera este gráfico seleccionando estos 3 valores (**tiempo > FiscalMonth**, **ventas > Ventas de este año**, **ventas > ventas del último año > valor**) y organizarlos en el **eje** y **valores** wells.

    ![](media/powerbi-service-tutorial-introduction-to-q-and-a/gnaTutorial_3.png)

## Método 2: uso de preguntas y respuestas
¿Cómo podría hacer acerca de cómo crear este mismo gráfico de líneas con preguntas y respuestas?
    ![](media/powerbi-service-tutorial-introduction-to-q-and-a/power-bi-questionbox.png)

1.  Desplácese atrás a la está el panel de ejemplo de análisis de venta directa.

2.  Con lenguaje natural, escriba algo parecido a esto en el cuadro de pregunta:

    **¿Cuáles fueron las ventas de este año y el año pasado por mes como gráfico de áreas**

    A medida que escribe su pregunta, preguntas y selecciona la mejor visualización para mostrar la respuesta; y la visualización cambia dinámicamente a medida que modifica la pregunta. Además, preguntas y respuestas le ayuda a dar formato a su pregunta con sugerencias, Autocompletar y las correcciones ortográficas.

    Cuando termine de escribir la pregunta, el resultado es el mismo gráfico que hemos visto en el informe.  Pero la creación de esta manera era mucho más rápida!

    ![](media/powerbi-service-tutorial-introduction-to-q-and-a/powerbi-qna-areachart.png)

4. Es similar a trabajar con informes, dentro de preguntas y respuestas tendrá acceso a los paneles de visualizaciones, filtros y campos.  Abrir estos paneles para explorar aún más y modificar el objeto visual.

3.  Para anclar el gráfico al panel, seleccione el icono de pin ![](media/powerbi-service-tutorial-introduction-to-q-and-a/pinNoOutline.png).

## Consulte también

[¿Qué tipo de preguntas que pueda hacer preguntas y respuestas?](powerbi-service-q-and-a.md)

[Preguntas y respuestas en Power BI](powerbi-service-q-and-a.md)

[Hacer que los datos funcionen bien con preguntas y respuestas en Power BI](powerbi-service-make-your-data-work-well-with-q-and-a.md)

[preparar un libro para preguntas y respuestas](powerbi-service-make-your-data-work-well-with-q-and-a.md)

¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)

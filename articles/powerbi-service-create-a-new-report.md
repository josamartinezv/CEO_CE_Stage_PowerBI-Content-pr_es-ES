<properties
   pageTitle="Crear un nuevo informe de Power BI"
   description="Crear un nuevo informe de Power BI"
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
# Crear un nuevo informe de Power BI

Hay muchas maneras diferentes de crear un nuevo informe. Este tema muestra dos de ellos.

-   Un conjunto de datos

-   Desde un informe existente

## Crear un informe desde un conjunto de datos

Este método crea un nuevo informe desde cero. Para continuar, [descargar el ejemplo de análisis de venta](powerbi-sample-downloads.md).

1.  Iniciar servicio Power BI y seleccione un conjunto de datos para abrirla. Abrir un conjunto de datos realmente abre el editor de informes.  Verá un lienzo en blanco y el informe de herramientas de edición.

    ![](media/powerbi-service-create-a-new-report/powerbi-select-datasetnew.png)

2.  Explorar los datos y [Agregar efectos visuales](powerbi-service-visualizations-for-reports.md). Para este informe, vamos a agregar un medidor elemento visual que realiza un seguimiento de las ventas de este año.

   -  En la **campos** panel, seleccione **ventas** > **ventas de este año** > valor.

        ![](media/powerbi-service-create-a-new-report/powerbi-report-step1.png)

   -  Convertir el objeto visual en un medidor seleccionando la plantilla medidor ![](media/powerbi-service-create-a-new-report/powerbi-gauge-icon.png) desde el **visualizaciones** panel.

        ![](media/powerbi-service-create-a-new-report/powerbi-report-step2.png)

   -  Arrastre **ventas** > **ventas de este año** > **objetivo** a la **valor de destino** bien.

        ![](media/powerbi-service-create-a-new-report/powerbi-report-step3.png)

3.  Opcionalmente, continúe agregando elementos visuales y luego [guardar su informe](powerbi-service-save-a-report.md).

    ![](media/powerbi-service-create-a-new-report/powerbi-save.png)


## Crear un nuevo informe desde un informe existente
Quizá tenga un informe que ya se conecta al conjunto de datos y tiene algunos efectos visuales que le gustaría volver a utilizar o modificar.  ¿Por qué no simplemente copiar ese informe como base para un nuevo informe?  Siga estos pasos:

1.  
            [Abrir un informe](powerbi-service-open-a-report-in-reading-view.md).

2.  Desde el **archivo** menú, seleccione **Guardar como**.

    ![](media/powerbi-service-create-a-new-report/powerbi-save-as.png)

3.  Escriba un nombre para el nuevo informe y seleccione **Guardar**.

    ![](media/powerbi-service-create-a-new-report/SaveReport.png)

    Un mensaje de confirmación le permite saber que se guardó el nuevo informe en Power BI.

    ![](media/powerbi-service-create-a-new-report/saveSuccess1.png)

4.  En el panel de navegación de Power BI, seleccione el nuevo informe para abrirlo. Opcionalmente, eliminar elementos visuales que no desea mantener, modificar otros elementos visuales y agregar nuevos.

    ![](media/powerbi-service-create-a-new-report/newReportNavPane.png)

5.  Diviértase actualizar y editar el nuevo informe.


## Pasos siguientes:

[Crear nuevas visualizaciones](powerbi-service-add-visualizations-to-a-report-ii.md)


            [Eliminar las visualizaciones](powerbi-service-delete-a-visualization.md) no es necesario

## Consulte también

Obtenga más información sobre [informes de Power BI](powerbi-service-reports.md)

[Introducción a Power BI](powerbi-service-get-started.md)

[Power BI: conceptos básicos](powerbi-service-basic-concepts.md)

¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)

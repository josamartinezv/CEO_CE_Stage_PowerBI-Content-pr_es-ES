<properties
   pageTitle="Anclar un mosaico a un panel de Power BI desde Excel"
   description="Anclar un mosaico a un panel de Power BI de Excel en OneDrive para la empresa. Intervalos de PIN, gráficos, tablas"
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   featuredVideoId="l8JoB7w0zJA"
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

# Anclar un mosaico a un panel de Power BI desde Excel

Inspección muestra varias maneras de importar los datos y conectarse a libros de Excel. A continuación, siga las instrucciones detalladas a continuación el vídeo para probarlo usted mismo.

<iframe width="560" height="315" src="https://www.youtube.com/embed/l8JoB7w0zJA" frameborder="0" allowfullscreen></iframe>

>[AZURE.NOTE]  Puede ver, pero no anclar, mosaicos de los libros que se han compartido con usted.

## Conectar su libro de Excel desde OneDrive para la empresa con Power BI

1.  Cargar un libro en su OneDrive para la empresa.

2. Desde Power BI, [conectarse a ese libro](powerbi-bring-in-whole-excel-files.md).

3.  En Power BI, el libro se muestra en el panel de navegación izquierdo bajo **informes**. El ![](media/powerbi-service-pin-a-tile-to-a-dashboard-from-excel/PBI_workbookIcon.png) icono indica se trata de un libro de Excel y el asterisco amarillo indica que es nuevo.

    ![](media/powerbi-service-pin-a-tile-to-a-dashboard-from-excel/PBI_pinnedFromExcel.png)

4.  Abra el libro en Power BI seleccionando el nombre del informe.

>[AZURE.NOTE]  Cambios realizados en el libro en Power BI no se guardan y no afectan el libro original en OneDrive para la empresa. Si ordenar, filtrar o cambiar los valores en Power BI, esos cambios no se guarden o anclados. Para actualizar el libro, ábralo en Excel Online seleccionando el botón de puntos suspensivos y **Editar**. Cambios en el libro pueden tardar unos minutos en actualizarse en los mosaicos.     


## Anclar un intervalo a un panel
Una manera de agregar un nuevo [icono Panel de](powerbi-service-dashboard-tiles.md) en un libro de Excel. Rangos se pueden anclar los libros de Excel que se han guardado en su OneDrive para la empresa u otra biblioteca de documentos compartidos de grupo. Los intervalos pueden contener datos, gráficos, tablas, tablas dinámicas, gráficos dinámicos y otras partes de Excel.

1. Resalte las celdas que desea anclar a un panel.

    ![](media/powerbi-service-pin-a-tile-to-a-dashboard-from-excel/PBI_selectRange.png)

2.  Seleccione el pin ![](media/powerbi-service-pin-a-tile-to-a-dashboard-from-a-report/PBI_PinTile_Small.png) icono. 

3.  Anclar el mosaico a un panel existente o a un nuevo panel. 

    -   Panel existente: seleccione el nombre del panel en la lista desplegable.

    -   Nuevo panel: escriba el nombre del nuevo panel.

    ![](media/powerbi-service-pin-a-tile-to-a-dashboard-from-excel/PBI_dashDialog1.png)

3.  Seleccione **Pin**.

    Un mensaje de confirmación (cerca de la esquina superior derecha) le permite saber que se ha agregado el intervalo, como un icono al escritorio.

    ![](media/powerbi-service-pin-a-tile-to-a-dashboard-from-excel/PBI_pinnedToDash1.png)

4.  En el panel de navegación, seleccione el panel con el nuevo icono. Allí, puede [cambiar el nombre, tamaño, vincular y mover](powerbi-service-edit-a-tile-in-a-dashboard.md) la visualización anclada.

## Anclar un gráfico completo dinámicas o de la tabla a un panel

1.  Para anclar una tabla o una tabla dinámica, seleccione todo el rango de la tabla.

  - Para las tablas, asegúrese de incluir los encabezados.

  - Para las tablas dinámicas, asegúrese de incluir todas las partes visibles de la tabla dinámica, incluidos los filtros si utiliza.

    ![](media/powerbi-service-pin-a-tile-to-a-dashboard-from-excel/PBI_selectTable.png)

2. Siga los pasos 2 a 4 anteriores.

>[AZURE.NOTE] Un icono creado a partir de una tabla o una tabla dinámica mostrará toda la tabla.  Si Agregar/quitar/filtrar filas o columnas del libro original, que se podrán agregar/quitar/filtrados en el icono.

## Ver el libro vinculado en el mosaico

Al hacer clic en un icono de libro, se abre el libro vinculado. Puesto que se encuentra el archivo de libro en OneDrive del propietario para la empresa, ver el libro requiere que tenga permisos de lectura para el libro. Si no tiene permiso para ver el archivo, recibirá un mensaje de error. Para obtener más información, consulte [panel en mosaico en Power BI](powerbi-service-dashboard-tiles.md)

>[AZURE.NOTE] Características no admitidas: Power BI utiliza Excel Services para recuperar los iconos de libro. Por lo tanto, puesto que no se admiten algunas características de escritorio de Excel en la API de REST de servicios de Excel, no se verán en mosaicos en Power BI. Por ejemplo: conjunto de iconos de minigráficos, condicional formato, segmentaciones de datos de tiempo. Para obtener una lista completa de características no admitidas, consulte [características no admitidas en la API de REST de servicios de Excel](http://msdn.microsoft.com/library/office/ff394477.aspx)


## Consulte también

[Compartir un panel que contiene vínculos a un libro de Excel](powerbi-service-share-dashboard-that-links-to-excel.md)

[Genere archivos completos de Excel en Power BI](powerbi-bring-in-whole-excel-files.md)

[Informes de Power BI](powerbi-service-reports.md)

[Vista previa de Power BI: conceptos básicos](powerbi-service-basic-concepts.md)

[Paneles de vista previa de Power BI](powerbi-service-dashboards.md)

¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)

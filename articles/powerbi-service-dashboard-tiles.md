<properties
   pageTitle="Iconos de panel en Power BI"
   description="Todo acerca de los iconos de panel en Power BI. Esto incluye iconos que se crean desde SQL Server Reporting Services (SSRS)."
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="monitoring"
   qualityDate="03/15/2016"/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="10/24/2016"  
   ms.author="mihart"/>

# <a name="dashboard-tiles-in-power-bi"></a>Iconos de panel en Power BI
## <a name="dashboard-tiles"></a>Iconos de panel

Un mosaico es una instantánea de los datos, anclados al panel. Puede crearse un mosaico de un informe, conjunto de datos, panel de las preguntas y respuestas, un cuadro de Excel y de SQL Server Reporting Services (SSRS) y mucho más.  Captura de pantalla siguiente muestra muchos iconos diferentes anclados a un panel.

Además de anclaje, mosaicos independiente pueden crearse directamente en el panel utilizando [Agregar mosaico](powerbi-service-add-a-widget-to-a-dashboard.md). Incluyen iconos independiente: cuadros de texto, imágenes, vídeos y contenido web.

![](media/powerbi-service-dashboard-tiles/PBI_DashFull_new.png)

¿Necesita ayuda para comprender los bloques de creación que conforman Power BI?  Consulte [BI: conceptos básicos de energía](powerbi-service-basic-concepts.md).

>[AZURE.NOTE] Si la visualización original utilizado para crear los cambios de mosaico, no cambia el mosaico.  Por ejemplo, si agregó un gráfico de líneas de un informe y, a continuación, cambiar el gráfico de líneas a un gráfico de barras, el icono Panel de sigue mostrando un gráfico de líneas. Las actualizaciones de los datos, pero la visualización no es de tipo.


## <a name="pin-a-tile-from..."></a>Anclar un mosaico de...

Pueden anclar mosaicos desde:

-   
            [Power BI Q & A](powerbi-service-pin-a-tile-to-a-dashboard-from-the-question-box.md)

-   
            [un informe](powerbi-service-pin-a-tile-to-a-dashboard-from-a-report.md)

-   
            [otro panel](powerbi-pin-a-tile-from-one-dashboard-to-another.md)

- 
            [Libro de Excel en OneDrive para la empresa](powerbi-service-pin-a-tile-to-a-dashboard-from-excel.md)

- 
            [Publicador de Power BI para Excel](powerbi-publisher-for-excel.md)


- 
            [Información rápida](powerbi-service-auto-insights.md)

-   
            [SSRS](https://msdn.microsoft.com/library/mt604784.aspx)

Independiente de mosaicos de imágenes, cuadros de texto, vídeos y contenido web se puede crear directamente en el panel utilizando [Agregar mosaico](powerbi-service-add-a-widget-to-a-dashboard.md).

  ![](media/powerbi-service-dashboard-tiles/add_widgetnew.png)


## <a name="interacting-with-tiles-on-a-dashboard"></a>Interactuar con mosaicos en un panel

### <a name="move-and-resize-a-tile"></a>Mover y cambiar el tamaño de un mosaico

Tomar un mosaico y [moverse en el panel](powerbi-service-edit-a-tile-in-a-dashboard.md). Mantenga el mouse y seleccione el identificador de ![](media/powerbi-service-dashboard-tiles/resize-handle.jpg) para cambiar el tamaño del mosaico.

### <a name="hover-over-a-tile-to-change-the-appearance-and-behavior"></a>Mantenga el mouse sobre un icono para cambiar la apariencia y comportamiento


1. Mantenga el mouse sobre el icono para mostrar el botón de puntos suspensivos.

    ![](media/powerbi-service-dashboard-tiles/ellipses_new.png)
2. Seleccione el botón de puntos suspensivos para abrir el menú de acción de mosaico.

    ![](media/powerbi-service-dashboard-tiles/tile-menu.png)

    Desde aquí puede:

  - 
            [Editar el título y el subtítulo, agregar un hipervínculo, mostrar la hora última actualización](powerbi-service-edit-a-tile-in-a-dashboard.md) ![](media/powerbi-service-dashboard-tiles/pencil-icon.jpg)
  - 
            [Exportar los datos utilizados en el mosaico](powerbi-service-edit-a-tile-in-a-dashboard.md)![](media/powerbi-service-dashboard-tiles/export-icon.png)

  - 
            [Vista en modo de enfoque](powerbi-service-display-dash-in-focus-mode.md) ![](media/powerbi-service-dashboard-tiles/fullscreen-icon.jpg)

  - 
             [Anclar el mosaico a otro panel](powerbi-pin-a-tile-from-one-dashboard-to-another.md)
![](media/powerbi-service-dashboard-tiles/pin-icon.jpg)

  - 
             [Quitar el mosaico](powerbi-service-edit-a-tile-in-a-dashboard.md)
![](media/powerbi-service-dashboard-tiles/trash-icon.png)

3. Para cerrar el menú Acción, seleccione el icono X ![](media/powerbi-service-dashboard-tiles/delete-icon.jpg).

### <a name="select-(click)-a-tile"></a>Seleccione (haga clic en) un mosaico
Cuando se selecciona un mosaico, ¿qué sucede después depende de cómo se creó el mosaico y si tiene una [vínculo personalizado](powerbi-service-edit-a-tile-in-a-dashboard.md). Si tiene un vínculo personalizado, seleccione el icono le lleva a ese vínculo. En caso contrario, al seleccionar el mosaico pasa al informe, el libro de Excel en línea, informe de SSRS es local o pregunta de preguntas y respuestas que se usó para crear el mosaico.

>[AZURE.NOTE] La excepción a esto es mosaicos de vídeo creados directamente en el panel utilizando **Agregar mosaico**. Si se selecciona un icono de vídeo (que se creó este modo), el vídeo se reproduzca aquí en el panel.   


## <a name="tips-and-troubleshooting"></a>Sugerencias y solución de problemas  

- Si no se ha guardado el informe que se usó para crear la visualización, a continuación, seleccione el icono no produce ninguna acción.

- Si se creó el icono de un libro en Excel en línea, y no tiene al menos permisos de lectura para ese libro, seleccione el icono no se abrirá el libro en Excel Online.

- En los mosaicos que se crean directamente en el panel utilizando **Agregar mosaico**, si se ha establecido un hipervínculo personalizado, seleccione el título, subtítulo y o mosaico abrirá esa dirección URL.  De lo contrario, de forma predeterminada, al seleccionar uno de estos iconos que se crean directamente en el panel de una imagen, código web o cuadro de texto no produce ninguna acción.

- Si no tiene permiso para el informe de SSRS, seleccionando un mosaico creado desde SSRS producen una página que indica que no tiene acceso (rsAccessDenied).

- Si no tiene acceso a la red donde se encuentra el servidor de SSRS, seleccionar un icono creado a partir de SSRS producto una página que indicará no se buscará el servidor (HTTP 404). El dispositivo debe tener acceso a la red al servidor de informes para ver el informe.

- Si la visualización original utilizado para crear los cambios de mosaico, no cambia el mosaico.  Por ejemplo, si agregó un gráfico de líneas de un informe y, a continuación, cambiar el gráfico de líneas a un gráfico de barras, el icono Panel de sigue mostrando un gráfico de líneas. Las actualizaciones de los datos, pero la visualización no es de tipo.

## <a name="see-also"></a>Consulte también  

            [Crear un icono de número grande de un informe](powerbi-service-create-a-big-number-tile-from-a-power-bi-report.md)


            [Crear un mosaico gran número de preguntas y respuestas](powerbi-service-create-a-big-number-tile-for-a-dashboard.md)


            [Paneles de Power BI](powerbi-service-dashboards.md)  

            [Actualización de datos](powerbi-refresh-data.md)


            [Power BI: conceptos básicos](powerbi-service-basic-concepts.md)


            [Exportar un mosaico a PowerPoint](http://blogs.msdn.com/b/powerbidev/archive/2015/09/28/integrating-power-bi-tiles-into-office-documents.aspx)


            [PIN elementos de Reporting Services para paneles de Power BI](https://msdn.microsoft.com/library/mt604784.aspx)

¿Preguntas más frecuentes? 
            [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)

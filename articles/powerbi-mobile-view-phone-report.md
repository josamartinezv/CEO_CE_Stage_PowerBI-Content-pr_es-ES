<properties 
   pageTitle="Ver e interactuar con informes de Power BI optimizados para el teléfono"
   description="Lea sobre la interacción con páginas de informe que se optimizan para visualizarse en las aplicaciones de teléfono de Power BI."
   services="powerbi" 
   documentationCenter="" 
   authors="maggiesMSFT" 
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
   ms.date="09/27/2016"
   ms.author="maggies"/>

# Ver e interactuar con informes de Power BI optimizados para el teléfono 

Al crear un informe de Power BI en Power BI Desktop, también puede crear una versión de dicho [informe optimizada para verlas en la aplicación de Power BI en un teléfono](powerbi-desktop-create-phone-report.md).

A continuación, cuando se abre un informe de Power BI en un teléfono, Power BI detecta automáticamente si el informe se ha optimizado para teléfonos. Si existe un informe optimizado por teléfono, la aplicación de teléfono de Power BI abre automáticamente el informe optimizado.

![](media/powerbi-mobile-view-phone-report/07-power-bi-phone-report-portrait.png)


Si no existe un informe optimizado por teléfono, se puede abrir el informe en la vista horizontal no optimizadas cambiando la orientación del teléfono.  

Incluso en un informe optimizado por teléfono, si cambia el teléfono en horizontal, el informe se abrirá en la vista no optimizada con el diseño del informe original.

Si sólo algunas páginas están optimizados, verá un mensaje en la vista vertical, que indica que el informe está disponible en horizontal.

![](media/powerbi-mobile-view-phone-report/06-power-bi-phone-report-page-not-optimized.png)

todas las características de informes de Power BI seguirán funcionan en informes optimizado por teléfono. Lea más acerca de lo que puede hacer:

*   
            [Informa sobre iPhone](powerbi-mobile-reports-in-the-iphone-app.md). 
*   
            [Informa sobre los teléfonos Android](powerbi-mobile-reports-in-the-android-app.md).

## Ver otras páginas del informe

- Ver otras páginas del informe al desplazarse desde el lado o punteando en el icono de páginas ![](media/powerbi-mobile-view-phone-report/power-bi-phone-report-page-icon.png).

## Elementos visuales de realzado cruzado
Cross resaltado de elementos visuales en teléfono informes funciona igual que en el servicio Power BI y en informes en teléfonos en vista landscape: al seleccionar datos en un objeto visual, resalta los datos relacionados en los otros elementos visuales en la página.

Obtenga más información sobre [filtrado y resaltado en Power BI](powerbi-service-about-filters-and-highlighting-in-reports.md).

## Seleccione los elementos visuales
En los informes de teléfono cuando se selecciona un elemento visual, el informe de teléfono resalta esa visual y se centra en ella, efecto para neutralizar el lienzo de gestos.

Con el objeto visual seleccionado, puede hacer cosas como desplazamiento dentro del objeto visual. Para anular la selección de un objeto visual, solo tiene que tocar en cualquier lugar fuera del área visual.

## Abrir elementos visuales en modo de enfoque
Los informes de Phone ofrecen un modo de enfoque, por lo que puede centrarse en un único elemento visual para obtener una vista más grande del objeto visual y explorar visual y el informe.

¿Qué hacer en el modo de enfoque incluye al lienzo del informe y viceversa, para una experiencia de exploración perfecta. Por ejemplo, si resalta un valor en un objeto visual y después volver a todo el informe, el informe como un todo se filtrarán al valor resaltada en el objeto visual.

Algunas acciones sólo son posibles en el modo de enfoque, debido a restricciones de tamaño de pantalla:

- 
              **Explorar en profundidad**, a continuación, copia de seguridad en la información mostrada en el objeto visual, si se definen los niveles de jerarquía.
  Obtenga más información sobre [perforación down y up](powerbi-service-drill-down-in-a-visualization.md) en Power BI.
- 
            **Ordenar** los valores del objeto Visual.
- 
            **Revertir**: borrar pasos de exploración tomadas en un objeto visual y revertir a la definición establecida cuando se creó el informe.

    Revertir está disponible en el nivel del informe, desactive todos los exploración de todos los elementos visuales o en el objeto visual, borrar todos los exploración desde visual específico seleccionado.   

### Consulte también
- [Crear informes optimizados para las aplicaciones de teléfono de Power BI](powerbi-desktop-create-phone-report.md)
- [Crear una vista de teléfono de un panel en Power BI](powerbi-service-create-dashboard-phone-view.md)
- ¿Preguntas más frecuentes? [Pruebe a formular a la Comunidad de Power BI](http://community.powerbi.com/)

<properties
   pageTitle="Categorización de datos en Power BI Desktop"
   description="Categorización de datos en Power BI Desktop"
   services="powerbi"
   documentationCenter=""
   authors="davidiseminger"
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
   ms.date="09/29/2016"
   ms.author="davidi"/>

# Categorización de datos en Power BI Desktop  

En **Power BI Desktop**, puede especificar la categoría de datos para una columna para Power BI Desktop sepa cómo debe tratar sus valores en una visualización.

Cuando Power BI Desktop importa datos, no sólo pone los datos en Sí, también obtiene información como los nombres de tabla y columna, ya sea un etc. clave, principal.  Con esa información, Power BI Desktop hace algunas suposiciones acerca de cómo proporcionar una experiencia buena opción predeterminada cuando se crea una visualización. 

Este es un ejemplo: Power BI Desktop detecta una columna tiene valores numéricos, probablemente deseará agregar de alguna manera, por lo que se coloca en el área de valores. O bien, para una columna con valores de fecha y hora, se supone que probablemente va a utilizar como un eje de la jerarquía de tiempo en un gráfico de líneas.

Sin embargo, existen algunos casos que son un poco más complicado, como la geografía. Tenga en cuenta la siguiente tabla desde una hoja de cálculo de Excel:

![](media/powerbi-desktop-data-categorization/DataCategorizationTable.png)

¿Power BI Desktop tratará los códigos en la columna de código geográfico como una abreviatura para un país o en estado nosotros?  No está claro porque un código como éste puede significar una.  Por ejemplo, puede significar AL Alabama o Albania, AR puede significar Arkansas o Argentina o CA puede significar California o Canadá. Marca la diferencia cuando se vaya a nuestro campo de código geográfico en un mapa del gráfico.  ¿Debe Power BI Desktop mostrar una imagen del mundo con países resaltado o una imagen de los Estados Unidos con Estados resaltado?  Puede especificar una categoría de datos para los datos de esta manera. Aún más la categorización de datos mejora la información de que Power BI Desktop puede utilizar para proporcionar las mejores visualizaciones.  

**Para especificar una categoría de datos**

1.  En la vista de informe o vista de datos, en la **campos** seleccione el campo que desea ordenar por una clasificación diferente.

2.  En la cinta de opciones, en el **Herramientas de modelado de datos** haga clic en el **datos categoría:** lista desplegable.  Esto muestra la lista de categorías de datos posibles que puede elegir para la columna.  Algunas selecciones pueden deshabilitarse si no funcionarán con el tipo de datos actual de la columna.  Por ejemplo, si una columna es un tipo de datos binarios, Power BI Desktop no le permitirá elegir categorías de datos geográficos. 

![](media/powerbi-desktop-data-categorization/DataCategorization.gif)

Y eso es todo!  Cualquier comportamiento que se acumula normalmente en un elemento visual ahora funcionará automáticamente.  

También podría interesados en aprender sobre [filtrado geográfica para aplicaciones móviles de Power BI](powerbi-desktop-mobile-geofiltering.md).

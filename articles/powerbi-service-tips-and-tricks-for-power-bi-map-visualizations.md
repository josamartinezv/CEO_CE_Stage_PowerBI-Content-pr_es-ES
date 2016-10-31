<properties
   pageTitle="Sugerencias y trucos para las visualizaciones de mapas de Power BI"
   description="Sugerencias y trucos para las visualizaciones de mapas de Power BI"
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   featuredVideoId="ajTPGNpthcg"
   qualityFocus="no"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/22/2016"
   ms.author="mihart"/>

# Sugerencias y trucos para las visualizaciones de mapas de Power BI  

Power BI se integra con Bing para proporcionar las coordenadas de la asignación predeterminada (es decir, un proceso denominado codificación geográfica) por lo que es más fácil para crear asignaciones. Bing usa algunos algoritmos y sugerencias para intentar obtener la ubicación correcta, pero es una mejor aproximación. Para aumentar la probabilidad de codificación de geográfica correcta, puede utilizar las siguientes sugerencias:

**1. Utilice términos de ubicación geográfica**

Cuando se asignan las columnas según la designación geográfica, resulta útil Bing adivinar lo que desea mostrar. Por ejemplo, si tiene un campo de NOSOTROS estado nombres como *California* y *Washington*, si la columna no tiene nombre según la designación geográfica (estado, en este caso), Bing podría devolver la ubicación de *Washington, DC* en lugar de Washington State para word *Washington*. Nombres de columna *estado* mejorará las coordenadas geográficas. Lo mismo es cierto para las columnas denominadas *País*, *estado*, y *City*.   

**2. Use una coma para agregar más contexto al campo geográfica**

Algunas designaciones son ambiguas Cuando se consideran en el contexto de varios países o regiones. Puede aumentar la precisión de codificación geográfica mediante la creación de columnas que anexar varios campos juntos y utilizarlas para trazar las ubicaciones de los datos. Por ejemplo, en lugar de pasar sólo *Wiltshire*, puede pasar *Wiltshire, Inglaterra* para obtener un resultado más preciso de codificación geográfica. 

**3. Usar específico latitud y longitud**

Siempre puede proporcionar ubicaciones específicas de latitud y longitud. Al hacerlo, también debe rellenar el *ubicación* campo al crear las visualizaciones. De lo contrario, los datos se agregan de forma predeterminada, por ejemplo, la latitud y longitud podría combinarse en el nivel de estado, no en el nivel de ciudad. Campos de latitud y longitud deben estar en *número Decimal* formato, que puede establecer en el modelo de datos.

<iframe width="560" height="315" src="https://www.youtube.com/embed/ajTPGNpthcg" frameborder="0" allowfullscreen></iframe>


## Categorizar campos geográficos para obtener las coordenadas geográficas de Bing  
En Power BI Desktop, puede asegurarse de campos de coordenadas geográficas correctamente estableciendo la *categoría datos* en los campos de datos. En Power BI Desktop, seleccione la tabla deseada, vaya a la **avanzadas** la cinta de opciones y, a continuación, establezca el **categoría datos** a **dirección**, **City**, **continente**, **país o región**, **País**, **Código Postal**, **estado** o **provincia**. Estas categorías de datos ayudan a Bing a codificar correctamente la fecha. Para obtener más información, consulte [categorización de datos en Power BI Desktop](powerbi-desktop-data-categorization.md).

## Mejor codificación geográfica con ubicaciones más específicas  
A veces, incluso establecer las categorías de datos de asignación no basta con Bing adivinar correctamente su intención. Dentro de la consulta, puede crear una ubicación más específica como una dirección postal mediante **Editor de consultas** en Power BI Desktop.  Utilice la **Agregar columna** característica para crear una columna personalizada, a continuación, crear la ubicación deseada como sigue: 


    = [Field1] & " " & [Field2]

A continuación, utilice el campo resultante en las visualizaciones de mapa. Este enfoque es muy útil para la creación de direcciones de los campos de dirección de envío, que son comunes en conjuntos de datos. Tenga en cuenta que la concatenación solo funciona con campos de texto. Si es necesario, convierta el número de la calle para una *texto* el tipo de datos antes de usarlo para generar una dirección.  

## Consulte también

[Visualizaciones de Power Bi](powerbi-service-visualizations-for-reports.md)

¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)

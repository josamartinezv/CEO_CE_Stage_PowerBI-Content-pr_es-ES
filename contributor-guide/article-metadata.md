

#Metadatos de artículos técnicos de Power BI

Todos los artículos técnicos de Power BI contienen dos secciones de metadatos: una sección de propiedades y una sección de etiquetas. La sección de propiedades habilita algunos elementos relacionados con la automatización del sitio web y la SEO, mientras que la de etiquetas permite la creación de una gran cantidad de informes de contenido interno. Ambas secciones resultan necesarias.

- [Sintaxis]
- [Uso]
- [Atributos y valores de la sección de propiedades]
- [Atributos y valores de la sección de etiquetas]

##Sintaxis

La sección propiedades utiliza esta sintaxis:

    <properties
       pageTitle="<Page title that displays in search results and the browser tab | Microsoft Power BI>"
       description="<Article description that will be displayed on landing pages and in most search results>"
       services="powerbi"
       documentationCenter="NA"
       authors="GitHub-alias-of-only-one-author"
       manager="mblythe"
       editor="NA"
       tags="NA"/>

La sección etiquetas, utiliza esta sintaxis:

    <tags
       ms.service="powerbi"
       ms.devlang="NA"
       ms.topic="<typically "article"; see list below>"
       ms.tgt_pltfrm="<typically "NA"; see list below>"
       ms.workload="powerbi"
       ms.date="mm/dd/yyyy"
       ms.author="Your MSFT alias or your full email address;semicolon separates two or more"/>

##Uso

- Se distingue entre mayúsculas y minúsculas en los nombres del elemento y de los atributos.
- La opción <properties> sección debe ser la primera línea del archivo.
- Deje una línea en blanco después de cada sección de metadatos y antes del título de la página para asegurarse de que este último se convierta correctamente a HTML durante el proceso de publicación.

## Atributos y valores de la sección de propiedades

![](./media/article-metadata/checkmark-small.png)
            **pageTitle**: necesario; importante SEO. El texto de este atributo aparece en la pestaña del navegador y como el título en los resultados de búsqueda. Utilice 55 y 60 caracteres incluidos los espacios e incluya el identificador de sitio *| Microsoft Power BI* (tipo: espacio espacio canalización Microsoft Power BI).

![](./media/article-metadata/checkmark-small.png)
            **descripción**: necesario; importante para SEO (relevancia) y funcionalidades de sitio. Utilice al menos de 140 caracteres, pero no superar 170 caracteres incluidos los espacios. Describir el propósito de su contenido para que los clientes sepa si debe elegir de una lista de resultados de búsqueda. El valor se muestra normalmente como la descripción o el párrafo abstracta en resultados de búsqueda.

![](./media/article-metadata/checkmark-small.png)
            **servicios**: siempre "powerbi" para el contenido de Power BI (Azure tiene varias opciones).

![](./media/article-metadata/checkmark-small.png)
            **documentationCenter**: "NA" para el contenido de Power BI.

![](./media/article-metadata/checkmark-small.png)
            **los autores**: requiere un único valor. Indique la cuenta de GitHub del autor principal o del SME del artículo. Este atributo activa la línea de autor en el artículo publicado. Especifique tan solo un valor, a pesar de la forma plural del nombre del atributo.

![](./media/article-metadata/checkmark-small.png)
            **Administrador de**: necesario si es un colaborador de Microsoft. El alias del Administrador de publicación de contenido para el área de tecnología de la lista. Si es un colaborador de la comunidad, incluya el atributo, pero déjelo vacío para que podamos rellenarlo.

![](./media/article-metadata/checkmark-small.png)
            **Editor de**: "NA" - no utilizado. No lo utilice para otros fines.

![](./media/article-metadata/checkmark-small.png)
            **etiquetas**: "NA" para el contenido de Power BI.


## Atributos y valores de la sección de etiquetas

![](./media/article-metadata/checkmark-small.png)
            **MS.Service**: siempre "powerbi" para el contenido de Power BI (Azure tiene varias opciones).

![](./media/article-metadata/checkmark-small.png)
            **MS.DevLang**: "NA" para el contenido de Power BI.

![](./media/article-metadata/checkmark-small.png)
            **MS.topic**: requerido. Especifica el tipo de tema. La mayoría de las páginas nuevas que crean los colaboradores serán artículos o material de referencia. NOTA: la lista siguiente es de Azure y he quitado algunas de las opciones que definitivamente no son válidas para Power BI. Decidimos cómo usar las opciones restantes como se desarrolla nuestra arquitectura de sitio. En caso de duda, utilice "artículo". 

 - 
            **article**: un tema conceptual, un tutorial, una guía de funciones u otro artículo que no sea de referencia.

 - 
            **página de campaña**: una página que está específicamente diseñada como una página de aterrizaje de campañas externas y no se incluye como parte del sitio primario IA.  No debe utilizarse para artículos de documentación o doc regular las páginas de inicio.

 - 
            **artículo iniciado Get**: asignar a los artículos que se muestran en la sección de introducción de la izquierda para un servicio.

 - 
            **artículo héroe**: un tutorial de "hero" que está diseñado para proporcionar una introducción a un servicio o característica que obtiene los visitantes a usar el servicio rápidamente y unidades de suscripciones de prueba gratuita y las activaciones de MSDN. Asigne este valor SOLO a los artículos que se destaquen en la parte superior de la página de destino de la documentación del servicio.

 - 
            **página principal**: página principal de documentación de nivel superior.

 - 
            **página infografía**: una página que incluye un infografía browsable o póster.

 - 
            **referencia**: página de referencia de una API o lenguaje (incluida la API de REST).

 - 
            **página de vídeo**: una página que incluye un vídeo.

![](./media/article-metadata/checkmark-small.png)
            **MS.tgt_pltfrm**: requerido. Especifica la plataforma de destino. Este valor será **NA** para la mayoría de los temas. NOTA: Todavía detemining si debemos usar nuestro contenido para dispositivos móviles.

 - **mobile-android**
 - **mobile-html**
 - **mobile-ios**
 - **mobile-multiple**
 - **múltiple**
 - **N/D**

![](./media/article-metadata/checkmark-small.png)
            **MS.Workload**: siempre "powerbi" para el contenido de Power BI (Azure tiene varias opciones).

![](./media/article-metadata/checkmark-small.png) 
            **MS.Date**: requerido. Especifica la fecha en la que se revisaron por última vez la relevancia, la precisión, la corrección de las capturas de pantalla y el funcionamiento de los vínculos. Especifique la fecha en el formato mm/dd/aaaa. Esta fecha también aparece en el artículo publicado como la fecha de la última actualización.

![](./media/article-metadata/checkmark-small.png) 
            **MS.author**: requerido. Indica los autores asociados con el tema. Para especificar varios valores, debe separarlos por punto y coma. Se aceptan alias de Microsoft o direcciones de correo completas. La longitud no puede superar los 200 caracteres.


###Vínculos de la Guía de los colaboradores

- [Artículo de información general](./../README.md)
- [Índice de artículos de la guía](./contributor-guide-index.md)


<!--Anchors-->
[Sintaxis]: #syntax
[Uso]: #usage
[Atributos y valores de la sección de propiedades]: #attributes-and-values-for-the-properties-section
[Atributos y valores de la sección de etiquetas]: #attributes-and-values-for-the-tags-section

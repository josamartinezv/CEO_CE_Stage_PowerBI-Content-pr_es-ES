

#Metadata for Power BI technical articles

All Power BI technical articles contain two metadata sections - a properties section and a tags section. La sección de propiedades habilita algunos elementos relacionados con la automatización del sitio web y la SEO, mientras que la de etiquetas permite la creación de una gran cantidad de informes de contenido interno. Ambas secciones resultan necesarias.

- [Sintaxis]
- [Uso]
- [Attributes and values for the properties section]
- [Attributes and values for the tags section]

##Sintaxis

The properties section uses this syntax:

    <properties
       pageTitle="<Page title that displays in search results and the browser tab | Microsoft Power BI>"
       description="<Article description that will be displayed on landing pages and in most search results>"
       services="powerbi"
       documentationCenter="NA"
       authors="GitHub-alias-of-only-one-author"
       manager="mblythe"
       editor="NA"
       tags="NA"/>

The tags section uses this syntax:

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
- La opción <properties> section must be the first line of your file.
- Deje una línea en blanco después de cada sección de metadatos y antes del título de la página para asegurarse de que este último se convierta correctamente a HTML durante el proceso de publicación.

## Attributes and values for the properties section

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>pageTitle<ept id="p1">**</ept>: Required; important to SEO. El texto de este atributo aparece en la pestaña del navegador y como el título en los resultados de búsqueda. Use 55-60 characters including spaces and including the site identifier <bpt id="p1">*</bpt>| Microsoft Power BI<ept id="p1">*</ept> (typed as: space pipe space Microsoft Power BI).

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>description<ept id="p1">**</ept>: Required; important for SEO (relevance) and site functionalities. Use at least 140 characters, but don't exceed 170 characters including spaces. Describe the  purpose of your content so customers will know whether to choose it from a list of search results. The value is usually displayed as the description or abstract paragraph in search results.

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>services<ept id="p1">**</ept>: Always "powerbi" for Power BI content (Azure has multiple options).

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>documentationCenter<ept id="p1">**</ept>: "NA" for Power BI content.

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>authors<ept id="p1">**</ept>: Required, one value only. Indique la cuenta de GitHub del autor principal o del SME del artículo. Este atributo activa la línea de autor en el artículo publicado. Especifique tan solo un valor, a pesar de la forma plural del nombre del atributo.

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>manager<ept id="p1">**</ept>: Required if you are a Microsoft contributor. List the alias of the content publishing manager for the technology area. Si es un colaborador de la comunidad, incluya el atributo, pero déjelo vacío para que podamos rellenarlo.

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>editor<ept id="p1">**</ept>: "NA" - Not used. No lo utilice para otros fines.

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>tags<ept id="p1">**</ept>: "NA" for Power BI content.


## Attributes and values for the tags section

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>ms.service<ept id="p1">**</ept>: Always "powerbi" for Power BI content (Azure has multiple options).

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>ms.devlang<ept id="p1">**</ept>: "NA" for Power BI content.

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>ms.topic<ept id="p1">**</ept>: Required. Specifies the topic type. La mayoría de las páginas nuevas que crean los colaboradores serán artículos o material de referencia. NOTE: the list below is from Azure, and I have removed some of the options that definitely aren't valid for Power BI. We will decide how to use the remaining options as our site architecture is developed. If in doubt, use "article". 

 - 
            **article**: un tema conceptual, un tutorial, una guía de funciones u otro artículo que no sea de referencia.

 - <bpt id="p1">**</bpt>campaign-page<ept id="p1">**</ept>: A page that is specifically designed as a landing page for external campaigns, and is not included as part of the primary site IA.  Should not be used for documentation articles or regular doc landing pages.

 - <bpt id="p1">**</bpt>get-started-article<ept id="p1">**</ept>: Assign to articles that are featured in the Get Started section of the left navigation for a service.

 - <bpt id="p1">**</bpt>hero-article<ept id="p1">**</ept>: A "hero" tutorial that is designed to provide an introduction to a service or feature that gets visitors started using the service quickly and drives free-trial sign-ups and MSDN activations. Asigne este valor SOLO a los artículos que se destaquen en la parte superior de la página de destino de la documentación del servicio.

 - <bpt id="p1">**</bpt>home-page<ept id="p1">**</ept>: Top level documentation home page.

 - <bpt id="p1">**</bpt>infographic-page<ept id="p1">**</ept>: A page that features a browsable infographic or poster.

 - <bpt id="p1">**</bpt>reference<ept id="p1">**</ept>: An API or language reference page (including REST API).

 - <bpt id="p1">**</bpt>video-page<ept id="p1">**</ept>: A page that features a video.

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>ms.tgt_pltfrm<ept id="p1">**</ept>: Required. Specifies the target platform. This value will be <bpt id="p1">**</bpt>NA<ept id="p1">**</ept> for most topics. NOTE: Still detemining whether we should use this for our mobile content.

 - **mobile-android**
 - **mobile-html**
 - **mobile-ios**
 - **mobile-multiple**
 - **múltiple**
 - **N/D**

![](./media/article-metadata/checkmark-small.png)<bpt id="p1">**</bpt>ms.workload<ept id="p1">**</ept>: Always "powerbi" for Power BI content (Azure has multiple options).

![](./media/article-metadata/checkmark-small.png) <bpt id="p1">**</bpt>ms.date<ept id="p1">**</ept>: Required. Especifica la fecha en la que se revisaron por última vez la relevancia, la precisión, la corrección de las capturas de pantalla y el funcionamiento de los vínculos. Especifique la fecha en el formato mm/dd/aaaa. Esta fecha también aparece en el artículo publicado como la fecha de la última actualización.

![](./media/article-metadata/checkmark-small.png) <bpt id="p1">**</bpt>ms.author<ept id="p1">**</ept>: Required. Indica los autores asociados con el tema. Para especificar varios valores, debe separarlos por punto y coma. Se aceptan alias de Microsoft o direcciones de correo completas. La longitud no puede superar los 200 caracteres.


###Contributors' Guide Links

- [Artículo de información general](./../README.md)
- [Índice de artículos de la guía](./contributor-guide-index.md)


<!--Anchors-->
[Sintaxis]: #syntax
[Uso]: #usage
[Attributes and values for the properties section]: #attributes-and-values-for-the-properties-section
[Attributes and values for the tags section]: #attributes-and-values-for-the-tags-section

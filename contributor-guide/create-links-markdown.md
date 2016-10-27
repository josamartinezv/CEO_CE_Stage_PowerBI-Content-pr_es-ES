<properties
   pageTitle="Create links in markdown articles" description="Explains how to code crosslinks in markdown." metaKeywords="" services="" solutions="" documentationCenter="" authors="mblythe" videoId="" scriptId="" manager="dongill" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="09/09/2015" ms.author="mblythe" />

# Linking guidance for Power BI technical content
## Guidelines for technical articles on powerbi.microsoft.com

| Escenario de vinculación | Orientación  |
|---------------|-----------|
|Linking from a Power BI article to another Power BI article|Use vínculos relativos. Do not include the en-us language locale in your relative links.|
|Linking to an MSDN library topic, a TechNet library topic, or KB article|Use the actual link to the article or topic, but remove the en-us language locale from the link.|
|Linking from a Power BI article to any other web page|Utilice el vínculo directo.|

### Markdown syntax for Power BI relative links

To create an inline link from a Power BI technical article to another Power BI technical article, use this link format.

> [AZURE.NOTE] Some aspects of linking are still TBD b/c we need to settle on a final structure for the github repo.

Artículo que se vincula de un subdirectorio a un artículo del directorio raíz:

    [link text](../article-name.md)

Article in the root directory links to an article in a subdirectory: 

    [link text](section-folder/article-name.md)

Article in a section subdirectory links to an article that is in another section subdirectory:

    [link text](../section-folder/article-name.md)
 
Artículo de un directorio que se vincula a otro artículo del mismo directorio:

    [link text](article-name.md)


You do not have to create anchors - they are automatically generated at publishing time for all H2 headings. Basta con establecer vínculos a las secciones del tipo H2:

    [link](#the-text-of-the-H2-section-separated-by-hyphens)
    [Create cache](#create-cache)

Para incluir un vínculo a un delimitador de otro artículo que se encuentre en el mismo subdirectorio:

    [link text](article-name.md#anchor-name)
    [Configure your profile](media-services-create-account.md#configure-your-profile)

Para incluir un vínculo a un delimitador de otro subdirectorio de servicio:

    [link text](section-folder/article-name.md#anchor-name)
    [Configure your profile](section-folder/media-services-create-account.md#configure-your-profile)


## Sintaxis de vinculación personalizada de Markdown

Debido a que los archivos de inclusión se encuentran en otro directorio, deberá usar rutas de acceso relativas tal y como se muestra a continuación. Para establecer un vínculo a un único artículo a partir de un archivo de inclusión, utilice este formato:

    [link text](../articles/section-folder/article-name.md)
    
Learn more about how to use an includes file in the <bpt id="p1">[</bpt>Custom markdown extensions guidelines<ept id="p1">](custom-markdown-extensions.md#includes)</ept>.

Si cuenta con selectores incrustados en un archivo de inclusión, utilice este tipo de vinculación: 

    > [AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )] <ph id="ph1">    - </ph><bpt id="p1">[</bpt>(Text1 | Example1 )<ept id="p1">](../articles/section-folder/article-name1.md)</ept><ph id="ph2">
    - </ph><bpt id="p2">[</bpt>(Text1 | Example2 )<ept id="p2">](../articles/section-folder/article-name2.md)</ept><ph id="ph3">
    - </ph><bpt id="p3">[</bpt>(Text2 | Example3 )<ept id="p3">](../articles/section-folder/article-name3.md)</ept><ph id="ph4">
    - </ph><bpt id="p4">[</bpt>(Text2 | Example4 )<ept id="p4">](../articles/section-folder/article-name4.md)</ept>

To link to a page on Power BI (such as a pricing page, SLA page or anything else that is not a documentation article), use an absolute URL, but omit the locale. La finalidad es que los vínculos funcionen en GitHub y en el sitio representado:

    [link text](http://powerbi.microsoft.com/pricing/)

To test your links, push your page to your fork and view it in the rendered view and publish to staging. The cross links on the GitHub version of the page should work as long as the targets of the URLs are present in your fork.

Our <bpt id="p1">[</bpt>markdown template for technical articles<ept id="p1">](../markdown templates/markdown-template-for-new-articles.md/)</ept> shows an alternate way to create crosslinks in markdown so all the crosslinks are coded together at the end of the article, even while they display inline.

## Vínculos de estilo de referencia

Puede utilizar vínculos de estilo de referencia para facilitar la lectura de su contenido de origen. Los vínculos de estilo de referencia reemplazan la sintaxis de vinculación insertada por una simplificada que permite mover las direcciones URL largas al final del artículo. Este es un ejemplo de Daring Fireball:

Texto insertado:

    I get 10 times more traffic from [Google][1] than from [Yahoo][2] or [MSN][3].

Vínculos de referencia al final del artículo:

    <!--Reference links in article-->
    [1]: http://google.com/
    [2]: http://search.yahoo.com/  
    [3]: http://search.msn.com/

## FWLinks

Avoid FWLinks (our redirection system) in powerbi.microsoft.com content. They should be used only as a last resort when you need to create a link for a page whose URL you don't yet know. They are almost never actually needed. For Power BI, you define the file name, so you can know what it will be ahead of time. For a library topic that is not yet published, you can create a link that uses the topic GUID so that you don't have to use an FWLink.

If you must use an FWLink on a web page, include the P parameter to make it a permanent redirect:

    http://go.microsoft.com/fwlink/p/?LinkId=389595

When you paste the target URL into the FWLink tool, remember to remove the locale if your target link is Power BI, or the MSDN or TechNet library.

### Contributors' Guide Links

- [Artículo de información general](./../README.md)
- [Índice de artículos de la guía](./contributor-guide-index.md)

<!--image references-->
[1]: ./media/create-tables-markdown/table-markdown.png
[2]: ./media/create-tables-markdown/break-tables.png

<properties
    title="required"
    pageTitle="Extensiones Markdown personalizadas que se usan en nuestros artículos técnicos"
    description="Lists the custom markdown extensions that enable embedded videos, notes and tips, reusable content, and other item in powerbi.microsoft.com technical articles."
    services=""
    solutions=""
    documentationCenter=""
    authors="mblythe"
    manager="dongill"
    editor=""/>

<tags
    ms.service="contributor-guide"
    ms.devlang=""
    ms.topic="article"
    ms.tgt_pltfrm=""
    ms.workload=""
    ms.date="09/09/2015"
    ms.author="mblythe"/>

## Markdown for powerbi.microsoft.com

For general markdown tips, see <bpt id="p1">[</bpt>Markdown Basics<ept id="p1">](https://help.github.com/articles/markdown-basics/)</ept> and our <bpt id="p2">[</bpt>markdown cheatsheet<ept id="p2">](./media/documents/markdown-cheatsheet.pdf?raw=true)</ept>. If you need to create article crosslinks in markdown, see the [linking guidance] (./create-links-markdown.md#markdown-syntax-for-acom-relative-links.md/).

powerbi.microsoft.com supports <bpt id="p1">[</bpt>fenced code blocks<ept id="p1">](https://help.github.com/articles/github-flavored-markdown/#fenced-code-blocks)</ept> and <bpt id="p2">[</bpt>syntax highlighting<ept id="p2">](https://help.github.com/articles/github-flavored-markdown/#syntax-highlighting)</ept>. However, Power BI supports only one syntax highlighting color scheme, regardless of the language you specify in a code block.

## Extensiones Markdown personalizadas que se usan en nuestros artículos técnicos

Nuestros artículos usan el marcado característico de GitHub para dar formato a la mayoría de los artículos; por ejemplo, párrafos, vínculos, listas, títulos, etc.  Estas son las extensiones que usamos actualmente:

+ [Notas y sugerencias]
+ [Includes]
+ [Vídeos insertados]
+ [Selectores de tecnología y plataforma]

## Notas y sugerencias

Puede elegir entre 4 tipos de notas y sugerencias:

- AZURE.NOTE
- AZURE.WARNING
- AZURE.TIP
- AZURE.IMPORTANT

###Uso
En general, utilice con moderación las notas y sugerencias en los artículos. Cuando lo haga, elija el tipo adecuado de nota o sugerencia:

- Use AZURE.NOTE to highlight neutral or positive information that emphasizes or supplements key points of the main text. Una nota proporciona información que se aplica solo en casos especiales.

  ![](./media/custom-markdown-extensions/Notes-note.PNG)

- Use AZURE.WARNING to alert the user to a condition that might cause a problem in the future. Por ejemplo, al seleccionar una opción determinada o tomar una decisión específica, es posible que ya no pueda dar marcha atrás.

  ![](./media/custom-markdown-extensions/Notes-warning.PNG)

- Use AZURE.TIP to help your users apply the techniques and procedures described in the text to their specific needs. Una sugerencia también podría recomendar métodos alternativos que puede que no sean evidentes. Sin embargo, las sugerencias no son esenciales para comprender el texto en líneas generales.

  ![](./media/custom-markdown-extensions/Notes-tip.PNG)

- Use AZURE.IMPORTANT to provide information that is essential to the completion of a task.

  ![](./media/custom-markdown-extensions/Notes-important.PNG)

Aunque estas notas y sugerencias son compatibles con vínculos, imágenes, listas y bloques de código, trate de lograr siempre que las notas y sugerencias sean simples y directas. Si está creando notas complejas con gran cantidad de formato, podría ser un indicio de que necesita otra sección en el texto principal del artículo. Asimismo, el uso de demasiadas notas en un artículo puede ser molesto y dificultar la lectura.

###Marcado de muestra

The samples all show a AZURE.NOTE. Para usar TIP, WARNING o IMPORTANT, reemplace "NOTE" en el marcado:

    > [AZURE.TIP]

    > [AZURE.WARNING]

    > [AZURE.IMPORTANT]

Un solo párrafo:

    > [AZURE.NOTE] To complete this tutorial, you must have an active Microsoft Power BI account. Si no tiene una cuenta, puede crear una cuenta de evaluación gratuita en un par de minutos.

Varios párrafos:

    > [AZURE.NOTE] To complete this tutorial, you must have an active Microsoft Power BI account.
    >
    > If you don't have an account, you can <bpt id="p1">[</bpt>create a free trial account<ept id="p1">](http://www.windowsPower BI.com/pricing/free-trial/)</ept> in just a couple of minutes.

## Includes

Reusable text fragments in our GitHub repository are called "includes". Si tiene texto que debe usarse en varios artículos, incluya una referencia a los fragmentos de texto en los archivos Markdown. The text fragment (the include) itself is a simple markdown (.md) file. Puede contener cualquier marcado válido, como texto, vínculos e imágenes. All include markdown files must be in <bpt id="p1">[</bpt>the /includes directory<ept id="p1">](https://github.com/azure/powerbi-content/tree/master/includes)</ept> in the root of the repository. When the article is published, the include text is seamlessly integrated into the published topic.

- We use a specific syntax to reference an include.

- Media files you put in an include must be created in a media folder specific to the include. Media folders for includes belong in <bpt id="p1">[</bpt>the powerbi-content/includes/media folder<ept id="p1">](https://github.com/azure/powerbi-content/tree/master/includes/media)</ept>. The media directory should not contain any images in its root. If the include does not have images, then a corresponding media directory is not required.

###Uso

- Use includes wherever you need the same text to appear in multiple articles.
- Includes are meant to be used for significant amounts of content - a paragraph or two, a shared procedure, or a shared section. No los utilice en unidades más pequeñas que una frase; no se pueden emplear en nombres de producto o frases incompletas.
- Don't embed includes within other includes. ya que se producirán problemas en el sistema de publicación.
- No comparta elementos multimedia entre archivos. Use a separate file with a unique name for each include and article. Store the media file in the media folder associated with the include.
- Don't use an includes as the only content of an article.  Includes are meant to be supplemental to the content in the rest of the article.
- Because all includes must be in the /includes directory, the path to an include from an article is always

    ../includes

- Do NOT repeat a link or image filename reference in both the article and the include. Add "-include" to the link reference or media filename to avoid repeating the reference:

 **Referencia de vínculo**

 Change: odata.org To: odata.org-include

 **Referencia de imagen**

 Change: table.png To: table-include.png

###Marcado de muestra
The syntax for adding an include to a documentation article is:

    [AZURE.INCLUDE [include-short-name](../includes/include-file-name.md)]

Ejemplo

    [AZURE.INCLUDE [howto-blob-storage](../includes/howto-blob-storage.md)]

The first part of the include is the include name without the path and without the .md extension. The second part is the relative path to the include in the /includes directory, with the .md extension.

###Representación

In the rendered GitHub page, the include will render as follows:

 [AZURE.INCLUDE howto-blob-storage]

In the rendered HTML on powerbi.microsoft.com, the HTML from the includes is merged into the rest of the document's HTML. However, the HTML will contain an HTML comment with the original include markdown filename and the GitHub commit hash. Este comentario se incluye para poder solucionar problemas, de modo que el contenido de origen pueda identificarse y encontrarse con facilidad en GitHub:

  ![](./media/custom-markdown-extensions/include.png)


## Vídeos insertados

Our technical articles will support embeddeded videos in technical articles, details are TBD (Azure requires Channel 9, but we want to use YouTube).


## Selectores de tecnología y plataforma

> [AZURE.NOTE] This info is for Azure but we might adopt selectors in the future.

Utilice modificadores de tecnología y plataforma en artículos técnicos al crear varias versiones del mismo artículo con el objetivo de corregir las diferencias de implementación entre plataformas o tecnologías. En la mayoría de los casos, tendrá que emplearlos en nuestro contenido de plataforma móvil para desarrolladores. Actualmente, hay dos tipos diferentes de selectores: [simples](#simple-selectors) y [bidireccionales](#two-way-selectors).

Because the same selector markdown goes in each topic in the selection, we recommend placing the selector for your topic in an include, then referencing that include in all of your topics that use the same selector.

###<a id="simple-selectors"></a>Selectores simples

Los selectores simples (unidireccionales) se representan como un conjunto de botones de opción justo debajo del título. Use these buttons when customers only need to choose from topics in a single platform or technology set, such as .NET, Node.js, and Java.  Please use the below custom markdown format for any selectors.  Do not use HTML for selector functions.  

Consulte [Get started with Notification Hubs](http://azure.microsoft.com/documentation/articles/notification-hubs-windows-phone-get-started/) (Introducción a Centros de notificaciones) para ver cómo el autor creó 8 versiones del mismo artículo y usó los selectores para permitir la navegación en todos ellos.

![Ejemplo de selector simple](./media/custom-markdown-extensions/selectors.PNG)

####Sintaxis

    > [AZURE.SELECTOR]
    - <bpt id="p1">[</bpt>Link #1 Label<ept id="p1">](link #1 url)</ept><ph id="ph1">
    - </ph><bpt id="p2">[</bpt>Link #2 Label<ept id="p2">](link #2 url)</ept>

Ejemplo:

    > [AZURE.SELECTOR]
    - <bpt id="p1">[</bpt>Universal Windows<ept id="p1">](../articles/notification-hubs-windows-store-dotnet-get-started/)</ept><ph id="ph1">
    - </ph><bpt id="p2">[</bpt>Windows Phone<ept id="p2">](../articles/notification-hubs-windows-phone-get-started/)</ept><ph id="ph2">
    - </ph><bpt id="p3">[</bpt>iOS<ept id="p3">](../articles/notification-hubs-ios-get-started/)</ept><ph id="ph3">
    - </ph><bpt id="p4">[</bpt>Android<ept id="p4">](../articles/notification-hubs-android-get-started/)</ept><ph id="ph4">
    - </ph><bpt id="p5">[</bpt>Kindle<ept id="p5">](../articles/notification-hubs-kindle-get-started/)</ept><ph id="ph5">
    - </ph><bpt id="p6">[</bpt>Baidu<ept id="p6">](../articles/notification-hubs-baidu-get-started/)</ept><ph id="ph6">
    - </ph><bpt id="p7">[</bpt>Xamarin.iOS<ept id="p7">](../articles/partner-xamarin-notification-hubs-ios-get-started/)</ept><ph id="ph7">
    - </ph><bpt id="p8">[</bpt>Xamarin.Android<ept id="p8">](../articles/partner-xamarin-notification-hubs-android-get-started/)</ept>

#### Representación

The image above shows the rendering on powerbi.microsoft.com. En las páginas de GitHub representadas, los selectores se representan como una lista con viñetas de vínculos.

###<a id="two-way-selectors"></a>Selectores bidireccionales

Los selectores bidireccionales permiten a los usuarios seleccionar un tema de una matriz bidireccional. This is essential when an Azure technology, such as Mobile Services, supports multiple backend platforms as well as multiple clients. Tenga en cuenta lo siguiente:

- While it was designed as <ph id="ph1">`(Platform | Backend)`</ph>, the dropwdown text can now be customized.
- No necesita un elemento de lista en todos los puntos de la matriz, solamente uno en el que haya una dirección URL de un tema y que no esté duplicada.
- El vínculo puede ser cualquier dirección URL, aunque, normalmente, es otro tema de GitHub.

Consulte [Introducción a Mobile Services](http://azure.microsoft.com/en-us/documentation/articles/mobile-services-ios-get-started/) para ver cómo el autor creó 15 versiones del mismo artículo (9 plataformas cliente móviles y 2 plataformas de back-end) y usó los selectores para permitir la navegación en todos ellos. Tenga en cuenta que 3 artículos no tienen las dos versiones de back-end.

![Ejemplo de selectores bidireccionales](./media/custom-markdown-extensions/selector-list.png)

####Sintaxis

    > [AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )] <ph id="ph1">    - </ph><bpt id="p1">[</bpt>(Dropdown1Text1 | Dropdown2Text1 )<ept id="p1">](../articles/dropdown1-text1-dropdown2-text1.md)</ept><ph id="ph2">
    - </ph><bpt id="p2">[</bpt>(Dropdown1Text1 | Dropdown2Text2 )<ept id="p2">](../articles/dropdown1-text1-dropdown2-text1.md)</ept><ph id="ph3">
    - </ph><bpt id="p3">[</bpt>(Dropdown1Text2 | Dropdown2Text3 )<ept id="p3">](../articles/dropdown1-text1-dropdown2-text1.md)</ept><ph id="ph4">
    - </ph><bpt id="p4">[</bpt>(Dropdown1Text3 | Dropdown2Text4 )<ept id="p4">](../articles/dropdown1-text1-dropdown2-text1.md)</ept>

Ejemplo:

    > [AZURE.SELECTOR-LIST (Platform | Backend )] <ph id="ph1">    - </ph><bpt id="p1">[</bpt>(iOS | .NET)<ept id="p1">](./mobile-services-dotnet-backend-ios-get-started-push.md)</ept><ph id="ph2">
    - </ph><bpt id="p2">[</bpt>(iOS | JavaScript)<ept id="p2">](./mobile-services-javascript-backend-ios-get-started-push.md)</ept><ph id="ph3">
    - </ph><bpt id="p3">[</bpt>(Windows universal C# | .NET)<ept id="p3">](./mobile-services-dotnet-backend-windows-universal-dotnet-get-started-push.md)</ept><ph id="ph4">
    - </ph><bpt id="p4">[</bpt>(Windows universal C# | Javascript)<ept id="p4">](./mobile-services-javascript-backend-windows-universal-dotnet-get-started-push.md)</ept><ph id="ph5">
    - </ph><bpt id="p5">[</bpt>(Windows Phone | .NET)<ept id="p5">](./mobile-services-dotnet-backend-windows-phone-get-started-push.md)</ept><ph id="ph6">
    - </ph><bpt id="p6">[</bpt>(Windows Phone | Javascript)<ept id="p6">](./mobile-services-javascript-backend-windows-phone-get-started-push.md)</ept><ph id="ph7">
    - </ph><bpt id="p7">[</bpt>(Android | .NET)<ept id="p7">](./mobile-services-dotnet-backend-android-get-started-push.md)</ept><ph id="ph8">
    - </ph><bpt id="p8">[</bpt>(Android | Javascript)<ept id="p8">](./mobile-services-javascript-backend-android-get-started-push.md)</ept><ph id="ph9">
    - </ph><bpt id="p9">[</bpt>(Xamarin iOS | Javascript)<ept id="p9">](./partner-xamarin-mobile-services-ios-get-started-push.md)</ept><ph id="ph10">
    - </ph><bpt id="p10">[</bpt>(Xamarin Android | Javascript)<ept id="p10">](./partner-xamarin-mobile-services-android-get-started-push.md)</ept>

#### Representación

La imagen anterior muestra la representación en azure.microsoft.com. En las páginas de GitHub representadas, los selectores se representan como una lista con viñetas de vínculos.

<!--Anchors-->
[Notas y sugerencias]: #notes-and-tips
[Includes]: #includes
[Vídeos insertados]: #embedded-videos
[Selectores de tecnología y plataforma]: #technology-and-platform-selectors

###Contributors' Guide Links

- [Artículo de información general](./../README.md)
- [Índice de artículos de la guía](./contributor-guide-index.md)

<properties
    title="required"
    pageTitle="Extensiones Markdown personalizadas que se usan en nuestros artículos técnicos"
    description="Enumera las extensiones de descuento personalizados que permiten vídeos incrustados, notas y sugerencias, contenido reutilizable y artículos técnicos de powerbi.microsoft.com otro elemento."
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

## Descuento para powerbi.microsoft.com

Para obtener sugerencias de descuento general, consulte [conceptos básicos de descuento](https://help.github.com/articles/markdown-basics/) y nuestro [datos básicos de descuento](./media/documents/markdown-cheatsheet.pdf?raw=true). Si necesita crear vínculos cruzados de artículo de descuento, consulte [orientación vinculación] (. / create-links-markdown.md#markdown-syntax-for-acom-relative-links.md/).

powerbi.Microsoft.com admite [bloqueado bloques de código](https://help.github.com/articles/github-flavored-markdown/#fenced-code-blocks) y [resaltado de sintaxis](https://help.github.com/articles/github-flavored-markdown/#syntax-highlighting). Sin embargo, Power BI admite sólo una combinación de colores, independientemente del idioma que especifique en un bloque de código para resaltar la sintaxis.

## Extensiones Markdown personalizadas que se usan en nuestros artículos técnicos

Nuestros artículos usan el marcado característico de GitHub para dar formato a la mayoría de los artículos; por ejemplo, párrafos, vínculos, listas, títulos, etc. Pero usar extensiones de descuento personalizado que necesitamos un formato más enriquecido en las páginas representadas en powerbi.microsoft.com. Estas son las extensiones que usamos actualmente:

+ [Notas y sugerencias]
+ [Incluye]
+ [Vídeos insertados]
+ [Selectores de tecnología y plataforma]

## Notas y sugerencias

Puede elegir entre 4 tipos de notas y sugerencias:

- AZURE. TENGA EN CUENTA
- AZURE. ADVERTENCIA
- AZURE. SUGERENCIA
- AZURE. IMPORTANTE

###Uso
En general, utilice con moderación las notas y sugerencias en los artículos. Cuando lo haga, elija el tipo adecuado de nota o sugerencia:

- Uso de AZURE. Tenga en CUENTA para resaltar información neutral o positiva que acentúa o complementa puntos clave del texto principal. Una nota proporciona información que se aplica solo en casos especiales.

  ![](./media/custom-markdown-extensions/Notes-note.PNG)

- Uso de AZURE. ADVERTENCIA para avisar al usuario a una condición que podría provocar un problema en el futuro. Por ejemplo, al seleccionar una opción determinada o tomar una decisión específica, es posible que ya no pueda dar marcha atrás.

  ![](./media/custom-markdown-extensions/Notes-warning.PNG)

- Uso de AZURE. SUGERENCIA para ayudar a los usuarios a aplicar las técnicas y los procedimientos descritos en el texto a sus necesidades específicas. Una sugerencia también podría recomendar métodos alternativos que puede que no sean evidentes. Sin embargo, las sugerencias no son esenciales para comprender el texto en líneas generales.

  ![](./media/custom-markdown-extensions/Notes-tip.PNG)

- Uso de AZURE. Es IMPORTANTE para proporcionar información esencial para la realización de una tarea.

  ![](./media/custom-markdown-extensions/Notes-important.PNG)

Aunque estas notas y sugerencias son compatibles con vínculos, imágenes, listas y bloques de código, trate de lograr siempre que las notas y sugerencias sean simples y directas. Si está creando notas complejas con gran cantidad de formato, podría ser un indicio de que necesita otra sección en el texto principal del artículo. Asimismo, el uso de demasiadas notas en un artículo puede ser molesto y dificultar la lectura.

###Marcado de muestra

Los ejemplos todos muestran un AZURE. TENGA EN CUENTA. Para usar TIP, WARNING o IMPORTANT, reemplace "NOTE" en el marcado:

    > [AZURE.TIP]

    > [AZURE.WARNING]

    > [AZURE.IMPORTANT]

Un solo párrafo:

    > [AZURE.NOTE] Para completar este tutorial, debe tener una cuenta activa de Microsoft Power BI. Si no tiene una cuenta, puede crear una cuenta de evaluación gratuita en un par de minutos.

Varios párrafos:

    > [AZURE.NOTE] Para completar este tutorial, debe tener una cuenta activa de Microsoft Power BI.
    >
    > Si no tiene una cuenta, puede [crear una cuenta gratuita](http://www.windowsPower BI.com/pricing/free-trial/) en tan solo unos minutos.

## Incluye

Fragmentos de texto reutilizable en nuestro repositorio de GitHub se denominan "incluye". Si tiene texto que debe usarse en varios artículos, incluya una referencia a los fragmentos de texto en los archivos Markdown. El fragmento de texto (incluir) es un archivo simple descuento (.md). Puede contener cualquier marcado válido, como texto, vínculos e imágenes. Todos incluyen reducciones de archivos deben estar en [el incluye el directorio](https://github.com/azure/powerbi-content/tree/master/includes) en la raíz del repositorio. Cuando se publica el artículo, el texto de inclusión se integra perfectamente con el tema publicado.

- Utilizamos una sintaxis específica para hacer referencia a una instrucción include.

- Los archivos multimedia que se colocan en una instrucción include deben crearse en una carpeta de medios específicos de la inclusión. Incluye las carpetas de medios para pertenecen a [la carpeta de powerbi contenido/incluye/medio](https://github.com/azure/powerbi-content/tree/master/includes/media). El directorio media no debe contener todas las imágenes en su raíz. Si la inclusión no tiene imágenes, no se requiere un directorio de medios correspondientes.

###Uso

- Utilice incluye siempre que necesite el mismo texto que aparezca en varios artículos.
- Incluye están diseñados para usarse para grandes cantidades de contenido, un párrafo o dos, un procedimiento compartido o una sección compartida. No los utilice en unidades más pequeñas que una frase; no se pueden emplear en nombres de producto o frases incompletas.
- No incruste incluye otros incluye. ya que se producirán problemas en el sistema de publicación.
- No comparta elementos multimedia entre archivos. Utilizar un archivo independiente con un nombre único para cada include y el artículo. Almacene el archivo multimedia en la carpeta de medios asociada con la inclusión.
- No utilice un incluye sólo el contenido de un artículo.  Incluye están diseñados para ser complementario para el contenido en el resto del artículo.
- Dado que todas las inclusiones debe estar en el incluye el directorio, la ruta de acceso include de un artículo es siempre

    .. incluye

- No se repiten una referencia de nombre de archivo de vínculo o una imagen en el artículo e incluir. Agregue "-incluyen" para el nombre de archivo vínculo multimedia o de referencia para evitar la repetición de la referencia:

 **Referencia de vínculo**

 Cambio: odata.org a: incluir odata.org

 **Referencia de imagen**

 Cambio: table.png a: include.png de tabla

###Marcado de muestra
La sintaxis para agregar una inclusión a un artículo de documentación es:

    [AZURE.INCLUDE [include-short-name](../includes/include-file-name.md)]

Ejemplo

    [AZURE.INCLUDE [howto-blob-storage](../includes/howto-blob-storage.md)]

La primera parte de la inclusión es el nombre de inclusión sin la ruta de acceso y sin la extensión .md. La segunda parte es la ruta de acceso relativa a la inclusión en el incluye el directorio, con la extensión .md.

###Representación

En la página GitHub representada, la inclusión se representará como sigue:

 [AZURE. INCLUIR el almacenamiento de blobs howto]

En el HTML representado en powerbi.microsoft.com, el código HTML de la incluye se combina con el resto del documento HTML. No obstante, el código HTML contiene HTML comentario con el original incluyen el nombre de archivo de descuento y el hash de la confirmación de GitHub. Este comentario se incluye para poder solucionar problemas, de modo que el contenido de origen pueda identificarse y encontrarse con facilidad en GitHub:

  ![](./media/custom-markdown-extensions/include.png)


## Vídeos insertados

Nuestros artículos técnicos admitirá vídeos embeddeded en artículos técnicos, detalles son TBD (Azure exige Channel 9, pero queremos usar YouTube).


## Selectores de tecnología y plataforma

> [AZURE.NOTE] Esta información es de Azure, pero nos podemos adoptar a selectores en el futuro.

Utilice modificadores de tecnología y plataforma en artículos técnicos al crear varias versiones del mismo artículo con el objetivo de corregir las diferencias de implementación entre plataformas o tecnologías. En la mayoría de los casos, tendrá que emplearlos en nuestro contenido de plataforma móvil para desarrolladores. Actualmente, hay dos tipos diferentes de selectores: [simples](#simple-selectors) y [bidireccionales](#two-way-selectors).

Ya que el mismo descuento selector va en cada tema de la selección, se recomienda colocar el selector para el tema en una instrucción include, a continuación, hacer referencia a los que incluyen en todos los temas que utilizan el mismo selector.

###<a id="simple-selectors"></a>Selectores simples

Los selectores simples (unidireccionales) se representan como un conjunto de botones de opción justo debajo del título. Use estos botones cuando los clientes sólo necesitan elegir entre los temas de un único conjunto de plataforma o tecnología, como. NET, Node.js y Java.  Utilice el siguiente formato de descuento personalizado para los selectores de.  No utilice HTML para las funciones del selector.  

Consulte [Get started with Notification Hubs](http://azure.microsoft.com/documentation/articles/notification-hubs-windows-phone-get-started/) (Introducción a Centros de notificaciones) para ver cómo el autor creó 8 versiones del mismo artículo y usó los selectores para permitir la navegación en todos ellos.

![Ejemplo de selector simple](./media/custom-markdown-extensions/selectors.PNG)

####Sintaxis

    > [AZURE.SELECTOR]
    - 
            [Vincular etiqueta 1 #](link #1 url)
    - [#2 etiqueta del vínculo](link #2 url)

Ejemplo:

    > [AZURE.SELECTOR]
    - 
            [Windows universal](../articles/notification-hubs-windows-store-dotnet-get-started/)
    - [Windows Phone](../articles/notification-hubs-windows-phone-get-started/)
    - [iOS](../articles/notification-hubs-ios-get-started/)
    - [Android](../articles/notification-hubs-android-get-started/)
    - [Kindle](../articles/notification-hubs-kindle-get-started/)
    - [Baidu](../articles/notification-hubs-baidu-get-started/)
    - [Xamarin.iOS](../articles/partner-xamarin-notification-hubs-ios-get-started/)
    - [Xamarin.Android](../articles/partner-xamarin-notification-hubs-android-get-started/)

#### Representación

La imagen anterior muestra la representación en powerbi.microsoft.com. En las páginas de GitHub representadas, los selectores se representan como una lista con viñetas de vínculos.

###<a id="two-way-selectors"></a>Selectores bidireccionales

Los selectores bidireccionales permiten a los usuarios seleccionar un tema de una matriz bidireccional. Esto es esencial cuando una tecnología de Azure, como los servicios móviles es compatible con varias plataformas de back-end, así como varios clientes. Tenga en cuenta lo siguiente:

- Mientras se diseñó como `(Platform | Backend)`, ahora se puede personalizar el texto dropwdown.
- No necesita un elemento de lista en todos los puntos de la matriz, solamente uno en el que haya una dirección URL de un tema y que no esté duplicada.
- El vínculo puede ser cualquier dirección URL, aunque, normalmente, es otro tema de GitHub.

Consulte [Introducción a Mobile Services](http://azure.microsoft.com/en-us/documentation/articles/mobile-services-ios-get-started/) para ver cómo el autor creó 15 versiones del mismo artículo (9 plataformas cliente móviles y 2 plataformas de back-end) y usó los selectores para permitir la navegación en todos ellos. Tenga en cuenta que 3 artículos no tienen las dos versiones de back-end.

![Ejemplo de selectores bidireccionales](./media/custom-markdown-extensions/selector-list.png)

####Sintaxis

    > [AZURE. LISTA de SELECCIÓN (Dropdown1 | Dropdown2)]     - [(Dropdown1Text1 | Dropdown2Text1)](../articles/dropdown1-text1-dropdown2-text1.md)
    - [(Dropdown1Text1 | Dropdown2Text2)](../articles/dropdown1-text1-dropdown2-text1.md)
    - [(Dropdown1Text2 | Dropdown2Text3)](../articles/dropdown1-text1-dropdown2-text1.md)
    - [(Dropdown1Text3 | Dropdown2Text4)](../articles/dropdown1-text1-dropdown2-text1.md)

Ejemplo:

    > [AZURE. SELECTOR-LIST (plataforma | Back-end)]     - [(iOS |. NET)](./mobile-services-dotnet-backend-ios-get-started-push.md)
    - [(iOS | JavaScript)](./mobile-services-javascript-backend-ios-get-started-push.md)
    - [(Windows universal C# |. NET)](./mobile-services-dotnet-backend-windows-universal-dotnet-get-started-push.md)
    - [(Windows universal C# | JavaScript)](./mobile-services-javascript-backend-windows-universal-dotnet-get-started-push.md)
    - [(Windows Phone |. NET)](./mobile-services-dotnet-backend-windows-phone-get-started-push.md)
    - [(Windows Phone | JavaScript)](./mobile-services-javascript-backend-windows-phone-get-started-push.md)
    - [(Android |. NET)](./mobile-services-dotnet-backend-android-get-started-push.md)
    - [(Android | JavaScript)](./mobile-services-javascript-backend-android-get-started-push.md)
    - [(Xamarin iOS | JavaScript)](./partner-xamarin-mobile-services-ios-get-started-push.md)
    - [(Xamarin Android | JavaScript)](./partner-xamarin-mobile-services-android-get-started-push.md)

#### Representación

La imagen anterior muestra la representación en azure.microsoft.com. En las páginas de GitHub representadas, los selectores se representan como una lista con viñetas de vínculos.

<!--Anchors-->
[Notas y sugerencias]: #notes-and-tips
[Incluye]: #includes
[Vídeos insertados]: #embedded-videos
[Selectores de tecnología y plataforma]: #technology-and-platform-selectors

###Vínculos de la Guía de los colaboradores

- [Artículo de información general](./../README.md)
- [Índice de artículos de la guía](./contributor-guide-index.md)

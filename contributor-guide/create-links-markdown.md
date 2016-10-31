<properties
   pageTitle="Crear vínculos de artículos de descuento" description="Explica cómo codificar vínculos cruzados de descuento." metaKeywords="" services="" solutions="" documentationCenter="" authors="mblythe" videoId="" scriptId="" manager="dongill" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="09/09/2015" ms.author="mblythe" />

# Vinculación de orientación para el contenido técnico de Power BI
## Directrices para artículos técnicos sobre powerbi.microsoft.com

| Escenario de vinculación | Orientación  |
|---------------|-----------|
|Vinculación de un artículo de Power BI para otro artículo de Power BI|Use vínculos relativos. No incluya la en-us configuración regional de idioma en los vínculos relativos.|
|Vincular a un tema de la biblioteca MSDN, un tema de la biblioteca de TechNet o un artículo KB|Use el vínculo real para el artículo o el tema, pero quita la en-us configuración regional de idioma desde el vínculo.|
|Vinculación de un artículo de Power BI a cualquier otra página web|Utilice el vínculo directo.|

### Sintaxis de descuento para los vínculos relativos de Power BI

Para crear un vínculo insertado en un artículo técnico de Power BI para otro artículo técnico de Power BI, use este formato de vínculo.

> [AZURE.NOTE] Algunos aspectos de vinculación siguen siendo TBD b y c que es necesario para liquidar en una estructura final para el repositorio de github.

Artículo que se vincula de un subdirectorio a un artículo del directorio raíz:

    [link text](../article-name.md)

Artículo en los vínculos de directorio raíz para un artículo en un subdirectorio: 

    [link text](section-folder/article-name.md)

Artículo en una sección subdirectorio contiene vínculos a un artículo que se encuentra en otro subdirectorio de sección:

    [link text](../section-folder/article-name.md)
 
Artículo de un directorio que se vincula a otro artículo del mismo directorio:

    [link text](article-name.md)


No es necesario que crear los delimitadores, se generan automáticamente en el tiempo para todos los títulos H2 la publicación. Basta con establecer vínculos a las secciones del tipo H2:

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
    
Obtener más información acerca de cómo usar un incluye el archivo en el [instrucciones de extensiones de descuento personalizado](custom-markdown-extensions.md#includes).

Si cuenta con selectores incrustados en un archivo de inclusión, utilice este tipo de vinculación: 

    > [AZURE. LISTA de SELECCIÓN (Dropdown1 | Dropdown2)]     - [(Text1 | Ejemplo1)](../articles/section-folder/article-name1.md)
    - [(Text1 | Ejemplo2)](../articles/section-folder/article-name2.md)
    - [(Text2 | Example3)](../articles/section-folder/article-name3.md)
    - [(Text2 | Example4)](../articles/section-folder/article-name4.md)

Para vincular a una página de Power BI (por ejemplo, una página de precios, página de SLA o cualquier otra cosa que no es un artículo de documentación), utiliza una dirección URL absoluta, pero se omite la configuración regional. La finalidad es que los vínculos funcionen en GitHub y en el sitio representado:

    [link text](http://powerbi.microsoft.com/pricing/)

Para comprobar los vínculos, la página de inserción en la bifurcación y verlo en la vista representada y publicación en ensayo. Los vínculos entre la versión de GitHub de la página deberían funcionar como los destinos de las direcciones URL están presentes en la bifurcación.

Nuestro [plantilla de descuento para artículos técnicos](../markdown templates/markdown-template-for-new-articles.md/) muestra una manera alternativa para crear vínculos cruzados de descuento para todos los vínculos cruzados se codifican juntos al final del artículo, aunque muestran insertados.

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

Evite FWLinks (nuestro sistema de redirección) en el contenido de powerbi.microsoft.com. Debe utilizarse sólo como último recurso cuando necesite crear un vínculo de una página cuya dirección URL que aún no se conoce. Casi nunca son necesarios. Para Power BI, defina el nombre de archivo para saber cuál será antes de tiempo. Un tema de biblioteca que no se ha publicado, puede crear un vínculo que utiliza el tema GUID para que no tiene que usar un FWLink.

Si debe utilizar un FWLink en una página web, incluya el parámetro P para realizar una redirección permanente:

    http://go.microsoft.com/fwlink/p/?LinkId=389595

Al pegar la dirección URL de destino en la herramienta FWLink, no olvide quitar la configuración regional si el vínculo de destino es la biblioteca de Power BI, o bien el MSDN o TechNet.

### Vínculos de la Guía de los colaboradores

- [Artículo de información general](./../README.md)
- [Índice de artículos de la guía](./contributor-guide-index.md)

<!--image references-->
[1]: ./media/create-tables-markdown/table-markdown.png
[2]: ./media/create-tables-markdown/break-tables.png

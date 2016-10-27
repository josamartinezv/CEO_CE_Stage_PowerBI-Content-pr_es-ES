<properties
    pageTitle="Create images in markdown"
    description="Explains how to create images in markdown according to guidelines set for the Power BI repositories."
    services=""
    solutions=""
    documentationCenter=""
    authors="mblythe"
    manager="dongill"
    editor="NA"/>

<tags
    ms.service="contributor-guide"
    ms.devlang=""
    ms.topic="article"
    ms.tgt_pltfrm=""
    ms.workload=""
    ms.date="05/19/2016"
    ms.author="mblythe" />

# Create images in markdown

## Creación de carpetas de imágenes y sintaxis de vínculos

For a new article, you'll need to create a folder in the following location on your local file system:

    /articles/media/<article-name>/

Por ejemplo:

    /articles/media/powerbi-analysis-services-connector/

Después de crear la carpeta y añadirle imágenes, emplee la sintaxis siguiente para crear imágenes en el artículo:

```
![Alt image text](./media/article-name/your-image-filename.png)
```

Then use the standard sync and pull request process so that your new images are merged into the master repo.

Ejemplo:

See <bpt id="p1">[</bpt>the markdown template<ept id="p1">](https://raw.githubusercontent.com/Azure/powerbi-content-pr/master/examples/_markdown-template.md)</ept> for an example.  The image call references in this markdown template are designed so the calls are made to image references at the bottom of the template.

## Guidelines specific to powerbi.microsoft.com

> [AZURE.NOTE] We will revise this section based on art guidelines specific to Power BI.

Screenshots are currently encouraged if it's not possible to include repro steps. Redacte el contenido de forma que pueda comprenderse sin las capturas de pantalla en caso de que fuera necesario.

Siga estas instrucciones a la hora de crear e incluir archivos de imágenes:
- Do not share art files across documents. Copy the file you need and add it to the media folder for your specific topic. Sharing between files is discouraged because it is easier to remove deprecated content and images which keeps the repo clean.

- .png files are highly preferred over other formats.

-   When possible, create your screengrabs uisng the Retail Analysis sample that is included with Power BI. If that sample doesn't work for what you're trying to demonstrate, use one of the other official sanctioned Power BI samples (to see the samples, in Power BI service, Get data &gt; Samples).

- Use pink squares of the default width provided in Paint (5 px) or SnagIt to call attention to particular elements in screenshots.  

    Ejemplo:
    
    ![En este ejemplo, se muestra la utilización de un cuadrado rojo como llamada.](./media/create-images-markdown/gs13noauth.png)
    
-   Use blue arrows (default size and shape in SnagIt!) to call attention to particular elements in screenshots...when a pink box is not enough, or to show a particular order of steps, or to point out something small.

    Ejemplo:
    
    ![This is an example of a blue arrow used as a callout.](./media/create-images-markdown/power-bi-see-data.png)

- Avoid whitespace on edges of screenshots. Si recorta una captura de pantalla de forma que le quede un fondo blanco en los márgenes, agregue un borde gris de un solo píxel alrededor de la imagen.  If using Paint, use the lighter gray in the default color pallete (0xC3C3C3). If using some other graphic app, the RGB color is R195, G195, 195. You can easily add a gray border around an image in Visio--to do this, select the image, select Line, and ensure the the correct color is set, and then change the line weight to 1 1/2 pt.  Screenshots should have a 1-pixel-wide gray border so that white areas of the screenshot do not blur into the web page.

    Ejemplo:

    ![En este ejemplo, aparece un borde gris rodeando un espacio en blanco.](./media/create-images-markdown/agent.png)

- Conceptual images with whitespace are allowed to not have a gray boder.  
    
    Ejemplo:
    
    ![En este ejemplo, se puede ver una imagen conceptual con espacio en blanco y sin borde gris.](./media/create-images-markdown/ic727360.png)

- Trate de no crear una imagen demasiado ancha.  En caso contrario, su tamaño se ajustará de forma automática. However, the resizing sometimes causes fuzziness, so we recommend that you limit the width of your images to a maximum of 780 px, and manually resize images before submission if necessary.

-   We recommend the following sizes: 780 pixels wide as a maximum.  5 inches wide at 120dpi for large screenshots.  4 inches wide at 120dpi for others.  Smaller than 4 inches is fine as long as the screenshot conveys what it needs at the smaller size. And, as mentioned above, try to capture what is needed at the pixel width and size that you need so that no resizing is necessary.

-   For inline icons, size to be at least 30 pixels x 30 pixels.  

    Ejemplo:
    
    ![This is an example of max size for an inline image](./media/create-images-markdown/power-bi-vertical-icon.png)

- Muestre salidas de comandos en capturas de pantalla.  Si el artículo incluye pasos en los que el usuario debe utilizar un shell, resultará de utilidad mostrar salidas de comandos en tales imágenes. In this case, restricting your shell width to about 72 characters generally ensures that your image will remain within the 780 px width guideline. Antes de realizar la captura de pantalla de una salida, ajuste la ventana de forma que se muestre únicamente el comando y la salida pertinentes (de manera opcional, puede incluir una línea blanca a cada lado).

- Maximum size of screenshots: Take whole screenshots of windows when possible. When taking a screenshot of a browser window, resize your browser window to 780 px wide or less, and keep the height of the browser window as short as possible such that your application fits within the window.  

    Ejemplo:

    ![En este ejemplo, se muestra la captura de pantalla de la ventana de un navegador.](./media/create-images-markdown/helloworldlocal.png)

- Tenga cuidado con la información que revela en las capturas de pantalla.  Do not reveal internal company information or personal information.  If you can't avoid including personal information, use the blur tool to obscure it or cut it out and replace with matching color.

- En los diagramas o imágenes conceptuales, recurra a los iconos oficiales del conjunto de símbolos e iconos de Cloud and Enterprise. A public set is available at http://aka.ms/CnESymbols.

###Contributors' Guide Links

- [Artículo de información general](./../README.md)
- [Índice de artículos de la guía](./contributor-guide-index.md)

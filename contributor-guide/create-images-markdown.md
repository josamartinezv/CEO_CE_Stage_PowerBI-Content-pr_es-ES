<properties
    pageTitle="Crear imágenes de descuento"
    description="Explica cómo crear imágenes de descuento según las directrices establecidas para los repositorios de Power BI."
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

# Crear imágenes de descuento

## Creación de carpetas de imágenes y sintaxis de vínculos

Para un nuevo artículo, debe crear una carpeta en la siguiente ubicación en el sistema de archivos local:

    /articles/media/<article-name>/

Por ejemplo:

    /articles/media/powerbi-analysis-services-connector/

Después de crear la carpeta y añadirle imágenes, emplee la sintaxis siguiente para crear imágenes en el artículo:

```
![Alt image text](./media/article-name/your-image-filename.png)
```

A continuación, utilice la sincronización estándar y extraer el proceso de solicitud para que las imágenes nuevas se combinan en el repositorio principal.

Ejemplo:

Consulte [la plantilla de descuento](https://raw.githubusercontent.com/Azure/powerbi-content-pr/master/examples/_markdown-template.md) para obtener un ejemplo.  Las referencias de la llamada de imagen en esta plantilla de descuento están diseñadas para que las llamadas se realizan en las referencias de imagen en la parte inferior de la plantilla.

## Directrices específicas de powerbi.microsoft.com

> [AZURE.NOTE] Revisaremos esta sección según arte instrucciones específicas de Power BI.

Capturas de pantalla actualmente se recomienda si no es posible incluir pasos de reproducción. Redacte el contenido de forma que pueda comprenderse sin las capturas de pantalla en caso de que fuera necesario.

Siga estas instrucciones a la hora de crear e incluir archivos de imágenes:
- No comparta archivos de imágenes prediseñadas entre documentos. Copie el archivo que necesita y agregarlo a la carpeta de medios para el tema específico. No se recomienda compartir entre archivos porque es fácil de quitar en desuso contenido y las imágenes que se mantiene limpio el repositorio.

- archivos .png son altamente preferidos sobre otros formatos.

-   Cuando sea posible, cree su usar screengrabs el ejemplo de análisis de venta que se incluye con Power BI. Si este ejemplo no funciona para lo que está intentando mostrar, utilice uno de los otros ejemplos oficiales de aprobado Power BI (para ver los ejemplos en el servicio de Power BI, obtener datos > ejemplos).

- Usar color rosas cuadrados de ancho predeterminado proporcionado en Paint (5 px) o SnagIt para llamar la atención sobre determinados elementos en capturas de pantalla.  

    Ejemplo:
    
    ![En este ejemplo, se muestra la utilización de un cuadrado rojo como llamada.](./media/create-images-markdown/gs13noauth.png)
    
-   Utilice las flechas azules (tamaño predeterminado y forma SnagIt) para llamar la atención sobre determinados elementos en capturas de pantalla... cuando un cuadro de color rosa no es suficiente, mostrar un orden concreto de pasos o señalar algo pequeño.

    Ejemplo:
    
    ![Este es un ejemplo de una flecha azul que se utiliza como una llamada.](./media/create-images-markdown/power-bi-see-data.png)

- Evite los espacios en blanco en los bordes de capturas de pantalla. Si recorta una captura de pantalla de forma que le quede un fondo blanco en los márgenes, agregue un borde gris de un solo píxel alrededor de la imagen.  Si el uso de Paint, utilice el gris más claro en la paleta de colores predeterminada (0xC3C3C3). Si utiliza otra aplicación de gráficos, el color RGB es R195, G195, 195. Puede agregar fácilmente un borde gris alrededor de una imagen en Visio--para hacerlo, seleccione la imagen, seleccione la línea y garantizar la se establece el color correcto y, a continuación, cambie el grosor de línea a 1 1/2 pto.  Capturas de pantalla deben tener un borde gris de 1 píxel de ancho para que las áreas blancas de la captura de pantalla no desenfoque en la página web.

    Ejemplo:

    ![En este ejemplo, aparece un borde gris rodeando un espacio en blanco.](./media/create-images-markdown/agent.png)

- Imágenes conceptuales con espacios en blanco pueden no tener un boder gris.  
    
    Ejemplo:
    
    ![En este ejemplo, se puede ver una imagen conceptual con espacio en blanco y sin borde gris.](./media/create-images-markdown/ic727360.png)

- Trate de no crear una imagen demasiado ancha.  En caso contrario, su tamaño se ajustará de forma automática. Sin embargo, el cambio de tamaño a veces hace tolerancia, por lo que recomendamos que limite el ancho de las imágenes a un máximo de 780 píxeles y manualmente las imágenes de tamaño antes de su envío, si es necesario.

-   Recomendamos los siguientes tamaños: 780 píxeles de ancho como máximo.  5 pulgadas de ancho a 120 ppp para capturas de pantalla grande.  4 pulgadas de ancho a 120 ppp para que otros usuarios.  Menor que 4 pulgadas está bien siempre y cuando la captura de pantalla transmite lo que necesita en el tamaño más pequeño. Y como se mencionó anteriormente, intenta capturar lo que se necesita en el ancho de píxel y el tamaño necesario para que ningún cambio de tamaño es necesario.

-   Para los iconos en línea, tamaño de al menos 30 píxeles x 30 píxeles.  

    Ejemplo:
    
    ![Este es un ejemplo de tamaño máximo para una imagen en línea](./media/create-images-markdown/power-bi-vertical-icon.png)

- Muestre salidas de comandos en capturas de pantalla.  Si el artículo incluye pasos en los que el usuario debe utilizar un shell, resultará de utilidad mostrar salidas de comandos en tales imágenes. En este caso, restringir el ancho de shell a aproximadamente 72 caracteres generalmente garantiza que la imagen permanezca dentro de la instrucción de ancho 780 px. Antes de realizar la captura de pantalla de una salida, ajuste la ventana de forma que se muestre únicamente el comando y la salida pertinentes (de manera opcional, puede incluir una línea blanca a cada lado).

- Tamaño máximo de capturas de pantalla: realice capturas de pantalla completa de windows cuando sea posible. Al tomar una captura de pantalla de una ventana del explorador, cambie el tamaño de la ventana del explorador a 780 píxeles o menos de ancho y mantener el alto de la ventana del explorador como breves posible que su aplicación entra dentro de la ventana.  

    Ejemplo:

    ![En este ejemplo, se muestra la captura de pantalla de la ventana de un navegador.](./media/create-images-markdown/helloworldlocal.png)

- Tenga cuidado con la información que revela en las capturas de pantalla.  No revele información interna de la compañía o información personal.  Si no se puede evitar incluyendo información personal, utilice la herramienta Desenfoque ocultarlo o recortar y reemplazar con la coincidencia de color.

- En los diagramas o imágenes conceptuales, recurra a los iconos oficiales del conjunto de símbolos e iconos de Cloud and Enterprise. Un conjunto público está disponible en http://aka.ms/CnESymbols.

###Vínculos de la Guía de los colaboradores

- [Artículo de información general](./../README.md)
- [Índice de artículos de la guía](./contributor-guide-index.md)

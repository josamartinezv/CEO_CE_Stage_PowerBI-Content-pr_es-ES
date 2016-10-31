<properties
   pageTitle="Cargar un mosaico de Power BI en un IFrame"
   description="Tutorial para integrar un mosaico en una aplicación - cargar un mosaico en un IFrame"
   services="powerbi"
   documentationCenter=""
   authors="guyinacube"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="monitoring"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="get-started-article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/23/2016"
   ms.author="asaxton"/>

# Paso 4: Cargar un mosaico en un IFrame

## Introducción

En **paso 3** de integración de un mosaico en una aplicación [obtener un mosaico de Power BI](powerbi-developer-integrate-tile-get-tile.md), obtendrá un mosaico de Power BI. En este paso, se carga un mosaico en un **IFrame**.

![](media\powerbi-developer-integrate-tile\integrate-tile-load-tile-iframe.png)

Para cargar un icono en un **IFrame**, Establece el **src** atributo de un **IFrame** a la **embedUrl** propiedad de una **icono**, y crear un **onload** controlador para enviar un mensaje con un **token de acceso** para obtener acceso a la ficha visual. A continuación se muestra código JavaScript para cargar un mosaico en un **IFrame**.

**Cargar un mosaico en un IFrame**

```
//Configure IFrame for the tile after you have an Access Token. See Default.aspx.cs to learn how to get an Access Token
window.onload = function () {
    if ("" != document.getElementById('MainContent_accessToken').value)
    {
        var iframe = document.getElementById('iFrameEmbedTile');

        // To load a tile do the following:
        // Set the IFrame source to the EmbedUrl from the Get Tiles operation
        iframe.src = document.getElementById('MainContent_tileEmbedUrl').value;

        // Add an onload handler to submit the access token
        iframe.onload = postActionLoadTile;
    }
};

// Post the access token to the IFrame
function postActionLoadTile() {

    // Construct the push message structure
    // This is where you assign the Access Token to get access to the tile visual
    var messageStructure = {
        action: "loadTile",
        accessToken: document.getElementById('MainContent_accessToken').value,
        height: 500,
        width: 500
    };
    message = JSON.stringify(messageStructure);

    // Push the message
    document.getElementById('iFrameEmbedTile').contentWindow.postMessage(message, "*");;
}
```

Si ha descargado y ejecutado el [integrar un ejemplo de mosaico](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app), el ejemplo tendrá un aspecto parecido al siguiente.

![](media\powerbi-developer-integrate-tile\integrate-tile-sample.png)

## Conclusión
En este tutorial aprendió a integrar un mosaico en una aplicación tomando el mosaico en un panel y, a continuación, cargar el mosaico en un **IFrame**. Puede descargar la completa [integrar un mosaico de ejemplo](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app)  que muestra todos los elementos de trabajo para incrustar un icono en una aplicación web ASP.NET. También puede ver la sección completa [integrar un mosaico en un listado de código de la aplicación](powerbi-developer-integrate-tile-code.md).

## Consulte también

[Registrarse para Power BI](powerbi-admin-free-with-custom-azure-directory.md)  
[Integrar un mosaico en un tutorial de la aplicación](powerbi-developer-integrate-tile.md)  
[Integrar un mosaico de ejemplo](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app)  
[Configurar la integración de un mosaico de ejemplo](powerbi-developer-integrate-tile-register.md#configure-sample)  
[Paneles de la operación de obtención](https://msdn.microsoft.com/library/mt465739.aspx)  
[Iconos de la operación de obtención](https://msdn.microsoft.com/library/mt465741.aspx)  
¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
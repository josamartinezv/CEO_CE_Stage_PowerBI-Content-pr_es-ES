<properties
   pageTitle="Cargar un informe de Power BI en un IFrame"
   description="Tutorial para integrar un informe en una aplicación - cargar un informe en un IFrame"
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

# Paso 3: Cargar un informe en un IFrame

## Introducción

En **paso 2** de integración de un informe en una aplicación [obtener un informe de Power BI](powerbi-developer-integrate-report-get-report.md), obtendrá un informe de Power BI. En este paso, carga un informe en un **IFrame**.

![](media\powerbi-developer-integrate-report\integrate-report-load-report-iframe.png)

Para cargar un informe en un **IFrame**, Establece el **src** atributo de un **IFrame** a la **embedUrl** propiedad de un **informe**, y crear un **onload** controlador para enviar un mensaje con un **token de acceso** para obtener acceso al informe visual. A continuación se muestra código JavaScript para cargar un informe en un **IFrame**.

**Cargar un informe en un IFrame**

```
//Configure IFrame for the report after you have an Access Token. See Default.aspx.cs to learn how to get an Access Token
window.onload = function () {
    if ("" != document.getElementById('MainContent_accessToken').value)
    {
        var iframe = document.getElementById('iFrameEmbedReport');

        // To load a Report do the following:
        // Set the IFrame source to the EmbedUrl from the Get Reports operation
        iframe.src = document.getElementById('MainContent_ReportEmbedUrl').value;

        // Add an onload handler to submit the access token
        iframe.onload = postActionLoadReport;
    }
};

// Post the access token to the IFrame
function postActionLoadReport() {

    // Construct the push message structure
    // this structure also supports setting the reportId, groupId, height, and width.
    // when using a report in a group, you must provide the groupId on the iFrame SRC
    var m = {
        action: "loadReport",
        accessToken: document.getElementById('MainContent_accessToken').value
    };
    message = JSON.stringify(m);

    // push the message.
    iframe = document.getElementById('iFrameEmbedReport');
    iframe.contentWindow.postMessage(message, "*");;
}
```

Si ha descargado y ejecutado el [integrar un informe de ejemplo](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-report-web-app), el ejemplo tendrá un aspecto parecido al siguiente.

![](media\powerbi-developer-integrate-report\integrate-report-sample.png)

## Conclusión
En este tutorial ha aprendido cómo integrar un informe en una aplicación mediante la obtención de un informe y, a continuación, cargar el informe en un **IFrame**. Puede descargar la completa [integrar un informe de ejemplo](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-report-web-app)  que muestra todos los elementos de trabajo para incrustar un informe en una aplicación web ASP.NET. También puede ver la sección completa [integrar un informe en un listado de código de la aplicación](powerbi-developer-integrate-report-code.md).

## Consulte también

[Registrarse para Power BI](powerbi-admin-free-with-custom-azure-directory.md)  
[Integrar un informe en un tutorial de la aplicación](powerbi-developer-integrate-report.md)  
[Integrar un informe de ejemplo](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-report-web-app)  
[Configurar la integración de un informe de ejemplo](powerbi-developer-integrate-report-register.md#configure-sample)  
[Operación de informes de obtención de](https://msdn.microsoft.com/library/mt634543.aspx)  
¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
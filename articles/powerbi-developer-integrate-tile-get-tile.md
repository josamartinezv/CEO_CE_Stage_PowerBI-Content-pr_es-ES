<properties
   pageTitle="Obtener un mosaico de Power BI"
   description="Tutorial: integrar un mosaico en una aplicación: registrar una aplicación web con Azure AD"
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

# Paso 3: Obtener un mosaico

## Introducción

En **paso 2** de integración de un mosaico en una aplicación [un panel de Power BI](powerbi-developer-integrate-tile-get-dashboard.md), obtendrá un panel de Power BI. En este paso, obtendrá un **Power BI** icono desde un panel.

![](media\powerbi-developer-integrate-tile\integrate-tile-get-tile.png)

Para obtener un **Power BI** mosaico necesita una autenticación **token de acceso**. Para obtener información sobre cómo obtener un **token de acceso**, consulte [obtener un token]((powerbi-developer-integrate-tile-get-dashboard.md#get-token) de acceso de autenticación en el paso 2: un panel de Power BI. Utiliza un **token de acceso** para autenticarse en **Azure AD** para tener acceso a **Power BI** mosaicos.

Estos son los pasos para obtener un mosaico de Power BI.

- 
            **Paso 1:** obtener un código de autorización de Azure AD. Consulte [obtener un código de autorización de Azure AD](powerbi-developer-integrate-tile-get-dashboard.md#auth-code) en el paso 2: un panel de Power BI.
- 
            **Paso 2:** obtener un token de acceso. Consulte [obtener un acceso token del código de autorización](powerbi-developer-integrate-tile-get-dashboard.md#access-token) paso 2: un panel de Power BI.
- 
            **Paso 3:** [obtener un mosaico de Power BI](#get-tile)

<a name="get-tile"/>
## Obtener un mosaico de Power BI con access token

En el paso 2 de la [integrar un mosaico en un tutorial de la aplicación](powerbi-developer-integrate-tile.md), obtendrá un **token de acceso** a un panel. Puede utilizar este **token de acceso** también obtener un mosaico. Obtener un icono con el [obtener mosaicos](https://msdn.microsoft.com/library/mt465741.aspx)  operación que devuelve una lista de mosaicos en un **panel**. A continuación se muestra un método de C# para obtener un mosaico. Una vez que tenga una **icono**, puede cargar el mosaico en un **IFrame**. Consulte [cargar un mosaico de Power BI en un IFrame](powerbi-developer-integrate-tile-load-tile-iframe.md).

**Obtener el mosaico**

```
//Get a tile from a dashboard. In this sample, you get the first tile.
protected void GetTile(string dashboardId, int index)
{
    //Configure tiles request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}Dashboards/{1}/Tiles",
        baseUri,
        dashboardId)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get tiles response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBITiles tiles = JsonConvert.DeserializeObject<PBITiles>(reader.ReadToEnd());

            //Sample assumes at least one Dashboard with one Tile.
            //You could write an app that lists all tiles in a dashboard
            if (tiles.value.Length > 0)
                tileEmbedUrl.Text = tiles.value[index].embedUrl;
        }
    }
}

//Power BI Tiles used to deserialize the Get Tiles response.
public class PBITiles
{
    public PBITile[] value { get; set; }
}
public class PBITile
{
    public string id { get; set; }
    public string title { get; set; }
    public string embedUrl { get; set; }
}
```

## Paso siguiente

Para integrar un mosaico en una aplicación, carga un mosaico en un IFrame. En el paso siguiente, aprenderá cómo [cargar un mosaico en un IFrame](powerbi-developer-integrate-tile-load-tile-iframe.md).

[Siguiente paso >](powerbi-developer-integrate-tile-load-tile-iframe.md)

## Consulte también

[Registrarse para Power BI](powerbi-admin-free-with-custom-azure-directory.md)  
[Integrar un mosaico en un tutorial de la aplicación](powerbi-developer-integrate-tile.md)  
[Integrar un mosaico de ejemplo](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app)  
[Configurar la integración de un mosaico de ejemplo](powerbi-developer-integrate-tile-register.md#configure-sample)  
[Paneles de la operación de obtención](https://msdn.microsoft.com/library/mt465739.aspx)  
[Iconos de la operación de obtención](https://msdn.microsoft.com/library/mt465741.aspx)  
[Paso 4: Cargar un mosaico de Power BI en un IFrame](powerbi-developer-integrate-tile-load-tile-iframe.md)  
¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)

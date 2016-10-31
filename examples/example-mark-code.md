<properties pageTitle="Ejemplo de documentación: código en línea" metaKeywords="" description="Esto es un ejemplo de documento" services="" documentationCenter="" title="Documentation Example - Inline code" authors="jamescon" solutions="" videoId="" scriptId="" />

# Ejemplo: código #
Se trata de un artículo de la documentación de ejemplo que se usa para probar y validar el sistema de publicación para Azure.com.  

El contenido entre las líneas siguientes muestra en las secciones de resaltado dentro de un fragmento de código mediante la <mark> etiqueta.

---

1. Fragmento de código en línea `console.log(<mark>"sometext"</mark>)` 

1. Bloque de código creado con  **PRE** y **CÓDIGO** etiquetas

<pre><code>
static private IAsset CreateEmptyAsset(string assetName, AssetCreationOptions assetCreationOptions)
{
    var asset = _context.Assets.Create(assetName, assetCreationOptions);

    Console.WriteLine(<mark>"Asset name: " + asset.Name</mark>);
    Console.WriteLine(<mark>"Time created: " + asset.Created.Date.ToString());
    Console.WriteLine("Time closed: " + asset.Closed.Date.ToString()</mark>);
    
    return asset;
}
</code></pre>

1. Bloque de código creado con  \`\`\`\` sintaxis (4)

````C#
static private IAsset CreateEmptyAsset(string assetName, AssetCreationOptions assetCreationOptions)
{
    var asset = _context.Assets.Create(assetName, assetCreationOptions);

    Console.WriteLine(<mark>"Asset name: " + asset.Name</mark>);
    Console.WriteLine(<mark>"Time created: " + asset.Created.Date.ToString());
    Console.WriteLine("Time closed: " + asset.Closed.Date.ToString()</mark>);
    
    return asset;
}
````

1. Bloque de código creado con  \`\`\` sintaxis (3)

```C#
static private IAsset CreateEmptyAsset(string assetName, AssetCreationOptions assetCreationOptions)
{
    var asset = _context.Assets.Create(assetName, assetCreationOptions);

    Console.WriteLine(<mark>"Asset name: " + asset.Name</mark>);
    Console.WriteLine(<mark>"Time created: " + asset.Created.Date.ToString());
    Console.WriteLine("Time closed: " + asset.Closed.Date.ToString()</mark>);

    return asset;
}
```

---

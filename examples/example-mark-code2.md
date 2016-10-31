<properties pageTitle="Ejemplo de documentación: marcar código" metaKeywords="" description="Esto es un ejemplo de documento" services="" documentationCenter="" title="Documentation Example - Inline code" solutions="" authors="" videoId="" scriptId="" />

# Ejemplo: marcar código #

En este ejemplo se ha tomado de http://www.asp.net/mvc/tutorials/mvc-5/introduction/adding-a-view para mostrar cómo agregar etiquetas de marca dentro de un fragmento de código

---
...

Cuando se creó el archivo Views\HelloWorld\Index.cshtml, incluye el código siguiente:

````
@{
    Layout = "~/Views/Shared/_Layout.cshtml";
}
````
    
El código Razor anterior es explicted establecer la página de diseño. Examinar las vistas\_archivo ViewStart.cshtml, que contiene el mismo marcado exacto de Razor. TheViews\_ViewStart.cshtml archivo define el diseño común que usan todas las vistas, por lo tanto, puede comentar o elimine ese código desde el archivo Views\HelloWorld\Index.cshtml.

````
<mark>@*@{
    Layout = "~/Views/Shared/_Layout.cshtml";
}*@</mark>

@{
    ViewBag.Title = "Index";
}

<h2>Index</h2>

<p>Hello from our View Template!</p>
````

Se puede utilizar la propiedad de diseño para establecer la vista de diseño diferente o se establece en null de modo que no se usará ningún archivo de diseño.

Ahora, vamos a cambiar el título de la vista de índice.

Abra MvcMovie\Views\HelloWorld\Index.cshtml. Hay dos lugares para realizar un cambio: en primer lugar, el texto que aparece en el título del explorador y, a continuación, en el encabezado secundario (el &lt;h2&gt; elemento). Hará que ligeramente diferente para que pueda ver qué parte de código cambia qué parte de la aplicación.

````
@{
    ViewBag.Title = "<mark>Movie List</mark>";
}

<h2><mark>My Movie List</mark></h2>

<p>Hello from our View Template!</p>
````

Para indicar el título HTML para mostrar, el código anterior establece una propiedad Title del objeto ViewBag (que se encuentra en la plantilla de vista de Index.cshtml). Observe que la plantilla de diseño (Views\Shared\_Layout.cshtml) usa este valor en el &lt;título&gt; elemento como parte de la &lt;head&gt; sección del código HTML que hemos modificado anteriormente.

````
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title><mark>@ViewBag.Title</mark> - Movie App</title>
    @Styles.Render("~/Content/css")
    @Scripts.Render("~/bundles/modernizr")
</head>
````

Con este enfoque ViewBag, puede pasar fácilmente otros parámetros entre la plantilla de vista y el archivo de diseño.

Ejecute la aplicación. Observe que el título del explorador, el encabezado principal y los títulos secundarios han cambiado. (Si no ve los cambios en el explorador, puede que esté viendo contenido almacenado en caché. Presione CTRL+F5 en el explorador para forzar la respuesta del servidor al que se va a cargar.) El título del explorador se crea con el ViewBag.Title se establece en la plantilla de vista de Index.cshtml y adicionales "-aplicación de película" agregado en el archivo de diseño.

Observe también que el contenido de la plantilla de vista de Index.cshtml se combinó con la plantilla de vista _Layout.cshtml y una sola respuesta HTML se envía al explorador. Plantillas de diseño facilitan realmente realizar cambios que se aplicarán a todas las páginas de la aplicación.

...

---

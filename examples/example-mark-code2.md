<properties pageTitle="Documentation Example - Mark code" metaKeywords="" description="This is an example document" services="" documentationCenter="" title="Documentation Example - Inline code" solutions="" authors="" videoId="" scriptId="" />

# Example - Mark Code #

This sample has been taken from http://www.asp.net/mvc/tutorials/mvc-5/introduction/adding-a-view to show how to add mark tags inside a snippet

---
...

When we first created the Views\HelloWorld\Index.cshtml file, it contained the following code:

````
@{
    Layout = "~/Views/Shared/_Layout.cshtml";
}
````
    
The Razor code above is explicted setting the layout page. Examine the Views<ph id="ph1">\_</ph>ViewStart.cshtml file, it contains the exact same Razor markup. TheViews<ph id="ph1">\_</ph>ViewStart.cshtml file defines the common layout that all views will use, therefore you can comment out or remove that code from the  Views\HelloWorld\Index.cshtml file.

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

You can use the Layout property to set a different layout view, or set it to null so no layout file will be used.

Now, let's change the title of the Index view.

Open MvcMovie\Views\HelloWorld\Index.cshtml. There are two places to make a change: first, the text that appears in the title of the browser, and then in the secondary header (the <ph id="ph1">&amp;lt;</ph>h2<ph id="ph2">&amp;gt;</ph> element). You'll make them slightly different so you can see which bit of code changes which part of the app.

````
@{
    ViewBag.Title = "<mark>Movie List</mark>";
}

<h2><mark>My Movie List</mark></h2>

<p>Hello from our View Template!</p>
````

To indicate the HTML title to display, the code above sets a Title property of the ViewBag object (which is in the Index.cshtml view template). Notice that the layout template  ( Views\Shared<ph id="ph1">\_</ph>Layout.cshtml ) uses this value in the <ph id="ph2">&amp;lt;</ph>title<ph id="ph3">&amp;gt;</ph> element as part of the <ph id="ph4">&amp;lt;</ph>head<ph id="ph5">&amp;gt;</ph> section of the HTML that we modified previously.

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

Using this ViewBag approach, you can easily pass other parameters between your view template and your layout file.

Ejecute la aplicación. Notice that the browser title, the primary heading, and the secondary headings have changed. (If you don't see changes in the browser, you might be viewing cached content.  

Also notice how the content in the Index.cshtml view template was merged with the _Layout.cshtml view template and a single HTML response was sent to the browser. Layout templates make it really easy to make changes that apply across all of the pages in your application.

...

---

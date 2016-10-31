<properties pageTitle="Comandos de GIT para almacenar provisionalmente un artículo nuevo o actualizado" description="Pasos para la retirada y cambiar el nombre de los artículos." metaKeywords="" services="" solutions="" documentationCenter="" authors="mblythe" videoId="" scriptId="" manager="dongill" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="09/09/2015" ms.author="mblythe" />

# Pasos a seguir al retirar o cambiar el nombre de un artículo técnico de Power BI

Esta guía es para PYME que aparecen como el autor de un artículo que necesita se retira de la sección de documentación técnica de powerbi.microsoft.com. Los pasos también se aplican si se le cambia el nombre a un archivo.

Si es miembro de nuestra comunidad de Power BI y cree un artículo que se debe retirar por cualquier motivo, deje un comentario en la secuencia de comentario de Disqus para el artículo informar al autor de que algo no funciona correctamente con el artículo.

Los autores expertos en la materia deben seguir varios pasos para retirar de manera correcta el contenido de forma que la experiencia de los usuarios del sitio web no se vea afectada negativamente cuando se elimine el artículo del sitio. La eliminación del artículo o el cambio de nombre deben ser los últimos pasos.

## Paso 1: Administración de vínculos de entrada

Compruebe si existen vínculos de entrada al contenido que no sean de Microsoft. Con frecuencia, blogs, foros y otro contenido en la web apunta a artículos. A menudo, puede trabajar con los propietarios del blog para modificar estos vínculos, así como eliminar o actualizar los que aparezcan en publicaciones de foros. Herramientas de análisis de Web pueden indicarle si hay cualquier vínculo de mucho tráfico entrante que tenga que administrar de esta manera.

## Paso 2: Quitar todos los vínculos cruzados para el artículo desde el repositorio de contenido técnico

1. Asegúrese de que está trabajando en una bifurcación local actualizada – ejecutar `git pull upstream master` (o la variación adecuada en este comando.

2.  Analizar la carpeta de Power BI-contenido-pr/artículos y la carpeta powerbi-contenido-pr/incluye cualquiera artículos e incluye ese vínculo para el artículo que desea retirar y quite los vínculos cruzados o reemplazarlos con vínculos cruzados nuevo adecuado. Puede usar una búsqueda y reemplace la utilidad para buscar los vínculos cruzados si tiene uno instalado. En caso contrario, puede usar Windows PowerShell de forma gratuita. Aquí se muestra cómo usar PowerShell para buscar los vínculos cruzados:

 a. Inicie Windows PowerShell.

 b. En el símbolo del sistema de PowerShell, cambie a la carpeta de contenido de Power BI de pr\articles:

 `cd powerbi-content-pr\articles`

 c. Escriba este comando, que creará una lista con todos los archivos que contengan referencias al artículo que va a eliminar:

 `Get-ChildItem -Recurse -Include *.md* | Select-String "<the name of the topic you are deleting>" | group path | select name`

  Si prefiere enviar la lista con los nombres de los archivos a un archivo de texto (en este case, denominado "psoutput.txt"), puede realizar lo siguiente:

  `Get-ChildItem -Recurse -Include *.md* | Select-String "<the name of the topic you are deleting>" | group path | select name | Out-File C:\Users\<your account>\psoutput.txt`

3. Agregar y confirmar todos los cambios, insertarlas en la bifurcación y crear una solicitud de extracción para mover los cambios de la bifurcación a la rama principal del repositorio principal.

## Paso 3: Actualizar la herramienta FWLink

Busque la herramienta FWLink cualquier FWLinks que puede señalar el artículo. Elija cualquier FWLinks al contenido de reemplazo; Si no está en el alias al que pertenece el vínculo, unirse a él. Si los propietarios no actualizarán el vínculo, presentar una incidencia a MSCOM para que el vínculo cambiarlo.

## Paso 4: Crear una redirección para la página retirada, si es necesario

Enviar correo electrónico a mblythe 4 p.m. los jueves - con la dirección URL que se va a cambiar el nombre o retirar y la dirección URL a la que debe redirigirse. Vínculos a los viernes de ingeniería para que la ingeniería puede colocar 301 redirecciones en lugar que vaya a presentar.

## Paso 5: Actualización de la tabla de Contenido

Quite la entrada de tabla de Contenido para el artículo. Si el artículo estaba en el conjunto "featured", asegúrese de que el número de artículos destacados continúa siendo adecuado.

## Paso 6: Retirar el artículo

Una vez que haya completado los tres pasos anteriores y que los cambios se hayan hecho efectivos, puede eliminar el artículo del repositorio.

## Paso 7: Quitar páginas en caché de los motores de búsqueda

Vaya a estas páginas web para quitar páginas web en caché de los motores de búsqueda: [Bing](https://www.bing.com/webmaster/tools/content-removal?rflid=1) y [Google](https://www.google.com/webmasters/tools/removals?pli=1)


### Vínculos de la Guía de los colaboradores

- [Artículo de información general](./../README.md)
- [Índice de artículos de la guía](./contributor-guide-index.md)

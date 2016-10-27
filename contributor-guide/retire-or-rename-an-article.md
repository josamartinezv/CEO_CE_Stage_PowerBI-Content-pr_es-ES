<properties pageTitle="Git commands for staging an new or updated article" description="Steps for retiring and renaming articles." metaKeywords="" services="" solutions="" documentationCenter="" authors="mblythe" videoId="" scriptId="" manager="dongill" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="09/09/2015" ms.author="mblythe" />

# Steps to follow when you retire or change the name of a Power BI technical article

This guidance is for SMEs who are listed as the author of an article that needs to be retired from the technical documentation section of powerbi.microsoft.com. Los pasos también se aplican si se le cambia el nombre a un archivo.

If you're a member of our Power BI community and you think an article should be retired for any reason, please leave a comment in the Disqus comment stream for the article to let the author know something is wrong with the article.

Los autores expertos en la materia deben seguir varios pasos para retirar de manera correcta el contenido de forma que la experiencia de los usuarios del sitio web no se vea afectada negativamente cuando se elimine el artículo del sitio. La eliminación del artículo o el cambio de nombre deben ser los últimos pasos.

## Paso 1: Administración de vínculos de entrada

Compruebe si existen vínculos de entrada al contenido que no sean de Microsoft. Frequently, blogs, forums, and other content on the web points to articles. A menudo, puede trabajar con los propietarios del blog para modificar estos vínculos, así como eliminar o actualizar los que aparezcan en publicaciones de foros. Web analytics tools can tell you if there are any high traffic inbound links you might need to manage in this way.

## Step 2: Remove all crosslinks to the article from the technical content repository

1. Ensure you are working in an up-to-date local branch – run <ph id="ph1">`git pull upstream master`</ph> (or the appropriate variation on this command.

2.  Scan the powerbi-content-pr/articles folder and the powerbi-content-pr/includes folder for any articles and includes that link to the article you want to retire, and either remove the crosslinks or replace them with appropriate new crosslinks. You can use a search and replace utility to find the crosslinks if you have one installed. En caso contrario, puede usar Windows PowerShell de forma gratuita. Here's how to use PowerShell to find the crosslinks:

 a. Inicie Windows PowerShell.

 b. At the PowerShell prompt, change into the powerbi-content-pr\articles folder:

 `cd powerbi-content-pr\articles`

 c. Escriba este comando, que creará una lista con todos los archivos que contengan referencias al artículo que va a eliminar:

 `Get-ChildItem -Recurse -Include *.md* | Select-String "<the name of the topic you are deleting>" | group path | select name`

  Si prefiere enviar la lista con los nombres de los archivos a un archivo de texto (en este case, denominado "psoutput.txt"), puede realizar lo siguiente:

  `Get-ChildItem -Recurse -Include *.md* | Select-String "<the name of the topic you are deleting>" | group path | select name | Out-File C:\Users\<your account>\psoutput.txt`

3. Add and commit all your changes, push them to your fork, and create a pull request to move your changes from your fork to the master branch of the main repository.

## Step 3: Update the FWLink tool

Check the FWLink tool for any FWLinks that might point to the article. Point any FWLinks at replacement content; if you are not on the alias that owns the link, join it. If the owners won't update the link, file a ticket with MSCOM to have the link changed.

## Step 4: Create a redirect for the retired page, if appropriate

Send mail to mblythe by 4pm on Thursdays - with the URL that you are renaming or retiring and the URL to which it should redirect. He will submit links to engineering on Fridays so that engineering can put 301 redirects in place.

## Step 5: Update the TOC

Remove the TOC entry for the article. If the article was in the "featured" set, make sure the featured articles number is still appropriate.

## Step 6: Retire the article

Una vez que haya completado los tres pasos anteriores y que los cambios se hayan hecho efectivos, puede eliminar el artículo del repositorio.

## Step 7: Remove cached pages from search engines

Go to these web pages to remove cached web pages from search engines: <bpt id="p1">[</bpt>Bing<ept id="p1">](https://www.bing.com/webmaster/tools/content-removal?rflid=1)</ept> and <bpt id="p2">[</bpt>Google<ept id="p2">](https://www.google.com/webmasters/tools/removals?pli=1)</ept>


### Contributors' guide links

- [Artículo de información general](./../README.md)
- [Índice de artículos de la guía](./contributor-guide-index.md)

<properties 
pageTitle="Instalación y configuración de herramientas de creación en GitHub" 
description="Tools and steps to get set up for authoring Power BI content in GitHub." 
services="contributor-guide" 
documentationCenter="" 
authors="mblythe"  
manager="dongill" />

<tags 
ms.service="contributor-guide"
 ms.devlang="" 
 ms.topic="article"
  ms.tgt_pltfrm="" 
  ms.workload="" 
  ms.date="09/09/2015" 
  ms.author="mblythe" />

#Instalación y configuración de herramientas de creación en GitHub

Follow the steps in this article to set up tools for contributing to the Power BI technical documentation. Casual and occasional contributors probably can use the GitHub UI described in step 2.

Si no está familiarizado con Git, le recomendamos consultar algunos términos de Git: [https://help.github.com/articles/github-glossary](https://help.github.com/articles/github-glossary). In addition, this StackOverflow thread contains a glossary of Git terms you'll encounter in this set of steps: <bpt id="p1">[</bpt>http://stackoverflow.com/questions/7076164/terminology-used-by-git<ept id="p1">](http://stackoverflow.com/questions/7076164/terminology-used-by-git)</ept>

## Contenido

- [Creación de una cuenta de GitHub y configuración del perfil](#create-a-github-account-and-set-up-your-profile)
- [Sign up for Disqus](#sign-up-for-disqus)
- [Determine whether you really need to follow the rest of these steps](#determine-whether-you-really-need-to-follow-the-rest-of-these-steps)
- [Permisos de GitHub](#permissions-in-github)
- [Instalación de Git para Windows](#install-git-for-windows)
- [Habilitación de la autenticación en dos fases](#enable-two-factor-authentication)
- [Instalación de un editor de marcado](#install-a-markdown-editor)
- [Configuración de Atom](#configure-atom)
- [Fork the repository and copy it to your computer](#fork-the-repository-and-copy-it-to-your-computer)
- [Configuración local del nombre de usuario y correo electrónico](#configure-your-user-name-and-email-locally)
- [Pasos siguientes](#next-steps)

## Creación de una cuenta de GitHub y configuración del perfil

To contribute to the Power BI technical content, you'll need a <bpt id="p1">[</bpt>GitHub<ept id="p1">](http://www.github.com)</ept> account.

If you are a Microsoft contributor, you need to set up your GitHub account so you're clearly identified as a Microsoft employee. Set up your profile as follows:

- 
            **Imagen de perfil**: una imagen suya (obligatorio).
- 
            **Nombre**: el nombre y los apellidos (obligatorio).
- <bpt id="p1">**</bpt>Email<ept id="p1">**</ept>: your Microsoft email address (required)
- <bpt id="p1">**</bpt>Company<ept id="p1">**</ept>: Microsoft Corporation (required)
- 
            **Ubicación**: muestra su ubicación (obligatorio).

El perfil debe ser similar a este:

<p align="center">
 ![Ejemplo de perfil de GitHub](./media/tools-and-setup/githubprofile.png)

## Sign up for Disqus

Every published Power BI technical article has a comment stream provided by the Disqus service.

 ![Discus logo](./media/tools-and-setup/discus.png)

If you are a Microsoft employee, and if you are the author of or a contributor to an article, you need to sign up for Disqus so you can participate in the comment stream for the article.

1. Sign up for an account at <bpt id="p1">[</bpt>http://www.disqus.com/<ept id="p1">](http://www.disqus.com/)</ept>
2. Fill out your profile as follows:

 - <bpt id="p1">**</bpt>Full Name<ept id="p1">**</ept>: your full name as displayed in your Microsoft address book listing, plus the bracketed info, which is your alias plus @MSFT. Format: <bpt id="p1">*</bpt>First Last [alias@MSFT]<ept id="p1">*</ept>
 - <bpt id="p1">**</bpt>Location<ept id="p1">**</ept>: Your location
 - <bpt id="p1">**</bpt>Short Bio<ept id="p1">**</ept>: Your title

## Determine whether you really need to follow the rest of these steps

You might not need to follow all the steps in this article. It depends on the sort of content contribution you want or need to make.

###Submit a text-only change to an existing article

If you only need or want to make textual updates to an existing article, you probably don't need to follow the rest of the steps. You can use GitHub's web-based markdown editor to submit your changes. Just click the GitHub link in the article you want to modify:

 ![Ejemplo de perfil de GitHub](./media/tools-and-setup/contributetogit.png)

 Then, click the edit icon in the GitHub version of the article

 ![Ejemplo de perfil de GitHub](./media/tools-and-setup/editicon.PNG)

 That opens the easy-to-use web editor that makes it easy to submit changes. You don't need to follow the other steps in this article.

###All other changes
You need to install the tools if you want to make any of the following sorts of changes:

 - Major changes to an article
 - Create and publish a new article
 - Add new images or update images
 - Update an article over a period of days without publishing changes each of those days

 Go to the next section!

##Permisos de GitHub

Anybody with a GitHub account can contribute to Power BI technical content through our public repository at <bpt id="p1">[</bpt>https://github.com/azure/powerbi-content<ept id="p1">](https://github.com/azure/powerbi-content)</ept>. Se requieren permisos especiales.

> [AZURE.NOTE] The powerbi-content repo will be private until further notice. You should work in the powerbi-content-pr repo.

If you are a Microsoft employee working on Power BI content, you should work in our private content repository, powerbi-content-pr. Visit <bpt id="p1">[</bpt>http://aka.ms/azuregithub<ept id="p1">](http://aka.ms/azuregithub)</ept> to obtain the read permissions that will let you make contributions through the private repo - click <bpt id="p2">**</bpt>Join a Team<ept id="p2">**</ept>, and join <bpt id="p3">**</bpt>cloud-enterprise-read<ept id="p3">**</ept>.

## Instalación de Git para Windows

Install Git for Windows from <bpt id="p1">[</bpt>http://git-scm.com/download/win<ept id="p1">](http://git-scm.com/download/win)</ept>. Esta descarga instala el sistema de control de versiones de Git y Git Bash, la aplicación de línea de comandos que empleará para interactuar con el repositorio local de Git.

You can accept the default settings; if you want the commands to be available within the Windows command line, select the option that enables it.

<p align="center">
 ![Ejemplo de perfil de GitHub](./media/tools-and-setup/gitbashinstall.png)

(Note: This is not the same as "Github for Windows". "Github para Windows" es una herramienta basada en GUI diferente que también sirve, pero tendrá que investigar usted mismo cómo funciona. 
            [https://windows.github.com/](https://windows.github.com/)) 

## Habilitación de la autenticación en dos fases

You have to enable two factor authentication (2FA) on your GitHub account if you are working in the private content repository. It's required in the private repository.

To enable this, follow the instructions in both the following GitHub help topics:

- [Acerca de la autenticación en dos fases](https://help.github.com/articles/about-two-factor-authentication/)
- [Creating an access token for command-line use](https://help.github.com/articles/creating-an-access-token-for-command-line-use/)

After you enable 2FA, you have to enter the access token instead of your GitHub password at the command prompt when you try to access a GitHub repository from the command line. The access token is not the authentication code that you get in a text message when you set up 2FA. It's a long string that looks something like this:  fdd3b7d3d4f0d2bb2cd3d58dba54bd6bafcd8dee. A few notes about this:

- When you create your access token, save it in a text file to make it readily accessible when you need it.

- Later, when you need to paste the token, know there are two ways to paste in the command line:

 - Click the icon in the upper left corner of the command line window&gt;Edit&gt;Paste.
 - Right-click the icon in the upper left corner of the window and click Properties&gt;Options&gt;QuickEdit Mode. This configures the command line so you can paste by right-clicking in the command line window.

## Instalación de un editor de marcado

We author content using simple "markdown" notation in the files, rather than complex "markup" (HTML, XML, etc.). So, you'll need to install a markdown editor.

- <bpt id="p1">**</bpt>Atom<ept id="p1">**</ept>: Most of us use GitHub's Atom markdown editor: <bpt id="p2">[</bpt>http://atom.io<ept id="p2">](http://atom.io)</ept>. It does not require a license for business use. It has spell check. 

- 
            **Bloc de notas**: puede utilizar el Bloc de notas si desea trabajar con una herramienta que consuma muy pocos recursos.

- 
            **Prose**: se trata de un editor de marcado que consume pocos recursos, elegante, en línea y de código abierto que ofrece una vista previa. Visite [http://prose.io](http://prose.io) y autorice a Prose en el repositorio.

- 
            **
            [Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx)**: la entrada de Microsoft en este mercado.

## Configuración de Atom

Si utiliza Atom, debe configurar algunas opciones.

- Atom utiliza de forma predeterminada 2 espacios para pestañas, pero se recomienda 4 para que se visualice correctamente. If you leave it at the default of two, your article will look great in local preview, but not when it’s imported into Power BI. So, configure Atom to use 4 spaces - you can find this setting under File&gt;Settings&gt;Editor Settings&gt;Tab Length. 
- También le recomendamos activar la característica Soft Wrap (Ajuste flexible) en esta sección, que tiene la misma función que el ajuste automático de línea del Bloc de notas. 
- To turn on the markdown preview, click Packages&gt;Markdown Preview&gt;Toggle Preview. Puede usar Ctrl + Mayús + M para cambiar a la vista previa de HTML. 

## Fork the repository and copy it to your computer

1. Create a fork of the repository in GitHub - go to the top-right of the page and click the Fork button. If prompted, select your account as the location where the fork should be created. This creates a copy of the repository within your Git Hub account. Generally speaking, technical writers and program managers need to fork powerbi-content-pr, the private repo. Community contributors need to fork powerbi-content, the public repo. You only need to fork one time; after your first setup, if you want to copy your fork to another computer, you only have to run the commands that follow in this section to copy the repo to your computer.  If you choose to create forks of both repositories, you will need to create a fork for each repository.

2. Copy the Personal Access Token that you got from <bpt id="p1">[</bpt>https://github.com/settings/applications#personal-access-tokens<ept id="p1">](https://github.com/settings/applications#personal-access-tokens)</ept>. You can accept the default permissions for the token.  Save the Personal Access Token in a text file for later reuse.

3. Next, copy the repository to your computer with your credentials embedded in the command string.  To do this, open GitBash.  En el símbolo del sistema, escriba el siguiente comando.  This command creates a powerbi-content(-pr) drectory on your computer.  If you're using the default location, it will be at c:\users<ph id="ph1">&lt;your Windows user name&gt;</ph>\powerbi-content(-pr).

Public repo:

        git clone https://[your GitHub user name]:[token]@github.com/<your GitHub user name>/powerbi-content.git

Private repo:

        git clone https://[your GitHub user name]:[token]@github.com/<your GitHub user name>/powerbi-content-pr.git

For example, this clone command could look something like this:

        git clone https://smithj:b428654321d613773d423ef2f173ddf4a312345@github.com/smithj/powerbi-content-pr.git  

## Establecimiento de una conexión remota de repositorio y configuración de las credenciales

Create a reference to the root repository by entering these commands. This sets up connections to the repository in GitHub so that you can get the latest changes onto your local machine and push your changes back to GitHub. This command also configures your token locally so that you don't have to enter your name and password each time you try to access the upstream repo and your fork on GitHub.

Public repo:

        cd powerbi-content
        git remote add upstream https://[your GitHub user name]:[token]@github.com/azure/powerbi-content.git
        git fetch upstream

Private repo:

        cd powerbi-content-pr
        git remote add upstream https://[your GitHub user name]:[token]@github.com/azure/powerbi-content-pr.git
        git fetch upstream

Esta operación tarda algún tiempo. After you do this, you won't have to fork again or enter your credentials again. You would only have to copy the forks to a local computer again if you set the tools up on another computer.


## Configuración local del nombre de usuario y correo electrónico

Para asegurarse de que aparece correctamente como colaborador, debe configurar el correo electrónico y el nombre de usuario localmente en Git.

1. Start Git Bash, and switch into powerbi-content or powerbi-content-pr:

   ````
   cd powerbi-content
   ````

 o

   ````
   cd powerbi-content-pr
   ````

2. Configure el nombre de usuario para que coincida con su nombre tal y como se ha configurado en el perfil de GitHub:

    ````
    git config --global user.name "John Doe"
    ````
3. Configure your email so it matches the primary email designated in your GitHub profile; if you're a MSFT employee, it should be your MSFT email address:

    ````
    git config --global user.email "alias@example.com"
    ````
4. Escriba `git config -l` y revise la configuración local para asegurarse de que el nombre de usuario y correo electrónico de la configuración son correctos.

##Pasos siguientes

- <bpt id="p1">[</bpt>Create a local working branch<ept id="p1">](./git-commands-for-master.md)</ept> on your computer so you can start work.
- Copy <bpt id="p1">[</bpt>the markdown template<ept id="p1">](../markdown templates/markdown-template-for-new-articles.md)</ept> as the basis for a new article.





###Contributors' Guide Links

- [Artículo de información general](./../README.md)
- [Índice de artículos de la guía](./contributor-guide-index.md)



<!--Anchors-->
[Use a customer-friendly voice]: #use-a-customer-friendly-voice
[Consider localization and machine translation]: #consider-localization-and-machine-translation
[other style and voice issues to watch for]: #other-style-and-voice-issues-to-watch-for


[Creación de una cuenta de GitHub y configuración del perfil]: #create-a-github-account-and-set-up-your-profile
[Determine whether you really need to follow the rest of these steps]: #determine-whether-you-really-need-to-follow-the-rest-of-these-steps
[Permisos de GitHub]: #permissions-in-github
[Instalación de Git para Windows]: #install-git-for-windows
[Habilitación de la autenticación en dos fases]: #enable-two-factor-authentication
[Instalación de un editor de marcado]: #install-a-markdown-editor
[Fork the repository and copy it to your computer]: #fork-the-repository-and-copy-it-to-your-computer
[Install git-credential-winstore]: #install-git-credential-winstore
[Sign up for Disqus]: #sign-up-for-disqus
[Configuración local del nombre de usuario y correo electrónico]: #configure-your-user-name-and-email-locally
[Pasos siguientes]: #next-steps

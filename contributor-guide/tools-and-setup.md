<properties 
pageTitle="Instalación y configuración de herramientas de creación en GitHub" 
description="Herramientas y pasos para obtener configurado para la creación de contenidos de Power BI en GitHub." 
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

Siga los pasos de este artículo para configurar las herramientas para contribuir a la documentación técnica de Power BI. Colaboradores ocasionales y ocasionales probablemente pueden utilizar la interfaz de Usuario que se describe en el paso 2 de GitHub.

Si no está familiarizado con Git, le recomendamos consultar algunos términos de Git: [https://help.github.com/articles/github-glossary](https://help.github.com/articles/github-glossary). Además, este subproceso StackOverflow contiene un glosario de términos de Git que encontrará en este conjunto de pasos: [http://stackoverflow.com/questions/7076164/terminology-used-by-git](http://stackoverflow.com/questions/7076164/terminology-used-by-git)

## Contenido

- [Creación de una cuenta de GitHub y configuración del perfil](#create-a-github-account-and-set-up-your-profile)
- [Regístrese para Disqus](#sign-up-for-disqus)
- [Determinar si realmente necesita siga el resto de estos pasos](#determine-whether-you-really-need-to-follow-the-rest-of-these-steps)
- [Permisos de GitHub](#permissions-in-github)
- [Instalación de Git para Windows](#install-git-for-windows)
- [Habilitación de la autenticación en dos fases](#enable-two-factor-authentication)
- [Instalación de un editor de marcado](#install-a-markdown-editor)
- [Configuración de Atom](#configure-atom)
- [Bifurcar el repositorio y cópielo en el equipo](#fork-the-repository-and-copy-it-to-your-computer)
- [Configuración local del nombre de usuario y correo electrónico](#configure-your-user-name-and-email-locally)
- [Pasos siguientes](#next-steps)

## Creación de una cuenta de GitHub y configuración del perfil

Para contribuir a que el contenido técnico de Power BI, necesitará un [GitHub](http://www.github.com) cuenta.

Si es un colaborador de Microsoft, debe configurar una cuenta de GitHub, por lo que está claramente identificado como empleado de Microsoft. Configure el perfil de la manera siguiente:

- 
            **Imagen de perfil**: una imagen suya (obligatorio).
- 
            **Nombre**: el nombre y los apellidos (obligatorio).
- 
            **Correo electrónico**: la dirección de correo electrónico de Microsoft (obligatorio)
- 
            **Compañía**: Microsoft Corporation (obligatorio)
- 
            **Ubicación**: muestra su ubicación (obligatorio).

El perfil debe ser similar a este:

<p align="center">
 ![Ejemplo de perfil de GitHub](./media/tools-and-setup/githubprofile.png)

## Regístrese para Disqus

Cada artículo técnico publicado de Power BI tiene una secuencia de comentario proporcionada por el servicio de Disqus.

 ![Logotipo de disco](./media/tools-and-setup/discus.png)

Si es un empleado de Microsoft y es autor de o colaborador a un artículo, debe iniciar sesión en Disqus para que pueda participar en el flujo de comentario para el artículo.

1. Regístrese para obtener una cuenta en [http://www.disqus.com/](http://www.disqus.com/)
2. Rellene su perfil como sigue:

 - 
            **Nombre completo**: su nombre completo como se muestra en la lista, además de la información entre corchetes, que es el alias más @MSFT la libreta de direcciones de Microsoft. Formato: *First, Last [alias@MSFT]*
 - 
            **Ubicación**: la ubicación
 - 
            **Corta la biografía**: su título

## Determinar si realmente necesita siga el resto de estos pasos

No tendrá que seguir los pasos descritos en este artículo. Depende de la ordenación de contribución contenido desea o necesita realizar.

###Envíe un cambio de sólo texto a un artículo existente

Si sólo necesita o desea realizar actualizaciones textuales de un artículo existente, probablemente no necesitará siga el resto de los pasos. Puede utilizar el editor de descuento basado en web de GitHub para enviar los cambios. Haga clic en el vínculo de GitHub en el artículo que desea modificar:

 ![Ejemplo de perfil de GitHub](./media/tools-and-setup/contributetogit.png)

 A continuación, haga clic en el icono de edición de la versión de GitHub del artículo

 ![Ejemplo de perfil de GitHub](./media/tools-and-setup/editicon.PNG)

 Que abre el editor web fácil de usar que facilita la tarea Enviar los cambios. No es necesario seguir los demás pasos de este artículo.

###Todos los demás cambios
Debe instalar las herramientas si desea realizar cualquiera de los siguientes tipos de cambios:

 - Cambios importantes en un artículo
 - Crear y publicar un nuevo artículo
 - Agregar nuevas imágenes o actualizar imágenes
 - Actualización de un artículo durante un período de días sin publicar cambios de aquellos días

 Visite la sección siguiente.

##Permisos de GitHub

Cualquier persona con una cuenta de GitHub puede contribuir al contenido técnico de Power BI a través de nuestro repositorio público en [https://github.com/azure/powerbi-content](https://github.com/azure/powerbi-content). Se requieren permisos especiales.

> [AZURE.NOTE] El repositorio de contenido de Power BI será privado hasta nuevo aviso. Debe trabajar en el repositorio de contenido de Power BI de pr.

Si es un empleado de Microsoft que trabaja en el contenido de Power BI, debe trabajar en nuestro privado pr de contenido de Power BI, repositorio de contenido. Visite [http://aka.ms/azuregithub](http://aka.ms/azuregithub) para obtener los permisos de lectura que le permitirán realizar contribuciones a través del repositorio privado - haga clic en **unir un equipo**, y la combinación **empresarial de nube de lectura**.

## Instalación de Git para Windows

Instalación de Git para Windows desde [http://git-scm.com/download/win](http://git-scm.com/download/win). Esta descarga instala el sistema de control de versiones de Git y Git Bash, la aplicación de línea de comandos que empleará para interactuar con el repositorio local de Git.

Puede aceptar la configuración predeterminada; Si desea que los comandos estén disponibles dentro de la línea de comandos de Windows, seleccione la opción que le permite.

<p align="center">
 ![Ejemplo de perfil de GitHub](./media/tools-and-setup/gitbashinstall.png)

(Nota: esto no es igual a "Github para Windows". "Github para Windows" es una herramienta basada en GUI diferente que también sirve, pero tendrá que investigar usted mismo cómo funciona. 
            [https://windows.github.com/](https://windows.github.com/)) 

## Habilitación de la autenticación en dos fases

Tendrá que habilitar la autenticación en dos fases (2FA) en su cuenta de GitHub si está trabajando en el repositorio de contenido privado. Se requiere en el repositorio privado.

Para ello, siga las instrucciones en tanto los temas de ayuda GitHub siguientes:

- [Acerca de la autenticación en dos fases](https://help.github.com/articles/about-two-factor-authentication/)
- [Creación de un token de acceso para su uso de línea de comandos](https://help.github.com/articles/creating-an-access-token-for-command-line-use/)

Después de habilitar 2FA, tendrá que escribir el token de acceso en lugar de la contraseña de GitHub en el símbolo del sistema al intentar obtener acceso a un repositorio de GitHub desde la línea de comandos. El token de acceso no es el código de autenticación que se obtiene en un mensaje de texto al configurar 2FA. Es una cadena larga que aspecto similar al siguiente: fdd3b7d3d4f0d2bb2cd3d58dba54bd6bafcd8dee. Algunas notas sobre esto:

- Cuando se crea el token de acceso, guárdelo en un archivo de texto para que sea fácilmente accesible cuando lo necesite.

- Más adelante, cuando tienes que pegar el token, sabe que hay dos formas para pegar en la línea de comandos:

 - Haga clic en el icono en la esquina superior izquierda de la ventana de línea de comandos > Editar > Pegar.
 - Haga clic en el icono en la esquina superior izquierda de la ventana y haga clic en Propiedades > Opciones > modalidad. Esto configura la línea de comandos, lo que puede pegar con el botón secundario en la ventana de línea de comandos.

## Instalación de un editor de marcado

Se crear contenido mediante una notación sencilla "markdown" en los archivos, en lugar de complejo "marcado" (HTML, XML, etc.). Por lo tanto, deberá instalar a un editor de descuento.

- 
            **Átomo**: la mayoría de nosotros utiliza editor de descuento Atom de GitHub: [http://atom.io](http://atom.io). No se requiere una licencia para uso empresarial. Tiene el corrector ortográfico. 

- 
            **Bloc de notas**: puede utilizar el Bloc de notas si desea trabajar con una herramienta que consuma muy pocos recursos.

- 
            **Prose**: se trata de un editor de marcado que consume pocos recursos, elegante, en línea y de código abierto que ofrece una vista previa. Visite [http://prose.io](http://prose.io) y autorice a Prose en el repositorio.

- 
            **
            [Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx)**: la entrada de Microsoft en este mercado.

## Configuración de Atom

Si utiliza Atom, debe configurar algunas opciones.

- Atom utiliza de forma predeterminada 2 espacios para pestañas, pero se recomienda 4 para que se visualice correctamente. Si deja el valor predeterminado de dos, el artículo tendrá un aspecto excelente en vista previa local, pero no cuando se importa a Power BI. Por lo tanto, configurar Atom para utilizar 4 espacios: puede encontrar esta configuración en archivo > Configuración > configuración del Editor > tamaño de tabulación. 
- También le recomendamos activar la característica Soft Wrap (Ajuste flexible) en esta sección, que tiene la misma función que el ajuste automático de línea del Bloc de notas. 
- Para activar la vista previa de descuento, haga clic en paquetes > vista previa de descuento > vista previa de alternancia. Puede usar Ctrl + Mayús + M para cambiar a la vista previa de HTML. 

## Bifurcar el repositorio y cópielo en el equipo

1. Crear una bifurcación del repositorio de GitHub: vaya a la parte superior derecha de la página y haga clic en el botón de bifurcación. Si se le solicita, seleccione la cuenta como la ubicación donde se debe crear la bifurcación. Esto crea una copia del repositorio en la cuenta del centro de Git. Por lo general, escritores técnicos y directores de programa necesitan bifurcar Power BI-contenido-pr, el repositorio privado. Colaboradores de la Comunidad necesitan bifurcar powerbi-content, el repositorio público. Sólo necesita bifurcar una vez; Después de la primera instalación, si desea copiar la bifurcación a otro equipo, sólo tiene que ejecutar los comandos que siguen en esta sección para copiar el repositorio en el equipo.  Si decide crear bifurcaciones de ambos repositorios, debe crear una bifurcación para cada repositorio.

2. Copie el Personal Token de acceso que obtuvo en [https://github.com/settings/applications#personal-access-tokens](https://github.com/settings/applications#personal-access-tokens). Puede aceptar los permisos predeterminados para el token.  Guarde el Token de acceso Personal en un archivo de texto para su uso posterior.

3. A continuación, copiar el repositorio en el equipo con las credenciales que se incrusta en la cadena de comandos.  Para ello, abra GitBash.  En el símbolo del sistema, escriba el siguiente comando.  Este comando crea un drectory powerbi-content(-pr) en el equipo.  Si utiliza la ubicación predeterminada, estará en c:\users<your Windows user name>\powerbi-content(-pr).

Repositorio público:

        git clone https://[your GitHub user name]:[token]@github.com/<your GitHub user name>/powerbi-content.git

Repositorio privado:

        git clone https://[your GitHub user name]:[token]@github.com/<your GitHub user name>/powerbi-content-pr.git

Por ejemplo, este comando de clonación podría este aspecto:

        git clone https://smithj:b428654321d613773d423ef2f173ddf4a312345@github.com/smithj/powerbi-content-pr.git  

## Establecimiento de una conexión remota de repositorio y configuración de las credenciales

Crear una referencia en el repositorio de raíz mediante estos comandos. Establece las conexiones con el repositorio de GitHub para que pueda obtener los últimos cambios en el equipo local y vuelva a insertar los cambios en GitHub. Este comando también configura el token localmente de modo que no tiene que escribir su nombre y contraseña cada vez que se intenta tener acceso el repositorio de nivel superior y la bifurcación en GitHub.

Repositorio público:

        cd powerbi-content
        git remote add upstream https://[your GitHub user name]:[token]@github.com/azure/powerbi-content.git
        git fetch upstream

Repositorio privado:

        cd powerbi-content-pr
        git remote add upstream https://[your GitHub user name]:[token]@github.com/azure/powerbi-content-pr.git
        git fetch upstream

Esta operación tarda algún tiempo. Después de hacer esto, no tendrá que volver a bifurcar o vuelva a escribir sus credenciales. Sólo tendría volver a copiar las bifurcaciones en un equipo local si configuró las herramientas en otro equipo.


## Configuración local del nombre de usuario y correo electrónico

Para asegurarse de que aparece correctamente como colaborador, debe configurar el correo electrónico y el nombre de usuario localmente en Git.

1. Inicie Git Bash y cambiar al contenido de Power BI o contenido de Power BI de pr:

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
3. Configurar el correo electrónico para que coincida con el correo electrónico principal designado en su perfil de GitHub; Si es un empleado MSFT, debe ser la dirección de correo electrónico MSFT:

    ````
    git config --global user.email "alias@example.com"
    ````
4. Escriba `git config -l` y revise la configuración local para asegurarse de que el nombre de usuario y correo electrónico de la configuración son correctos.

##Pasos siguientes

- 
            [Crear una bifurcación de trabajo local](./git-commands-for-master.md) en su equipo, por lo que puede empezar a trabajar.
- Copia [la plantilla de descuento](../markdown templates/markdown-template-for-new-articles.md) como base para un nuevo artículo.





###Vínculos de la Guía de los colaboradores

- [Artículo de información general](./../README.md)
- [Índice de artículos de la guía](./contributor-guide-index.md)



<!--Anchors-->
[Utilice una voz e intuitivo]: #use-a-customer-friendly-voice
[Considere la posibilidad de localización y traducción automática]: #consider-localization-and-machine-translation
[otros problemas de estilo y voz a inspeccionar]: #other-style-and-voice-issues-to-watch-for


[Creación de una cuenta de GitHub y configuración del perfil]: #create-a-github-account-and-set-up-your-profile
[Determinar si realmente necesita siga el resto de estos pasos]: #determine-whether-you-really-need-to-follow-the-rest-of-these-steps
[Permisos de GitHub]: #permissions-in-github
[Instalación de Git para Windows]: #install-git-for-windows
[Habilitación de la autenticación en dos fases]: #enable-two-factor-authentication
[Instalación de un editor de marcado]: #install-a-markdown-editor
[Bifurcar el repositorio y cópielo en el equipo]: #fork-the-repository-and-copy-it-to-your-computer
[Instalar incluye de credencial de git]: #install-git-credential-winstore
[Regístrese para Disqus]: #sign-up-for-disqus
[Configuración local del nombre de usuario y correo electrónico]: #configure-your-user-name-and-email-locally
[Pasos siguientes]: #next-steps

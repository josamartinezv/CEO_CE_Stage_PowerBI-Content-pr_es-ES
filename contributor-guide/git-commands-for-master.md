<properties pageTitle="Comandos de Git para crear un nuevo artículo o actualizar uno existente" description="Pasos para trabajar con la técnica de Power BI GitHub repositorios de contenido." metaKeywords="" services="" solutions="" documentationCenter="" authors="mblythe" videoId="" scriptId="" manager="dongill" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="09/09/2015" ms.author="mblythe" />

# Comandos de Git para crear un nuevo artículo o actualizar uno existente


## Proceso estándar (trabajo maestro)
Siga los pasos de este artículo para crear una bifurcación de trabajo local en el equipo para que pueda crear un nuevo artículo de la sección de documentación técnica de powerbi.microsoft.com o actualizar un artículo existente.

![](./media/git-commands-for-master/githubcommands1.png)

1. Iniciar Git Bash (o la herramienta de línea de comandos que use para Git).

 
            **Nota:** Si está trabajando en el repositorio público, cambiar el contenido de Power BI de pr al contenido de Power BI de todos los comandos.

2. Cambie a pr de contenido de Power BI:

        cd powerbi-content-pr
3. Revise la bifurcación principal:

        git checkout master

4. Crear una bifurcación de trabajo local nueva derivada de la bifurcación principal:

        git pull upstream master:<working branch>


5. Mover a la nueva bifurcación de trabajo:

        git checkout <working branch>

6. Avise a la bifurcación que creó la bifurcación de trabajo local:

        git push origin <working branch>

7. Cree el nuevo artículo o modifique uno que ya exista. Utilice el Explorador de Windows para abrir y crear nuevos archivos de descuento y usar Atom (http://atom.io) como editor de descuento. Una vez que haya creado o modificado el artículo y las imágenes, avance al siguiente paso.

8. Agregar y confirmar los cambios realizados:

        git add .
        git commit –m "<comment>"
        
   O bien, agregar sólo la específica de archivos modificado:

        git add <file path>
        git commit –m "<comment>"

9. Actualice su bifurcación de trabajo local con los cambios de nivel superior:

        git pull upstream master

10. Inserte los cambios en la bifurcación en GitHub:

        git push origin <working branch>

12. Cuando esté listo para enviar el contenido a la rama principal de nivel superior para la publicación, o de ensayo, validación, en la UI de GitHub, cree una solicitud de extracción desde la bifurcación en la bifurcación principal.

13. El receptor de la solicitud de extracción revisa la solicitud de extracción, proporciona comentarios o acepta la solicitud de extracción. 

14. Compruebe el artículo publicado o cambios en

 http://powerbi.Microsoft.com/documentation/articles/*name-of-your-article-without-the-MD-extension*

**Notas:**

- En este momento, artículos técnicos se publican una vez al día en torno a 10 A.M. hora estándar del Pacífico (PST), de lunes a viernes. Recuerde que su solicitud de extracción debe aceptarse antes de cambios incluidos en la siguiente publicación programada que se ejecute.
- Si es un empleado que trabaja en el repositorio privado, todas las solicitudes de extracción están sujetos a reglas de validación que deban solucionarse antes de que se puede aceptar la solicitud de extracción. 
- En el repositorio privado, los cambios que se envíe automáticamente se almacenan provisionalmente y un vínculo de ensayo se escribe en la solicitud de extracción. Revise el contenido de ensayo y firmar en los comentarios de la solicitud de extracción para indicar que los cambios están listos para insertarse en vivo. Si no desea que la solicitud de extracción para que se acepte - si solo se prueba cambios - agregar esa nota a la solicitud de extracción.

## Trabajar con bifurcaciones de versión

Cuando se trabaja con una bifurcación de la versión, la mejor manera de crear una bifurcación de trabajo local de la bifurcación de versión es utilizar esta sintaxis de comando:

    git checkout upstream/<upstream branch name> -b <local working branch name>

Esto crea la bifurcación local directamente desde la rama de nivel superior, evitar cualquier combinación local.


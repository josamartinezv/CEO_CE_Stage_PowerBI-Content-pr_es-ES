# Guía de conversión de página web

1.  Visite el sitio Web de destino y `File -> Save As`
2.  Guarde la página mediante su `github-file-name`
3.  Abra el símbolo del sistema y navegue hasta la carpeta de la página web
4.  Ejecute pandoc para convertir el tema `pandoc -f html -t markdown_github <github-file-name>.html -o <github-file-name>.md`
5.  Cambiar el nombre de la carpeta de recursos de `<github-file-name>_files` a `<github-file-name>`. No existe tal vez una advertencia pero haga clic en a través de él de todos modos.
6.  Abra el archivo de descuento con [notepad ++](https://notepad-plus-plus.org/).
7.  Quite cualquier contenido no deseado, como encabezados, pies de página y barras laterales.
8.  Corrija la headding H1 agregando una hashtag y un espacio antes del título H1 y quitando el subrayado doble.
9.  Quitar el intervalo vacío con las etiquetas para buscar y reemplazar
    
    1.  Presione `Ctrl+H` o navegar desde el menú `Search -> Replace`
    2.  Asegúrese de que estas opciones estén activadas
        -  Ajuste alrededor de
        -  Modo de búsqueda: Expresión Regular
        -  Modo de búsqueda:. coincide con la nueva línea
    3.  Buscar: `<span>(.*?)</span>` Reemplazar por: `\1`
    4.  Reemplazar todo

10.  Corregir los vínculos de imagen:

    1.  Search: `\!\[(.*?)\]\(./<github-file-name>_files/`
    2.  Reemplace: `![\1]\(media/<github-file-name/`
    3.  En el explorador desplazamiento de archivos de la carpeta de imágenes en un directorio de multimedia, crear uno si no anota lo hace.
    4.  En la carpeta de imágenes quita elementos no sean de imágenes como .js, .css, .php y todas las imágenes no utilizadas de las secciones quitadas de la página (logotipos e iconos).

11.  Abra el archivo de descuento en el editor de su elección. 

12. Comparar el contenido de la reducción de la página web original. Tendrá que corregir algunas otras cosas tales como listas de seguro ordenadas que hace que se espacian correctamente. Puede haber algunas `<span>` etiquetas que deberán quitarse ni otros formatos de cambian que deben realizarse. Todas las tablas que no se convierten deberá fijarse también.

13.  Agregue los metadatos relevantes para el tema.

14.  Agregar su propio tema en el repositorio de github (no para obtener la carpeta de imágenes), realizar la confirmación en una bifurcación local.

15.  Inserte la bifurcación en la bifurcación privada y enviar una solicitud de extracción en la bifurcación principal

16.  Espere a que el tema para pasar la validación y realizar todas las correcciones según sea necesario. Una vez que esté satisfecho de inicio de sesión desactivado en la solicitud de extracción con `#sign-off`.
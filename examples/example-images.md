<properties pageTitle="Ejemplo de documentación: imágenes" metaKeywords="" description="Esto es un ejemplo de documento" services="" documentationCenter="" title="Documentation Example - Images" solutions="" authors="" videoId="" scriptId="" />

# Por ejemplo, imágenes #

Se trata de un artículo de la documentación de ejemplo que se usa para probar y validar el sistema de publicación para azure.microsoft.com.  

El contenido entre las líneas siguientes muestra la sintaxis de otra imagen compatible.  


---
## Sintaxis de imagen en línea ##

Con esta sintaxis, se debe colocar una marca de exclamación al principio. A continuación, entre corchetes, un identificador de la imagen. Después de eso, entre paréntesis, la ruta de acceso relativa a la imagen dentro de la estructura de carpetas.

**Sintaxis de imagen:**  `![windows-azure-logo](./media/example-images/windows-azure.png) `

**Imagen resultante:** 

![logotipo de Windows azure](./media/example-images/windows-azure.png)

---

## Sintaxis de imágenes que se hace referencia ##

Esta sintaxis es similar al anterior, pero funciona con las referencias de la ruta de acceso de la imagen en el artículo. Utiliza una marca de exclamación al principio y un par de corchetes que contienen el identificador de referencia de la imagen en el artículo. La referencia de la imagen, a continuación, debe contener la ruta de acceso relativa de la imagen dentro de la estructura de carpetas.

**Sintaxis de imagen:** 
`![][windows-azure-logo]`

**Referencia de imagen:** `[windows-azure-logo]: ./media/example-images/windows-azure.png `

**Imagen resultante:** 

![][windows-azure-logo]

[logotipo de Windows azure]: ./media/example-images/windows-azure.png


Otra forma de imágenes de referencia:

`![windows-azure-logo][] `

![logotipo de Windows azure][]

`![windows-azure-logo][windows-azure-logo] `

![logotipo de Windows azure][windows-azure-logo]

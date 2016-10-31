<properties pageTitle="Ejemplo de documentación - propiedades de metadatos" description="Esto es un ejemplo de documento" services="" documentationCenter="" authors="" tags="tag1,tag2" />

# Por ejemplo, las propiedades de metadatos #

Este documento es una demostración de valores de propiedad que deben tener todos los documentos para publicarse.  

---
## Propiedades de metadatos ##

Las propiedades de metadatos deben colocarse al principio del documento de origen descuento. Hay propiedades u obligatoria necesarios y opcionales. Si los metadatos son necesarios, el servicio de publicación de documentación generará un error al validar el contenido y el bloqueo hasta que se ha corregido los metadatos de publicación.  Si no se requieren los metadatos se generará una advertencia por el servicio de publicación.


Deberían seguir esta sintaxis:

`<properties pageTitle="page-title" description="description" services="services" documentationCenter="documentation-center"  authors="authors" tags="tag1,tag2" />`

En la tabla siguiente muestra más información para cada valor de la propiedad:

|  Propiedad      |    Obligatorio    | Descripción |
|--------|--------|--------|
| pageTitle       | Sí       | Título de la página utilizado en el HTML, Head y título.  Tenga en cuenta que podría ser diferente que el título del documento. |
| description       | Sí       | Breve descripción de texto asignado al elemento de descripción de metadatos en el código HTML y se utiliza dentro del sitio.  |
| servicios       | No       | Lista de nombres de servicio como "sitios web", "almacenamiento", etc. de separados por comas. |
| documentationCenter       | No       | Centro de desarrollo único lenguaje que se aplican al documento.  |
| autores       | No       | Lista separada por comas de los nombres de autor.   |
| tags       | No       | Etiquetas para identificar un artículo de documentación. |

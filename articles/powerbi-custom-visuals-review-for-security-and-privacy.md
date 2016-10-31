<properties
   pageTitle="Revise los elementos visuales personalizados para la seguridad y privacidad"
   description="Antes de habilitar un objeto visual personalizado, debe revisar que visual para la seguridad y privacidad para hacer seguro if ajustará los estándares de su organización."
   services="powerbi"
   documentationCenter=""
   authors="guyinacube"
   manager="erikre"
   backup=""
   editor=""
   tags=""
   qualityFocus="no"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="10/10/2016"
   ms.author="asaxton"/>

# Revise los elementos visuales personalizados para la seguridad y privacidad

Antes de habilitar un objeto visual personalizado, debe revisar que visual para la seguridad y privacidad para hacer seguro if ajustará los estándares de su organización.

## Habilitar un objeto visual personalizado

<a name="enable"></a>Un objeto visual personalizado en el informe está deshabilitado hasta que usted decida **Habilitar elementos visuales personalizados** tal como se muestra a continuación.  

![](media/powerbi-custom-visuals-review-for-security-and-privacy/EmptyVisual.png)

## Consideraciones antes de habilitar un objeto visual personalizado  
<a name="considerations"></a>

> [AZURE.WARNING] Un objeto visual personalizado podría contener código con seguridad o riesgos de privacidad; por lo tanto, un objeto visual personalizado en el informe está deshabilitado hasta que usted decida elementos visuales personalizados de habilitar. Estas son algunas consideraciones para decidir si desea habilitar un objeto visual personalizado:

1. Asegúrese de que confía en el autor y el origen de los elementos visuales personalizados utilizados en el informe

2. Si no está seguro de qué hacer, que debe llegar a su equipo de TI sopesan si debe habilitar elementos visuales personalizados para ver los informes.

3. Si un usuario comparte un informe con usted que contiene un objeto visual personalizado, incluso si tienen un colega cerrar, no se sienta obligado a habilitar el objeto visual personalizado. Está bien retroceder y tener en cuenta si es esencial para la tarea en cuestión. Siempre es correcto pida a alguien que proporcionan un informe sin elementos visuales personalizados si prefiere no molestarse plena confianza en el objeto visual personalizado.

## Prácticas recomendadas de seguridad para profesionales de TI habilitar un objeto visual personalizado  
<a name="security"></a>

> [AZURE.WARNING] Un objeto visual personalizado podría contener código con seguridad o riesgos de privacidad; por lo tanto, un objeto visual personalizado en el informe está deshabilitado hasta que usted decida elementos visuales personalizados de habilitar. Hay varios procedimientos recomendados que puede seguir para evaluar un objeto visual personalizado de seguridad y privacidad.

1.  Implementar un proceso vetting para elementos visuales personalizados dentro de la organización. Cuenta elementos visuales personalizados se podrían compartir con los usuarios internos a través de un sitio Web interno, como una biblioteca de documentos de SharePoint o un documento de OneNote.
2.  Proporcionar instrucciones para los usuarios empresariales en uso adecuado de los elementos visuales personalizados y un grupo de correo electrónico para los usuarios empresariales enviar preguntas sobre la privacidad a y seguridad.
3.  Evalúe el código de JavaScript en el archivo pbiviz visual personalizado.

**Para evaluar el código JavaScript en un objeto visual personalizado**

Un objeto visual personalizado usa JavaScript y, por tanto, puede contener los riesgos de seguridad o privacidad. Si recibe un objeto visual personalizado o un archivo pbix con un objeto visual personalizado de un origen desconocido, puede mirar el código JavaScript para ver si es seguro.

Para evaluar el código JavaScript en un objeto visual personalizado, extraiga el código visual personalizado. Aquí se muestra cómo extraer el código:  

1. Guarde el archivo .pbiviz en una carpeta.

2. Cambie el nombre a un archivo zip.

3. Extraiga el archivo zip en una carpeta local.

## Contenido del archivo visual personalizado

El siguiente es el contenido de un archivo pbiviz:

| **Archivo**                     | **Descripción**                                                                                                                                                           |
|:-----------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ./Package.JSON               | Un archivo de manifiesto que indica qué archivos de carga para el objeto visual personalizado.                                                                                                 |
| . / recursos                  | Contiene la CSS, TypeScript y JavaScript utilizados por el objeto visual personalizado.                                                                                                   |
| ./resources/&lt;nombre&gt;     | &lt;nombre&gt; es el nombre del objeto visual personalizado.                                                                                                                            |
| ./resources/&lt;nombre&gt;.css | El archivo de recursos de css para el objeto visual personalizado.                                                                                                                              |
| ./resources/&lt;nombre&gt;.js  | El código que se ejecuta cuando un usuario hace clic en elementos visuales personalizados de habilitar o después de que un usuario importa un objeto visual personalizado. Advertencia de código JavaScript podría contener riesgos la seguridad o privacidad. |
| ./resources/&lt;nombre&gt;.ts  | El código fuente de JavaScript para el objeto visual en formato de TypeScript. Código de advertencia JavaScript o TypeScript podría contener los riesgos de seguridad o privacidad.                            |
| ./resources/&lt;nombre&gt;.png | El icono que se muestra al usuario para el objeto visual.                                                                                                                                |

Después de extraer el archivo pbiviz, puede evaluar el código. Estas son algunas prácticas recomendadas y las amenazas a buscar.

## Mejores prácticas para evaluar el código de JavaScript o TypeScript


            **JavaScript** o **TypeScript** código podría contener los riesgos de seguridad o privacidad. Estas son algunas prácticas recomendadas y las amenazas a buscar.

### Mejores prácticas para evaluar el código JavaScript

-  Siempre se evaluará el contenido del archivo .js. Este es el código que se ejecuta realmente. Es posible que el contenido del archivo .ts no se compila en el archivo .js que se incluyen en el objeto visual personalizado.

-  Siempre se evaluará el contenido del archivo .ts. Puede cargar el archivo .ts en la **Developer Tools**, exportar el objeto visual y comparar el archivo .js resultante el recién creado archivo .pbiviz en el archivo .js original contenido en el objeto visual

-  Compruebe que el icono para el objeto visual personalizado no se parecen a demasiado estrechamente otros elementos visuales que está familiarizado con el usuario.

-  Siempre se evaluará el objeto visual en una cuenta de prueba que tiene los privilegios mínimos y no tiene acceso a los datos confidenciales. Lo ideal es que la cuenta de prueba podría ser una cuenta local sin información de inicio de sesión para los servicios que no sean de Power BI.

### Amenazas para buscar en el código de JavaScript

-  Comprobar la actividad de red cuando se usa el objeto visual en modo de edición y de vista. Asegúrese de que está satisfecho con las solicitudes que se realizan. No debería ver las solicitudes a recursos fuera del dominio de Power BI a menos que el autor visual ha comunicado de antemano.

-  Los datos que verá que abandonar el dominio de Power BI deben coincidir con sus expectativas para el uso de 'normal' sería. Por ejemplo: si el objeto visual implementa un Reproductor de vídeo que utiliza un iFrame para ver un vídeo desde otro sitio, debe incluir cierta información en las solicitudes de IFrame para representar el vídeo correctamente. Sin embargo, si ve el conjunto de datos que se envían a través de la red, podría investigar aún más si esto es necesario y que desee.

-  Compruebe si personalmente identificables datos se están enviado o almacenados por el objeto visual personalizado.

-  Compruebe si el objeto visual personalizado está intentando obtener acceso a recursos de la máquina local, como la escritura de archivos en disco o tiene acceso a las cookies.

-  Compruebe si el objeto visual personalizado tiene lo que parece ser confusa código o sin un objetivo claro.

-  Guardar copias de cada visual revisado en el pasado.

-  Si está revisando una actualización de un elemento visual que ha examinado previamente, asegúrese de comprobar los cambios. Siempre se aplican rigor igual a las actualizaciones al igual que la primera vez que recibe el objeto visual para su revisión

-  Si encuentra algo sospechoso o confuso, póngase en contacto out nos estamos aquí para ayudarle.

## Consulte también

[Visualizaciones en Power BI](powerbi-service-visualizations-for-reports.md)  
[Visualizaciones personalizadas en Power BI](powerbi-custom-visuals.md)  
[La Galería de elementos visuales personalizados de Power BI](https://app.powerbi.com/visuals)  
[Agregar una visualización personalizada a un informe (Power BI Desktop)](powerbi-custom-visuals-use.md)  
[Agregar una visualización personalizada a un informe (servicio Power BI)](powerbi-custom-visuals-add-to-report.md)  
[Descargar visualizaciones personalizadas de la Galería](powerbi-custom-visuals-download-from-the-gallery.md)  
[Crear y enviar una visualización en la Galería](powerbi-custom-visuals-create-for-the-gallery.md)  
[Introducción a las herramientas de desarrollo de elementos visuales personalizados (vista previa)](powerbi-custom-visuals-getting-started-with-developer-tools.md)  
[Vídeo: Crear visualizaciones personalizadas para Power BI con Sachin Patney y Nico Cristache](https://www.youtube.com/watch?v=kULc2VbwjCc)  
¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
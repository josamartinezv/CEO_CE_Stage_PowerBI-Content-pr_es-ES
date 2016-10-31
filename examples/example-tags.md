<properties pageTitle="Ejemplo de documentación - etiquetas" metaKeywords="" description="Esto es un ejemplo de documento" services="" documentationCenter="" title="Documentation Example - Tags" solutions="" authors="" videoId="" scriptId="" />

<tags ms.service="AzureWebSites" ms.devlang="CSharp" ms.topic="home-page" ms.tgt_pltfrm="Windows" ms.workload="50" ms.date="06/12/2014" ms.author="maurok;v-nabeni@microsoft.com;lito@mail.com" />

# Por ejemplo, etiquetas #

Se trata de un artículo de la documentación de ejemplo que se usa para probar y validar el sistema de publicación para Azure.com.  

El ejemplo `<tags />` se puede encontrar el elemento justo debajo del `<properties />` elemento situado al principio del documento.

A menos que se especifique lo contrario (por ejemplo, para ms.date), valores deben estar restringidos a caracteres alfanuméricos y guiones y la longitud del valor deben estar restringidos a 30 caracteres.

Hay 7 atributos necesarios para el elemento de etiquetas: 

- 
            **MS.Service**: especifica el servicio de Azure, herramienta o característica que se aplica el artículo.

- 
            **MS.DevLang**: especifica el lenguaje de programación que se aplica el artículo.

- 
            **MS.topic**: especifica el tipo de tema.

    > 
            **Los valores válidos**: *artículo, artículo héroe, referencia, página de índice, página de campaña, página de vídeo, página infografía, página principal, página de inicio del servicio, dev--página principal del centro de, sección-página principal del sitio*  

- 
            **MS.tgt_pltfrm**: especifica la plataforma de destino, por ejemplo Windows, Linux, Windows Phone, iOS o Android.

- 
            **MS.Workload**: especifica una carga de trabajo de C & E a la que el tema se aplica a.

- 
            **MS.Date**: especifica la última fecha actualizada para el tema.

    > 
            **Los valores válidos**: fechas del formato mm/dd/aaaa, p. ej. “04/10/2014”

- 
            **MS.author**: especifica los autores asociados al tema. Para especificar varios valores, debe separarlos por punto y coma.

    > 
            **Los valores válidos**: alias de Microsoft y las direcciones de correo electrónico completa. Longitud debe ser no más de 200 caracteres.


Este es un ejemplo de un elemento de etiquetas:

````XML
<tags ms.service="AzureWebSites" ms.devlang="CSharp" ms.topic="home-page" ms.tgt_pltfrm="Windows" ms.workload="50" ms.date="06/12/2014" ms.author="maurok;v-nabeni@microsoft.com;lito@mail.com" />
````


---
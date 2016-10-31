<properties 
   pageTitle="Área de trabajo de archivado de Power BI"
   description="Área de trabajo Power BI archivado después de administrar al inquilino de Office 365"
   services="powerbi" 
   documentationCenter="" 
   authors="guyinacube" 
   manager="mblythe" 
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
   ms.date="09/21/2016"
   ms.author="asaxton"/>

# Área de trabajo de archivado de Power BI  

Con Power BI, cualquier usuario puede registrarse y empezar a usar el servicio en unos minutos.  Más adelante, de la organización departamento de TI puede optar por sacar sobre la administración de Power BI para los usuarios de su organización.  Si se produce esta adquisición, se beneficiará de la administración central de usuarios y permisos de la organización y es posible que pueda aprovechar optimizada iniciar sesión con el mismo nombre de usuario y contraseña que se usa para otros servicios de su organización. 

Cualquier contenido que se haya creado antes de que el departamento de TI a administrar Power BI se colocará en un área de archivado de Power BI, que es accesible desde el panel izquierdo de [Power BI](https://app.powerbi.com).  Debería empezar a crear el contenido nuevo Power BI en Mi área de trabajo que sea seguro y administrado por su organización departamento de TI.  El área de trabajo de archivado seguirán existiendo, pero existen restricciones sobre las acciones que puede realizar en el contenido del área de trabajo de archivado.  Para quitar estas restricciones, debe migrar el contenido del área de trabajo archivados a su mi área de trabajo administrados por el departamento de TI.

## Restricciones en el área de trabajo archivado  
Se eliminará ningún contenido del área de trabajo archivados.  Puede continuar obtener datos, crear informes y paneles y actualizar conjuntos de datos.  Los usuarios existentes que comparta contenido podrá ver el contenido en su área de trabajo de archivado demasiado.

Sin embargo, hay algunas restricciones en el contenido del área de trabajo de archivado:

-   
            **OneDrive para la empresa.  ** Ya no podrá obtener datos o actualizar de OneDrive para la empresa para conjuntos de datos en el área de trabajo de archivado.  Si intenta conectarse a este origen, recibirá una advertencia.

-   
            **Compartir paneles.  ** No puede compartir paneles con otros usuarios de su área de trabajo de archivado.  Los usuarios que ya tienen acceso seguirá poder ver los paneles compartidos mediante el acceso a su área de trabajo de archivado.

-   
            **Creación de grupos.  ** No se puede crear grupos en el área de trabajo de archivado.

-   
            **Acceso en aplicaciones móviles de Power BI.  **﻿Aunque todavía puede ver el contenido en la web en el área de trabajo de archivado, este contenido ya no aparecerá en las aplicaciones móviles de Power BI.

## Migración de contenido en el área de trabajo archivado  
Para seguir usando Power BI, debe crear nuevo contenido en el área de trabajo Mi administrado por el departamento de TI.   También debe planear migrar contenido en el área de trabajo de archivado a mi área de trabajo.  Cómo migrar contenido depende del tipo de contenido:

-   
            **Excel o Power BI Desktop conjuntos de datos.  ** Migrar estos conjuntos de datos cambiando el área de trabajo de archivado a mi área de trabajo y volver a cargar el archivo de Excel o Power BI Desktop haciendo clic en el botón "Mis datos".  Si establece la actualización programada, debe volver a configurar los valores del conjunto de datos nuevo en Mi área de trabajo.

-   
            **Otros conjuntos de datos.  ** Cambie a mi área de trabajo y, a continuación, haga clic en el botón obtener datos para volver a conectar a los otros conjuntos de datos que creó en el área de trabajo de archivado.  Debe volver a escribir la información de conexión o de seguridad.

-   
            **Informes.  ** Informes que se incluían en los archivos de Excel o Power BI Desktop o informes que se instalan como parte de los paquetes de contenido se volverá automáticamente una vez que vuelva a cargar el archivo de Excel o Power BI Desktop correspondiente o volver a conectar con el paquete de contenido.  Si crea sus propios informes a través del servicio Power BI, debe volver a crear los informes de Mi área de trabajo.

-   
            **Paneles.  ** Los paneles que se instala como parte de los paquetes de contenido se volverá automáticamente al conectarse de nuevo para el paquete de contenido en Mi área de trabajo.  Si crea sus propios paneles a través del servicio Power BI, debe volver a crear esos paneles en Mi área de trabajo.

¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)  
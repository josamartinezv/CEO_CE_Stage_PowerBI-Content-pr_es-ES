<properties
pageTitle="Solución de problemas de errores de mosaico"
description="Errores comunes que pueden presentarse cuando intente actualizar un mosaico"
services="powerbi"
documentationCenter=""
authors="guyinacube"
manager="mblythe"
backup=""
editor=""
tags=""
qualityFocus="monitoring"
qualityDate="06/13/2016"/>

<tags
ms.service="powerbi"
ms.devlang="NA"
ms.topic="article"
ms.tgt_pltfrm="na"
ms.workload="powerbi"
ms.date="08/15/2016"
ms.author="asaxton"/>
# Solución de problemas de errores de mosaico

A continuación se muestran los errores comunes que pueden producirse con mosaicos junto con una explicación.

> [AZURE.NOTE] Si se produce un error que no se enumera a continuación y está causando problemas, puede pedir ayuda adicional en el [sitio de la Comunidad](http://community.powerbi.com/), o puede crear un [admite vale](https://powerbi.microsoft.com/support/).

## errores

**Power BI encontró un error inesperado al cargar el modelo. Vuelva a intentarlo más tarde.**
o **no se pudo recuperar el modelo de datos. Póngase en contacto con el propietario del panel para asegurarse de que los orígenes de datos y el modelo existen y son accesibles.**

No se puede tener acceso a los datos porque el origen de datos no estaba accesible. Esto podría ocurrir si el origen de datos se ha quitado, ha cambiado el nombre, mover, sin conexión o que han cambiado los permisos. Compruebe que el origen aún está en la ubicación que estamos seleccionando y todavía tiene permiso para acceder a ella. Si no es el problema, el origen puede ser lento. Inténtelo de nuevo más tarde durante un tiempo cuando la carga en el origen es menor. Si es un origen local, el propietario del origen de datos puede proporcionar más información. 

**No tiene permiso para ver este mosaico o abrir el libro.**

Póngase en contacto con el propietario del panel para asegurarse de que los orígenes de datos y el modelo existen y son accesibles para su cuenta.

**Formas de datos deben contener al menos un grupo o cálculo que envía los datos. Póngase en contacto con el propietario del panel.**

No tenemos ningún dato que mostrar porque la consulta está vacía. Intente agregar algunos campos de la lista de campos para el objeto visual y lo anclarlo.

**No se puede mostrar los datos porque Power BI no puede determinar la relación entre dos o más campos.**

Está intentando usar dos o más campos de tablas que no están relacionadas. Debe quitar los campos no relacionados de visual y, a continuación, crear una relación entre las tablas. Cuando haya hecho esto, puede agregar los campos al objeto visual. Esto puede hacerse en Power BI Desktop o PowerPivot para Excel. [Obtener más información](powerbi-desktop-create-and-manage-relationships.md)

**Los grupos en el eje principal y el eje secundario se superponen. Grupos del eje principal no pueden tener las mismas claves como grupos en el eje secundario.**

Por lo general, suele ser un problema transitorio. Esto ocurre normalmente cuando mueva los grupos de filas a las columnas. En este caso, el error debería desaparecer cuando haya terminado de mover todos los grupos. Si continúa recibiendo el mensaje, intente campos conmutación entre las filas y columnas o en la leyenda de eje o quitar campos desde el objeto visual.  

**Este objeto visual superó los recursos disponibles. Intente filtrar para disminuir la cantidad de datos que se muestran.**

El objeto visual ha intentado consultar demasiados datos para poder completar el resultado con los recursos disponibles. Intente filtrar visual para reducir la cantidad de datos en el resultado.

**No es posible identificar los campos siguientes: {0}. Actualice el objeto visual con campos que existen en el conjunto de datos.**

Es probable que el campo se ha eliminado o se ha cambiado. Puede quitar el campo roto de visual, agregue un campo diferente y anclar a.

**No se pudo recuperar los datos para este objeto visual. Vuelva a intentarlo más tarde.**

Por lo general, suele ser un problema transitorio. Si lo intenta más tarde y todavía aparece este mensaje, póngase en contacto con el soporte técnico.

## Póngase en contacto con el soporte técnico.

Si sigue teniendo un problema, inicie [póngase en contacto con soporte técnico](https://support.powerbi.com) investigar más.

## Consulte también

[Solución de problemas de la puerta de enlace de datos local](powerbi-gateway-onprem-tshoot.md)  
[Solución de problemas de Power BI Personal Gateway](powerbi-admin-troubleshooting-power-bi-personal-gateway.md)  
¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
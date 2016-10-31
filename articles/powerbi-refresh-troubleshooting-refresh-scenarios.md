<properties 
   pageTitle="Para solucionar problemas de actualización"
   description="Para solucionar problemas de actualización"
   services="powerbi" 
   documentationCenter="" 
   authors="guyinacube" 
   manager="mblythe" 
   backup=""
   editor=""
   tags=""
   qualityFocus="complete"
   qualityDate="04/04/2016"/>
 
<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/15/2016"
   ms.author="asaxton"/>

# Para solucionar problemas de actualización  

Aquí puede encontrar información sobre escenarios diferentes pueden producirse al actualizar datos en el servicio Power BI. 

> [AZURE.NOTE] Si se encuentra un caso que no se enumera a continuación y está causando problemas, puede pedir ayuda adicional en el [sitio de la Comunidad](http://community.powerbi.com/), o puede crear un [admite vale](https://powerbi.microsoft.com/support/).

## Origen de datos no admitidos para la actualización
Al configurar un conjunto de datos, obtendrá un error que indica que el conjunto de datos utiliza un origen de datos no admitidos para la actualización. Para obtener más información, consulte [solución de problemas origen de datos no admitidos para la actualización](powerbi-admin-troubleshoot-unsupported-data-source-for-refresh.md)

## Panel no refleja los cambios después de la actualización  
Espere aproximadamente 10-15 minutos para la actualización para que se reflejen en los iconos de panel.  Si aún no se muestra, volver a anclar la visualización en el panel.

## GatewayNotReachable al establecer credenciales  
Puede encontrar GatewayNotReachable al intentar establecer las credenciales para un origen de datos. Esto podría deberse a una puerta de enlace obsoleto.  Instale la puerta de enlace más reciente y vuelva a intentarlo.

## Error de procesamiento: El error del sistema: no coinciden los tipos  
Podría tratarse de un problema con la secuencia de comandos de M dentro de su archivo de Power BI Desktop o un libro de Excel.  También podría ser debido a una versión actualizada de Power BI Desktop.

## Errores de actualización de mosaico
Para obtener una lista de errores que pueden producirse con los iconos de panel y explicaciones, consulte [solucionar errores de mosaico](powerbi-refresh-troubleshooting-tile-errors.md).

## Véase también  

[Actualización de datos](powerbi-refresh-data.md)  
[Solución de problemas de la puerta de enlace de datos local](powerbi-gateway-onprem-tshoot.md)  
[Solución de problemas de la puerta de enlace de Power BI - Personal](powerbi-admin-troubleshooting-power-bi-personal-gateway.md)  
¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
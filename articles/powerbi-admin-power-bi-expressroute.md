<properties
   pageTitle="ExpressRoute y power BI"
   description="ExpressRoute y power BI"
   services="powerbi"
   documentationCenter=""
   authors="davidiseminger"
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
   ms.date="10/10/2016"
   ms.author="davidi"/>

# ExpressRoute y power BI

Con **Power BI** y **ExpressRoute**, puede crear una conexión de red privada de su organización a Power BI (o mediante instalación de coubicación de un ISP), omitiendo Internet para proteger mejor sus datos confidenciales de Power BI y conexiones.


            **ExpressRoute** es un servicio de Azure que le permite crear conexiones privadas entre los centros de datos de Azure (donde reside Power BI) y la infraestructura local o crear conexiones privadas entre los centros de datos de Azure y su entorno de colocación.


![](media/powerbi-admin-power-bi-expressroute/pbi_expressroute_1.png)

Puede obtener [para obtener más información acerca de ExpressRoute](https://azure.microsoft.com/services/expressroute/) u obtenga [cómo suscribirse a](https://azure.microsoft.com/pricing/details/expressroute/).


## Excepciones de Power BI ExpressRoute

Power BI es compatible con ExpressRoute, con algunas excepciones en Power BI Obtiene o envía datos a través de la red Internet pública. Estas excepciones específicas suelen incluyan datos estáticos, como archivos de configuración de explorador que se descargan de más próximo **red de entrega de contenido (CDN)** nodo. Existen algunas excepciones generales que se aplican a todos de Power BI y existen algunas excepciones específico del servicio o de la función, cada uno de los cuales se documentan en las secciones siguientes.

### Excepciones generales Power BI y ExpressRoute

Una excepción **Power BI** y **ExpressRoute** significa que los datos que se transmiten desde Power BI o pasan a través de la red Internet pública, en lugar de transmitirse a través del vínculo ExpressRoute privado.

Las dos excepciones general para Power BI mediante ExpressRoute son:

-   Archivos estáticos que se descarga desde el **red de entrega de contenido (CDN)** y sitios Web

-   
            **Telemetría** datos enviados a través de la red Internet pública

Power BI usa varios **redes de entrega de contenido (CDN)** o sitios web para distribuir eficazmente los archivos a los usuarios según la región geográfica a través de la red Internet pública y es necesario contenido estático. Estos archivos estáticos incluyen descargas de productos (como **Power BI Desktop**, **puerta de enlace de datos local**, o **paquetes de contenido de Power BI** de distintos proveedores de servicios independientes), archivos de configuración de explorador que se usan para iniciar y establecer las conexiones posteriores con Power BI, así como la página Inicio de sesión seguro inicial de Power BI: sólo se envían las credenciales reales sobre ExpressRoute.   

Ciertos **datos de telemetría** también se envía a través de la red Internet pública y ExpressRoute. Los datos de telemetría incluyen las estadísticas de uso y datos similares, que se transmiten a los servicios que se utilizan para supervisar la actividad y el uso.

### ExpressRoute y aplicación de SaaS de BI de energía

Cuando un usuario inicia una conexión con el servicio Power BI (powerbi.com o a través de Cortana), la página de inicio de Power BI, la página de inicio de sesión y los archivos estáticos que preparación el explorador para conectarse e interactuar con Power BI se recuperan de una CDN o sitios Web, que se conecta a través de la red Internet pública.

Una vez establecido el inicio de sesión, se producen las interacciones de datos subsiguientes de Power BI con ExpressRoute, con la excepción de ciertas características y servicios que dependen de datos públicos de Internet:

-   
            **Asignar elementos visuales** requieren la transmisión de datos y la conexión al servicio Bing Virtual Earth o el servicio de coordenadas geográficas de Bing, cada uno de los cuales se establece a través de la red Internet pública.

-   Con la integración de BI de energía **Cortana** requiere acceso a Bing a través de la Internet pública.

-   Cuando **vínculos personalizados** se agregan a un usuario, como un widget de imagen o un vídeo, Power BI solicita datos basándose en el vínculo proporcionado por el usuario, que pueden o no se puede usar ExpressRoute.

-   Los usuarios pueden enviar **comentarios a Power BI** en texto (y, opcionalmente, imágenes) sobre el mecanismo de comentarios de voz del usuario, que utiliza la red Internet pública para la transmisión.

-   El **proveedor de contenido de noticias de Bing** descarga contenido de Bing mediante la red Internet pública.

-   Al conectarse a **aplicaciones** (por ejemplo, paquetes de contenido), los usuarios a menudo deben escribir las credenciales y configuraciones mediante páginas proporcionadas por el proveedor de SaaS. Estas páginas pueden o no pueden usar ExpressRoute.


|Actividad del usuario |Destination|
|---|---|
|Página de aterrizaje (antes del inicio de sesión)| `maxcdn.bootstrapcdn.com ; ajax.aspnetcdn.com ; netdna.bootstrapcdn.com ; cdn.optimizely.com; google-analytics.com ` |
|Login | `*.mktoresp.com ; *.aadcdn.microsoftonline-p.com ; *.msecnd.com ; *.localytics.com ; ajax.aspnetcdn.com`  |
|Panel, informes, administración de conjunto de datos (incluye mapas y codificación geográfica)| `*.localytics.com ; *.virtualearch.net ; platform.bing.com; powerbi.microsoft.com; c.microsoft.com; app.powerbi.com; *.powerbi.com; dc.services.visualstudio.com `  |
|Support| `support.powerbi.com ; powerbi.uservoice.com ; go.microsoft.com `|


### Power BI Desktop y ExpressRoute

Power BI Desktop también es compatible con algunas excepciones que se describen en la siguiente lista de ExpressRoute:

-   
            **Notificaciones de actualización**, se utiliza para detectar si los usuarios tienen la versión más reciente de Power BI Desktop, vaya a través de la Internet pública.

-   Ciertos **datos de telemetría** supera la Internet pública.

-   
            **Asignar elementos visuales** requieren la transmisión de datos y la conexión a la **Bing Virtual Earth** servicio o la **coordenadas geográficas de Bing** servicio, cada uno de los cuales se establece a través de la red Internet pública.

-   
            **Obtener datos** de datos de varios orígenes como **Web** o proveedores de SaaS de terceros pasan por la Internet pública.


### Power BI PaaS y ExpressRoute

Power BI ofrece API y otras características de plataforma que permiten a los desarrolladores crear aplicaciones y soluciones personalizadas de Power BI. Los siguientes servicios, además de telemetría y datos de la red CDN mencionados anteriormente en este tema, se utilizan cuando se transmiten datos de Power BI PaaS sobre la Internet pública:

|Actividad de PaaS |Destinos adicionales que se utilizan |
|---|---|
|Público incrustar telemetría)| `c1.microsoft.com` |
|Elementos visuales personalizados (CDN) | `*.azureedge.net`  |

Algunos **elementos visuales personalizados** creadas por terceros, algunas son creadas por Microsoft. Pueden, o no se puede usar ExpressRoute.

### Power BI Mobile y ExpressRoute

Este documento no cubre el uso de aplicaciones móviles de Power BI.  


### Datos locales puerta de enlace y ExpressRoute

Cuando un **puerta de enlace de datos local** se usa con Power BI, las transmisiones están conformes con la excepción de las actividades de usuario que se documentan en ExpressRoute el **aplicación SaaS de Power BI y ExpressRoute** sección aparecía anteriormente en este tema.  

<properties
pageTitle="Preguntas más frecuentes de puerta de enlace de datos local"
description="Se trata de la puerta de enlace de datos local preguntas más frecuentes. Éste reúne las preguntas más frecuentes en un solo lugar para la puerta de enlace."
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
ms.tgt_pltfrm="na"
ms.workload="powerbi"
ms.date="10/12/2016"
ms.author="asaxton"/>
# Preguntas más frecuentes de puerta de enlace de datos local

<!-- Shared FAQ shared Include -->
[AZURE.INCLUDE [gateway-onprem-faq-shared-include](../includes/gateway-onprem-faq-shared-include.md)]

## Analysis Services


            **Pregunta:** puedo usar msdmpump.dll para crear asignaciones de nombre de usuario efectivo personalizado para Analysis Services?  

            **Respuesta:** no. Esto no se admite en este momento.


            **Pregunta:** puedo usar la puerta de enlace para conectarse a una instancia multidimensional (OLAP).  

            **Respuesta:** Sí! La puerta de enlace de enterprise admite conexiones directas a los modelos tabulares de Analysis Services y multidimensionales.


            **Pregunta:** ¿Qué ocurre si instalo la puerta de enlace en un equipo en un dominio distinto de mi servidor local que usa la autenticación de Windows?  

            **Respuesta:** garantías aquí. Todo depende de la relación de confianza entre los dos dominios. Si los dos dominios diferentes están en un modelo de dominio de confianza, a continuación, la puerta de enlace pueden conectarse al servidor de Analysis Services y se puede resolver el nombre de usuario efectivo. Si no es así, se puede producir un error de inicio de sesión. 


            **Pregunta:** ¿Cómo puedo encontrar a qué nombre de usuario efectivo se pasa a mi servidor de Analysis Services local?  

            **Respuesta:** respondemos en el [artículo de solución de problemas](powerbi-gateway-onprem-tshoot.md).


            **Pregunta:** tener 25 bases de datos en Analysis Services, allí es una manera escribirlos habilitado para la puerta de enlace a la vez?  

            **Respuesta:** no. Se trata de la guía, pero no tenemos un período de tiempo.

## Administration


            **Pregunta:** ¿puedo tener más de un administrador de una puerta de enlace?  

            **Respuesta:** Sí! Al administrar una puerta de enlace, puede ir a la pestaña del administrador para agregar administradores adicionales.


            **Pregunta:** el Administrador de puerta de enlace debe ser un administrador en el equipo donde está instalada la puerta de enlace?  

            **Respuesta:** no. El Administrador de puerta de enlace se utiliza para administrar la puerta de enlace desde el servicio. 


            **Pregunta:** puedo evitar que los usuarios de mi organización desde la creación de una puerta de enlace?  

            **Respuesta:** no. Se trata de la guía, pero no tenemos un período de tiempo.


            **Pregunta:** puedo obtener información de uso y las estadísticas de las puertas de enlace de mi organización?  

            **Respuesta:** no. Se trata de la guía, pero no tenemos un período de tiempo.

## Power BI


            **Pregunta:** Si utilizo la puerta de enlace de Power BI actual para las implementaciones empresariales, ¿necesito actualizar?

            **Respuesta:** Sí, pero es sencillo hacerlo ya que sólo funciona del mismo modo se actualizó a la puerta de enlace empresarial más reciente. Puerta de enlace de datos simple las instalaciones nuevas de instalación para actualizar la puerta de enlace existente.


            **Pregunta:** Necesito actualizar la puerta de enlace personal?

            **Respuesta:** No, puede seguir usando la puerta de enlace personal de Power BI.


            **Pregunta:** con qué frecuencia se actualizan cuando se conecta a través de la puerta de enlace empresarial de mosaicos en un panel en Power BI,?  

            **Respuesta:** unos diez minutos. Conexiones de DirectQuery son precisamente eso. Esto no significa que un mosaico emite una consulta a su servidor local y nuevos datos, muestra cada diez minutos.


            **Pregunta:** ¿Puedo cargar libros de Excel con modelos de datos de PowerPivot que se conectan a orígenes de datos locales? ¿Necesita una puerta de enlace para este escenario?  

            **Respuesta:** Sí, puede cargar el libro. Y no, no necesita una puerta de enlace. Pero, dado que los datos residen en el modelo de datos de Excel, informes de Power BI basadas en el libro de Excel no serán dinámicos. Para actualizar los informes en Power BI, se tendría que volver a cargar un libro actualizado cada vez. O bien, utilizar la puerta de enlace con la actualización programada.


            **Pregunta:** si los usuarios comparten paneles que tiene una conexión de DirectQuery, los otros usuarios podrán ver los datos, aunque quizás no tengan los mismos permisos.  

            **Respuesta:** para un panel conectado a Analysis Services, los usuarios sólo verán los datos que tienen acceso. Si los usuarios no tienen los mismos permisos, no podrá ver ningún dato. Para otros orígenes de datos, todos los usuarios comparten las credenciales especificadas por el administrador para ese origen de datos.


            **Pregunta:** requerido utilizar la puerta de enlace de una licencia de Pro?  

            **Respuesta:** Sí.


            **Pregunta:** Pro requerido una licencia para los usuarios al interactuar con un panel o informe que hace uso de la puerta de enlace?  

            **Respuesta:** Sí.


            **Pregunta:** ¿por qué no puedo conectarme a mi servidor Oracle?  

            **Respuesta:** debe instalar el cliente de Oracle y configurar el archivo tnsnames.ora con la información del servidor correcta para poder conectarse al servidor de Oracle. Se trata de una instalación independiente fuera de la puerta de enlace. Para obtener más información, consulte [instalar el cliente de Oracle](powerbi-gateway-onprem-manage-oracle.md#installing-the-oracle-client).


            **Pregunta:** funcionará la puerta de enlace con ExpressRoute?  

            **Respuesta:** Sí. Para obtener más información acerca de ExpressRoute y Power BI, consulte [Power BI y ExpressRoute](powerbi-admin-power-bi-expressroute.md).

## Consulte también
[Puerta de enlace de datos local](powerbi-gateway-onprem.md)  
[Puerta de enlace de datos a local detallada](powerbi-gateway-onprem-indepth.md)  
[Solución de problemas de la puerta de enlace de datos local](powerbi-gateway-onprem-tshoot.md)  
¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
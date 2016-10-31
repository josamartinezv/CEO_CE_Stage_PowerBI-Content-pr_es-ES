<properties
pageTitle="Configuración de proxy para la puerta de enlace de datos local"
description="Información acerca de la configuración del proxy de la puerta de enlace de datos local."
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
ms.tgt_pltfrm="na"
ms.workload="powerbi"
ms.date="10/01/2016"
ms.author="asaxton"/>
# Configuración de proxy para la puerta de enlace de datos local

El entorno de trabajo puede requerir que pasen por un proxy para tener acceso a internet. Esto puede impedir que en local Data Gateway de conectar con el servicio.

## ¿Su red utiliza a un servidor proxy?

La siguiente entrada en superuser.com describe cómo puede probar determinar si tiene un proxy en la red.

[¿Cómo sé qué servidor proxy que estoy usando? (SuperUser.com)](https://superuser.com/questions/346372/how-do-i-know-what-proxy-server-im-using)

## Configuración de la ubicación y el valor predeterminado del archivo de configuración

Información de proxy se configura en un archivo de configuración. NET. La ubicación y los nombres de archivo, será diferentes dependiendo de la puerta de enlace que se está utilizando.

### Puerta de enlace de datos local

Hay dos archivos de configuración principales que participan en la puerta de enlace de datos local.

**Configuración**

La primera es para las pantallas de configuración que en realidad configuración la puerta de enlace. Si tiene problemas de configuración de la puerta de enlace, este es el archivo que desea examinar.

    C:\Program Files\On-premises data gateway\enterprisegatewayconfigurator.exe.config

**Servicio de Windows**

La segunda es para el servicio de windows real que interactúa con el servicio Power BI y controla las solicitudes.

    C:\Program Files\On-premises data gateway\Microsoft.PowerBI.EnterpriseGateway.exe.config

### Puerta de enlace de Power BI - Personal

La puerta de enlace personal puede instalarse en una de dos maneras. Como un servicio de windows (admin) o como una aplicación en modo usuario. Esto se determina durante la instalación. Como resultado, los archivos de configuración pueden estar en uno de dos ubicaciones, dependiendo de cómo se haya instalado la puerta de enlace. Desea comprobar ambas ubicaciones.

**Configuración**

La primera es para las pantallas de configuración que en realidad configuración la puerta de enlace. Si tiene problemas de configuración de la puerta de enlace, este es el archivo que desea examinar.

Para el *servicio de windows*, será la siguiente.

    C:\Program Files\Power BI Personal Gateway\1.0\Configurator\GWConfig.exe.config
    C:\Program Files\Power BI Personal Gateway\1.0\Configurator\PowerBIGatewayAgentCmdLine.exe.config

Para el *aplicación de modo usuario*, será la siguiente.

    C:\Users\<user>\AppData\Local\Power BI Gateway - Personal \1.0\Configurator\GWConfig.exe.config
    C:\Users\<user>\AppData\Local\Power BI Gateway - Personal \1.0\Configurator\PowerBIGatewayAgentCmdLine.exe.config

**Servicio de Windows**

La segunda es para el servicio de windows real que interactúa con el servicio Power BI y controla las solicitudes.

Para el *servicio de windows*, será la siguiente.

    C:\Program Files\Power BI Personal Gateway\1.0\Gateway\diawp.exe.config

Para el *aplicación de modo usuario*, será la siguiente.

    C:\Users\<user>\AppData\Local\Power BI Gateway - Personal \1.0\Gateway\diawp.exe.config

## Configuración de los ajustes del proxy

La configuración del proxy predeterminada es la siguiente.

    <system.net>
        <defaultProxy useDefaultCredentials="true" />
    </system.net>

La configuración predeterminada funciona con la autenticación de windows. Si el servidor proxy usa otro tipo de autenticación, debe cambiar la configuración. Si no está seguro, póngase en contacto con el Administrador de red.

Para obtener más información acerca de la configuración de los elementos de proxy para los archivos de configuración. NET, consulte [defaultProxy Element (Network Settings)](https://msdn.microsoft.com/library/kd3cf2ex.aspx)

## Cambiar la cuenta de servicio de puerta de enlace a un usuario de dominio

Al configurar la configuración de proxy para utilizar las credenciales predeterminadas, como se explicó anteriormente, pueden producirse problemas de autenticación con el servidor proxy. Esto es porque la cuenta de servicio predeterminada es el SID de servicio y no es un usuario de dominio autenticado. Puede cambiar la cuenta de servicio de la puerta de enlace para permitir la autenticación correcta con el servidor proxy.

> [AZURE.NOTE] Se recomienda que utilice una cuenta de servicio administrada para evitar tener que restablecer las contraseñas. Obtenga información acerca de cómo crear un [cuenta de servicio administrada](https://technet.microsoft.com/library/dd548356.aspx) dentro de Active Directory.

### Cambiar la cuenta de servicio de puerta de enlace de datos local

1. Cambiar la cuenta de servicio de Windows para el **servicio de puerta de enlace de datos local**. 

    La cuenta predeterminada para este servicio es *SERVICE\PBIEgwService NT*. Desea cambiarlo a una cuenta de usuario de dominio dentro de su dominio de Active Directory. O bien, si desea utilizar una cuenta de servicio administrada para evitar tener que cambiar la contraseña.

    Desea cambiar la cuenta en la **Inicio de sesión** ficha dentro de las propiedades del servicio de Windows.

2. Reinicie el **servicio de puerta de enlace de datos local**.

    Desde un símbolo del sistema de administración, emita los siguientes comandos.

        net stop PBIEgwService

        net start PBIEgwService

3. Iniciar el **Configurador de puerta de enlace de datos local**. Puede seleccionar el botón de inicio de windows y busque *puerta de enlace de datos local*.

4. Inicie sesión Power BI.

5. Restaure la puerta de enlace con la clave de recuperación.

    Esto permitirá que la nueva cuenta de servicio descifrar las credenciales almacenadas para orígenes de datos.

## Consulte también

[Información de Firewall](powerbi-gateway-onprem-tshoot.md#firewall-or-proxy)  
¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
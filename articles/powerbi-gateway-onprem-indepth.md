<properties
pageTitle="Puerta de enlace de datos a local detallada"
description="Este artículo examina la puerta de enlace local detallada. Esto se estudia cómo funciona el servicio con Azure Active Directory y su Active Directory local cuando se trabaja con Analysis Services"
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
# Puerta de enlace de datos a local detallada

Los usuarios de su organización pueden ver los datos locales, pero antes de que los usuarios pueden conectarse al origen de datos local, una puerta de enlace de datos local debe estar instalado y configurado. La puerta de enlace facilita la comunicación interna de un usuario en la nube a su origen de datos local y volver a la nube segura y rápida.

Instalar y configurar una puerta de enlace se realiza normalmente por un administrador. Puede que necesite un conocimiento especial de los servidores locales y en algunos casos puede necesitar permisos de administrador del servidor.

Este artículo no proporciona instrucciones paso a paso acerca de cómo instalar y configurar la puerta de enlace. Para ello, asegúrese de ver [puerta de enlace de datos local](powerbi-gateway-onprem.md). Este artículo pretende proporcionar una comprensión detallada del funcionamiento de la puerta de enlace. También presentaremos información detallada sobre los nombres de usuario y la seguridad de Azure Active Directory y Analysis Services, y cómo el servicio de nube usa la dirección de correo electrónico con un inicio de sesión de usuario, la puerta de enlace y Active Directory para conectarse de forma segura y consultar los datos locales.

<!-- Shared Requirements Include -->
[AZURE.INCLUDE [gateway-onprem-requirements-include](../includes/gateway-onprem-how-it-works-include.md)]

<!-- Shared Install steps Include -->
[AZURE.INCLUDE [gateway-onprem-datasources-include](../includes/gateway-onprem-datasources-include.md)]

## Inicie sesión en la cuenta

Los usuarios iniciar sesión con un trabajo o escuela cuenta. Se trata de la cuenta de la organización. Si registró para una oferta de Office 365 y no ha proporcionado el correo electrónico de trabajo real, podría parecer nancy@contoso.onmicrosoft.com. La cuenta en un servicio de nube, se almacena en un inquilino de Azure Active Directory (AAD). En la mayoría de los casos, los UPN de la cuenta AAD coincidirá con la dirección de correo electrónico.

## Autenticación para orígenes de datos locales

Una credencial almacenada se utilizará para conectarse a orígenes de datos locales de la puerta de enlace excepto a Analysis Services. Independientemente del usuario individual, la puerta de enlace utiliza la credencial almacenada para conectarse. 

## Autenticación a un origen de datos de Analysis Services en directo 

Cada vez que un usuario interactúa con Analysis Services, el nombre de usuario efectivo se pasa a la puerta de enlace y, a continuación, en el servidor de Analysis Services local. El nombre principal de usuario (UPN), normalmente la dirección de correo electrónico que inicie sesión en la nube, es lo que se pasará a Analysis Services como el usuario efectivo. El UPN se pasa la propiedad de conexión EffectiveUserName. Esta dirección de correo electrónico debe coincidir con un UPN definido dentro del dominio de Active Directory local. El UPN es una propiedad de una cuenta de Active Directory. A continuación, esa cuenta de Windows debe estar presente en una función de Analysis Services para tener acceso al servidor. El inicio de sesión no tendrá éxito si se encuentra ninguna coincidencia en Active Directory.

Analysis Services también pueden proporcionar filtrado basado en esta cuenta. El filtrado puede producirse con la seguridad basada en roles o seguridad de nivel de fila.

## Seguridad basada en roles

Los modelos proporcionan seguridad basada en roles de usuario. Las funciones se definen para un proyecto de modelo determinado durante la edición de SQL Server Data Tools – Business Intelligence (SSDT-BI), o después de implementa un modelo, mediante el uso de SQL Server Management Studio (SSMS). Roles contienen a miembros por nombre de usuario o grupo de Windows. Roles definen los permisos que un usuario tiene para consultar o realizar acciones en el modelo. La mayoría de los usuarios pertenecerá a un rol con permisos de lectura. Otros roles están diseñados para los administradores con permisos para procesar elementos, administrar las funciones de base de datos y administrar otros roles.

## Seguridad de nivel de fila

Seguridad de nivel de fila es específica para la seguridad de nivel de fila de Analysis Services. Modelos pueden proporcionar seguridad dinámica de nivel de fila. A diferencia de tener al menos un rol que pertenecen a los usuarios, la seguridad dinámica no es necesaria para cualquier modelo tabular. En una alto nivel, la seguridad dinámica define el acceso de lectura de un usuario a datos delimitado a una fila determinada en una tabla determinada. Similar a los roles, la seguridad dinámica de nivel de fila se basa en nombre de usuario de Windows del usuario.

Capacidad de un usuario a la consulta y ver los datos de modelo se determina primero mediante las funciones de su cuenta de usuario de Windows es un miembro de y en segundo lugar, la seguridad dinámica de nivel de fila, si ha configurado.

Rol de aplicación y seguridad dinámica de nivel de fila en los modelos están fuera del ámbito de este artículo.  Puede obtener más información en [Roles (SSAS Tabular)](https://msdn.microsoft.com/library/hh213165.aspx) y [Roles de seguridad (Analysis Services - datos multidimensionales)](https://msdn.microsoft.com/library/ms174840.aspx) en MSDN. Y, para obtener una descripción más detallada de la seguridad de modelos tabulares, descargue y lea la protección del [notas del producto modelo semántico de BI Tabular](https://msdn.microsoft.com/library/jj127437.aspx). 

## ¿Qué sucede con Azure Active Directory?

Uso de servicios de nube de Microsoft [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/) encargarse de autenticar a los usuarios. Azure Active Directory es el inquilino que contiene grupos de nombres de usuario y seguridad. Normalmente, un usuario inicia sesión con la dirección de correo electrónico es el mismo que el UPN de la cuenta.

¿Cuál es la función de mi local de Active Directory?

Para que Analysis Services determinar si un usuario se conecta a él pertenece a un rol con permisos para leer los datos, el servidor debe convertir el nombre de usuario efectivo pasado de AAD a la puerta de enlace y en el servidor de Analysis Services. El servidor de Analysis Services pasa el nombre de usuario efectivo a un controlador de dominio (DC) de Active Directory de Windows. El DC de Active Directory, a continuación, valida la vigencia del nombre de usuario es un UPN válido en una cuenta local y devuelve el nombre de usuario de Windows del usuario al servidor de Analysis Services.

No se puede usar EffectiveUserName en un servidor unido a un dominio no Analysis Services. El servidor de Analysis Services debe estar unido a un dominio para evitar los errores de inicio de sesión.

## ¿Cómo se puede saber qué es mi UPN?

Puede que no sepa qué es el UPN y puede que no sea un administrador de dominio. Puede utilizar el siguiente comando desde la estación de trabajo para averiguar el UPN de la cuenta.

    whoami /upn

El resultado tendrá un aspecto similar a una dirección de correo electrónico, pero esto es el UPN de la cuenta de dominio local. Si utiliza un origen de datos de Analysis Services para las conexiones en directo, debe coincidir con lo que se pasó a EffectiveUserName de la puerta de enlace.

## Asignación de nombres de usuario para los orígenes de datos de Analysis Services

Power BI permite la asignación de nombres de orígenes de datos de Analysis Services. Puede configurar reglas para asignar un nombre de usuario que inició sesión con Power BI en un nombre que se pasa para EffectiveUserName en la conexión de Analysis Services. La característica nombres de usuario de asignación es una excelente manera de evitar cuando su nombre de usuario de AAD no coincide con un UPN en su Active Directory local. Por ejemplo, si su dirección de correo electrónico es nancy@contoso.onmicrsoft.com, podría asignar a nancy@contoso.com, y ese valor se pasará a la puerta de enlace. Puede obtener más información acerca de cómo [asignar nombres de usuario](powerbi-gateway-enterprise-manage-ssas.md#map-user-names).

## Sincronizar un Active Directory local con Azure Active Directory

¿Desea que las cuentas de Active Directory locales para que coincida con Azure Active Directory si va a usar conexiones directas de Analysis Services. Como el UPN debe coincidir entre las cuentas.

Los servicios de nube solo saber acerca de las cuentas de Active Directory de Azure. No importa si ha agregado una cuenta en su Active Directory local, si no existe en AAD, no se puede usar. Hay diferentes maneras que puede coincidir con las cuentas de Active Directory locales con Azure Active Directory.

1.  Puede agregar manualmente cuentas de Azure Active Directory.

    Puede crear una cuenta en el portal de Azure, o en el Portal de administración de Office 365, y el nombre de cuenta coincide con el UPN de la cuenta de Active Directory local.

2.  Puede usar el [Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) herramienta para sincronizar las cuentas locales para el inquilino de Azure Active Directory.

    La herramienta Azure AD Connect proporciona opciones para la sincronización de directorios y la contraseña. Si no son administradores de inquilinos o un administrador de dominio local, debe ponerse en contacto con el Administrador de TI para obtener este configurado.

3.  Puede configurar los servicios de federación de Active Directory (ADFS).

    Puede asociar el servidor de ADFS en el inquilino AAD con el [Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) herramienta. Experiencia hace ADFS, uso de la sincronización de directorios descritos anteriormente, pero permite un inicio de sesión único (SSO). Por ejemplo, si se encuentra en la red de trabajo, cuando un servicio de nube y vaya a iniciar sesión, no puede le pedirá que especifique un nombre de usuario o contraseña. Debe analizar con el Administrador de TI, si está disponible para su organización.

El uso de Azure AD Connect garantiza que coincida con el UPN entre AAD y su Active Directory local.

> [AZURE.NOTE] Sincronización de cuentas con la herramienta Azure AD Connect creará cuentas nuevas dentro de su inquilino de ADD.

## Ahora, aquí es donde entra en juego la puerta de enlace

La puerta de enlace actúa como puente entre la nube y el servidor local. Transferencia de datos entre la nube y la puerta de enlace se protege mediante [Bus de servicio de Azure](https://azure.microsoft.com/documentation/services/service-bus/). El Bus de servicio, se crea un canal seguro entre la nube y el servidor local a través de una conexión saliente en la puerta de enlace.  No hay ninguna conexión entrante que se debe abrir en el firewall local.

Si tiene un origen de datos de Analysis Services, debe instalar la puerta de enlace en un equipo unido al mismo bosque o dominio que el servidor de Analysis Services.

Cuanto más se acerque la puerta de enlace es el servidor, más rápida será la conexión. Si la puerta de enlace puede obtener en el mismo servidor que el origen de datos, que es mejor evitar la latencia de red entre la puerta de enlace y el servidor.

## Dónde pueden surgir problemas

No se puede instalar a veces la puerta de enlace. O tal vez parece bien instalar la puerta de enlace, pero el servicio sigue sin poder trabajar con él. En muchos casos, es algo simple, como la contraseña de las credenciales de la puerta de enlace que se utiliza para iniciar sesión en el origen de datos.

En otros casos, puede haber problemas con el tipo de dirección de correo electrónico a los usuarios inician sesión o no Analysis Services resolver un nombre de usuario eficaz. Si tiene varios dominios con relaciones de confianza entre ellos y la puerta de enlace está en uno y Analysis Services en otro, a veces puede producir algunos problemas.

En su lugar de acudir a la solución de problemas de la puerta de enlace aquí, hemos reunido una serie de pasos en el artículo de solución de problemas [Solución de problemas de la puerta de enlace de datos local](powerbi-gateway-onprem-tshoot.md). Espero que no tenga problemas. Pero si lo hace, comprender cómo todo funciona y el artículo de solución de problemas debe ayudar a.

<!-- Account and Port information -->
[AZURE.INCLUDE [gateway-onprem-accounts-ports-more](../includes/gateway-onprem-accounts-ports-more.md)]

## Consulte también

[Solución de problemas de la puerta de enlace de datos local](powerbi-gateway-onprem-tshoot.md)  
[Service Bus de Azure](https://azure.microsoft.com/documentation/services/service-bus/)  
[Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)  
¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
<properties
   pageTitle="Permisos de Power BI"
   description="Permisos de Power BI"
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
   ms.date="08/23/2016"
   ms.author="asaxton"/>

# Permisos de Power BI

## Ámbitos de permiso
Permisos de Power BI proporcionan a una aplicación la capacidad de realizar ciertas acciones en nombre de un usuario. Todos los permisos deben estar aprobados por el usuario para que sean válidos.

|Nombre para mostrar|Descripción|Valor de ámbito|
|---|---|---|
|Ver todos los conjuntos de datos|La aplicación puede ver todos los conjuntos de datos para el usuario ha iniciado sesión y que el usuario tiene acceso a los conjuntos de datos.|Dataset.Read.All|
|Leer y escribir todos los conjuntos de datos|La aplicación puede ver y escribir en todos los conjuntos de datos para el usuario que inicia sesión y conjuntos de datos que el usuario tiene acceso a.|Dataset.ReadWrite.All|
|Ver grupos de usuarios|La aplicación puede ver todos los grupos a los que pertenece el usuario ha iniciado sesión.|Group.Read.All|
|Ver todos los paneles (vista previa)|La aplicación puede ver todos los paneles para el usuario ha iniciado sesión y paneles que el usuario tiene acceso.|Dashboard.Read.All|
|Ver todos los informes (vista previa)|La aplicación puede ver todos los informes para que el usuario ha iniciado sesión y que el usuario tenga acceso a. La aplicación también puede ver los datos de los informes, así como su estructura.|Report.Read.All|

Una aplicación puede solicitar permisos cuando primero intenta iniciar sesión en la página de un usuario pasando los permisos solicitados en el parámetro de ámbito de la llamada. Si se conceden los permisos, se devolverá un token de acceso a la aplicación que se puede usar en futuras llamadas API. Sólo puede utilizarse el acceso mediante una aplicación específica.

## Solicitar permisos
Aunque puede llamar a la API para autenticarse con un nombre de usuario y una contraseña, para realizar acciones en nombre de otro usuario, necesitará solicitar permisos que el usuario aprobará posteriormente y, a continuación, enviar el token de acceso resultante en todas las futuras llamadas. En este proceso, se sigue el estándar [OAuth 2.0](http://oauth.net/2/) protocolo. Aunque la implementación real puede variar, el flujo de OAuth de Power BI tiene los siguientes elementos:

- 
            **Interfaz de Usuario de inicio de sesión** : se trata de una interfaz de Usuario que el desarrollador puede evocar para solicitar permisos. Requeriría que el usuario inicie sesión en si aún no está. El usuario también necesitaría aprobar los permisos que solicita la aplicación. La ventana de inicio de sesión contabilizará un código de acceso o un mensaje de error en una dirección URL de redireccionamiento proporcionado.
    - Una dirección URL de redireccionamiento estándar debe proporcionar Power BI para su uso por las aplicaciones nativas.
- 
            **Código de autorización** -devuelve códigos de autorización para aplicaciones web después de iniciar sesión a través de los parámetros de URL en la dirección URL de redireccionamiento. Puesto que están en parámetros hay algunos riesgos de seguridad. Aplicaciones Web tendrán que intercambiar el código de autorización para un Token de autorización
- 
            **Token de autorización** -se utilizan para autenticar las llamadas de API en nombre de otro usuario. Se limitarán a una aplicación específica. Los tokens tienen una duración establecida y cuando caducan necesitan actualizarse.
- 
            **Token de actualización** : cuando expiren los tokens será un proceso de actualización de estos.

¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)

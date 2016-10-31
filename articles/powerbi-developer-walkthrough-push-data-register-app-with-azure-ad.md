<properties
   pageTitle="Registrar una aplicación con Azure AD"
   description="Tutorial: insertar datos en un panel: registrar una aplicación con Azure AD"
   services="powerbi"
   documentationCenter=""
   authors="guyinacube"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="monitoring"
   qualityDate="04/15/2016"/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="get-started-article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/23/2016"
   ms.author="asaxton"/>

# Paso 1: Registrar una aplicación con Azure AD

Este artículo forma parte de un tutorial paso a paso para [Insertar datos en un panel](powerbi-developer-walkthrough-push-data.md).

El primer paso para insertar datos en un panel de Power BI es registrar su aplicación en Azure AD. Debe hacer esto en primer lugar para que tenga un **Id. de cliente** que identifica la aplicación en Azure AD. Sin un **Id. de cliente**, Azure AD no puede autenticar la aplicación.

>
            **NOTA**: antes de registrar una aplicación de Power BI, necesita [suscribirse en Power BI](powerbi-admin-free-with-custom-azure-directory.md).

Estos son los pasos para registrar una aplicación en Azure AD.

## Registrar una aplicación en Azure AD

1. Vaya a dev.powerbi.com/apps.
2. Haga clic en **inicie sesión con su cuenta existente**, e inicie sesión en su cuenta de Power BI.
3. Escriba un **nombre de aplicación** como "Aplicación de datos de ejemplo inserción".
4. Para **el tipo de aplicación**, elija **aplicación nativa**.
5. Escriba un **dirección URL de redireccionamiento**, como **https://login.live.com/oauth20_desktop.srf**. Para una **aplicación Native client**, proporciona un uri de redireccionamiento **Azure AD** obtener más información sobre la aplicación específica que autenticará. El Uri para una aplicación de cliente estándar es https://login.live.com/oauth20_desktop.srf.
6. Para **Elija API para tener acceso a**, elija **leer y escribir todos los conjuntos de datos**. Para todos los permisos de la aplicación de Power BI, consulte [permisos de Power BI](powerbi-developer-power-bi-permissions.md).
7. Haga clic en **Registrar aplicación**, y guarde el **Id. de cliente** que se ha generado. Un **Id. de cliente** identifica la aplicación en Azure AD.

Le mostramos cómo su **registrar una aplicación de Power BI** página debe ser:

![](media\powerbi-developer-walkthrough-push-data\powerbi-developer-sample-register-app.png)

El paso siguiente muestra cómo al [obtener un acceso de autenticación token](powerbi-developer-walkthrough-push-data-get-token.md).

[Siguiente paso >](powerbi-developer-walkthrough-push-data-get-token.md)

## Consulte también

[Registrarse para Power BI](powerbi-admin-free-with-custom-azure-directory.md)  
[Obtener un acceso de autenticación token](powerbi-developer-walkthrough-push-data-get-token.md)  
[Tutorial: Insertar datos en un panel](powerbi-developer-walkthrough-push-data.md)  
[Registrar una aplicación cliente](powerbi-developer-register-a-client-app.md)  
[Información general sobre la API de REST de Power BI](powerbi-developer-overview-of-power-bi-rest-api.md)  
¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)

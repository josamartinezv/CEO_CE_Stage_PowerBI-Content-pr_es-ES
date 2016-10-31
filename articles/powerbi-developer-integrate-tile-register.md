<properties
   pageTitle="Registrar una aplicación web con Azure AD"
   description="Registrar una aplicación web con Azure AD"
   services="powerbi"
   documentationCenter=""
   authors="guyinacube"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="monitoring"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="get-started-article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/23/2016"
   ms.author="asaxton"/>

# Paso 1: Registrar una aplicación web con Azure AD

## Introducción

En este paso de la [integrar un mosaico en un tutorial de la aplicación](powerbi-developer-integrate-tile.md), registre la aplicación en **Azure Active Directory (AD)**. Debe hacer esto en primer lugar para que tenga un **Id. de cliente** y **secreto de cliente** que identifica la aplicación web en Azure AD. Sin un **Id. de cliente** y **secreto de cliente**, Azure AD no puede autenticar la aplicación web. Si descargó el [integrar un ejemplo de mosaico](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app), utiliza el **Id. de cliente** y **secreto de cliente** obtener después del registro para configurar el ejemplo para que pueda autenticar el ejemplo a Azure AD.

![](media\powerbi-developer-integrate-tile\integrate-tile-step1a.png)

>
            **NOTA**: antes de registrar una aplicación web para **Power BI**, necesita [suscribirse en Power BI](powerbi-admin-free-with-custom-azure-directory.md).

Estos son los pasos para registrar una aplicación web en Azure AD.

## Registrar una aplicación web en Azure AD

1. Vaya a dev.powerbi.com/apps.
2. Haga clic en **inicie sesión con su cuenta existente**, e inicie sesión en su cuenta de Power BI.
3. Escriba un **nombre de la aplicación**. En este tutorial, escriba **integrar un mosaico de ejemplo**.
4. Para **el tipo de aplicación**, elija **aplicación de servidor Web**.
5. Escriba un **dirección URL de redireccionamiento**. En este tutorial, Azure AD redirige a la página predeterminada, por tanto, escriba 13526. Azure Active Directory (AD) se redirigirá a esta página con un **código de autorización**. Para obtener información sobre cómo adquirir un **el Token de acceso** para tener acceso a **Power BI** mosaicos mediante un **código de autorización**, consulte [obtener un acceso de autenticación token](powerbi-developer-integrate-tile-get-dashboard.md#get-token).
6. Escriba un **página principal**. En este tutorial, escriba 13526 que es la página principal del ejemplo.
7. Para **Elija API para tener acceso a**, elija **(vista previa) de todos los paneles de lectura**. Para todos los permisos de la aplicación de Power BI, consulte [permisos de la aplicación](powerbi-developer-power-bi-permissions.md).
7. Haga clic en **Registrar aplicación**, y guarde el **Id. de cliente** y **secreto de cliente** que se ha generado. Un **Id. de cliente** y **secreto de cliente** identifica la aplicación en Azure AD. Para configurar el [integrar un ejemplo de mosaico](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app) utilizar el **Id. de cliente** y **secreto de cliente** para autenticar, consulte [Configurar la integración de un mosaico de ejemplo](powerbi-developer-integrate-tile-register.md#configure-sample).

Le mostramos cómo su **registrar una aplicación de Power BI** página debe ser:

![](media\powerbi-developer-integrate-tile\register-app.png)

Ahora que ha registrado su aplicación web con **Azure AD**, puede obtener un acceso de autorización de token de **Azure AD** acceso **Power BI** paneles y mosaicos.

![](media\powerbi-developer-integrate-tile\integrate-tile-step1b.png)

Después de tener un **Id. de cliente** y **secreto de cliente**, puede configurar la aplicación web, como el [integrar un ejemplo de mosaico](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app), para tener acceso a **Power BI** mosaicos. La sección siguiente muestra cómo configurar el ejemplo.

<a name="configure-sample"/>
## Configurar la integración de un mosaico de ejemplo
Si descargó el [integrar un ejemplo de mosaico](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app), utiliza el **Id. de cliente** y **secreto de cliente** obtener después del registro para que el ejemplo puede autenticarse en Azure AD. Para configurar el ejemplo, cambie el **Id. de cliente** y **secreto del cliente** en el archivo web.config. Para obtener más información acerca de cómo autenticar a Azure AD, consulte [paso 2: un panel de Power BI](powerbi-developer-integrate-tile-get-dashboard.md).

## Paso siguiente

Para integrar un mosaico en una aplicación, debe obtener un icono que se encuentra en un panel. En el paso siguiente, aprenderá cómo [un panel de Power BI](powerbi-developer-integrate-tile-get-dashboard.md). En el paso 3, aprenda a obtener un mosaico de un panel.

[Siguiente paso >](powerbi-developer-integrate-tile-get-dashboard.md)

## Consulte también

[Registrarse para Power BI](powerbi-admin-free-with-custom-azure-directory.md)  
[Integrar un mosaico en un tutorial de la aplicación](powerbi-developer-integrate-tile.md)  
[Integrar un mosaico de ejemplo](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app)  
[Configurar la integración de un mosaico de ejemplo](powerbi-developer-integrate-tile-register.md#configure-sample)  
[Obtener un acceso de autenticación token](powerbi-developer-integrate-tile-get-dashboard.md#get-token)  
[Permisos de aplicación](powerbi-developer-power-bi-permissions.md)  
[Paso 2: Obtener un panel de Power BI](powerbi-developer-integrate-tile-get-dashboard.md)  
¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
<properties
   pageTitle="Integrar un mosaico de Power BI en una aplicación"
   description="Tutorial para integrar un mosaico en una aplicación, el código de ejemplo"
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

# Integrar un mosaico en una aplicación

## Introducción

En este tutorial, integrar o incrustar un icono en una aplicación web con C# y el **Power BI** API, algún código JavaScript y un IFrame.

>
            **NOTA**: para empezar a trabajar con este tutorial, necesita un **Power BI** cuenta. Si no tiene una cuenta, consulte [suscribirse en Power BI]( powerbi-admin-free-with-custom-azure-directory.md).

Para integrar un mosaico en una aplicación web, utiliza el **Power BI** API y una autorización de Azure Active Directory (AD) **token de acceso** para obtener un panel y el mosaico. A continuación, cargar el mosaico en un **IFrame** usando el mismo token de acceso. El **Power BI** API proporciona acceso mediante programación a ciertos **Power BI** recursos. Consulte [información general sobre la API de REST de Power BI](https://msdn.microsoft.com/library/dn877544.aspx). La siguiente ilustración muestra el flujo general para integrar un mosaico.

![](media\powerbi-developer-integrate-tile\integrate-tile-flow.png)

Estos son los pasos para integrar o incrustar un icono en una página web.

>
            **NOTA**: este artículo muestra el código usado en el [integrar un ejemplo de mosaico](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app) en GitHub. Para seguir este tutorial, debe descargar el ejemplo. Para ejecutar el ejemplo, vea [Configurar la integración de un mosaico de ejemplo](powerbi-developer-integrate-tile-register.md#configure-sample) en el registro de una aplicación web con el paso de Azure AD.

## Pasos para integrar un mosaico en una aplicación

- 
            [Paso 1: Registrar una aplicación web con Azure AD](powerbi-developer-integrate-tile-register.md). Debe registrar su aplicación web con **Azure Active Directory (AD)** para que Azure AD pueda identificar su aplicación necesita tener acceso a **Power BI** mosaicos.
- [Paso 2: Obtener un panel de Power BI](powerbi-developer-integrate-tile-get-dashboard.md)
- [Paso 3: Obtener un mosaico de Power BI](powerbi-developer-integrate-tile-get-tile.md)
- [Paso 4: Cargar un mosaico de Power BI en un IFrame](powerbi-developer-integrate-tile-load-tile-iframe.md)
- [Integrar un mosaico en un listado de código de aplicación](powerbi-developer-integrate-tile-code.md)

## Paso siguiente

En el paso siguiente, aprenderá cómo [registrar una aplicación web con Azure AD](powerbi-developer-integrate-tile-register.md) para obtener un **Id. de cliente** y **secreto de cliente** para autenticar la aplicación web con **Azure AD**. Un identificador de cliente y el secreto del cliente se utiliza para identificar la aplicación en Azure AD. Después de obtener un **Id. de cliente** y **secreto de cliente**, puede configurar la [integrar un mosaico de ejemplo](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app). Consulte [Configurar la integración de un mosaico de ejemplo](powerbi-developer-integrate-tile-register.md#configure-sample).

[Siguiente paso >](powerbi-developer-integrate-tile-register.md)

## Consulte también

[Registrarse para Power BI]( powerbi-admin-free-with-custom-azure-directory.md)  
[Integrar un mosaico de ejemplo](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app)  
[Configurar la integración de un mosaico de ejemplo](powerbi-developer-integrate-tile-register.md#configure-sample)  
[Paso 1: Registrar una aplicación web con Azure AD](powerbi-developer-integrate-tile-register.md)  
¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
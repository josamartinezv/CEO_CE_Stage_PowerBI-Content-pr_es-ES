<properties
   pageTitle="Power BI empezar a trabajar con aplicaciones de terceros"
   description="Power BI empezar a trabajar con aplicaciones de terceros"
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
   ms.topic="get-started-article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="10/10/2016"
   ms.author="asaxton"/>

# Introducción a las aplicaciones de terceros

Con Power BI, puede usar una aplicación compilada por una empresa o individual que no sea Microsoft. Por ejemplo, podría utilizar una aplicación de terceros que integra los mosaicos de Power BI en una aplicación web integrada personalizada. Cuando se utiliza una aplicación de terceros, deberá conceder a esa aplicación determinados permisos para la cuenta de Power BI y los recursos. Es importante que sólo se concedan permisos a las aplicaciones que son de confianza. Pueden revocar los permisos a una aplicación en cualquier momento. Consulte [revocar los permisos de la aplicación de terceros](#revoke).

Estos son los tipos de una aplicación puede solicitar el acceso.

## Permisos de Power BI App

-   **Ver todos los paneles (vista previa)**

  - Este permiso otorga a una aplicación la capacidad para ver todos los paneles que tienen acceso a. Esto incluye los paneles que posee, han de paquetes de contenido y se han compartido para usted y se encuentran en grupos que pertenecen a. La aplicación no puede realizar ninguna modificación en el panel. Entre otras cosas, este permiso se puede utilizar una aplicación para incrustar el contenido del panel en sus experiencias.

-   **Ver todos los informes (vista previa)**

  - Este permiso otorga a una aplicación la capacidad para ver todos los informes a que tienen acceso. Esto incluye los informes que posee, han de paquetes de contenido y se encuentran en grupos que pertenecen a. Parte de ver el informe, significa que la aplicación también puede ver los datos en él. La aplicación no puede realizar ninguna modificación en los informes en Sí. Entre otras cosas, este permiso se puede utilizar una aplicación para incrustar el contenido del informe en sus experiencias.

-   **Ver todos los conjuntos de datos**

  - Este permiso otorga a una aplicación la capacidad para enumerar todos los conjuntos de datos que tienen acceso a. Esto incluye los conjuntos de datos que posee, han de paquetes de contenido y se encuentran en grupos que pertenecen a. Una aplicación puede ver los nombres de todos los conjuntos de datos, así como su estructura incluidos los nombres de tabla y columna. Este permiso otorga derechos para leer los datos de un conjunto de datos. El permiso no otorga derechos para agregar o modificar un conjunto de datos a la aplicación.

-   **Leer y escribir todos los conjuntos de datos**

  - Este permiso otorga a una aplicación la capacidad para enumerar todos los conjuntos de datos que tienen acceso a. Esto incluye los conjuntos de datos que posee, han de paquetes de contenido y se encuentran en grupos que pertenecen a. Una aplicación puede ver los nombres de todos los conjuntos de datos, así como su estructura incluidos los nombres de tabla y columna. Este permiso otorga derechos para leer y escribir los datos en un conjunto de datos. La aplicación también puede crear nuevos conjuntos de datos o realizar modificaciones en las existentes. Esto se utiliza normalmente por una aplicación para enviar datos directamente a Power BI.

-   **Ver grupos del usuario**

  -  Este permiso otorga la capacidad de mostrar todos los grupos que son miembros de la aplicación. Puede usar este permiso junto con algunos de los otros permisos para ver o actualizar el contenido de ese grupo en particular. La aplicación no puede realizar modificaciones en el propio grupo.

<a name="revoke"/>
## Revocar permisos de la aplicación de terceros

Revocar permisos para una aplicación de terceros, vaya al sitio de mis aplicaciones de Office 365.

En el **Office 365 mis aplicaciones** de sitio, aquí se muestra cómo revocar los permisos de otros fabricantes:

1. Vaya a [sitio de mis aplicaciones de Office 365](https://portal.office.com/myapps).
2. En el **Mis aplicaciones** página, busque la aplicación de terceros.
3. Mantenga el mouse sobre el icono de la aplicación, haga clic en el **(...)** y haga clic en **quitar**.

  ![](media/powerbi-service-power-bi-get-started-third-party-apps/remove.png)

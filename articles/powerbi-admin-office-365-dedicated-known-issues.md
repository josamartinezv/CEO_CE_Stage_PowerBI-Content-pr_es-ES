<properties 
   pageTitle="Office 365 dedicado - problemas conocidos"
   description="Compatibilidad con clientes de Office 365 dedicado - problemas conocidos. Este tema describe los problemas específicos de un cliente de Office 365 dedicado. Esto incluye las limitaciones de la función de grupo, así como la aplicación de iPhone con dominios de cortesía."
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
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="10/10/2016"
   ms.author="asaxton"/>

# Soporte para clientes de Office 365 dedicado - problemas conocidos

Ahora se admite Power BI para los clientes de Office 365 dedicado.  Si es un cliente de Office 365 dedicado, puede iniciar sesión con una cuenta de inquilino y usar Power BI. Actualmente, hay dos problemas conocidos.

## Grupos

Al seleccionar **miembros** o **calendario** en el menú contextual del grupo, se le redirigirá a la aplicación de correo electrónico en su lugar.  
            **Archivos** y **conversaciones** funcionan según lo esperado.

![](media/powerbi-admin-office-365-dedicated-known-issues/group-menu.png)

## iPhone aplicación - iniciar sesión con el dominio personal conduce a error

Al iniciar sesión, en la aplicación de iPhone, con un inicio de sesión de un dominio personal, puede producir un error.

*Error de inicio de sesión*  
*Se produjo un error interno inesperado. Inténtelo de nuevo.*

Para evitar este problema, inicie sesión con la dirección de correo electrónico que aparece al hacer clic en el icono de usuario en el servicio de Power BI en lugar de con el dominio personal.

![](media/powerbi-admin-office-365-dedicated-known-issues/sign-in-address.png)

¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
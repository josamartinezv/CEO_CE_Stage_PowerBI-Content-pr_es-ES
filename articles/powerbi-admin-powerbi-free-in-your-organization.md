<properties
pageTitle="Power BI (gratuito) de su organización"
description="Este artículo examina las opciones de Power BI (gratuito) desde una perspectiva de la organización. Si es el administrador del inquilino, esto le mostrará cómo administrar SAI (UPS) de inicio de sesión gratuita."
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
ms.date="09/21/2016"
ms.author="asaxton"/>
# Power BI (gratuito) de su organización

Examinará cómo puede usarse el Power BI (gratuito) de la oferta dentro de su organización. Una organización significa que tiene un inquilino y puede administrar usuarios y servicios dentro de ese inquilino. Como administrador, puede controlar la asignación de licencias o puede permitir que los usuarios inicien sesión como usuario individual. Veremos la licencia de Power BI (gratuito) y cómo se puede controlar el inicio de sesión individual de.

## Suscripción individual frente a asignación de licencias

Los usuarios de su organización pueden tener acceso a Power BI de dos maneras diferentes. Puede firmar individualmente para Power BI, o puede asignar una licencia de Power BI a ellos en el portal de administración de Office 365.

Permitir inicio de sesión individual de reduce la carga, de los administradores de organización, permitiendo a los usuarios que están interesados en Power BI para suscribirse de forma gratuita. 

Para obtener más control, puede bloquear el inicio de sesión individual de y asignar licencias de Power BI en el centro de administración de Office 365. Esto le permite ser específica de quién puede acceder a los servicios dentro de su organización. También es una buena opción si tiene que tratar con la auditoría y necesita saber exactamente quién puede usar qué.

## Cómo obtener el bloque de licencias ilimitadas
En el centro de administración de Office 365, bajo **facturación** > **licencias**, puede o no ver Power BI (gratuito) con licencias ilimitadas.

![](media/powerbi-admin-powerbi-free-in-your-organization/unlimited-licenses.png)
 
Este bloque de licencias se mostrará la primera vez que alguien se suscribe a Power BI como usuario individual. Durante ese proceso, este bloque de licencia se asocia a su organización y se asigna una licencia al usuario que se inscribe.

Si va a bloquear individuales usuario registrarse y nadie ha suscrito, no verá este bloque de licencia. O bien puede permitir el inicio de sesión de usuario individual y a tener un usuario registrarse u obtener licencias gratuitas a través del flujo de Agregar suscripción a Office 365 que se hablado siguiente.

Una vez que el bloque de la licencia de Power BI (gratuito) está disponible, puede asignar las licencias a los usuarios. [Obtener más información](https://support.office.com/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc)

## Obtener licencias gratuitas a través de Agregar suscripción dentro de Office 365

1.  Desplácese hasta el [Centro de administración de Office 365](https://portal.office.com/admin/default.aspx).
2.  En el panel de navegación izquierdo, seleccione **facturación** > **suscripciones**.
3.  Seleccione **Agregar suscripciones +** en el lado derecho.
4.  En otros planes, mantenga el mouse sobre el **puntos suspensivos (...)** para Power BI (gratuito) y seleccione **comprar ahora**.

    ![](media/powerbi-admin-powerbi-free-in-your-organization/buy-powerbi-free.png)

5.  Escriba el número de licencias que desea agregar y seleccione **Desproteger ahora** o **Agregar al carro**.

    > [AZURE.NOTE] Puede agregar más adelante si es necesario.

6.  Escriba la información necesaria en la comprobación de flujo de cierre.

No hay ninguna compra cuando se usa este enfoque, pero debe especificar la información de su tarjeta de crédito para la facturación o elija facturación.

Si más adelante decide que desea agregar más licencias, puede volver a **Agregar suscripciones**, y seleccione **cambiar la cantidad de licencias** para Power BI (gratis).

![](media/powerbi-admin-powerbi-free-in-your-organization/change-license-quantity.png)
 
Ahora puede asignar las licencias a los usuarios. [Obtener más información](https://support.office.com/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc)

## Habilitar o deshabilitar, cada usuario de inicio de sesión de Azure Active Directory

Como administrador, puede habilitar o deshabilitar, ups de inicio de sesión de usuario individual como parte de Azure Active Directory (AAD). Si sabe cómo aprovechar los comandos de PowerShell de AAD, puede habilitar o deshabilitar, ad hoc suscripciones usted mismo. [Obtener más información](https://technet.microsoft.com/library/jj151815.aspx)

Es la configuración de AAD que controla este **AllowAdHocSubscriptions**. La mayoría de los inquilinos tendrán esta propiedad establecida en true, lo que significa que está habilitada. Si adquirió Power BI a través de un socio, esto se puede establecer en false de forma predeterminada, lo que significa que está deshabilitado.

1.  Debe iniciar sesión primero en Azure Active Directory mediante las credenciales de Office 365. La primera línea le solicitará las credenciales. La segunda línea se conecta a Azure Active Directory.

        $msolcred = get-credential
        connect-msolservice -credential $msolcred
    
    ![](media/powerbi-admin-powerbi-free-in-your-organization/aad-signin.png)

2.  Una vez que ha iniciado sesión, puede emitir el comando siguiente para ver lo que el inquilino está configurado actualmente para.

        Get-MsolCompanyInformation | fl AllowAdHocSubscriptions

3.  Puede que este comando para habilitar ($true) o deshabilitar AllowAdHocSubscriptions ($false).

        Set-MsolCompanySettings -AllowAdHocSubscriptions $true

> [AZURE.NOTE] Este bloqueo impide que nuevos usuarios de su organización de registrarse para Power BI. Los usuarios que se suscriben para Power BI antes de desactivar las suscripciones nuevas para su organización aún conserva sus licencias.

## Consulte también

[Suscripción de autoservicio para Power BI](powerbi-service-self-service-signup-for-power-bi.md)  
[Registrarse para Power BI (gratuito) con un inquilino de Azure Active Directory personalizado](powerbi-admin-free-with-custom-azure-directory.md)  
¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
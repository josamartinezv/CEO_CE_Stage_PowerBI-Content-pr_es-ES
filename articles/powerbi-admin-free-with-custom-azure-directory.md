<properties
pageTitle="Suscribirse a un directorio personalizado de Azure"
description="Es posible que un desarrollador y desea probar la aplicación de Power BI que utiliza la API de REST. Crear un directorio personalizado en su suscripción de Azure le permiten probar un entorno aislado. Hay algunas cosas que debe hacer para Power BI para trabajar con ese directorio personalizado."
services="powerbi"
documentationCenter=""
authors="guyinacube"
manager="erikre"
backup=""
editor=""
tags=""
qualityFocus="monitoring"
qualityDate="8/15/2016"/>

<tags
ms.service="powerbi"
ms.devlang="NA"
ms.topic="article"
ms.tgt_pltfrm="na"
ms.workload="powerbi"
ms.date="10/10/2016"
ms.author="asaxton"/>
# Registrarse para Power BI (gratuito) con un inquilino de Azure Active Directory personalizado

Si es desarrollador, con Microsoft Azure y buscan para crear una aplicación de Power BI mediante la API de REST, probablemente deseará usar Power BI con un inquilino de Azure Active Directory (AAD) personalizada para fines de prueba.  Hay algunas cosas que debe hacer para poner en funcionamiento. Esto le permite crear a un inquilino de Azure Active Directory para su uso con las pruebas de Power BI. 

Hay un paso adicional que debe realizar para realmente hacer el Power BI de registro debido a que no tiene acceso a un servidor de correo electrónico para el dominio personalizado con su inquilino de ADD.

<iframe width="560" height="315" src="https://www.youtube.com/embed/97IfXEWZMfU?showinfo=0" frameborder="0" allowfullscreen></iframe>

## Crear el directorio personalizado y los nuevos usuarios

Para probar un nuevo inquilino, debe crear a un inquilino de Azure Active Directory. Puede hacerlo a través del portal de Azure creando un nuevo directorio. Una vez hecho esto, deberá crear un nuevo usuario que nos podemos registrarse para Power BI con.

### Crear a un inquilino de Azure Active Directory

Le mostramos cómo configurar **Azure Active Directory**:

 1. Vaya a https://manage.windowsazure.com e inicie sesión con la cuenta que tiene una suscripción de Azure.

 2. Seleccione **ACTIVE DIRECTORY** icono de administración en el panel izquierdo.

    ![](media/powerbi-developer-create-an-azure-active-directory-tenant/active-directory.png)

 3. Seleccione **NUEVO** situado en la parte inferior de la página.

 4. Seleccione **SERVICIOS de aplicaciones** > **ACTIVE DIRECTORY** > **DIRECTORIO** > **CREACIÓN PERSONALIZADA**

    ![](media/powerbi-developer-create-an-azure-active-directory-tenant/new-ad.png)

 5. En el **Agregar directorio** escriba un nombre y el nombre de dominio. Está disponible para el país o región elija Estados Unidos o el país Power BI.

    ![](media/powerbi-developer-create-an-azure-active-directory-tenant/add-directory.png)

 6. Elija el icono Aceptar. Se crea un directorio de Azure Active Directory.

### Agregar un usuario a su inquilino de Azure Active Directory

Ahora que tenemos un nuevo inquilino, podemos crear un usuario dentro de nuestra organización de pruebas.

1. Vaya a https://manage.windowsazure.com e inicie sesión con la cuenta que tiene una suscripción de Azure.

2. Seleccione **ACTIVE DIRECTORY** icono de administración en el panel izquierdo.

3. En su **Azure Active Directory**, seleccione **USUARIOS**.

    ![](media/powerbi-developer-create-an-azure-active-directory-tenant/add-ad-user.png)

4. En la parte inferior de la página, seleccione **Agregar USUARIO**. Una cuenta de usuario se usa para registrar una aplicación Power BI.

5. En la **más información sobre esta página usuario**:

    1. Para **TIPO DE USUARIO**, seleccione **nuevo usuario de la organización**.
    2. Escriba su **NOMBRE de USUARIO**.
    3. Seleccione **siguiente**.

        ![](media/powerbi-developer-create-an-azure-active-directory-tenant/add-ad-user2.png)

6. En el **el perfil de usuario** escriba su **NOMBRE para MOSTRAR**. Nombre para mostrar es un campo obligatorio.

    ![](media/powerbi-developer-create-an-azure-active-directory-tenant/user-profile.png)

7. Seleccione **siguiente**. Para **ROL**, puede utilizar **usuario**.

8. Seleccione **crear** para crear una contraseña temporal. El nuevo usuario se asigna una contraseña temporal que debe cambiarse en el primer inicio de sesión.

9. En el **contraseña temporal de Get** página, copie la contraseña temporal y haga clic en **Complete** icono. Utilice la contraseña temporal al que primero inicie sesión en su AAD.

10. Después de seleccionar el **completado** icono, un nuevo usuario de Azure AD se crea.

 Puede obtener más información acerca de este paso en [crear un inquilino de Azure Active Directory](powerbi-developer-create-an-azure-active-directory-tenant.md).

## Obtener licencias gratuitas a través de Agregar suscripción dentro de Office 365

Si intenta iniciar sesión en Power BI (gratuito) con el nuevo usuario creado en el directorio, se le ofrecerá un mensaje que indica para comprobar su correo electrónico para el paso de comprobación. Sin embargo, no tiene un servidor de correo electrónico para el dominio de este directorio personalizado. 

Para solucionar este problema, necesitamos agregar licencias de Power BI (gratuitas) desde el centro de administración de Office 365.

> [AZURE.IMPORTANT] Este paso requiere que proporcione información de tarjeta de crédito, pero no se le cobrará por licencias de Power BI (gratis).

> [AZURE.NOTE] Asegúrese de que tiene al menos un usuario marcado como un **Administrador Global** en el directorio. Esto es para que pueda acceder el centro de administración de Office 365.

1.  Desplácese hasta el [Centro de administración de Office 365](https://portal.office.com/admin/default.aspx), e inicie sesión con su usuario de administrador Global para el directorio personalizado.

2.  En el panel de navegación izquierdo, seleccione **facturación** > **suscripciones**.

3.  Seleccione **Agregar suscripciones** en el lado derecho. Si no ve **Agregar suscripciones**, puede que no tenga el rol de administrador global.

    ![](media/powerbi-admin-powerbi-free-in-your-organization/o365-add-subscription.png)

4.  En otros planes, mantenga el mouse sobre el **puntos suspensivos (...)** para Power BI (gratuito) y seleccione **comprar ahora**.

    ![](media/powerbi-admin-powerbi-free-in-your-organization/buy-powerbi-free.png)

5.  Escriba el número de licencias que desea agregar y seleccione **Desproteger ahora** o **Agregar al carro**.

    > [AZURE.NOTE] Puede agregar más adelante si es necesario.

6.  Escriba la información necesaria en la comprobación de flujo de cierre.

No hay ninguna compra cuando se usa este enfoque, pero debe especificar la información de su tarjeta de crédito para la facturación o elija facturación.

Si más adelante decide que desea agregar más licencias, puede volver a **Agregar suscripciones**, y seleccione **cambiar la cantidad de licencias** para Power BI (gratis).

![](media/powerbi-admin-powerbi-free-in-your-organization/change-license-quantity.png)

Ahora puede asignar las licencias a los usuarios. Durante la desprotección, pueden haber asignado las licencias (gratuitas) de Power BI a todos los usuarios que no tienen licencias asignadas. [Obtener más información](https://support.office.com/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc)

Puede comprobar si el usuario tiene una licencia asignada a la cuenta, vaya a **usuarios** > **usuarios activos** y seleccionar el usuario. En la parte derecha, verá **licencia asignada**.

## Inicio de sesión en Power BI

Ahora podrá iniciar sesión en [Power BI](https://app.powerbi.com) con el usuario que ha creado en el directorio.

## Consulte también

[Crear a un inquilino de Azure Active Directory](powerbi-developer-create-an-azure-active-directory-tenant.md)  
[Power BI (gratuito) de su organización](powerbi-admin-powerbi-free-in-your-organization.md)  
[¿Qué es un directorio de Azure AD?](https://msdn.microsoft.com/library/azure/jj573650.aspx)  
[Cómo obtener a un inquilino de Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-howto-tenant/)  
¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
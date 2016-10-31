<properties
   pageTitle="Administración de Power BI en su organización"
   description="Administración de Power BI en su organización"
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
   ms.date="09/16/2016"
   ms.author="asaxton"/>

# Administración de Power BI en su organización

Microsoft Power BI permite a los usuarios visualizar datos, detecciones de compartir y colaborar de forma intuitiva de nueva. Para obtener más información, consulte [Introducción a Power BI](powerbi-service-get-started.md).

Administración de Power BI puede producirse en diversas ubicaciones. Presentamos dos ubicaciones comunes.

> [AZURE.NOTE] La cuenta debe estar marcada como un **Administrador Global**, dentro de Office 365 o Azure Active Directory, para obtener acceso al portal de administración de Power BI.

- [Portal de administración de BI de energía](https://app.powerbi.com/admin-portal)
- [Centro de administración de Office 365](https://portal.office.com/adminportal/home)

## ¿Qué es en este artículo

**Registrarse para Power BI**

- [¿Cómo los usuarios suscribirse a Power BI?](#how-do-users-sign-up-for-power-bi)

- [¿Cómo se registran a usuarios individuales en mi organización?](#how-do-individual-users-in-my-organization-sign-up)

- [¿Cómo puedo evitar que los usuarios unirse a mi inquilino de Office 365 existente?](#how-can-i-prevent-users-from-joining-my-existing-office-365-tenant)

- [¿Cómo se puede permitir a los usuarios unirse a mi inquilino de Office 365 existente?](#how-can-i-allow-users-to-join-my-existing-office-365-tenant)

- [¿Cómo se puede comprobar si tiene el bloque el inquilino?](#how-do-i-verify-if-i-have-the-block-on-in-the-tenant)

- [¿Cómo puedo evitar que los usuarios existentes comenzando a utilizar Power BI?](#how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi)

- [¿Cómo puedo permitir Mis usuarios inicien sesión en Power BI existentes?](#how-can-i-allow-my-existing-users-to-sign-up-for-power-bi)

**Administración de Power BI**

- [¿Cómo se cambia la manera de que administrar las identidades de los usuarios de mi organización hoy?](#how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today)

- [¿Cómo se administran Power BI?](#how-do-we-manage-power-bi)

- [¿Qué es el proceso para administrar a un inquilino creado por Microsoft para Mis usuarios?](#what-is-the-process-to-manage-a-tenant-created-by-Microsoft-for-my-users)
   
- [¿Si dispone de varios dominios, puedo controlar al inquilino de Office 365 se agregan usuarios a?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to)

- [¿Cómo quito Power BI para los usuarios que ya está suscrito?](#how-do-i-remove-power-bi-for-users-that-already-signed-up)

- [¿Cómo se puede saber cuando nuevos usuarios han unido a mi inquilino?](#how-do-i-know-when-new-users-have-joined-my-tenant)

- [¿Hay aspectos adicionales que debería estar preparado para?](#are-there-any-additional-things-i-should-be-prepared-for)

- [¿Es este gratuito? ¿Aplicarán cargos por estas licencias?](#is-this-free-will-i-be-charged-for-these-licenses)

- [¿Dónde se encuentra mi inquilino de Power BI?](#where-is-my-power-bi-tenant-located)

**Seguridad en Power BI**

- [¿Power BI cumple los requisitos de cumplimiento nacional, regional y específicas del sector?](#does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements)

- [¿Cómo funciona la seguridad en Power BI?](#how-does-security-work-in-power-bi?)

## Registrarse para Power BI

### ¿Cómo los usuarios suscribirse a Power BI?

Puede registrarse para Power BI a través de la [sitio web de Power BI](https://powerbi.microsoft.com). También puede registrarse a través de la página de servicios de compra en el centro de administración de Office 365. Cuando un administrador se suscribe a Power BI, pueden asignar licencias de usuario a los usuarios que deben tener acceso.

Además, los usuarios individuales de la organización puede registrarse para Power BI a través de la [sitio web de Power BI](https://powerbi.microsoft.com). Cuando un usuario de la organización se suscribe a Power BI, ese usuario se asigna automáticamente una licencia de Power BI. [Obtener más información](powerbi-service-self-service-signup-for-power-bi.md)

### ¿Cómo se registran a usuarios individuales en mi organización?

Hay tres escenarios que se pueden aplicar a los usuarios de su organización:

Escenario 1: Su organización ya tiene un entorno de Office 365 existente y el usuario al registrarse para Power BI ya tiene una cuenta de Office 365.
En este escenario, si un usuario ya tiene un trabajo o cuenta de school en el inquilino (por ejemplo, contoso.com) pero no lo hace aún tiene Power BI, Microsoft simplemente activará el plan para esa cuenta y automáticamente se notificará al usuario sobre cómo utilizar el servicio Power BI.

Escenario 2: Su organización tiene un entorno de Office 365 existente y el usuario al registrarse para Power BI no tiene una cuenta de Office 365.
En este escenario, el usuario tiene una dirección de correo electrónico en el dominio de su organización (por ejemplo, contoso.com), pero todavía no tiene una cuenta de Office 365. En este caso, el usuario puede registrarse para Power BI y automáticamente se dará una cuenta. Esto permite al usuario acceso al servicio Power BI. Por ejemplo, si un empleado denominado a Nancy utiliza su dirección de correo electrónico de trabajo (por ejemplo, Nancy@contoso.com) para iniciar sesión, Microsoft se agrego a Nancy como un usuario en el entorno de Contoso Office 365 automáticamente y activar Power BI para esa cuenta.

Escenario 3: Su organización no tiene un entorno de Office 365 conectado a su dominio de correo electrónico.
No hay ninguna acción administrativa su organización debe tomar para aprovechar las ventajas de Power BI. Los usuarios se agregará a un nuevo directorio usuario solo en la nube y, tendrá la opción de elegir tomar como el Administrador de inquilinos y administrarlos.

> [AZURE.IMPORTANT] Si su organización tiene varios dominios de correo electrónico y prefiere que todas las extensiones de dirección de correo electrónico en el mismo inquilino, agregue todos los dominios de dirección de correo electrónico a un inquilino de Azure Active Directory antes de registran los usuarios. No hay ningún mecanismo automático para mover los usuarios a través de los inquilinos después de haber creado. Para obtener más información acerca de este proceso, consulte [Si dispone de varios dominios, puedo controlar el inquilino de Office 365 se agregan usuarios a?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to) más adelante en este artículo y [Agregue su dominio a Office 365](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611) en línea.

### ¿Cómo puedo evitar que los usuarios unirse a mi inquilino de Office 365 existente?

Hay pasos que puede realizar, como administrador, para impedir que los usuarios unirse a su inquilino de Office 365 existente. Si se bloquea, se producirá un error en los intentos de los usuarios para iniciar sesión y se dirigirá a ponerse en contacto con el Administrador de. su organización No es necesario repetir este proceso si ya ha deshabilitado la distribución automática de licencias (por ejemplo, Office 365 para educación para estudiantes, profesores y personal).

Estos pasos requieren el uso de Windows PowerShell. Para empezar a trabajar con Windows PowerShell, consulte el [PowerShell Guía de introducción](http://go.microsoft.com/fwlink/p/?LinkID=286814).

Para llevar a cabo los pasos siguientes, debe instalar la última versión de 64 bits de la [Azure módulo Active Directory para Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297).

Después de seleccionar el vínculo, seleccione **ejecutar** para ejecutar el paquete de instalador.


            **Deshabilitar la combinación automática inquilino**: Utilice este comando de Windows PowerShell para evitar que usuarios nuevos de la combinación de un inquilino administrado:

- Para deshabilitar la combinación automática de inquilinos para usuarios nuevos:

    Set-MsolCompanySettings - AllowEmailVerifiedUsers $false

- Para habilitar la combinación automática de inquilinos para usuarios nuevos:

    Set-MsolCompanySettings - AllowEmailVerifiedUsers $true

> [AZURE.NOTE] Este bloqueo impide que nuevos usuarios de su organización de registrarse para Power BI. Los usuarios que se suscriben para Power BI antes de desactivar las suscripciones nuevas para su organización aún conserva sus licencias. Consulte la [¿Cómo puedo quitar licencias?] sección para obtener instrucciones sobre cómo quitar el acceso a Power BI para los usuarios que había registrado anteriormente en el servicio.

### ¿Cómo se puede permitir a los usuarios unirse a mi inquilino de Office 365 existente?

Para permitir que los usuarios a participar en el inquilino, ejecute el comando opuesto como se describe en la pregunta anterior:

    Set-MsolCompanySettings -AllowEmailVerifiedUsers $true

### ¿Cómo se puede comprobar si tiene el bloque el inquilino?

Use el siguiente script de PowerShell:

    Get-MsolCompanyInformation | fl allow*

### ¿Cómo puedo evitar que los usuarios existentes comenzando a utilizar Power BI?

Hay pasos que puede realizar, como administrador, para impedir que los usuarios suscribirse a Power BI. Si se bloquea, se producirá un error en los intentos de los usuarios para iniciar sesión y se dirigirá a ponerse en contacto con el Administrador de. su organización No es necesario repetir este proceso si ya ha deshabilitado la distribución automática de licencias (por ejemplo, Office 365 para educación para estudiantes, profesores y personal). [Obtener más información](powerbi-admin-powerbi-free-in-your-organization.md#enable-or-disable-individual-user-sign-up-in-Azure-Active-Directory)

> [AZURE.NOTE] El indicador AllowAdHocSubscriptions se utiliza para controlar varias funciones de usuario de su organización, incluida la capacidad para que los usuarios inicien sesión en el servicio de administración de derechos de Azure. Cambiando este marcador afectará a todas estas capacidades.

### ¿Cómo puedo permitir Mis usuarios inicien sesión en Power BI existentes?

Para permitir que los usuarios inicien sesión en Power BI existentes, ejecute el comando enumerado para la pregunta anterior, pero pasa true en lugar de false. [Obtener más información](powerbi-admin-powerbi-free-in-your-organization.md#enable-or-disable-individual-user-sign-up-in-Azure-Active-Directory)

## Administración de Power BI

### ¿Cómo se cambia la manera de que administrar las identidades de los usuarios de mi organización hoy?

Si su organización ya tiene un entorno de Office 365 existente y todos los usuarios de su organización tienen cuentas de Office 365, la administración de identidades no cambiará.

Si su organización ya tiene un entorno de Office 365 existente, pero no todos los usuarios de su organización tienen cuentas de Office 365, crearemos un usuario en el inquilino y asignar licencias basadas en el usuario trabajo o escuela, dirección de correo electrónico. Esto significa que el número de usuarios que está administrando en cualquier momento determinado crecerá como signo de los usuarios de su organización para el servicio.

Si está administrando su directorio local y usar los servicios de federación de Active Directory (AD FS), Microsoft no agregará los usuarios a los inquilinos y los usuarios que intenten unirse a su inquilino recibirá un mensaje para ponerse en contacto con el Administrador de. su organización

Si su organización no tiene un entorno de Office 365 conectado a su dominio de correo electrónico, no habrá ningún cambio en la forma de administrar identidades. Los usuarios se agregará a un nuevo directorio usuario solo en la nube y, tendrá la opción de elegir tomar como el Administrador de inquilinos y administrarlos.

### ¿Cómo se administran Power BI?

Power BI proporciona un portal de administración que le permite ver las estadísticas de uso, proporciona un vínculo al centro de administración de Office 365 para administrar usuarios y grupos y la capacidad de controlar la configuración de todo el inquilino. 

> [AZURE.NOTE] La cuenta debe estar marcada como un **Administrador Global**, dentro de Office 365 o Azure Active Directory, para obtener acceso al portal de administración de Power BI.

Para obtener más información, consulte [Portal de administración de energía BI](powerbi-admin-portal.md).

### ¿Qué es el proceso para administrar a un inquilino creado por Microsoft para Mis usuarios?

Si se ha creado un inquilino de Microsoft, puede reclamar y administrar ese inquilino siguiendo estos pasos:

1. Únase a los inquilinos, registrándose para Power BI, con un dominio de la dirección de correo electrónico que coincida con el dominio del inquilino que desea administrar. Por ejemplo, si Microsoft creó al inquilino de contoso.com, debe unir el inquilino con una dirección de correo electrónico termina con @contoso.com.

2. Notificación de control de administración mediante la comprobación de la propiedad de dominio: cuando se encuentre en el inquilino, puede promover a sí mismo un *Administrador Global* rol mediante la comprobación de la propiedad de dominio. Para hacerlo, siga estos pasos:

    1. Vaya a [https://portal.office.com](https://portal.office.com).

    2. Seleccione el icono del selector de aplicación en la superior izquierda y elija **Admin**.

    3. Lea las instrucciones en el **se convierten en el Administrador de** página y, a continuación, elija **Sí, quiero que el administrador**.

    > [AZURE.NOTE] Si no aparece esta opción, ya hay un administrador de Office 365 en su lugar.
    
### ¿Si dispone de varios dominios, puedo controlar al inquilino de Office 365 se agregan usuarios a?

Si no hace nada, se creará un inquilino para cada dominio de correo electrónico del usuario y el subdominio.

Si desea que todos los usuarios en el mismo inquilino independientemente de sus extensiones de dirección de correo electrónico:

- Crear a un inquilino de destino antes de tiempo, o usar a un inquilino existente y agregar todos los dominios existentes y los subdominios que desee consolidados dentro de ese inquilino. A continuación, todos los usuarios con direcciones de correo electrónico que terminen en esos dominios y subdominios combinará automáticamente el inquilino de destino cuando se registren.

> [AZURE.IMPORTANT] No hay ningún mecanismo automatizado admitido para mover los usuarios a través de los inquilinos una vez que se han creado. Para obtener información acerca de cómo agregar dominios a un solo inquilino de Office 365, consulte [Agregar los usuarios y el dominio a Office 365](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).

### ¿Cómo quito Power BI para los usuarios que ya está suscrito?

Si un usuario registrado en Power BI, pero ya no desea que tengan acceso a Power BI, puede quitar la licencia de Power BI para ese usuario.

1. Desplácese hasta el centro de administración de Office 365.

2. En la barra de navegación izquierdo, seleccione **usuarios** > **usuarios activos**.

3. Busque el usuario que desea quitar la licencia para, a continuación, seleccione su nombre > **Editar**.

4. En la página de detalles de usuario, seleccione **licencias** en la barra de navegación izquierda.

5. Desactive **Power BI (gratuito)**, o **Power BI Pro**, dependiendo de qué licencia se aplica a su cuenta.

6. Seleccione **Guardar**.

> [AZURE.NOTE] Puede realizar la administración masiva de licencia para los usuarios. Para ello, seleccione varios usuarios y seleccione **Editar**.

### ¿Cómo se puede saber cuando nuevos usuarios han unido a mi inquilino?

Los usuarios que han participado en el inquilino como parte de este programa se asignan una licencia única que se puede filtrar en el panel de usuario activo en el panel de administración.

Para crear esta nueva vista, en el centro de administración de Office 365, vaya a **usuarios** > **usuarios activos**, y en la **Seleccionar una vista** menú, seleccione **nueva vista**. El nombre de la nueva vista y en **licencia asignada**, seleccione **Power BI (gratuito)** o **Power BI Pro**. Sólo puede tener una licencia seleccionada por vista. Si has **Power BI (gratuito)** y **Power BI Pro** licencias de su organización, deberá crear dos vistas. Una vez creada la nueva vista, podrá ver todos los usuarios en el inquilino que han inscrito en este programa.

### ¿Hay aspectos adicionales que debería estar preparado para?

Es posible que experimente un aumento de las solicitudes de restablecimiento de contraseña. Para obtener información acerca de este proceso, consulte [Restablecer una contraseña de usuario](https://support.office.com/article/Reset-a-users-password-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c).

Puede quitar un usuario de su inquilino mediante el proceso estándar en el centro de administración de Office 365. Sin embargo, si el usuario todavía tiene una dirección de correo de su organización, podrán unirse a menos que bloquee todos los usuarios de la combinación.

### ¿Es este gratuito? ¿Aplicarán cargos por estas licencias?

El **Power BI (gratuito)** licencias son para la versión gratuita de Power BI. Si está interesado en capacidades adicionales, eche un vistazo a la [Power BI Pro versión](powerbi-power-bi-pro-content-what-is-it.md).

### ¿Dónde se encuentra mi inquilino de Power BI?

¿Para obtener información sobre cómo averiguar dónde se encuentra el inquilino de Power BI, también conocido como una región de datos, consulte [donde se encuentra mi inquilino de Power BI?](powerbi-admin-where-is-my-tenant-located.md)

## Seguridad en Power BI

### ¿Power BI cumple los requisitos de cumplimiento nacional, regional y específicas del sector?

Para obtener más información acerca de la compatibilidad de Power BI, consulte el [Microsoft Trust Center](http://go.microsoft.com/fwlink/?LinkId=785324).

### ¿Cómo funciona la seguridad en Power BI?

Power BI se basa en la base de Office 365, que a su vez se basa en los servicios de Azure como Azure Active Directory. Para obtener información general de arquitectura de Power BI, consulte [Power BI seguridad](powerbi-admin-power-bi-security.md). 

## Consulte también

[Portal de administración de Power BI](powerbi-admin-portal.md)  
[Suscripción de autoservicio para Power BI](powerbi-service-self-service-signup-for-power-bi.md)  
[Power BI (gratuito) de su organización](powerbi-admin-powerbi-free-in-your-organization.md)  
[Poder adquisitivo BI Pro](powerbi-admin-purchasing-power-bi-pro.md)  
[Administración de cuentas de usuario de Office 365](https://technet.microsoft.com/library/office-365-user-account-management.aspx)  
[Administración de grupo de Office 365](https://support.office.com/Article/Find-help-about-Groups-in-Office-365-7a9b321f-b76a-4d53-b98b-a2b0b7946de1)  

            [¿Administrar el grupo en Power BI y Office 365](powerbi-service-manage-your-group-in-power-bi-and-office-365.md) más preguntas? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
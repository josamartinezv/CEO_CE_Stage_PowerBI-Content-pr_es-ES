<properties
   pageTitle="Crear a un inquilino de Azure Active Directory"
   description="Crear a un inquilino de Azure Active Directory"
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

# Crear a un inquilino de Azure Active Directory

Mediante la API de REST de Power BI, puede crear una aplicación Power BI en cualquier plataforma que admite llamar a operaciones de REST. Sin embargo, antes de empezar a crear una aplicación Power BI, necesita un **Azure Active Directory**, un usuario de la organización y un [cuenta de servicio de Power BI](powerbi-admin-free-with-custom-azure-directory.md).

## Crear a un inquilino de Azure Active Directory para una aplicación de Power BI

Aplicaciones de Power BI se integran con **Azure Active Directory** (Azure AD) para proporcionar el inicio de sesión seguro y autorización para la aplicación. Para integrar una aplicación Power BI con Azure AD, registre los detalles acerca de la aplicación con Azure AD mediante el Portal de administración de Azure.


            **Importante** para registrarse en el **servicio Power BI**, su **Azure Active Directory** debe tener al menos un usuario de la organización. Utilice el usuario de la organización a [suscribirse al servicio Power BI](powerbi-admin-free-with-custom-azure-directory.md).

<a name="setup"></a>
### Crear a un inquilino de Azure Active Directory
Antes de empezar a crear una aplicación Power BI, necesita **Azure Active Directory** y un usuario de la organización. Le mostramos cómo configurar **Azure Active Directory**:

 1. Vaya a https://manage.windowsazure.com e inicie sesión con la cuenta que tiene una suscripción de Azure.
 2. Haga clic en **ACTIVE DIRECTORY** icono de administración en el panel izquierdo.

    ![](media/powerbi-developer-create-an-azure-active-directory-tenant/active-directory.png)

 3. Haga clic en **NUEVO** situado en la parte inferior de la página.
 4. Elija **SERVICIOS de aplicaciones** > **ACTIVE DIRECTORY** > **DIRECTORIO** > **CREACIÓN PERSONALIZADA**

    ![](media/powerbi-developer-create-an-azure-active-directory-tenant/new-ad.png)

 5. En el **Agregar directorio** escriba un nombre y el nombre de dominio. Está disponible para el país o región elija Estados Unidos o el país Power BI.

    ![](media/powerbi-developer-create-an-azure-active-directory-tenant/add-directory.png)

 6. Elija el icono Aceptar. Se crea un directorio de Azure Active Directory.

<a name="newuser"></a>
### Agregar un usuario a su inquilino de Azure Active Directory
Necesita un usuario de la organización de Azure AD para registrarse en el **servicio Power BI**. Una vez que inicie sesión en el **servicio Power BI** por primera vez, verá el **servicio Power BI** agregado a Azure AD que le permitirá crear aplicaciones de Power BI con los permisos adecuados. Aquí se muestra cómo agregar un usuario a Azure Active Directory:

1. Vaya a https://manage.windowsazure.com e inicie sesión con la cuenta que tiene una suscripción de Azure.
2. Haga clic en **ACTIVE DIRECTORY** icono de administración en el panel izquierdo.
3. En su **Azure Active Directory**, haga clic en **USUARIOS**.

    ![](media/powerbi-developer-create-an-azure-active-directory-tenant/add-ad-user.png)
4. En la parte inferior de la página, haga clic en **Agregar USUARIO**. Una cuenta de usuario se usa para registrar una aplicación Power BI.
5. En la **más información sobre esta página usuario**:

    1. Para **TIPO DE USUARIO**, elija **nuevo usuario de la organización**.
    2. Escriba su **NOMBRE de USUARIO**.
    3. Haga clic en **Siguiente**.

        ![](media/powerbi-developer-create-an-azure-active-directory-tenant/add-ad-user2.png)

6. En el **el perfil de usuario** escriba su **NOMBRE para MOSTRAR**. Nombre para mostrar es un campo obligatorio.

    ![](media/powerbi-developer-create-an-azure-active-directory-tenant/user-profile.png)

7. Haga clic en **Siguiente**. Para **ROL**, puede utilizar **usuario**.
8. Haga clic en **crear** para crear una contraseña temporal. El nuevo usuario se asigna una contraseña temporal que debe cambiarse en el primer inicio de sesión.
9. En el **contraseña temporal de Get** página, copie la contraseña temporal y haga clic en **Complete** icono. Utilice la contraseña temporal al que primero inicie sesión en su AAD.
10. Tras hacer clic en el **completado** icono, un nuevo usuario de Azure AD se crea.

Una vez que tenga una **Azure Active Directory** inquilino y un usuario de la organización, le [suscribirse en Power BI](powerbi-admin-free-with-custom-azure-directory.md).


            **Nota** al suscribirse al servicio Power BI, use el usuario de la organización. Una vez que inicie sesión en el **servicio Power BI** por primera vez, verá el **servicio Power BI** agregado a Azure AD.

## Véase también

[¿Qué es un directorio de Azure AD?](https://msdn.microsoft.com/library/azure/jj573650.aspx)  
[Cómo obtener a un inquilino de Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-howto-tenant/)  
¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
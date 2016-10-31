<properties
   pageTitle="Actualizar un conjunto de datos creado a partir de un archivo de Power BI Desktop - nube"
   description="Actualizar un conjunto de datos creado a partir de un archivo de Power BI Desktop en OneDrive o SharePoint Online"
   services="powerbi"
   documentationCenter=""
   authors="guyinacube"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="complete"
   qualityDate="04/01/2016"/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/15/2016"
   ms.author="asaxton"/>

# Actualizar un conjunto de datos creado a partir de un archivo de Power BI Desktop en OneDrive o SharePoint Online

## ¿Cuáles son las ventajas?  
Importación de archivos de OneDrive o de SharePoint Online es una excelente manera de asegurarse de que el trabajo que esté realizando en Power BI Desktop permanece en sincronización con el servicio Power BI. Los datos que ha cargado en el modelo de su archivo se importación en el conjunto de datos y los informes que ha creado en el archivo se cargan en informes de Power BI. Si realiza cambios en el archivo en OneDrive o SharePoint Online, como agregar nuevas medidas, cambiar los nombres de columna o editar visualizaciones, una vez guardada, esos cambios se actualizarán en Power BI demasiado, normalmente dentro de una hora aproximadamente.

Puede realizar una actualización manual de una sola vez directamente en Power BI Desktop seleccionando la actualización en la cinta de opciones de inicio. Al seleccionar la actualización aquí, los datos de la *del archivo* se actualiza el modelo con datos actualizados del origen de datos original. Este tipo de actualización, completamente desde Power BI Desktop propia aplicación, es diferente de una actualización manual o programada en Power BI y es importante comprender la diferencia.

![](media/powerbi-refresh-desktop-file-local-drive/pbix-refresh.png)

Al importar el archivo de Power BI Desktop desde OneDrive o SharePoint Online, datos, junto con otra información sobre el modelo se carga en un conjunto de datos en Power BI. En el servicio de Power BI no Power BI Desktop, desea actualizar los datos del conjunto de datos ya que es lo que se basan los informes, en el servicio de Power BI. Dado que los orígenes de datos son externos, puede actualizar manualmente el conjunto de datos mediante **Actualizar ahora** o puede configurar una programación de actualización utilizando **Programar actualización**.

Al actualizar el conjunto de datos, Power BI no se conecta al archivo en OneDrive o SharePoint Online, para consultar los datos actualizados. Utiliza la información del conjunto de datos para conectarse directamente a los orígenes de datos para consultar los datos actualizados a continuación, se carga en el conjunto de datos. Estos datos actualizados del conjunto de datos no se sincronizan en el archivo en OneDrive o en SharePoint Online.

## ¿Qué es compatible?  
En Power BI, actualizar ahora y programar la actualización se admite para conjuntos de datos creado a partir de archivos de Power BI Desktop importados desde una unidad local donde se utiliza el Editor de datos o consulta obtener para conectarse y cargar datos desde cualquiera de los siguientes orígenes de datos:  

### Puerta de enlace de Power BI - Personal
-   Todos los orígenes de datos en línea que se muestra en el Editor de consultas y obtener datos en Power BI Desktop.
-   Todos los orígenes de datos local que se muestra en el Editor de consultas y obtener datos en Power BI Desktop excepto archivo Hadoop (HDFS) y Microsoft Exchange.

<!-- Refresh Data sources-->
[AZURE.INCLUDE [refresh-datasources](../includes/refresh-datasources.md)]

> [AZURE.NOTE] Una puerta de enlace debe estar instalado y en ejecución para Power BI para conectarse a orígenes de datos locales y actualizar el conjunto de datos.

## OneDrive o OneDrive para la empresa. ¿Cuál es la diferencia?  
Si tiene un OneDrive personal y OneDrive para la empresa, se recomienda que mantener los archivos que desea importar en Power BI en OneDrive para la empresa. Esta es la razón: es probable que utiliza dos cuentas diferentes para iniciar sesión en ellos.

Conectarse a OneDrive para la empresa en Power BI es normalmente transparente, ya que la misma cuenta de con que inicio de sesión en Power BI suele ser la misma cuenta utilizada para iniciar sesión en OneDrive para la empresa. Pero, con OneDrive personal, es probable que inicie sesión con otra [cuenta de Microsoft](http://www.microsoft.com/account/default.aspx).

Cuando inicia sesión con tu cuenta de Microsoft, no olvide seleccionar mantener la sesión iniciada. Power BI, a continuación, puede sincronizar las actualizaciones que realice en el archivo de Power BI Desktop con conjuntos de datos en Power BI  
    ![](media/powerbi-refresh-desktop-file-onedrive/Refresh_SignIn_KeepMeSignedIn.png)

Si realiza cambios en el archivo en OneDrive que no se puede sincronizar con el conjunto de datos o informes de Power BI, porque pueden haber cambiado sus credenciales de cuenta de Microsoft, debe conectarse a y vuelva a importar el archivo desde su OneDrive personal.

## ¿Cómo programar la actualización?  
Al configurar una programación de actualización, Power BI conectarse directamente a los orígenes de datos con información de conexión y credenciales en el conjunto de datos de consulta para obtener datos actualizados y cargar los datos actualizados en el conjunto de datos. También se actualizan las visualizaciones en informes y paneles basados en ese conjunto de datos en el servicio Power BI.

Para obtener más información acerca de cómo programar la actualización de instalación, consulte [Configurar actualización de programación](powerbi-refresh-scheduled-refresh.md).

## Cuando existe algún problema  
Cuando existe algún problema, suele ser porque Power BI no puede iniciar sesión en orígenes de datos, o si el conjunto de datos se conecta a un origen de datos local, la puerta de enlace está sin conexión. Asegúrese de que Power BI puede iniciar sesión en orígenes de datos. Si cambia una contraseña que se utiliza para iniciar sesión en un origen de datos o Power BI Obtiene la sesión de un origen de datos, asegúrese de intentar iniciar sesión en los orígenes de datos en las credenciales de origen de datos.

Si está realizando cambios en el archivo de Power BI Desktop en OneDrive y guardar, y esos cambios no se refleja en Power BI dentro de una hora o menos, podría deberse a que no se puede conectar Power BI a su OneDrive. Intente conectarse de nuevo para el archivo en OneDrive. Si se le pedirá que inicie sesión, asegúrese de que seleccionar mantener la sesión en. Porque Power BI no pudo conectarse a su OneDrive para sincronizar con el archivo, debe volver a importar el archivo.

Asegúrese de dejar el **Enviar correo de electrónico de notificación de error de actualización me** activada. Deseará saber inmediatamente si se produce un error en una actualización programada.

## Solucionar problemas

No puede ir a veces, actualizar los datos según lo esperado. Normalmente se trata de un problema conectado con una puerta de enlace. Eche un vistazo a los artículos de solución de problemas de puerta de enlace para herramientas y problemas conocidos.

[Solución de problemas de la puerta de enlace de datos local](powerbi-gateway-onprem-tshoot.md)

[Solución de problemas de la puerta de enlace de Power BI - Personal](powerbi-admin-troubleshooting-power-bi-personal-gateway.md)

¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
<properties
   pageTitle="Actualizar un conjunto de datos creado a partir de un libro de Excel - local"
   description="Actualizar un conjunto de datos creado a partir de un libro de Excel en una unidad local"
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

# Actualizar un conjunto de datos creado a partir de un libro de Excel en una unidad local

## ¿Qué es compatible?  
En Power BI, actualizar ahora y programar la actualización se admite para conjuntos de datos creado a partir de libros de Excel que se importan desde una unidad local donde se usa Power Query (Get y transformación de datos en Excel 2016) o Power Pivot para conectarse a cualquiera de los siguientes orígenes de datos y cargar datos en el modelo de datos de Excel:  

### Puerta de enlace de Power BI - Personal

-   Todos los orígenes de datos en línea que se muestra en Power Query.
-   Todos los orígenes de datos local que se muestra en Power Query, excepto el archivo Hadoop (HDFS) y Microsoft Exchange.
-   Todos los orígenes de datos en línea que se muestra en Power Pivot.\*
-   Todos los orígenes de datos locales que se muestran en Power Pivot excepto archivo Hadoop (HDFS) y Microsoft Exchange.

<!-- Refresh Data sources-->
[AZURE.INCLUDE [refresh-datasources](../includes/refresh-datasources.md)]

>**Notas:**  
>- Una puerta de enlace debe estar instalado y en ejecución para Power BI para conectarse a orígenes de datos locales y actualizar el conjunto de datos.
>
>- Cuando utiliza Excel 2013, asegúrese de que ha actualizado Power Query a la versión más reciente.
>
>- No se admite la actualización de los libros de Excel importados de una unidad local que existen datos en hojas de cálculo o tablas vinculadas. La actualización se admite para los datos de la hoja de cálculo si se almacena y se importan desde OneDrive. Para obtener más información, consulte [actualizar un conjunto de datos creado a partir de un libro de Excel en OneDrive o SharePoint Online](powerbi-refresh-excel-file-onedrive.md).
>
>- Al actualizar un conjunto de datos creado a partir de un libro de Excel que se importan desde una unidad local, se actualizan únicamente los datos consultados de orígenes de datos. Si cambia la estructura del modelo de datos en Excel o Power Pivot; Por ejemplo, cree una nueva medida o cambiar el nombre de una columna, esos cambios no se copiará en el conjunto de datos. Si realiza estos cambios, necesitará volver a cargar o volver a publicar el libro. Si piensa realizar cambios periódicos en la estructura del libro y desea que los que queden reflejados en el conjunto de datos en Power BI sin tener que volver a cargar, considere la posibilidad de colocar el libro en OneDrive. Power BI actualiza automáticamente los datos de la estructura y la hoja de cálculo de los libros almacenados e importado desde OneDrive.

## ¿Cómo puedo asegurarme de que se cargan datos en el modelo de datos de Excel?  
Cuando usa Power Query (Get y transformación de datos en Excel 2016) para conectarse a un origen de datos, tiene varias opciones donde desea cargar los datos. Para asegurarse de que se cargan datos en el modelo de datos, debe seleccionar la **agregar estos datos al modelo de datos** opción en la **cargar a** cuadro de diálogo.

> [AZURE.NOTE] Las imágenes a continuación muestran Excel 2016.

En **Navigator**, haga clic en **cargar...**  
    ![](media/powerbi-refresh-excel-file-local-drive/Refresh_LoadToDM_1.png)

O bien, si hace clic **modificar** en Navigator, se abrirá el Editor de consultas. Se puede hacer clic en **Cerrar y cargar...**  
    ![](media/powerbi-refresh-excel-file-local-drive/Refresh_LoadToDM_2.png)

A continuación, en **cargar**, asegúrese de seleccionar **agregar estos datos al modelo de datos**.  
    ![](media/powerbi-refresh-excel-file-local-drive/Refresh_LoadToDM_3.png)

### ¿Qué ocurre si utilizo obtener datos externos en Power Pivot?  
No hay problema. Siempre que use Power Pivot para conectarse y consultar datos de una implementación local o el origen de datos en línea, los datos se cargan automáticamente al modelo de datos.

## ¿Cómo programar la actualización?  
Al configurar una programación de actualización, Power BI conectarse directamente a los orígenes de datos con información de conexión y credenciales en el conjunto de datos de consulta para obtener datos actualizados y cargar los datos actualizados en el conjunto de datos. También se actualizan las visualizaciones en informes y paneles basados en ese conjunto de datos en el servicio Power BI.

Para obtener más información acerca de cómo programar la actualización de instalación, consulte [Configurar actualización de programación](powerbi-refresh-scheduled-refresh.md).

## Cuando existe algún problema  
Cuando existe algún problema, suele ser porque Power BI no puede iniciar sesión en orígenes de datos, o si el conjunto de datos se conecta a un origen de datos local, la puerta de enlace está sin conexión. Asegúrese de que Power BI puede iniciar sesión en orígenes de datos. Si cambia una contraseña que se utiliza para iniciar sesión en un origen de datos o Power BI Obtiene la sesión de un origen de datos, asegúrese de intentar iniciar sesión en los orígenes de datos en las credenciales de origen de datos.

Asegúrese de dejar el **Enviar correo de electrónico de notificación de error de actualización a mí comprueban**. Deseará saber inmediatamente si se produce un error en una actualización programada.

## Notas importantes  
\* No se admite la actualización en las fuentes de OData conectado a y consulta de PowerPivot. Al utilizar una OData fuente como un origen de datos, use Power Query.

## Solucionar problemas

No puede ir a veces, actualizar los datos según lo esperado. Normalmente se trata de un problema conectado con una puerta de enlace. Eche un vistazo a los artículos de solución de problemas de puerta de enlace para herramientas y problemas conocidos.

[Solución de problemas de la puerta de enlace de datos local](powerbi-gateway-onprem-tshoot.md)

[Solución de problemas de la puerta de enlace de Power BI - Personal](powerbi-admin-troubleshooting-power-bi-personal-gateway.md)

¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)

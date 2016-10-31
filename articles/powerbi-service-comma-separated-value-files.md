<properties
   pageTitle="Obtener datos de valores separados por comas (. Archivos CSV)"
   description="Obtenga información sobre cómo obtener datos de archivos CSV en Power BI"
   services="powerbi"
   documentationCenter=""
   authors="davidiseminger"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="monitoring"
   qualityDate="03/30/2016"/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="10/12/2016"
   ms.author="davidi"/>

# Obtener datos de valores separados por comas (. Archivos CSV)
![](media/powerbi-service-comma-separated-value-files/csv_icon.png)

Separada por comas de archivos de valores, que suele conocidos como un. CSV, archivos de texto simple con filas de datos donde cada valor se separa por comas. Estos tipos de archivos pueden contener grandes cantidades de datos dentro de un tamaño de archivo relativamente pequeño, lo que un origen de datos ideal para Power BI. Puede descargar un ejemplo. Archivo CSV [aquí](http://go.microsoft.com/fwlink/?LinkID=619356).

Si tiene una. CSV, es el momento de obtener en el sitio de Power BI como un conjunto de datos donde puede empezar a explorar los datos, crear algunos paneles y compartir sus conocimientos con otros usuarios.


            **Sugerencia:** salida muchas de las organizaciones una. CSV con datos actualizados cada día. Para asegurarse de que el conjunto de datos en Power BI permanecen sincronizados con el archivo actualizado, asegúrese de que el archivo se guarda en OneDrive con el mismo nombre.

## Donde se guarda el archivo marca la diferencia

            **Local** - Si guarda su. Archivo CSV a una unidad local en el equipo o en otra ubicación de su organización, desde Power BI puede *importar* el archivo en Power BI. El archivo realmente permanecerá en la unidad local, por lo que todo el archivo no importa realmente en Power BI. Lo que sucede en realidad es un nuevo conjunto de datos se crea en Power BI y los datos de la. Archivo CSV se carga en el conjunto de datos.


            **OneDrive - Business** : si tiene OneDrive para la empresa e iniciar sesión en ella con la misma cuenta que inicie sesión en Power BI con, se trata por lejos la manera más eficaz mantener su. Archivo CSV y su conjunto de datos, informes y paneles en Power BI en la sincronización. Dado que son Power BI y OneDrive en la nube, Power BI *conecta* a su archivo en OneDrive sobre cada hora. Si se detectan cambios, se actualizan automáticamente el conjunto de datos, informes y paneles en Power BI.


            **OneDrive - Personal** – Si guarda los archivos en su propia cuenta de OneDrive, obtendrá muchas de las mismas ventajas como lo haría con OneDrive para la empresa. La principal diferencia es cuando se conecta primero a su archivo (mediante obtener datos > archivos > OneDrive – Personal) deberá iniciar sesión en su OneDrive con su cuenta de Microsoft, que normalmente es distinta de lo que use para iniciar sesión en Power BI. Al iniciar sesión en su OneDrive con su cuenta de Microsoft, asegúrese de seleccionar el mantener la sesión en la opción. De este modo, será capaz de conectarse a su archivo sobre cada hora y asegúrese de que el conjunto de datos en Power BI está en la sincronización de Power BI.


            **Sitios de SharePoint Team** : guardar los archivos de Power BI Desktop en SharePoint, sitios de grupo es igual que el ahorro de OneDrive para la empresa. La diferencia más importante es cómo se conecta al archivo de Power BI. Puede especificar una dirección URL o conectarse a la carpeta raíz.

## Importar o conectarse a una. Archivo CSV


            **Importante:** el tamaño de archivo máximo que se puede importar en Power BI es de 1 gigabyte.

1.  Power BI, en el panel de navegación, haga clic en **obtener datos**.

    ![](media/powerbi-service-comma-separated-value-files/csv_get_data_button.png)

2.  En **archivos**, haga clic en **obtener**.

    ![](media/powerbi-service-comma-separated-value-files/csv_files_get.png)

3.  Busque el archivo.

    ![](media/powerbi-service-comma-separated-value-files/csv_find_your_file.png)

## ¿Qué viene a continuación?


            **Explorar los datos** -una vez que obtenga datos de su archivo en Power BI, es hora de explorar. Simplemente haga clic en el nuevo conjunto de datos y, a continuación, haga clic en **Explorar**.


            **Programar la actualización** -Si el archivo se guarda en una unidad local, puede configurar actualización programada para el conjunto de datos e informes de Power BI mantenerse al día. Para obtener más información, consulte [de actualización de datos en Power BI](articles/powerbi-refresh-data.md). Si el archivo se guarda en OneDrive, Power BI sincronizará automáticamente con él sobre cada hora.

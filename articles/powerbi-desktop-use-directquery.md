<properties
   pageTitle="Usar DirectQuery en Power BI Desktop"
   description="Usar DirectQuery en Power BI Desktop"
   services="powerbi"
   documentationCenter=""
   authors="davidiseminger"
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
   ms.date="09/29/2016"
   ms.author="davidi"/>

# Usar DirectQuery en Power BI Desktop  

Con Power BI Desktop, cuando se conecta al origen de datos, siempre es posible importar una copia de los datos a Power BI Desktop. Para algunos orígenes de datos, está disponible un enfoque alternativo: conectar directamente con el origen de datos mediante **DirectQuery**.

## Orígenes de datos compatibles  
Actualmente se admiten los siguientes orígenes de datos:  

-   SQL Server
-   Azure SQL Database
-   Almacenamiento de datos SQL Azure
-   [SAP HANA](powerbi-desktop-sap-hana.md)
-   [Base de datos de Oracle](powerbi-desktop-directquery-for-oracle-teradata.md)
-   [Base de datos de Teradata](powerbi-desktop-directquery-for-oracle-teradata.md)
-   [Amazon Redshift (vista previa)](powerbi-desktop-connect-redshift.md)
-   [Impala (vista previa)](powerbi-desktop-connect-impala.md)

## Cómo conectar con DirectQuery  
Al usar **obtener datos** para conectarse a un origen de datos compatible con **DirectQuery**, la ventana de conexión le permite seleccionar cómo desea conectarse.  

![](media/powerbi-dekstop-use-directquery/DirectQuery_2a.png)

Las diferencias entre la selección de **importación** y **DirectQuery** son los siguientes:


            **Importar** : las tablas y columnas seleccionadas se importan en Power BI Desktop. Crear o interactuar con una visualización, Power BI Desktop utiliza los datos importados. Debe actualizar los datos que se importan de nuevo, el conjunto completo de datos para ver los cambios que se produjeron los datos subyacentes desde la importación inicial o la actualización más reciente.


            **DirectQuery** : datos no se importan o copian en Power BI Desktop. Las tablas y columnas seleccionadas aparecen en el escritorio de BI energía **campos** lista. Crear o interactuar con una visualización, Power BI Desktop consulta el origen de datos subyacente, lo que significa que siempre está viendo los datos actuales.

Muchas transformaciones de datos y modelado de datos están disponibles al utilizar **DirectQuery**, aunque con algunas limitaciones. Al crear o interactuar con una visualización, se debe consultar el origen subyacente y el tiempo necesario para actualizar la visualización es depende del rendimiento del origen de datos subyacente. Cuando los datos necesarios para la solicitud de servicio recientemente se ha solicitado, Power BI Desktop usa datos recientes para reducir el tiempo necesario para mostrar la visualización. Seleccionar **actualizar** desde el **Inicio** cinta se asegurará de que todas las visualizaciones se actualizan con los datos actuales.

Consulte las siguientes secciones para obtener más información sobre las ventajas, limitaciones y consideraciones importantes al utilizar **DirectQuery**.

## Ventajas del uso de DirectQuery  
Hay dos ventajas principales de utilizar **DirectQuery**:


-   
            **DirectQuery** le permite crear visualizaciones sobre conjuntos de datos muy grandes, donde lo contrario sería viable para importar todos los datos

-   Datos subyacentes cambian pueden requerir una actualización de datos y, en algunos informes, la necesidad de mostrar los datos actuales puede requerir grandes transferencias de datos, lo vuelve a importar datos viable. Por el contrario, **DirectQuery** informes siempre utilizan los datos actuales


## Limitaciones de DirectQuery
Actualmente hay algunas limitaciones para utilizar **DirectQuery**:


-   Todas las tablas deben proceder de una base de datos

-   Si el **Editor de consultas** consulta es demasiado compleja, se producirá un error. Para resolver el error, debe, elimine el paso problemático en **Editor de consultas**, o *importación* los datos en lugar de usar **DirectQuery**

-   Filtrado de relación se limita a un solo sentido, en lugar de ambas direcciones

-   Las capacidades de inteligencia de tiempo no están disponibles en **DirectQuery**. Por ejemplo, un tratamiento especial de columnas de fecha (año, trimestre, mes, día, etc.) no se admiten en **DirectQuery** modo.

-   De forma predeterminada, las limitaciones se colocan en expresiones de DAX permitidas en medidas. consulte el siguiente apartado para obtener más información

-   Hay un límite de 1 millón de filas para devolver datos al usar **DirectQuery**. Esto no afecta a las agregaciones o cálculos utilizados para crear el conjunto de datos que se devuelven mediante **DirectQuery**, solo las filas devueltas. Por ejemplo, 10 millones de filas de agregado con la consulta que se ejecuta en el origen de datos y devolver con precisión los resultados de dicha agregación al uso de Power BI **DirectQuery** siempre y cuando los datos se devuelven a Power BI es menor que 1 millón de filas. Si más de 1 millón de filas se devolverán de **DirectQuery**, Power BI devuelve un error.

Para asegurarse de que las consultas enviadas al origen de datos subyacente tienen un rendimiento aceptable, se imponen limitaciones en medidas de forma predeterminada. Los usuarios avanzados pueden optar por omitir esta limitación seleccionando **archivo > opciones** y, a continuación, **Configuración > Opciones > DirectQuery**, a continuación, seleccionando la opción *Permitir medidas sin restricciones en el modo DirectQuery**. Cuando se selecciona esta opción, se puede usar cualquier expresión de DAX es válido para una medida. Los usuarios deben tener en cuenta, sin embargo, que pueden producir algunas expresiones que realizan muy bien cuando los datos se importan en consultas muy lentas al origen de back-end cuando se encuentra en el modo DirectQuery.

## Consideraciones importantes al utilizar DirectQuery

Deben tenerse en cuenta los tres puntos siguientes al usar **DirectQuery**:

-   
            **Carga y rendimiento** - All **DirectQuery** las solicitudes se envían a la base de datos de origen, por lo que el tiempo necesario para actualizar un objeto visual depende de cuánto tiempo tarda ese origen de back-end para responder con los resultados de la consulta (o consultas). La respuesta recomendada de tiempo (con los datos solicitados que se devuelven) para usar **DirectQuery** para elementos visuales es de cinco segundos o menos, con un máximo recomendado tiempo de respuesta de resultados de 30 segundos. Ya, y la experiencia de usuario consume el informe se vuelve demasiado baja. Además, una vez publicado un informe al servicio Power BI, cualquier consulta que tarda más de unos minutos le tiempo de espera y el usuario recibirá un error.

    Carga en la base de datos de origen también debe considerarse, en función del número de usuarios de Power BI que consumirá el informe publicado. Mediante *seguridad de nivel de fila* (RLS) puede tener un gran impacto; un icono de panel de RLS no compartido por varios resultados de los usuarios en una sola consulta a la base de datos, pero usan RLS en un icono de panel generalmente significa que la actualización de un mosaico requiere una consulta *por usuario*, lo que aumenta significativamente la carga en la base de datos de origen y podría afectar al rendimiento.

    Power BI crea consultas que son tan eficaces como sea posible. En determinadas situaciones sin embargo, la consulta generada puede no ser lo suficientemente eficaz para evitar la actualización que se produciría un error. Un ejemplo de esta situación es cuando una consulta generada recuperaría un número excesivamente grande de filas (más de 1 millón) desde el origen de datos back-end, en que se produce el siguiente error de caso:

        The resultset of a query to external data source has exceeded
        the maximum allowed size of '1000000' rows.

    Esta situación puede producirse con un gráfico sencillo que incluye una columna de cardinalidad muy alta, con la opción de agregación establecida en *no resumir*. El objeto visual debe tener solo las columnas con cardinalidad por debajo de 1 millón o deben haber aplicado filtros adecuados.

-   
            **Seguridad** -todos los usuarios que consumen un informe publicado conectarán al origen de datos back-end con las credenciales especificadas después de la publicación para el servicio Power BI. Se trata de la misma situación que los datos que se importen: todos los usuarios ven los mismos datos, independientemente de las reglas de seguridad definidas en el origen de back-end.

-   
            **Características admitidas** -no todas las características en **Power BI Desktop** se admiten en **DirectQuery** modo, o tiene algunas limitaciones. Además, hay algunas capacidades en el servicio Power BI (como *profundas*) que no están disponibles para el uso de conjuntos de datos **DirectQuery**. Como tal, la limitación de estas características al usar **DirectQuery** debe tenerse en cuenta al determinar si se debe usar **DirectQuery**.   


## Publicar en el servicio Power BI
Los informes creados mediante **DirectQuery** se pueden publicar en el servicio Power BI.

Si el origen de datos usado es **base de datos de SQL Azure** o **el almacenamiento de datos de SQL Azure**, se deben proporcionar credenciales antes de que se mostrará el informe publicado en el servicio Power BI.

Puede proporcionar credenciales seleccionando la **configuración** icono en Power BI de engranaje y seleccione **configuración**.

![](media/powerbi-dekstop-use-directquery/DirectQuery_3.png)

Power BI muestra el **configuración** ventana. Desde allí, seleccione la **conjuntos de datos** ficha y elija el conjunto de datos que usa **DirectQuery**, y seleccione **Editar credenciales**.

![](media/powerbi-dekstop-use-directquery/DirectQuery_4.png)

Hasta que se proporcionan credenciales, abrir un informe publicado o explorar un conjunto de datos creado con una **DirectQuery** conexión **base de datos de SQL Azure** o **el almacenamiento de datos de SQL Azure** genera un error.

Para datos de fuentes distinto de **base de datos de SQL Azure** o **el almacenamiento de datos de SQL Azure** que utilizan DirectQuery y puerta de enlace empresarial debe estar instalado y se debe registrar el origen de datos para establecer una conexión de datos. Puede [obtener más información acerca de la puerta de enlace empresarial](http://go.microsoft.com/fwlink/p/?LinkID=627094).

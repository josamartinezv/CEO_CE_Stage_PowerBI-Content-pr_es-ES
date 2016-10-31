<properties
   pageTitle="Datos multidimensionales de servicios de análisis en Power BI Desktop"
   description="Datos multidimensionales de servicios de análisis en Power BI Desktop"
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
   ms.date="10/12/2016"
   ms.author="davidi"/>

# Conectarse a modelos multidimensionales de SSAS en Power BI Desktop  

Con Power BI Desktop, puede tener acceso a **modelos multidimensionales de SSAS**, normalmente denominado **SSAS MD**.

Para conectarse a un **SSAS MD** base de datos, seleccione **obtener datos &gt; base de datos &gt; base de datos de SQL Server Analysis Services** tal como se muestra en la siguiente imagen.

![](media/powerbi-desktop-ssas-multidimensional/ssas-multidimensional-2.png)


            **Modelos multidimensionales de SSAS** en modo de conexión en directo se admiten en el servicio Power BI y en Power BI Desktop. También puede publicar y cargar informes que usan **modelos multidimensionales de SSAS** en modo directo al servicio Power BI.

## Capacidades y características de SSAS MD
Las secciones siguientes describen características y capacidades de las conexiones de Power BI y MD de SSAS.

### Metadatos tabulares de modelos multidimensionales
La siguiente tabla muestra la correspondencia entre los objetos multidimensionales y los metadatos tabulares que se devuelven a Power BI Desktop. Power BI consulta el modelo de metadatos tabulares y basándose en los metadatos devueltos, ejecuciones de consultas DAX adecuados con Analysis Services cuando se crea una visualización como una tabla, matriz, gráfico o segmentación de datos.

|Objeto multidimensional BISM |Metadatos tabulares|
|---|---|
|Cubo|Modelo |
|Dimensión de cubo | Tabla |
|Atributos de dimensión (claves), nombre) | Columnas  |
|Grupo de medida | Tabla|
|Measure | Measure |
|Medidas sin grupo de medida asociado | En la tabla denominada *medidas*|
|Grupo de medida -> relación de dimensión de cubo | Relationship |
|Perspectiva | Perspectiva|
|KPI | KPI |
|Jerarquías de usuario, elementos primarios y secundarios | Jerarquías |

### Medidas, grupos de medidas y KPI
Grupos de medida de un cubo multidimensional se exponen en Power BI como tablas con el inicio de sesión ∑ junto a ellos en la **campos** panel. Calcula las medidas que no tienen un grupo de medida asociado se agrupan en una tabla especial denominada *medidas* en los metadatos tabulares.

En un modelo multidimensional, puede definir un conjunto de medidas o KPI en un cubo que se encuentre dentro de un *carpeta para mostrar*, lo que puede ayudar a simplificar modelos complejos. Power BI reconoce las carpetas de visualización de metadatos tabulares y muestra las medidas y KPI dentro de las carpetas para mostrar. KPI en la compatibilidad con bases de datos multidimensionales *valor*, *objetivo*, *estado gráfico* y *gráficos de tendencia*.

### Tipo de atributo de dimensión
Modelos multidimensionales también permiten asociar atributos de dimensión con tipos de atributo de dimensión específicos. Por ejemplo, un **Geography** dimensión dónde el *City*, *State-Province*, *País* y *Código Postal* atributos de dimensión tienen geography adecuado se exponen los tipos asociados con ellos en los metadatos tabulares. Power BI reconoce los metadatos, lo que permite crear visualizaciones de mapas. Reconocerá estas asociaciones por la *mapa* icono situado junto al elemento en el **campo** panel en Power BI.

Power BI también puede procesar imágenes al proporcionar un campo que contiene las direcciones URL (localizador uniforme de recursos) de las imágenes. Puede especificar estos campos como *ImageURL* tipo de SQL Server Data Tools (o posteriormente en Power BI) y su información de tipo que se proporciona para Power BI en los metadatos tabulares. Power BI, a continuación, puede recuperar las imágenes de la dirección URL y mostrarlos en objetos visuales.

### Jerarquías de elementos primarios y secundarios
Modelos multidimensionales admiten jerarquías de elementos primarios y secundarios, que se presentan como un *jerarquía* en los metadatos tabulares. Cada nivel de la jerarquía de elementos primarios y secundarios se expone como una columna oculta en los metadatos tabulares. El atributo clave de la dimensión de elementos primarios y secundarios no se expone en los metadatos tabulares.

### Miembros calculados de dimensión
Los modelos multidimensionales admiten la creación de diversos tipos de *miembros calculados*. Los dos tipos más comunes de los miembros calculados son los siguientes:

-   Calcula miembros de jerarquías de atributo y no relacionado con *todos*
-   Miembros calculados en jerarquías de usuario

Exponer un modelo multidimensional *miembros en las jerarquías de atributos calculados* como valores de una columna. Existen algunas opciones adicionales y restricciones al exponer este tipo de miembro calculado:
-   Atributo de dimensión puede tener un opcional *UnknownMember*
-   Un atributo que contenga a miembros calculados no puede ser el atributo clave de la dimensión, a menos que sea el único atributo de la dimensión
-   Un atributo que contenga a miembros calculados no puede ser un atributo de elementos primarios y secundarios

Los miembros calculados de las jerarquías de usuario no se exponen en Power BI. En su lugar, podrá conectarse a un cubo que contenga a miembros calculados en jerarquías de usuario, pero no podrá ver a los miembros calculados si no se ajustan a las restricciones mencionadas en la lista con viñetas anterior.

### Seguridad
Seguridad de nivel de celdas y dimensiones por medio de los modelos multidimensionales admiten *funciones*. Cuando se conecta a un cubo con Power BI, se autentican y evalúa los permisos adecuados. Cuando un usuario tiene *seguridad de la dimensión* aplicado, los miembros de dimensión correspondiente no se ven por el usuario en Power BI. Sin embargo, cuando un usuario tiene un *seguridad de celda* permiso definido, que ciertas celdas están restringidas, a continuación, ese usuario no puede conectarse al cubo con Power BI.

## Limitaciones de los modelos multidimensionales de SSAS en Power BI Desktop
Existen ciertas limitaciones al uso **SSAS MD**:

-   Servidores deben ejecutar SQL Server 2012 SP1 CU4 o versiones posteriores de Analysis Services para el conector de Power BI Desktop SSAS MD funcione correctamente
-   Formato de nivel de celda y funciones de traducción no se admiten en esta versión de MD de SSAS. Estas características se habilitarán en futuras versiones de Power BI Desktop.
-   
            *Acciones* y *conjuntos con nombre* no están expuestos a Power BI, pero todavía puede conectarse a los cubos que contienen *acciones* o *conjuntos con nombre* y crear elementos visuales e informes.

Además, como se mencionó anteriormente no se puede publicar un informe creado con esta versión de **SSAS MD** al servicio Power BI.

## Características admitidas de SSAS MD en Power BI Desktop
Se admiten las siguientes características de SSAS MD en Power BI Desktop:

-   Consumo de los elementos siguientes se admiten en esta versión de **SSAS MD** (puede obtener [obtener más información](https://msdn.microsoft.com/library/jj969574.aspx) acerca de estas características):
    - Carpetas para mostrar
    - Tendencias KPI
    - Miembros predeterminados
    - Atributos de dimensión
    - Miembros calculados de la dimensión (debe ser un único miembro real cuando la dimensión tenga más de un atributo, no puede ser el atributo clave de la dimensión a menos que sea el único y no puede ser un atributo de elementos primarios y secundarios)
    - Tipos de atributo de dimensión
    - Jerarquías
    - Medidas (con o sin grupos de medida)
    - Medidas como variante
    - KPI
    - ImageUrls
    - Seguridad de dimensión

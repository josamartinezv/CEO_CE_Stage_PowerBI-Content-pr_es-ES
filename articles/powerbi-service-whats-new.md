<properties
   pageTitle="Novedades en el servicio Power BI"
   description="Novedades en el servicio Power BI"
   services="powerbi"
   documentationCenter=""
   authors="fetiyekarabay"
   manager="mblythe"
   backup="mihart"
   editor=""
   tags=""
   qualityFocus="no"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="get-started-article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/03/2016"
   ms.author="fetiyek"/>

# Novedades en el servicio Power BI  

Compruebe esta página para funciones publicado recientemente y problemas conocidos **servicio Power BI**.

>
            **NOTA**:
>
Para "What's New" información relacionada, vea:
>
>[Novedades de Power BI Desktop](powerbi-desktop-latest-update.md)  
>
>[Novedades en las aplicaciones móviles para Power BI](powerbi-mobile-whats-new-in-the-mobile-apps.md)  
>
>
            [Blog de desarrolladores de BI de energía](http://blogs.msdn.com/b/powerbidev/).



## Actualizaciones recientes
**29 de julio de 2016**

***RLS graduados de vista previa***

- Seguridad de nivel de fila (RLS) le permite restringir el acceso de datos en función de quién tiene acceso a ella. Recientemente hemos simplificado el proceso de configuración RLS exponiendo los roles y las reglas en Power BI Desktop. Hoy en día, nos complace anunciar que RLS está generalmente disponible para todos los usuarios de Power BI Pro.

***Clasificación de datos***

- Ahora puede etiquetar sus paneles con clasificaciones definidas por su empresa del departamento de TI, haciéndolos conscientes de las ver sus paneles sobre qué nivel de seguridad que debe utilizarse.

***Analizar los datos locales en Excel***

- Analizar en Excel característica se ha ampliado para admitir conjuntos de datos local. Se establezca una conexión directa y segura para el conjunto de datos local que permite analizar en Excel. También presentamos a una configuración para que los administradores desactivar la característica analizar en Excel para orígenes locales.  

Para obtener detalles, [visite el blog del equipo de Power BI](https://powerbi.microsoft.com/blog/power-bi-july-update-for-service-and-mobile/)

**1 de junio de 2016**

***Información rápida***

-   Rápida visión trabaja con filtros complejos: nos complace anunciar que profundas ámbito a un único mosaico ahora entienden filtros complejos.

Para obtener detalles, [visite el blog del equipo de Power BI](https://powerbi.microsoft.com/blog/smarter-auto-generated-insights-with-complex-filters/)

**16 de mayo de 2016**

***Obtener datos***

-   Aumento del límite de tamaño a 1 GB de archivos: hemos incrementado el límite de tamaño de archivo para los libros de Excel y archivos de Power BI Desktop a 1 GB.

-   Buscar servidores SSAS configurada con la puerta de enlace de la empresa y otras actualizaciones de puerta de enlace: ahora al configurar una puerta de enlace de la empresa, los usuarios de su empresa podrán tener acceso a estos servidores en el servicio Power BI a través de la página de obtención de datos. También agregamos compatibilidad para actualizar los conjuntos de datos que incluyen datos de SAP Business Server de almacenamiento mediante la puerta de enlace y la creación de UPN las reglas de asignación cuando se utiliza Analysis Services con la puerta de enlace.

***Seguridad de nivel de fila (RLS)***

-   Compatibilidad con grupos de Azure Active Directory (AAD): los usuarios ahora pueden asignar grupos AAD (grupos de seguridad y listas de distribución) a una función. Esto facilita asignar roles a un grupo grande de usuarios a la vez.

-   
            [Probar las funciones RLS con informes respaldados por los datos con RLS en su lugar](powerbi-admin-rls.md#test-the-role): hemos agregado una característica a nuestro preview RLS que le permite probar el conjunto de datos como un rol específico. Esto hará que el rol funcione como se espera antes de que los usuarios tener en sus manos en el panel.

-   Definir y aplicar RLS a modelos de nube basados en las consultas directas: ahora puede crear y aplicar reglas RLS para orígenes de datos de consulta directa.

***Paneles***

-   Los paneles Favoritos: para ayudarle a alcanzar los paneles que se vaya a la mayoría, agregamos una manera favorito esos paneles y hacerlos fácilmente accesibles desde las áreas de trabajo.

***Analizar en Excel***

-   Mejorar la experiencia de descarga: descargar fácilmente las actualizaciones de la característica analizar en Excel a través de una nueva experiencia de cuadro de diálogo.

-   Compatibilidad con RLS: una vez configurado RLS, las reglas que se aplica a los datos fluyen a través de cuando un usuario analiza los datos en Excel.

-   Mejorado de errores de mensajería para bases de datos de Analysis Services local: anteriormente, si selecciona analizar en Excel para un origen de datos no admitidos, obtendría un mensaje de error hasta después de descargar el archivo ODC y ha intentado conectar a Power BI. Ahora tan pronto como seleccione Analizar en Excel para un origen de datos que no se admite, verá un mensaje informándole de que aún no admiten ese origen de datos.

Para obtener detalles, [visite el blog del equipo de Power BI](https://powerbi.microsoft.com/blog/power-bi-service-may-update-file-size-increase-to-1-gb/)

**1 de junio de 2016**

-   Rápida visión trabaja con filtros complejos: nos complace anunciar que profundas ámbito a un único mosaico ahora entienden filtros complejos.

Para obtener detalles, [visite el blog del equipo de Power BI](https://powerbi.microsoft.com/blog/smarter-auto-generated-insights-with-complex-filters/)

**16 de mayo de 2016**

***Obtener datos***

-   Aumento del límite de tamaño a 1 GB de archivos: hemos incrementado el límite de tamaño de archivo para los libros de Excel y archivos de Power BI Desktop a 1 GB.

-   Buscar servidores SSAS configurada con la puerta de enlace de la empresa y otras actualizaciones de puerta de enlace: ahora al configurar una puerta de enlace de la empresa, los usuarios de su empresa podrán tener acceso a estos servidores en el servicio Power BI a través de la página de obtención de datos. También agregamos compatibilidad para actualizar los conjuntos de datos que incluyen datos de SAP Business Server de almacenamiento mediante la puerta de enlace y la creación de UPN las reglas de asignación cuando se utiliza Analysis Services con la puerta de enlace.

***Seguridad de nivel de fila (RLS)***

-   Compatibilidad con grupos de Azure Active Directory (AAD): los usuarios ahora pueden asignar grupos AAD (grupos de seguridad y listas de distribución) a una función. Esto facilita asignar roles a un grupo grande de usuarios a la vez.

-   
            [Probar las funciones RLS con informes respaldados por los datos con RLS en su lugar](powerbi-admin-rls.md#test-the-role): hemos agregado una característica a nuestro preview RLS que le permite probar el conjunto de datos como un rol específico. Esto hará que el rol funcione como se espera antes de que los usuarios tener en sus manos en el panel.

-   Definir y aplicar RLS a modelos de nube basados en las consultas directas: ahora puede crear y aplicar reglas RLS para orígenes de datos de consulta directa.

***Paneles***

-   Los paneles Favoritos: para ayudarle a alcanzar los paneles que se vaya a la mayoría, agregamos una manera favorito esos paneles y hacerlos fácilmente accesibles desde las áreas de trabajo.

***Analizar en Excel***

-   Mejorar la experiencia de descarga: descargar fácilmente las actualizaciones de la característica analizar en Excel a través de una nueva experiencia de cuadro de diálogo.

-   Compatibilidad con RLS: una vez configurado RLS, las reglas que se aplica a los datos fluyen a través de cuando un usuario analiza los datos en Excel.

-   Mejorado de errores de mensajería para bases de datos de Analysis Services local: anteriormente, si selecciona analizar en Excel para un origen de datos no admitidos, obtendría un mensaje de error hasta después de descargar el archivo ODC y ha intentado conectar a Power BI. Ahora tan pronto como seleccione Analizar en Excel para un origen de datos que no se admite, verá un mensaje informándole de que aún no admiten ese origen de datos.

Para obtener detalles, [visite el blog del equipo de Power BI](https://powerbi.microsoft.com/blog/power-bi-service-may-update-file-size-increase-to-1-gb/)

**13 de mayo de 2016**

-   
            [Power BI Q & un soporte para los modelos tabulares de Analysis Services de SQL Server 2016](powerbi-service-q-and-a-direct-query.md): nos complace anunciar mejoras en Power BI Q & una experiencia de usuario y el inicio de la vista previa de Power BI Q & A gateway conectado orígenes de datos empresariales - inicio con soporte para los modelos tabulares de Analysis Services de SQL Server 2016. Para obtener detalles, [consulte el blog](https://powerbi.microsoft.com/blog/power-bi-q-a-for-enterprise-gateway-connected-data-sources-now-available-in-public-preview/)

-   
            [Soporte de archivo local para los informes de Excel](powerbi-service-excel-workbook-files.md#local-excel-workbooks): ahora puede cargar los archivos de Excel desde la unidad local o de otros servicios de almacenamiento y utilizar ese informe de Excel, tal como haría en Excel Online con las ventajas adicionales de Power BI. Para obtener detalles, [consulte el blog](https://powerbi.microsoft.com/blog/powerbi-upload-excel-reports-from-local-files/)

**28 de abril de 2016**

-   
            [Rápida visión en iconos de panel](powerbi-service-auto-insights.md#run-quick-insights-on-a-dashboard-tile): cuando ve un mosaico en el modo de enfoque, haga clic en obtener información para buscar el mosaico y sus datos relacionados de correlaciones, los valores atípicos, tendencias, estacionalidad, cambiar puntos de tendencias y las principales factores automáticamente, en segundos.

Para obtener detalles, [visite el blog del equipo de Power BI](https://powerbi.microsoft.com/blog/find-more-insights-in-your-dashboards-with-quick-insights/)

**26 de abril de 2016**

-   Narraciones para Power BI: al interactuar con los datos y las visualizaciones, este objeto visual personalizado dinámicamente proporciona información en forma de narración, como se esperaría escribiría un analista. Este objeto visual se nutre de [Descripción ciencia ave](https://www.narrativescience.com/quill).

Para obtener detalles, [visite el blog del equipo de Power BI](https://powerbi.microsoft.com/blog/get-natural-language-narratives-in-power-bi-reports/)

**16 de abril de 2016**

-   Microsoft Trust Center: Power BI había unido el Microsoft Trust Center, un único origen para documentar las certificaciones de cumplimiento para productos de Microsoft. Certificaciones de Power BI incluyen ISO 27001, ISO 27018, cláusulas de modelo de la UE, BAA HIPAA y nube G Reino Unido.

Para obtener detalles, [visite el blog del equipo de Power BI](https://powerbi.microsoft.com/blog/power-bi-added-to-microsoft-trust-center/)

**14 de abril de 2016**

***Enterprise***

-   
            [ExpressRoute](powerbi-admin-power-bi-expressroute.md): utilizar para establecer una conexión privada administrada a Power BI.

-   
            [Compatibilidad con paquete de RLS de contenido](powerbi-admin-rls.md) (vista previa): RLS si se define para esos paneles e informes que se distribuyen como parte de un paquete de contenido, a continuación, se respetan las reglas de seguridad para los paquetes de contenido.

***Paneles***

-   
            [Icono de vídeo Vimeo](powerbi-service-add-a-widget-to-a-dashboard.md): en el panel, agregar un icono que contiene un reproductor incrustado de Vimeo.

***Analizar en Excel***

-   
            [Analizar en Excel](powerbi-service-analyze-in-excel.md) disponibles para todos los usuarios: la capacidad de tener acceso a los modelos de datos de Power BI en Excel se ha extendido para todos los usuarios; libre y Pro.

-   Cuenta de usuario de la experiencia mejorada: si tiene más de 1 cuenta de usuario de Power BI, ahora es más fácil iniciar sesión.


Para obtener detalles, [visite el blog del equipo de Power BI](https://powerbi.microsoft.com/blog/power-bi-service-april-update-expressroute-for-power-bi/)


            **31 de marzo de 2016** gran número de actualizaciones que se anunció en la cumbre de visión de datos de Microsoft.

***Paneles***

-   Panel destacado: facilita la cobertura del panel que más le interesa.

-   Lista de filtros de panel: Mostrar todo, mostrar el contenido que creó, mostrar contenido compartido con usted.


***Características empresariales***

-   Informes de uso de administración: agrega un informe de uso en el centro de administración de Power BI.

-   Seguridad de nivel de fila: esta es una característica de vista previa que le permite establecer permisos en conjuntos de datos de Power BI.

-   Deshabilitar la exportación de datos: los usuarios en el inquilino ya no podrán exportar mosaico y datos visuales a un archivo .csv.

***PREGUNTAS Y RESPUESTAS***

-   Autocompletar para "es": preguntas y respuestas le sugerirá valores si escribe el nombre de columna seguido de "es".

***Móvil***

-   KPI en su Apple Watch: supervisar los KPI y mosaicos de tarjeta sin tener que abrir la aplicación Power BI.

***Excel***

-   Analizar en Excel: conectar el modelo de datos de Power BI con Excel y realizar su análisis dentro de Excel en lugar de Power BI.

***Otros***

-   Power BI en Australia: ahora cualquiera en Australia, individual o a través de una organización, puede subir a powerbi.microsoft.com e inicie sesión para Power BI.

-   Configuración de idioma: invalidar la detección automática de idioma y establecer el idioma para Power BI.

Para obtener detalles, [visite el blog del equipo de Power BI](https://powerbi.microsoft.com/blog/power-bi-service-march-update-part-two/)

**11 de marzo de 2016**

Este mes se realizan algunas actualizaciones a los paneles, información rápidamente y preguntas y respuestas.

***Paneles***

-   Modo de pantalla completa: impresión sin tener que salir del modo de pantalla completa en primer lugar

-   Modo de pantalla completa: expanda los iconos para llenar todo el lienzo y quitar los espacios en blanco sobrantes seleccionando **Ajustar a ancho**

-   Usar flujo de mosaico para alinear automáticamente los iconos en la esquina superior izquierda del lienzo.

***Información rápida***

-   La información de tendencia y Correlaction ahora tiene líneas de tendencia para que resulten más fáciles de ver patrones en los datos.

***PREGUNTAS Y RESPUESTAS***

-   Ahora puede especificar el medidor y el área de gráficos en preguntas y respuestas

-   Mejorado Autocompletar para preguntas y respuestas - tan pronto como escribe unos pocos caracteres, preguntas y respuestas comienza automáticamente completar y sugerir elementos visuales para usted.


Para obtener detalles, [visite el blog del equipo de Power BI](https://powerbi.microsoft.com/blog/power-bi-service-march-update/)




**10 de febrero de 2016**

Hoy lanzamos una larga lista de características más solicitadas. 
            [Leer la entrada de blog](https://powerbi.microsoft.com/blog/power-bi-february-service-update/).

***Uso compartido***

- Compartir con los usuarios fuera de su organización

- Solicitar acceso a un panel

***Portal de administración***

- Administración de usuario sencilla con un vínculo al centro de administración de Office 365

- Capacidad de deshabilitar publicación en web

- Impedir que los usuarios publicar paquetes de contenido en la organización completa

- Capacidad de deshabilitar el uso compartido de contenido externos a los usuarios

***Información rápida***

- Rápida visión al publicar los archivos de Power BI Desktop

***Panel***

- Agregar contenido Web al escritorio (a través de Widget)
- Agregar contenido de vídeo en el panel (mediante Widget)
- Acercar en paneles

***Conectividad***
- Conectarse a los archivos en su sitio de SharePoint del equipo a través de una dirección URL

Para obtener detalles, [visite el blog del equipo de Power BI](https://powerbi.microsoft.com/blog/power-bi-february-service-update/)

**28 de enero de 2016**

Actualizaciones de informes y visualizaciones:

- [Agregar bordes a objetos visuales](https://powerbi.microsoft.com/blog/power-bi-updates-this-week-new-report-authoring-capabilities/#borders)

- [Agregar imágenes de fondo para las páginas y las áreas de trazado del gráfico cartesiano](
https://powerbi.microsoft.com/blog/power-bi-updates-this-week-new-report-authoring-capabilities/#background)

Mejoras de rendimiento para la representación del informe, realzado cruzado, etc..

- Independientemente de la versión de explorador que se va a usar, se puede apreciar una mejora considerable del rendimiento por los usuarios al cargar informes, cambiar entre las páginas de datos realzado cruzado entre objetos visuales, etc. con esta nueva actualización.


**6 de enero de 2016**

El equipo de Power BI ha estado ocupado en descanso de vacaciones. Para obtener detalles, [visite el blog del equipo de Power BI](http://blogs.msdn.com/b/powerbi/archive/2016/01/06/power-bi-service-update-0106.aspx)

***Paneles***

- Exportar datos de mosaico

- Agregar un widget de cuadro de texto o imagen para paneles

- Paneles de impresión

- Hora en mosaicos de actualización

- Información sobre herramientas en los iconos de panel

***Colaboración***

- Notificación de panel compartido

- Póngase en contacto con el propietario de un escritorio compartido o de la organización

***Reports***

- Imprimir la página actual del informe

- Exportar datos de informe visual

***Conectividad***

- Conectarse a los archivos de los sitios de SharePoint team

***Informes de Excel***

- Abrir informes de Excel en el escritorio de Excel

- Anclar los gráficos de Excel

- Mejoras de formato de iconos de Excel

***Otros***

- Power BI en Brasil

- Compatibilidad con hebreo y árabe

Para obtener detalles, [visite el blog del equipo de Power BI](http://blogs.msdn.com/b/powerbi/archive/2016/01/06/power-bi-service-update-0106.aspx)


**16 de diciembre de 2015**

Gran número de actualizaciones de esta semana, más se aplican a Power BI Desktop pero varias actualizaciones importantes para la creación de informes y visualizaciones así. El [Blog del equipo de Power BI](http://blogs.msdn.com/b/powerbi/archive/2015/12/16/more-power-bi-feature-updates-power-bi-desktop-december-update-and-new-power-bi-service-features.aspx) contiene descripciones completas e incluso un vídeo que describe las actualizaciones.   

[Descargar Power BI Desktop](https://powerbi.microsoft.com/desktop?WT.mc_id=Blog_Desktop_Update)

* Actualizaciones para el formato panel y la cinta de opciones de creación de informes:

  1. Formato de etiquetas de datos por serie de categoría

  2. Cambiar el número de posiciones decimales que se mostró en objetos visuales

  3. Cambiar el tamaño del texto en elementos visuales

  4. Capacidad para disponer elementos visuales con precisión: alineación, distribuir, tamaño, posición (requiere Power BI Desktop para la creación)

  5. Establecer estilos a través de varios objetos visuales mediante Copiar formato (requiere Power BI Desktop para la creación)

* Mejoras de visualizaciones:

  1. elementos visuales de indicación de estado de ordenación en visual de la tabla

  2. nuevo visual: gráfico de áreas apiladas

  3. Smart información sobre herramientas para los gráficos de líneas y de áreas al mantener el mouse

  4. capacidad para crear la línea de referencia o región para un objeto visual cartesiano

  5. etiquetas de datos mejoradas para los gráficos circulares y de dispersión

* Integración de elementos visuales de R en el escritorio (característica de vista previa)

* Escritorio sugerirá relaciones de tabla a la tabla al intentar crear 2 tablas que no están relacionadas.

* Escritorio había optimizado de diseño de la cinta de opciones de inicio.

* Actualizaciones en la vista de relaciones de modelado de datos escritorio:

  1. control deslizante de zoom

  2. ajustar el zoom

  3. Restablecer diseño

  4. capacidad de ampliación con el rectángulo de selección del Mouse Ctrl

* Mejoras de conectividad de datos de escritorio

  1. Soporte Multidimensional de SSAS - soporte de jerarquías (característica de vista previa)

  2. Conector de bandas

  3. Conector de Smartsheet

  4. "Escribir datos": pegar o escribir datos para crear una tabla

  5. Mejoras de DirectQuery: Compatibilidad con todos los tipos de datos de T-SQL y SAP HANA, lo que las mejoras de rendimiento.

  6. Conector ODBC: Compatibilidad para la selección de DSN de usuario o sistema

  7. Conector CSV: Especifique el delimitador de columna en el cuadro de diálogo origen de capacidad

Para todos los detalles, incluyendo un vídeo que muestra muchas de estas actualizaciones, visite la [Blog de Power BI](http://blogs.msdn.com/b/powerbi/archive/2015/12/16/more-power-bi-feature-updates-power-bi-desktop-december-update-and-new-power-bi-service-features.aspx).

**10 de diciembre de 2015**

* Páginas del informe PIN al panel

* Actualizar los iconos de panel

* Utilizar imágenes en segmentaciones de datos

* Cambiar las interacciones entre los elementos visuales del informe

  Para obtener detalles, visite la [Blog de Power BI](http://blogs.msdn.com/b/powerbi/archive/2015/12/10/power-bi-weekly-service-update-1210.aspx).


**8 de diciembre de 2015**

* [Códigos QR en Power BI](http://blogs.msdn.com/b/powerbi/archive/2015/12/08/bridge-the-gap-between-your-physical-world-and-your-bi-using-qr-codes.aspx)

**3 de diciembre de 2015**

*  Detectar tendencias y descubrir patrones en un conjunto de datos con una visión rápida automáticamente: [vídeo](http://blogs.msdn.com/b/powerbi/archive/2015/12/02/power-bi-updates-from-browser-to-desktop-and-new-automated-insights-mf.aspx) o  [artículo](powerbi-service-auto-insights.md)

* [Visualizar los datos VMob en Power BI](http://blogs.msdn.com/b/powerbi/archive/2015/11/25/visualize-your-vmob-data-in-power-bi.aspx)

*   [Integración de Power BI con Cortana](http://blogs.msdn.com/b/powerbi/archive/2015/12/01/announcing-power-bi-integration-with-cortana-and-new-ways-to-quickly-find-insights-in-your-data.aspx)

*   [Vista previa de puerta de enlace de Power BI para enterprise](http://blogs.msdn.com/b/powerbi/archive/2015/12/02/announcing-preview-of-power-bi-gateway-for-enterprise-deployments.aspx)

* Introducting un nuevo paquete de contenido: [análisis de búsqueda de Bing en paneles de Power BI](http://blogs.msdn.com/b/powerbi/archive/2015/12/02/search-analytics-from-bing-on-your-power-bi-dashboards.aspx)

* Nuevas mejoras orientadas a desarrolladores: [dos nuevas API y registro de la aplicación sea más fácil](http://blogs.msdn.com/b/powerbi/archive/2015/12/02/power-bi-for-developers-reports-api-and-a-simple-app-registration-experience.aspx)


**24 de noviembre de 2015**

*   Rangos de Excel de PIN para paneles

*   Modo de pantalla completa sin cromo para paneles e informes

*   Saber dónde se almacenan los datos

* Carga mejorada de informes local

* Compartir paneles directamente al área de trabajo de otro usuario

* Mejor experiencia de conector de Google Analytics

* Cerrar su cuenta de power bi

Para obtener detalles, visite la [Blog de Power BI](http://blogs.msdn.com/b/powerbi/archive/2015/11/24/power-bi-weekly-service-update-1124.aspx)


**18 de noviembre de 2015**

*   Crear un panel duplicado

*   Colocar libremente los iconos de panel

*   Navegación mejorada para la vista de pantalla completa

* Mejor experiencia al invitar a pares de su organización en grupos de Power BI

* Mensajes de error mejorados para iconos

Para obtener detalles, visite la [Blog de Power BI](http://blogs.msdn.com/b/powerbi/archive/2015/11/17/power-bi-weekly-service-update-1117.aspx)


**11 de noviembre de 2015**

*   Nuevo sitio de documentación de Power BI, localizada

*   Tiempo de carga mejorado para informes

*   Actualizar paquetes de contenido organizativo con cambios sólo informe

* Estado de mantenimiento de BI de energía en el Portal de administración de Office 365

* KPI e imágenes en tablas, matrices y tarjetas

Para obtener detalles, visite la [Blog de Power BI](http://blogs.msdn.com/b/powerbi/archive/2015/11/11/power-bi-weekly-service-update-1110.aspx)


**3 de noviembre de 2015**

*   Experiencia guiada de compra de Power BI.

*   Personas pueden comprar Power BI Pro.

*   Página de informe duplicado.

Para obtener detalles, visite la [Blog de Power BI](http://blogs.msdn.com/b/powerbi/archive/2015/11/03/power-bi-weekly-service-update-1103.aspx)


**28 de octubre de 2015**

- Compartir paneles con grupos de seguridad de Active Directory

- Selector de personas

- Uso compartido con un gran número de direcciones de correo electrónico

- Contraer el panel de navegación a través de una dirección URL con parámetros

Para obtener detalles, visite la [Blog de Power BI](http://blogs.msdn.com/b/powerbi/archive/2015/10/28/power-bi-weekly-service-update-1027.aspx)


**20 de octubre de 2015**

-   Miembros de solo lectura en grupos de Power BI

-   Preguntas destacadas en preguntas y respuestas

-   Modo de pantalla completa emergente para las visualizaciones de informes

Para obtener detalles, visite la [blog de Power BI](http://blogs.msdn.com/b/powerbi/archive/2015/10/20/power-bi-weekly-service-update-1020.aspx)


**13 de octubre de 2015**

-   Modo de pantalla completa para mostrar los paneles e informes en los televisores de pantalla grande

-   'Se ajustan a la pantalla' admite en modo de pantalla completa para mostrar el panel de todo en el espacio disponible

-   Modo de foco para obtener más información acerca de los iconos de panel

-   Capacidad de ver la hora de última actualización para cada mosaico

-   Capacidad de ver el código fuente para cada mosaico

-   ERoom PlanView Enterprise es una cartera de extremo a extremo y la solución de administración de recursos que se conecta la estrategia de ejecución, mejorar la toma de decisiones en toda la empresa. El paquete de contenido eRoom Planview Enterprise para Power BI permite visualizar los recursos y datos de administración de trabajo en una forma totalmente nueva. Simplemente inicie sesión con sus credenciales y empiece a explorar de forma interactiva la inversión de cartera gastar, estado y cómo alinean los proyectos con las prioridades estratégicas de presupuesto.

Ver nuestra [blog](http://blogs.msdn.com/b/powerbi/archive/2015/10/13/power-bi-weekly-service-update-1013.aspx) y [documentación en línea](powerbi-service-get-started.md) para obtener más información.


**6 de octubre de 2015**

-   Con Power BI Q & A, puede explorar los datos utilizando preguntas sencillas y recibir respuestas en forma de gráficos y gráficos interactivos. Con esta versión, hemos agregado una característica que le ayudarán a empezar a trabajar con Power BI Q & A, incluso cuando no se sabe nada acerca de los datos. Para empezar a trabajar con esto, [navegar a cualquier panel y haga clic en el vínculo "Cómo pedir" cerca de las preguntas y respuestas cuadro](powerbi-service-how-to-use-q-and-a.md). Power BI presenta una serie de sugerencias basadas en los datos.

-   Hace dos semanas se introdujo la compatibilidad para la inserción de formas en el lienzo de informe en Power BI Desktop. Esta semana, nos complace anunciar que ahora puede agregar formas a su lienzo de informes al crear o editar informes en la aplicación web de Power BI.

-   Hemos agregado la opción para desactivar la notificación de correo electrónico cuando se comparte un panel. Simplemente, desactive la casilla de verificación "Enviar notificación de correo electrónico a los destinatarios" en el cuadro de diálogo del recurso compartido de Power BI. Se ofrecerá una dirección URL: copiar y compartir esta URL a sus compañeros para concederles acceso al panel.

-   Microsoft Dynamics NAV es una solución de administración empresarial para organizaciones pequeñas y medianas. Ofrece a los clientes una solución completa para sus negocios con mayor control sobre sus operaciones financieras y los procesos empresariales. El paquete de contenido de Power BI proporciona informes de out-of-box para usuarios de Dynamics NAV, como ventas y beneficios, canalización de oportunidades, rentabilidad y mucho más. Estas métricas se organizan en un panel que puede personalizarse completamente, lo que le permite conectar fácilmente y comenzar a explorar los datos inmediatamente.

Consulte la [blog](http://blogs.msdn.com/b/powerbi/archive/2015/10/06/power-bi-service-weekly-update-10-06.aspx) y [documentación en línea](powerbi-service-get-started.md) para obtener más información.


**29 de septiembre de 2015**

-   Con el servicio de la semana de actualización, al crear nuevos informes puede ahora elegir entre varios tamaños de página, así como definir su propio tamaño de página. Controla el tamaño y la proporción de cada página del informe.

-   Hemos agregado compatibilidad adicional en formato visual para las imágenes y gráficos de burbujas. Puede bloquear el aspecto al cambiar el tamaño de imágenes para evitar la distorsión de imagen y las burbujas de gráfico de dispersión pueden configurarse para rellenar o no.

-   En la actualidad, Power BI enviará compartir invita a una dirección de correo electrónico alternativa. Cuando un panel se comparte con usted, se enviará el vínculo de la invitación para compartir a su dirección de correo electrónico original y a su dirección de correo electrónico alternativa (si se haya configurado).

-   Power BI está disponible para todos los clientes incluidos aquellos en lo dedicado en la arquitectura de Office 365 para varios inquilinos (DonMT). Usar Power BI como un servicio compartido en el modo de varios inquilinos. En la mayoría de los casos, puede registrarse para Power BI siguiendo simple [proceso de autoayuda servicio suscripción](https://powerbi.microsoft.com/) – simplemente escriba su dirección de correo electrónico, escriba su nombre y contraseña para empezar. Si usted es el Administrador de inquilinos, puede asignar licencias a los usuarios mediante las instrucciones [aquí](http://go.microsoft.com/fwlink/?LinkId=627174).

-   Registros de auditoría de Azure le permite ver registros operativos de plano de control en su suscripción de Azure. Los registros de auditoría de Power BI Azure contenido módulo puede ayudarle fácilmente analizar y visualizar la gran variedad de información contenida en estos registros. El paquete de contenido le permite conectarse a los datos y comenzar a detectar información con los informes y paneles fuera del cuadro. Leer nuestra [blog](http://blogs.msdn.com/b/powerbi/archive/2015/09/30/monitor-azure-audit-logs-with-power-bi.aspx) y [documentación en línea](powerbi-content-pack-azure-audit-logs.md)para obtener más información.


            [Obtenga más información en nuestro blog](http://blogs.msdn.com/b/powerbi/archive/2015/09/30/power-bi-weekly-service-update-0929.aspx).


**22 de septiembre de 2015**

-   Tiene más flexibilidad en el panel de personalizar sus paneles con tamaños de mosaico adicional, que van desde 1 x 1 a 5 x 5.

-   Ahora puede [share (y dejar de compartir) un panel desde el espacio de grupo](powerbi-service-collaborate-with-your-power-bi-group.md) exactamente la forma que lo haría en su propio espacio. Una vez que sus colegas aceptan la invitación para compartir, se agregará al panel compartido (y sus informes asociados) en su propio espacio con permiso de sólo lectura.

-   Hemos agregado 5 adicionales [ejemplos relacionados con la industria](powerbi-sample-datasets.md) Power BI: rentabilidad del cliente, recursos humanos, análisis de oportunidad, análisis de compras y ventas y Marketing de ejemplo.

-   Bandas es una plataforma de pago avanzadas para empresas en línea. De nuevas empresas para empresas Fortune 500, miles de empresas usan bandas para aceptar pagos en más de 130 monedas, de cualquier persona del mundo. Al conectar Power BI con su cuenta de bandas existente, podrá [utilizar el paquete de contenido de Power BI Stripe para supervisar, explorar y visualizar la actividad de bandas](powerbi-content-pack-stripe.md).


            [Obtenga más información en nuestro blog](http://blogs.msdn.com/b/powerbi/archive/2015/09/22/power-bi-weekly-service-update-0922.aspx).


**15 de septiembre de 2015**

-   Ahora puede elegir qué panel desea anclar la visual a! Elija el panel de destino en los paneles existentes, o incluso puede crear un nuevo panel y anclar la visualización a él de una sola vez.

-   Además, puede controlar los colores visuales en el panel. Si el informe está usando un tema diferente del tema de escritorio, puede controlar si el objeto visual conserva el tema actual o utiliza el tema predeterminado del panel para conseguir coherencia entre los elementos visuales de diversos orígenes.

-   Ahora puedes simplemente anclar el mosaico de un panel a otro, del mismo modo que haría anclar un visual de informe a un panel.

-   Si el período de prueba de 60 días Power BI Pro está a punto de caducar, puede [en contacto con nosotros]( http://go.microsoft.com/fwlink/?LinkID=624573&clcid=0x409now) para solicitar una extensión de la versión de prueba. Si se aprueba, la versión de prueba se ampliará para otra 60 días.

-   comScore Digital Analytix es una solución en línea que proporciona información sobre el usuario en base a través de los mejores datos demográficos de audiencia y análisis. Con el paquete de contenido de comScore Power BI, rápidamente puede conectarse y empezar a obtener información sobre los datos de análisis de web. Este paquete de contenido incluye un panel fuera del cuadro, un conjunto de informes y un conjunto de datos protegido para ayudarle a explorar y profundizar en los datos. Más información sobre el paquete de contenido en nuestros [blog](http://blogs.msdn.com/b/powerbi/archive/2015/09/16/visualize-and-explore-your-comscore-data-with-power-bi.aspx) y [tema de Ayuda](powerbi-content-pack-content-pack.md). 

**8 de septiembre de 2015**

-   ﻿Hipervínculos descriptivos permiten proporcionar vínculos a los usuarios sin necesidad de mostrar la dirección URL completa en el cuadro de texto.

-   Se ha agregado compatibilidad con la obtención de detalles para informes de Power BI. Puede crear una ruta de acceso de obtención de detalles que permite a los usuarios navegar desde un nivel de datos a los datos relacionados.

-   Se agregaron dos nuevos ejemplos relacionados de la industria, que dedicar el análisis y análisis de calidad del proveedor, en la sección de ejemplos de la experiencia de obtención de datos. Estos ejemplos son buenos ejemplos de cómo puede utilizar los datos para crear paneles e informes perspicaces.

-   Tenemos un nuevo módulo de contenido de tyGraph, lo que permite obtener fácilmente información detallada sobre los datos de Yammer. El paquete de contenido incluye un panel, un conjunto de informes y un conjunto de datos seleccionado para explorar y proporcionar información como la medida de la contratación activa (la puntuación de MAE) y métricas de consumo de contenido como vistas de archivos y las descargas de archivos. Más información sobre nuestro [blog](http://blogs.msdn.com/b/powerbi/archive/2015/09/09/analyze-and-monitor-your-tygraph-data-with-power-bi.aspx) y [tema de Ayuda](powerbi-content-pack-tygraph.md).

**1 de septiembre de 2015**

-   WebTrends ayuda a las empresas sentido de sus datos de cliente para conseguir el éxito de marketing digital. Los usuarios tienen la capacidad de observar, analizar y proporcionar información en el trayecto de visitante en web, social, móviles y canales de SharePoint. Con el lanzamiento de [paquete de contenido de la Webtrends](http://blogs.msdn.com/b/powerbi/archive/2015/09/01/visualize-and-explore-your-webtrends-data-in-power-bi.aspx), los usuarios tendrán ahora la capacidad de usar Power BI para supervisar, analizar y visualizar los datos de análisis de Webtrends. El Webtrends paquete de contenido de Power BI [página de Ayuda](powerbi-content-pack-webtrends.md) obtener más información.

-   Introducción a las preguntas y respuestas es incluso más sencillo. El momento en que se coloca el cursor dentro de las preguntas y un cuadro de texto al instante mostramos una lista de preguntas y las métricas clave que son relevantes para los datos.  En la lista desplegable, de forma predeterminada, verá las preguntas de iconos ya está anclados en el panel, así como una entrada para cada tabla que tiene en el conjunto de datos.

-   El tamaño del lienzo dinámica que mostramos predeterminada presenta nuestro de los elementos de informe con dimensiones óptimas para el tamaño de la ventana de explorador. Si desea bloquear en la relación de aspecto o desea ajustar su informe de manera diferente, ahora se admiten tres opciones de otro para usted: ajustar a la página, ajustar al ancho y el tamaño real.

-   También hemos incrementado el límite del número de conjuntos de datos e informes que pueden tener. Ahora puede tener hasta 200 conjuntos de datos y de 200 informes estándar para cada conjunto de datos en su cuenta de Power BI.

**25 de agosto de 2015**

-   Ahora puede usar Power BI para supervisar, explorar y [visualizar los datos de análisis de Adobe](http://blogs.msdn.com/b/powerbi/archive/2015/08/25/exploring-your-adobe-analytics-data-in-power-bi.aspx). Con un paquete de contenido de out-of-box, puede conectarse y detectar información de los datos inmediatamente. Para obtener más información, visite la [Adobe Analytics paquete de contenido de la página de Ayuda de Power BI](powerbi-content-pack-adobe-analytics.md).

**18 de agosto de 2015**

-   Azure Mobile Engagement es un servicio de análisis de aplicaciones que permite a los desarrolladores un seguimiento del rendimiento de la aplicación que les ayudan a aumentar el uso de la retención y la aplicación. Mediante el [paquete de contenido de Power BI Azure Mobile Engagement](http://blogs.msdn.com/b/powerbi/archive/2015/08/17/monitor-and-analyze-your-azure-mobile-engagement-data-in-power-bi.aspx) puede conectarse rápidamente a un panel de out-of-box, un conjunto de informes y un vasto conjunto de datos y al instante obtener información sobre cómo está haciendo la aplicación. Consulte el [paquete de contenido de Azure Mobile Engagement para la página de Ayuda de Power BI](powerbi-content-pack-azure-mobile.md) para obtener más información.

**11 de agosto de 2015**

-   Mandrill es un servicio de la infraestructura de correo electrónico desarrollado por MailChimp que permite analizar sus campañas de correo electrónico desde una amplia variedad de información. Con el [paquete de contenido de Power BI Mandrill](http://blogs.msdn.com/b/powerbi/archive/2015/08/12/explore-and-analyze-your-mandrill-data-in-power-bi.aspx), puede conectarse rápidamente a los datos de Mandrill e inmediatamente obtener información sobre la campaña de marketing o su boletín. Para obtener más información acerca de cómo empezar a trabajar, consulte el [paquete de contenido de Mandrill para la página de Ayuda de Power BI](powerbi-content-pack-mandrill.md).

**4 de agosto de 2015**

-   Power BI ahora ofrece [Id. de circuito](http://blogs.msdn.com/b/powerbi/archive/2015/08/04/circuit-id-data-with-power-bi.aspx) a los usuarios la capacidad de realizar un seguimiento y supervisar su identificador de circuito servicios de comunicaciones, les permite tomar las decisiones de negocio correctas lo que en la nube. Para obtener más detalles sobre cómo empezar a trabajar, consulte el paquete de contenido de Id. de circuito de [página de Ayuda de Power BI](powerbi-content-pack-circuit-id.md).

-   Hoy en día, se ha lanzado una mejora de la característica de panel recurso compartido que sea más fácil de utilizar.  Si su organización usa Office 365 para correo electrónico, ahora puede [compartir a un grupo de distribución de correo electrónico](http://blogs.msdn.com/b/powerbi/archive/2015/08/04/easier-dashboard-sharing-with-distribution-groups.aspx) exactamente de la misma forma podría enviar un correo electrónico en Outlook.  Escriba la dirección del grupo de distribución y haga clic en compartir.  Todos los miembros del grupo de distribución recibirán una invitación por correo electrónico para ver el panel.

**28 de julio de 2015**

-   Nos complace anunciar la actualización de esta semana en Power BI ahora el seguimiento del rendimiento con la base de datos ofrece el [paquete de contenido de SQL Sentry](http://blogs.msdn.com/b/powerbi/archive/2015/07/28/monitoring-your-sql-sentry-data-with-power-bi.aspx). Este paquete de contenido incluye un panel y los informes que le ayudarán a supervisar las implementaciones de SQL Server que realiza el seguimiento mediante la nube de SQL Sentry. Para obtener más detalles sobre cómo empezar a trabajar, consulte el paquete de contenido de SQL Sentry para Power BI [página de Ayuda](powerbi-content-pack-sql-sentry.md).

**24 de julio de 2015**

-   Nos complace anunciar nuestra "disponibilidad general" versión (GA) de Power BI. Aún puede utilizar la versión gratuita de Power BI o suscribirse a [Power BI Pro](powerbi-free-trial-for-power-bi-pro.md). Como parte de la versión GA, le ofrecemos algunas características nuevas:

-   Una nueva visualización y la experiencia de creación de informes: el nuevo lienzo de informes tiene una gran variedad de visualizaciones, más control sobre el formato de los títulos, leyendas, ejes, colores, fondos y mucho más.

-   
            [Grupos de BI de energía](powerbi-service-create-a-group-in-power-bi.md): grupos ofrecen una experiencia de colaboración eficaces basada en grupos de Office 365.
-   
            [Paquetes de contenido organizativo](powerbi-service-organizational-content-packs-introduction.md): Power BI permite crear paneles e informes muy sencillo y ahora los usuarios pueden publicar contenido en la Galería de contenido de organización.

-   
            [Poner los archivos de Excel completos](powerbi-bring-in-whole-excel-files.md): puede poner cualquier libro de Excel almacenado en OneDrive para la empresa en Power BI y ver todo el libro, tal y como lo haría en Excel Online.

-   
            [Poner en archivos CSV](powerbi-service-get-data-from-files.md): igual que el archivo de Excel o Power BI Desktop, un archivo de valores separados por comas (CSV) de texto también puede ser un conjunto de datos para los informes y paneles de Power BI.

-   
            [Reemplazar los archivos de Excel, Power BI Desktop y CSV](powerbi-replace-an-excel-power-bi-desktop-or-csv-file.md): puede cargar una versión actualizada de un archivo en Power BI y reemplazar el conjunto de datos existente. Todos los informes y paneles conectados a este conjunto de datos ahora automáticamente utilizan la nueva versión.

-   Nos complace anunciar la actualización de esta semana en Power BI ahora ofrece seguimiento de elementos de trabajo [el paquete de contenido de Visual Studio Online](http://blogs.msdn.com/b/powerbi/archive/2015/07/22/monitoring-your-visual-studio-online-work-items-with-power-bi.aspx). Esta actualización incluye un nuevo panel, informe y un conjunto de datos actualizado visión en los elementos de trabajo, además de las métricas importantes sobre su repositorio Git, solicitudes de extracción y el contenido del control de versiones incluidas en la versión inicial de la oferta. Para obtener más información acerca de cómo empezar a trabajar, consulte [el paquete de contenido de Visual Studio Online para la página de Ayuda de Power BI](powerbi-content-pack-quickbooks-online.md).

**14 de julio de 2015**

-   Acumatica ERP de nube ofrece un conjunto de aplicaciones de administración empresarial totalmente integrada como finanzas, distribución, CRM y contabilidad de proyectos, con tecnología de una plataforma sólida y flexible. Con Power BI [paquete de contenido de Acumatica](http://blogs.msdn.com/b/powerbi/archive/2015/07/13/analyze-and-explore-your-acumatica-cloud-erp-data-with-power-bi.aspx), puede conectarse rápidamente y obtener información sobre sus datos de la oportunidad de inmediatamente. Este contenido incluye un panel de out-of-box, un conjunto de informes y un conjunto de datos seleccionado para explorar y proporcionar detalles como el total ganó oportunidades por fecha. Leer más [aquí](powerbi-content-pack-acumatica.md). 

-   
            [HDInsight de Azure](http://blogs.msdn.com/b/powerbi/archive/2015/07/14/visualize-big-data-with-power-bi-and-spark-for-azure-hdinsight.aspx) ahora ofrece un servicio Spark completamente administrado. Esta capacidad permite escenarios como análisis de datos interactivos y aprendizaje automático iterativo. Power BI le permite conectarse directamente a los datos de Spark en HDInsight ofrece exploración simple y directo. Leer nuestra [Ayuda doc](powerbi-spark-on-hdinsight-with-direct-connect.md) para obtener más información.

-   
            [Integración de selector de navegación y la aplicación de Office 365](http://blogs.msdn.com/b/powerbi/archive/2015/07/15/new-capabilities-added-to-power-bi.aspx#launcher). Con un solo clic, puede navegar a todas las aplicaciones de Office 365.

-   
            [Especificar una dirección URL personalizada](http://blogs.msdn.com/b/powerbi/archive/2015/07/15/new-capabilities-added-to-power-bi.aspx#url) que los usuarios desplazarse a cuando hagan clic en un mosaico. Ahora tiene la capacidad de controlar exactamente donde los usuarios van: un informe específico, otro panel, un informe de SSRS o un sitio Web externo. 

-   
            [Visibilidad y administración del almacenamiento de información](http://blogs.msdn.com/b/powerbi/archive/2015/07/15/new-capabilities-added-to-power-bi.aspx#storage) consumen en Power BI

-   [Configurar el objeto visual y campos que se muestran en preguntas y respuestas](http://blogs.msdn.com/b/powerbi/archive/2015/07/15/new-capabilities-added-to-power-bi.aspx#visual)

**7 de julio de 2015**

-   ﻿Una de las características más esperada y solicitada ya está disponible en Power BI. A partir de hoy, en Power BI puede [actualizar conjuntos de datos](http://blogs.msdn.com/b/powerbi/archive/2015/07/07/refresh-for-on-premises-sources-is-here.aspx) conectarse a los orígenes locales como SQL Server. Puede actualizar un conjunto de datos que se ha creado desde un archivo de Power BI Designer o un libro de Excel con datos importados en el libro con Power Query o Power Pivot. 

**30 de junio de 2015**

-   Hemos lanzado un nuevo [paquete de contenido de Power BI UserVoice](http://blogs.msdn.com/b/powerbi/archive/2015/07/01/monitor-and-visualize-your-uservoice-data-with-power-bi.aspx) que puede ayudarle a supervisar y visualizar los datos de UserVoice e inmediatamente obtener conocimientos en él con el panel de lista para usar y el informe.

**23 de junio de 2015**

-   Pueden ser archivos de Power BI Desktop [actualiza](http://blogs.msdn.com/b/powerbi/archive/2015/06/22/announcing-refresh-support-for-power-bi-designer-files-in-the-power-bi-service.aspx) (programa actualización & Actualizar ahora) cuando se cargan en el servicio Power BI.

-   Estamos lanzando el mayor cambio visual a Power BI desde diciembre: una experiencia más limpia y sencilla a [obtener datos](http://blogs.msdn.com/b/powerbi/archive/2015/06/23/the-new-get-data-experience.aspx).  Al hacer clic en obtener datos, ahora aparecerá con un conjunto de categorías para elegir una sola pantalla. Esto hará que aún más fáciles de encontrar el contenido que es importante para usted.

-   
            [Almacenamiento de datos de SQL Azure](http://blogs.msdn.com/b/powerbi/archive/2015/06/24/exploring-azure-sql-data-warehouse-with-power-bi.aspx) ofrece escalado elástico y procesamiento masivo en paralelo. Con la public preview limitada anunciada hoy, Power BI le permite conectarse directamente a los datos almacenados en el almacén de datos de SQL Azure ofrece exploración sencilla y dinámica. Después de crear una conexión con el almacén de datos, las consultas se generan en tiempo real y se envían al origen como explorar los datos. Esto elimina la necesidad de crear y cargar un modelo de datos personalizadas y ofrece exploración interactiva de los datos.

**16 de junio de 2015**

-   SweetIQ le permite realizar un seguimiento de los anuncios locales proporcionando ubicación fácilmente y revisar los datos de su ecosistema de búsqueda local. Power BI le permite analizar y supervisar esos datos, ofreciendo [fuera del contenido del cuadro](http://blogs.msdn.com/b/powerbi/archive/2015/06/16/analyze-and-monitor-your-sweetiq-data-with-power-bi.aspx) crea a partir de los datos de SweetIQ. Para obtener más detalles sobre cómo empezar a trabajar, consulte el paquete de contenido de SweetIQ para Power BI [página de Ayuda](powerbi-content-pack-sweetiq.md).

**9 de junio de 2015**

-   Power BI le permite supervisar y explorar esa datos mediante el [MailChimp APIs](http://blogs.msdn.com/b/powerbi/archive/2015/06/09/user-power-bi-to-monitor-and-visualize-your-mailchimp-data.aspx), que ofrece un conjunto de contenido de out-of-box para su análisis. El panel, informes y conjunto de datos seleccionada para el escenario de MailChimp le permiten tener acceso fácilmente a los datos como Top campañas de Total abre por día de la semana. Para obtener más detalles sobre cómo empezar a trabajar, consulte el paquete de contenido de MailChimp para Power BI [documentación](powerbi-content-pack-mailchimp.md).

**2 de junio de 2015**

-   Seguimiento de las estadísticas importantes sobre sus aplicaciones es fácil con Power BI y la [contenido de appFigures](http://blogs.msdn.com/b/powerbi/archive/2015/06/02/explore-and-analyze-your-appfigures-data-with-power-bi.aspx). Para obtener más detalles sobre cómo conectar y empezar a trabajar, consulte el [documentación](powerbi-content-pack-appfigures.md) para contenido de appfigures para Power BI.

**28 de mayo de 2015**

-   Obtener información rápida sobre los datos de cuenta QuickBooks Online mediante nuestra [paquete de contenido](http://blogs.msdn.com/b/powerbi/archive/2015/05/28/get-quick-insights-into-your-quickbooks-online-account-data.aspx). Para obtener más detalles sobre cómo conectar y empezar a trabajar, consulte el paquete de contenido de QuickBooks Online para Power BI [documentación](powerbi-content-pack-quickbooks-online.md).

**19 de mayo de 2015**

-   Con esta actualización, ahora puede conectarse a [Twilio a través de nuestro paquete de contenido](powerbi-content-pack-twilio.md)

-   ¡La API de Power BI tiene nuevas adiciones! Ahora puede [Mostrar todas las tablas](http://docs.powerbi.apiary.io/#reference/datasets/tables-collection/list-all-tables) y [actualizar un esquema de tabla existente](http://docs.powerbi.apiary.io/#reference/datasets/table/update-an-existing-tables-schema)

**13 de mayo de 2015**

-   Con la actualización más reciente de Power BI, puede conectarse a los datos registrados por **auditoría de base de datos de SQL Server** con un conjunto de informes y un panel personalizado.Este paquete de contenido facilita encontrar eventos sospechosos, actividades inusuales y tendencias, basándose en un conjunto de datos que se ha creado para los informes. Obtenga más información en el [entrada de blog](http://blogs.msdn.com/b/powerbi/archive/2015/05/14/monitor-your-azure-sql-database-auditing-activity-with-power-bi.aspx) y [documentación](powerbi-azure-sql-database-auditing-connector.md).

-   Puede conectarse directamente a los datos almacenados en su **base de datos de SQL Azure**. Generamos dinámicamente y enviar las consultas al origen, lo que permite crear informes interactivos directamente a través de la base de datos. Puede leer el [entrada de blog](http://blogs.msdn.com/b/powerbi/archive/2015/05/13/using-power-bi-to-visualize-and-explore-azure-sql-databases.aspx) y [documentación](powerbi-azure-sql-database-with-direct-connect.md) para obtener más información.

**7 de mayo de 2015**

-   Ahora puede usar el **Visual Studio Online** paquete de contenido de Power BI obtener información sobre la git y los proyectos de equipo TFVC. Puede leer nuestra [documentación](powerbi-content-pack-visual-studio-online.md) o [de blog](http://blogs.msdn.com/b/powerbi/archive/2015/05/07/gain-understanding-and-insights-into-projects-in-visual-studio-online-with-power-bi.aspx) para obtener más información.

-   Hemos actualizado nuestro aspecto moderno diseño, un aspecto nuevo y distintivo manteniendo su enfoque en lo que realmente importa: los datos y la información.

**28 de abril de 2015**

-   ﻿Ahora está disponible en Power BI **44 idiomas**. Leer nuestra [de blog](http://blogs.msdn.com/b/powerbi/archive/2015/04/28/power-bi-preview-now-available-in-your-language.aspx) para ver la lista completa.

**23 de abril de 2015**

-   Ahora puede visualizar y explorar su **Microsoft Dynamics Marketing** datos con nuestro paquete de contenido nuevo! Puede leer nuestra [de blog](http://blogs.msdn.com/b/powerbi/archive/2015/04/23/monitor-and-explore-your-microsoft-dynamics-marketing-data-with-power-bi.aspx) y [documentación](powerbi-content-pack-microsoft-dynamics-marketing.md) para obtener más información.﻿

**15 de abril de 2015**

-   Ahora puede visualizar y explorar su **Google Analytics** datos con nuestro paquete de contenido nuevo! Con el paquete de contenido de Google Analytics obtendrá un panel, informe y un conjunto de datos que le permiten obtener información sobre el uso del sitio en los últimos 6 meses. Puede leer [nuestra entrada de blog](http://blogs.msdn.com/b/powerbi/archive/2015/04/15/visualize-and-explore-your-google-analytics-data-with-power-bi.aspx) y [documentación](powerbi-content-pack-google-analytics.md) para obtener más información.

-   Ahora puede **Anclar todas las tarjetas** espera los KPI y las imágenes de preguntas y respuestas que contienen e informes

-   Ahora puede **usar tarjetas de preguntas y respuestas** mediante la frase 'como tarjeta' al final de la consulta

**31 de marzo de 2015**

-   
            **GitHub **paneles tener nuevos elementos visuales que se centran en comunidad creando, cálculos mejorados y mejorado diseño

-   
            **SendGrid **paneles tienen nuevos elementos visuales y un nuevo diseño que le ayudarán a encontrar una mejor percepción

-   Ahora puede usar** treemaps en preguntas y respuestas** mediante la frase 'como treemap' al final de la consulta

-   Ahora puede **Anclar treemaps** de preguntas y respuestas y los informes 

-   Muchas correcciones de errores.

**25 de febrero de 2015**

-   Correcciones de errores y mejoras en la experiencia del usuario y la confiabilidad. 

**26 de enero de 2015**

-   Confiabilidad y facilidad de uso del servicio se ha mejorado a través de varias correcciones de errores. ﻿

**﻿11 de diciembre de 2014**

-   Se ha mejorado la confiabilidad de la actualización con OneDrive.  Algunas situaciones donde los libros no estaban actualizando desde OneDrive se han resueltos.

## Consulte también  
[Introducción a Power BI](powerbi-service-get-started.md)  

¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)

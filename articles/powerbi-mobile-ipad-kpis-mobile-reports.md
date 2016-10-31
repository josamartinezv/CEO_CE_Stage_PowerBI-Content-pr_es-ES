<properties 
   pageTitle="Ver informes de Reporting Services móviles y los KPI en la aplicación de iPad"
   description="La aplicación de iPad (Power BI para iOS) ofrece acceso móvil directo y táctil a la información de negocios importante en local."
   services="powerbi" 
   documentationCenter="" 
   authors="maggiesMSFT" 
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
   ms.date="10/11/2016"
   ms.author="maggies"/>

# <a name="view-reporting-services-mobile-reports-and-kpis-in-the-ipad-app-(power-bi-for-ios)"></a>Ver informes de Reporting Services móviles y los KPI en la aplicación de iPad (Power BI para iOS)  

La aplicación de iPad para Microsoft Power BI para iOS ofrece acceso móvil directo y táctil a la información de negocios importante en local. 

![](media/powerbi-mobile-ipad-kpis-mobile-reports/power-bi-ipad-ssrs-home.png)

Lo primero es lo primero:

-  Crear [móviles informes de Reporting Services](https://msdn.microsoft.com/library/mt652547.aspx) con el publicador de SQL Server Mobile informes y publicarlos en la [portal web de Reporting Services](https://msdn.microsoft.com/library/mt637133.aspx). 
-  Crear [KPI en el portal web de Reporting Services](https://msdn.microsoft.com/library/mt683632.aspx). Organizarlos en carpetas y marcar los favoritos para que pueda encontrar fácilmente. 

A continuación, en la aplicación de iPad para Power BI, ver los informes móviles y KPI, organizados en carpetas o recopilados como favoritos. 

> [AZURE.NOTE]  Debe ejecutar al menos el iPad iOS 8.0. 

## <a name="explore-samples-without-an-ssrs-server"></a>Explorar ejemplos sin un servidor SSRS

Incluso si no tiene acceso a un portal web de Reporting Services, todavía puede explorar las características de informes de Reporting Services móviles. 

-  Puntee en el botón de navegación global ![](media/powerbi-mobile-ipad-kpis-mobile-reports/power-bi-iphone-global-nav-button.png) en la esquina superior izquierda, desplácese hacia abajo y pulsa **ejemplos de Reporting Services**.

    ![](media/powerbi-mobile-ipad-kpis-mobile-reports/power-bi-ipad-ssrs-samples.png)


Examinar los ejemplos para interactuar con informes móviles y KPI.

## <a name="connect-to-a-server-to-view-reporting-services-mobile-reports"></a>Conectarse a un servidor para ver los informes de Reporting Services móviles 

1.  En el iPad, abra la aplicación Power BI.
  
2.  Puntee en el botón de navegación global ![](media/powerbi-mobile-ipad-kpis-mobile-reports/power-bi-iphone-global-nav-button.png) en la esquina superior izquierda y puntee **Conectar servidor**.

    ![](media/powerbi-mobile-ipad-kpis-mobile-reports/power-bi-ipad-ssrs-connect-server.png)

4. Rellene la dirección del servidor y su nombre de usuario y contraseña.

    >
            **Nota**: incluir **http** o **https** delante de la cadena de conexión. Por ejemplo, http://*nombreDeServidor*.com/reports.

    (Opcional) Puntee en **Opciones avanzadas** para asignar un nombre de servidor.

5.  Puntee en **Conectar**. 

6.  Ahora verá que el servidor en la barra de navegación izquierda.

    ![](media/powerbi-mobile-ipad-kpis-mobile-reports/power-bi-ipad-ssrs-menu.png)

>
            **Sugerencia**: pulse el botón de navegación global ![](media/powerbi-mobile-ipad-kpis-mobile-reports/power-bi-iphone-global-nav-button.png) en cualquier momento a vaya entre los informes de Reporting Services móviles y los paneles en el servicio Power BI. 

## <a name="view-reporting-services-kpis-and-mobile-reports-in-the-power-bi-app"></a>KPI de vista Reporting Services e informes móviles en la aplicación Power BI

Reporting Services KPI e informes móviles se muestran en las mismas carpetas estuvieran en el portal web de Reporting Services. 

- Puntee en un KPI para verlo en modo de enfoque.

    ![](media/powerbi-mobile-ipad-kpis-mobile-reports/PBI_iPad_SSMRP_Tile.png)

- Puntee en un informe móvil para abrir e interactuar con él en la aplicación de Power BI.

    ![](media/powerbi-mobile-ipad-kpis-mobile-reports/PBI_iPad_SSMRP_MobRpt.png)

## <a name="view-your-favorite-kpis-and-reports"></a>Ver los KPI y los informes favoritos

Puede marcar KPI e informes móviles como favoritos en el portal web de Reporting Services y, a continuación, verlos en una carpeta adecuada en su iPad, junto con los informes y paneles de Power BI favoritos.

-  Puntee en **favoritos**.

    ![](media/powerbi-mobile-ipad-kpis-mobile-reports/power-bi-ipad-favorites-menu.png)
   
    Son los favoritos desde el portal web en esta página.

    ![](media/powerbi-mobile-ipad-kpis-mobile-reports/power-bi-ipad-favorites-page.png)

## <a name="remove-a-connection-to-a-report-server"></a>Quitar una conexión a un servidor de informes

Solo puede conectar a un servidor de informes a la vez desde su aplicación de iPad. Si desea conectarse a un servidor diferente, debe desconectar de la actual.

1. En la parte inferior de la barra de navegación izquierdo, puntee **configuración**.
2. Puntee en el nombre del servidor que no desea estar conectado a.
3. Puntee en **Quitar conexión**.


## <a name="create-reporting-services-mobile-reports-and-kpis"></a>Crear informes de Reporting Services móviles y KPI

No se crean informes móviles y Reporting Services KPI en la aplicación móvil de Power BI. Se crea en el publicador de SQL Server Mobile informes y un portal web de SQL Server 2016 Reporting Services.

- 
            [Crear sus propios informes de Reporting Services móviles](https://msdn.microsoft.com/library/mt652547.aspx), y publíquelos en el portal web de Reporting Services.
- Crear [KPI en el portal web de Reporting Services](https://msdn.microsoft.com/library/mt683632.aspx)


### <a name="see-also"></a>Consulte también  
- 
            [Introducción a la aplicación de iPad para Power BI](powerbi-mobile-ipad-app-get-started.md)  
- 
            [Introducción a Power BI](powerbi-service-get-started.md)  
- ¿Tiene preguntas? 
            [Pruebe a formular a la Comunidad de Power BI](http://community.powerbi.com/)
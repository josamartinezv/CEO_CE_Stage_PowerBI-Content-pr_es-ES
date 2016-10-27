<properties
   pageTitle="Tutorial: ArcGIS in Power BI"
   description="Tutorial: ArcGIS in Power BI"
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   featuredVideoId=""
   qualityFocus="no"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="09/26/2016"
   ms.author="mihart"/>

# Tutorial: ArcGIS maps in Power BI (Preview)

ArcGIS Maps for Power BI (Preview) by <bpt id="p1">[</bpt>Esri<ept id="p1">](https://www.Esri.com/powerbi)</ept> geo-enables Power BI. ArcGIS Maps offer enhanced mapping capability, demographic data, and even more compelling map visualizations so you can tell your best story.

## User consent
ArcGIS Maps for Power BI is provided by <bpt id="p1">[</bpt>Esri<ept id="p1">](https://www.esri.com)</ept>. Your use of ArcGIS Maps for Power BI is subject by Esri's terms and privacy policy. Power BI users wishing to use the ArcGIS Maps for Power BI visual, need to accept the consent dialog.

**Recursos**

[Términos](https://go.microsoft.com/fwlink/?LinkID=826322)

[Directiva de directiva](https://go.microsoft.com/fwlink/?LinkID=826323)

[ArcGIS Maps for Power BI product page](https://www.esri.com/powerbi)

## Enable the ArcGIS map preview

The ArcGIS map visual is in preview, and must be enabled in Power BI. This tutorial uses the <bpt id="p1">[</bpt>Retail Analysis sample<ept id="p1">](powerbi-sample-retail-analysis-take-a-tour.md)</ept>. To enabled <bpt id="p1">**</bpt>ArcGIS Maps for Power BI<ept id="p1">**</ept>:

1. Select <bpt id="p1">**</bpt>File &gt; Options and Settings &gt; Options &gt; Preview Features<ept id="p1">**</ept>.

2. Select the <bpt id="p1">**</bpt>ArcGIS Maps for Power BI<ept id="p1">**</ept> checkbox. You'll need to restart Power BI after you make the selection.

    ![](media/powerbi-service-tutorial-arcgis/power-bi-preview-dialog2.png)

3. Open a report in Editing view and select the ArcGIS Maps for Power BI icon from the Visualizations pane.

    ![](media/powerbi-service-tutorial-arcgis/power-bi-viz-pane2.png)

4. Power BI displays the user consent dialog, select <bpt id="p1">**</bpt>OK<ept id="p1">**</ept> to continue.

    ![](media/powerbi-service-tutorial-arcgis/power-bi-esri-consent2.png)

5. Power BI adds an empty ArcGIS map template to the report canvas.

    ![](media/powerbi-service-tutorial-arcgis/power-bi-esri-placeholder2.png)

## Create an AcrGIS map visual
Take the following steps to create a <bpt id="p1">**</bpt>ArcGIS Maps for Power BI<ept id="p1">**</ept>.

1. From the <bpt id="p1">**</bpt>Fields<ept id="p1">**</ept> pane, drag a data field to the <bpt id="p2">**</bpt>Location<ept id="p2">**</ept> or <bpt id="p3">**</bpt>Latitude<ept id="p3">**</ept> and <bpt id="p4">**</bpt>Longitude<ept id="p4">**</ept> buckets.

    >[AZURE.NOTE] Power BI will automatically detect if the fields you've selected are best viewed as a shape or a point on a map. You can adjust the default in the settings (see below).

    ![](media/powerbi-service-tutorial-arcgis/power-bi-fields-pane2.png)

2.  From the <bpt id="p1">**</bpt>Fields<ept id="p1">**</ept> pane, drag a measure to the <bpt id="p2">**</bpt>Size<ept id="p2">**</ept> or <bpt id="p3">**</bpt>Color<ept id="p3">**</ept> buckets to adjust how the data is shown.
   ![](media/powerbi-service-tutorial-arcgis/power-bi-esri-point-map-size2.png)


## Settings and formatting for AcrGIS maps
To access <bpt id="p1">**</bpt>ArcGIS Maps for Power BI<ept id="p1">**</ept> formatting features:

1. Select the In-Focus edit mode icon within the visual.
   ![](media/powerbi-service-tutorial-arcgis/power-bi-edit-mode-icon2.png)

2. Access additional features through the ribbon contained within the visual. Each feature, when selected, opens a task pane that provides detailed options.
   ![](media/powerbi-service-tutorial-arcgis/power-bi-ribbon-options2.png)

   >  [AZURE.NOTE]  For more information about the settings and features, see <bpt id="p1">**</bpt>Detailed documentation<ept id="p1">**</ept> below.

3. To return to the report, select <bpt id="p1">**</bpt>Back to Report<ept id="p1">**</ept> from the top-left corner of your report canvas.

## Detailed documentation
<bpt id="p1">**</bpt>Esri<ept id="p1">**</ept> provides <bpt id="p2">[</bpt>comprehensive documentation<ept id="p2">](https://go.microsoft.com/fwlink/?LinkID=828772)</ept> on the feature set of <bpt id="p3">**</bpt>ArcGIS Maps for Power BI<ept id="p3">**</ept>.

### Features overview

#### Base Maps
Four base maps are provided: Dark Gray Canvas, Light Gray Canvas, OpenStreetMap, and Streets.  Streets is ArcGIS's standard base map.

To apply a base map select it in the task pane.

![](media/powerbi-service-tutorial-arcgis/power-bi-esri-base-maps2.png)

#### Location type
ArgGIS Maps for Power BI automatically detects the best way to show data on the map. It selects from Points or Boundaries. The Location type options allow you to fine tune these selections.

![](media/powerbi-service-tutorial-arcgis/power-bi-esri-location-types2.png)

<bpt id="p1">**</bpt>Boundaries<ept id="p1">**</ept> will only work if your data contains standard geographic values. Esri automatically figures out the shape to show on the map.    

#### Map theme
Four map themes are provided. Location only and Size themes are automatically chosen based on the fields you bind to the location and size buckets in the Fields pane. We're currently using <bpt id="p1">**</bpt>Size<ept id="p1">**</ept>, so let's change to <bpt id="p2">**</bpt>Heat map<ept id="p2">**</ept>.  

![](media/powerbi-service-tutorial-arcgis/power-bi-esri-map-theme2.png)

<table>
<tr><th>Theme</th><th>Descripción</th>
<tr>
<td>Location Only</td>
<td>Plots data points or filled boundaries on the map based on the settings in Location Type.</td>
</tr>
<tr>
<td>Heat Map</td>
<td>Plots an intensity plot of data on the map.</td>
</tr>
<tr>
<td>Tamaño</td>
<td>Plots data points on the map based that are sized based on the value in the size bucket in the fields pane.</td>
</tr>
<tr>
<td>Agrupación en clústeres</td>
<td>Plot the count of data points in regions on the map. </td>
</tr>
</table>

#### Symbol style
Symbol styles enable you to fine tune how data is presented on the map. Symbol styles are context sensitive based on the selected Location type and Map theme.

![](media/powerbi-service-tutorial-arcgis/power-bi-esri-symbol-style2.png)

### Reference Layer
####  Reference layer - Demographics
ArcGIS Maps for Power BI provides a selection of demographic layers that help contextualize data from Power BI.

1. Select the <bpt id="p1">**</bpt>Reference layer<ept id="p1">**</ept> tab and choose <bpt id="p2">**</bpt>Demographics<ept id="p2">**</ept>.

2. Each layer listed has a checkbox. Add a checkmark to add that layer to the map.  In this example we've added average household income.
   ![](media/powerbi-service-tutorial-arcgis/power-bi-esri-reference-layer-demographics1.png)

2. Each layer is interactive as well. Just as you can hover over a bubble to see the details, you can click a shaded area on the map to see the details.
   ![](media/powerbi-service-tutorial-arcgis/power-bi-esri-reference-layer-demographics2.png)


#### Reference layer - ArcGIS
ArcGIS Online provides the ability for organizations to publish public web maps. Additionally, Esri provides a curated set of web maps through Living Atlas. In the ArcGIS tab, you can search all public web maps or Living Atlas maps, and add them to the map as reference layers.

1. Select the <bpt id="p1">**</bpt>Reference layer<ept id="p1">**</ept> tab and choose <bpt id="p2">**</bpt>ArcGIS<ept id="p2">**</ept>.

2. Enter search terms and then select a map layer. In this example we've chosen USA Congressional districts.

    ![](media/powerbi-service-tutorial-arcgis/power-bi-esri-demographics-esri2.png)   
3. To see the details, select a shaded area to open the <bpt id="p1">_</bpt>Select from reference layer<ept id="p1">_</ept>: Use the reference layer selection tool to selection boundaries or objects on the reference layer.

## Selecting Data points
ArcGIS Maps for Power BI allows three selection modes.

Change the selection mode using switch:

![](media/powerbi-service-tutorial-arcgis/power-bi-esri-selection-tools2.png)

![](media/powerbi-service-tutorial-arcgis/power-bi-esri-selection-single2.png) Select individual data points.

![](media/powerbi-service-tutorial-arcgis/power-bi-esri-selection-marquee2.png) Draws a rectangle on the map and selects the contained data points.

![](media/powerbi-service-tutorial-arcgis/power-bi-esri-selection-reference-layer2.png) Allows boundaries or polygons within reference layers to be used to select contained data points.

<bpt id="p1">**</bpt>Note:<ept id="p1">**</ept> a maximum of 250 data points can be selected at a time.

## Getting help
<bpt id="p1">**</bpt>Esri<ept id="p1">**</ept> provides <bpt id="p2">[</bpt>comprehensive documentation<ept id="p2">](https://go.microsoft.com/fwlink/?LinkID=828772)</ept> on the feature set of <bpt id="p3">**</bpt>ArcGIS Maps for Power BI<ept id="p3">**</ept>.

You can ask questions and find answers on the Power BI <bpt id="p1">[</bpt>community thread related to <bpt id="p2">**</bpt>ArcGIS Maps for Power BI<ept id="p2">**</ept><ept id="p1">](https://go.microsoft.com/fwlink/?LinkID=828771)</ept> to find the latest information or to report issues.

If you have a suggestion for an improvement, please submit them to <bpt id="p1">[</bpt>Power BI's ideas list<ept id="p1">](https://ideas.powerbi.com)</ept>.

## Managing use of ArcGIS Maps for Power BI within your organization

Power BI provides the ability for users, tenant administrators, and IT administrators to manage whether to use ArcGIS Maps for Power BI.

<bpt id="p1">**</bpt>User options<ept id="p1">**</ept> In Power BI Desktop, users can stop using ArcGIS Maps for Power BI by disabling it on the security tab in options. When disabled, ArcGIS Maps will not load by default.

![](media/powerbi-service-tutorial-arcgis/power-bi-desktop-security-dialog2.png)

In Power BI service, users can stop using ArcGIS Maps for Power BI by disabling it on the ArcGIS Maps for Power BI (Preview) tab in user Settings. When disabled, ArcGIS Maps will not load by default.

![](media/powerbi-service-tutorial-arcgis/power-bi-service-user-settings2.png)

<bpt id="p1">**</bpt>Tenant admin options<ept id="p1">**</ept> In PowerBI.com, tenant administrators can prevent all tenant users from using ArcGIS Maps for Power BI by disabling. When this happens, Power BI will no longer see the ArcGIS Maps for Power BI icon in the visualizations pane.

![](media/powerbi-service-tutorial-arcgis/power-bi-arcgis-admin-portal2.png)

<bpt id="p1">**</bpt>IT Administrator options<ept id="p1">**</ept> Power BI Desktop supports using <bpt id="p2">**</bpt>Group Policy<ept id="p2">**</ept> to disable ArcGIS Maps for Power BI across an organization's deployed computers.

<table>
<tr><th>Atributo</th><th>Valor</th>
</tr>
<tr>
<td>key</td>
<td>Software\Policies\Microsoft\Power BI Desktop\</td>
</tr>
<tr>
<td>valueName</td>
<td>EnableArcGISMaps</td>
</tr>
</table>

A value of 1 (decimal) enables ArcGIS Maps for Power BI.

A value of 0 (decimal) disable ArcGIS Maps for Power BI.

You can use the provided <bpt id="p1">**</bpt>Group Policy<ept id="p1">**</ept> templates to quickly add the required configuration to your <bpt id="p2">**</bpt>Group Policy<ept id="p2">**</ept>.

**Plantilla**

[PowerBIEsri.adml](./groupPolicyTemplates/PowerBIEsri.adml)

[PowerBIEsri.admx](./groupPolicyTemplates/PowerBIEsri.admx)

## Preguntas frecuentes
**Is there any charge for using ArcGIS Maps for Power BI?**

The ArcGIS Map for Power BI (Preview) is available to all Power BI users at no additional cost. It is a component provided by <bpt id="p1">**</bpt>Esri<ept id="p1">**</ept> and your use is subject to the terms and privacy policy provided by <bpt id="p2">**</bpt>Esri<ept id="p2">**</ept> as noted earlier in this article.

**Does ArcGIS Maps for Power BI support Esri Shapefiles?**

ArcGIS Maps for Power BI automatically detects standard boundaries like countries/regions, states/provinces, and zip/postal codes. If you need to provide your own shapes you can do so using the <bpt id="p1">[</bpt>Shape Maps for Power BI Desktop (Preview)<ept id="p1">](powerbi-desktop-shape-map.md)</ept>.

**Can I connect to my ArcGIS Online account from Power BI?**

Todavía no. <bpt id="p1">[</bpt>Vote for this idea<ept id="p1">](https://ideas.powerbi.com/forums/265200-power-bi-ideas/suggestions/9154765-arcgis-geodatabases )</ept> and we'll send you an email when we start working on this feature.  

More questions? [Try the Power BI Community](http://community.powerbi.com/)

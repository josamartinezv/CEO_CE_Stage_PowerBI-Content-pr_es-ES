<properties 
   pageTitle="Create reports optimized for the Power BI phone apps"
   description="Learn how to optimize report pages in Power BI Desktop for the Power BI phone apps."
   services="powerbi" 
   documentationCenter="" 
   authors="maggiesMSFT" 
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
   ms.date="09/27/2016"
   ms.author="maggies"/>

# Create reports optimized for the Power BI phone apps

When you <bpt id="p1">[</bpt>create a report in Power BI Desktop<ept id="p1">](powerbi-desktop-report-view.md)</ept>, you can improve the experience of using it on phones by creating a version of the report specifically for the phone. You adapt your report for the phone by rearranging and resizing visuals, maybe not including all of them, for an optimal experience.  

![](media/powerbi-desktop-create-phone-report/07-power-bi-phone-report-portrait.png)

## Lay out a report page for the phone in Power BI Desktop

After you <bpt id="p1">[</bpt>create a report in Power BI Desktop<ept id="p1">](powerbi-desktop-report-view.md)</ept>, you can optimize it for phones.

1. In Power BI Desktop, select <bpt id="p1">**</bpt>Report View<ept id="p1">**</ept> in the left navigation bar.

    ![](media/powerbi-desktop-create-phone-report/PBI_ReportViewInPBIDesigner_ChangeView.png)

2. On the <bpt id="p1">**</bpt>Home<ept id="p1">**</ept> tab, select <bpt id="p2">**</bpt>Change Layout<ept id="p2">**</ept>.  

    ![](media/powerbi-desktop-create-phone-report/01_change_form_factor.gif)

    You see a blank phone canvas. All of the visuals on the original report page are listed in the Visualizations pane on the right.
 
2. To add a visual to the phone layout, drag it from the Visualizations pane to the phone canvas.

    Phone reports use a grid layout. As you drag visuals to the mobile canvas, they snap to that grid.

    ![](media/powerbi-desktop-create-phone-report/02_Dragging_and_droping_a_vis.gif)

    You can add some or all the master report page visuals to the phone report page. You can add each visual only once.

3.  You can resize your visuals on the grid, as you would for tiles on dashboards and mobile dashboards.

    > [AZURE.NOTE] The phone report grid scales across phones of different sizes, so your report will look as good on small- and on large-screen phones.

    ![](media/powerbi-desktop-create-phone-report/03_Resizing_a_viz_to_grid.gif)

## Notes about creating phone report layouts
- For reports with multiple pages, you can optimize all the pages or only a few. 
- On a phone, you move between pages by swiping from the side or tapping the page menu.
- You can’t modify formatting settings for just the phone. Formatting is consistent between master and mobile layouts. For example, font sizes will be the same.
- To change a visual, such as changing its formatting, dataset, filters, or any other attribute, return to the regular report authoring mode.

    > <bpt id="p1">**</bpt>Tip<ept id="p1">**</ept>: By default, Power BI provides titles and page names for phone reports in the mobile app. If you’ve created text visuals for titles and page names in your report, consider not adding them to your phone reports.     

## Remove a visual from the phone layout

-  To remove a visual, click the X in the top-right  of the visual on the phone canvas, or select it and press <bpt id="p1">**</bpt>Delete<ept id="p1">**</ept>.

    > [AZURE.NOTE] Removing a visual here only removes it from the Mobile canvas, the visual and the original report will not be effected.
    
    ![](media/powerbi-desktop-create-phone-report/05_Removing_a_vis.gif)

## Enhance slicers to to work well in phone reports
Slicers offer on-canvas filtering of report data. When designing slicers in the regular report authoring mode, you can modify some slicer settings to make them more usable in phone reports:

- Decide if report readers can select only one or more than one item.
- Make the slicer vertical or horizontal. 
- Put a box around the slicer to make the report easier to scan.

Read more about <bpt id="p1">[</bpt>creating slicers in the Power BI service<ept id="p1">](powerbi-learning-3-4-create-slicers.md)</ept>.

## Publish a phone report
- To publish the phone version of a report, you <bpt id="p1">[</bpt>publish the main report from Power BI Desktop to the Power BI service<ept id="p1">](powerbi-desktop-upload-desktop-files.md)</ept>, and the phone version publishes at the same time.

    Read more about <bpt id="p1">[</bpt>sharing and permissions in Power BI<ept id="p1">](powerbi-service-how-should-i-share-my-dashboard.md)</ept>.

## View optimized and non-optimized reports on a phone 

In the mobile apps on phones, Power BI automatically detects optimized and non-optimized phone reports. If a phone-optimized report exists, the Power BI phone app automatically opens the report in phone report mode.

If a phone-optimized report doesn’t exist, the report will open in the non-optimized, landscape view.  

When in a phone report, changing the phone’s orientation to landscape will open the report in the non-optimized view with the original report layout, whether you optimize the report or not.

If you only optimize some pages, readers will see a message in portrait view, indicating the report is available in landscape.

![](media/powerbi-desktop-create-phone-report/06-power-bi-phone-report-page-not-optimized.png)

Report readers can turn their phones sideways to see the page in landscape mode.

## Interact with optimized phone reports on a phone

You can scroll in a phone report, cross-highlight and select visuals, and open visuals in focus mode. Read more about what it's like to <bpt id="p1">[</bpt>interact with Power BI reports optimized for your phone<ept id="p1">](powerbi-mobile-view-phone-report.md)</ept>.

## How visuals scale in a phone report
Power BI phone reports use a concept called “virtual pixels” to ensure an optimized experience across various devices, screen sizes, and form factors.  

When creating a phone report, visuals are aligned to a grid. In the grid, some aspects such as square size are relative to the size of the screen, and other aspects such as side spacing are constant.
This allows the grid to scale correctly across different screen sizes.

For example, the size of a grid “square” on an iPhone SE will be ~xx pixels. The same square on an iPhone 6s Plus will be ~YY pixels. Thus, the phone report you create will scale well on all modern phones.    

### Consulte también
- [Create a phone view of a dashboard in Power BI](powerbi-service-create-dashboard-phone-view.md)
- [View Power BI reports optimized for your phone](powerbi-mobile-view-phone-report.md)
- More questions? [Try asking the Power BI Community](http://community.powerbi.com/)

<properties
   pageTitle="Publish to web from Power BI"
   description="With Power BI Publish to web, you can easily embed interactive Power BI visualizations online, such as in blog posts, websites, through emails or social media, on any device."
   services="powerbi"
   documentationCenter=""
   authors="guyinacube"
   manager="ericre"
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
   ms.date="10/10/2016"
   ms.author="asaxton"/>

# Publish to web from Power BI

With Power BI <bpt id="p1">**</bpt>Publish to web<ept id="p1">**</ept>, you can easily embed interactive Power BI visualizations online, such as in blog posts, websites, through emails or social media, on any device.

You can also easily edit, update, refresh or un-share your published visuals.

> [AZURE.WARNING] When you use <bpt id="p1">**</bpt>Publish to web<ept id="p1">**</ept>, the report or visual you publish can be viewed by anyone on the Internet. There is no authentication used when viewing these reports. Only use Publish to web with reports and data that the anyone on the Internet (unauthenticated members of the public) should be able to see. Before publishing this report, ensure you have the right to share the data and visualizations publicly. Do not publish confidential or proprietary information. If in doubt, check your organization's policies before publishing.

## How to use Publish to Web

<bpt id="p1">**</bpt>Publish to web<ept id="p1">**</ept> is available on reports in your personal or group workspaces that you can edit.  You cannot use Publish to web with reports that were shared with you, or reports that rely on row level security to secure the data. See the <bpt id="p1">**</bpt>Limitations<ept id="p1">**</ept> section below for a complete list of cases where Publish to web is not supported. Please review the <bpt id="p1">**</bpt>Warning<ept id="p1">**</ept> earlier in this article before using Publish to web.

You can watch how this feature works in the following <bpt id="p1">*</bpt>short video<ept id="p1">*</ept>. Then, follow the steps below to try it yourself.


<iframe width="560" height="315" src="https://www.youtube.com/embed/UF9QtqE7s4Y" frameborder="0" allowfullscreen></iframe>


The following steps describe how to use <bpt id="p1">**</bpt>Publish to web<ept id="p1">**</ept>.


1.  On a report in your workspace that you can edit, select <bpt id="p1">**</bpt>File  &gt; Publish to web<ept id="p1">**</ept>.

    ![](media/powerbi-service-publish-to-web/Publish_To_Web1.png)

2.  Review the content on the dialog, and select <bpt id="p1">**</bpt>Create embed code<ept id="p1">**</ept> as shown in the following dialog.

    ![](media/powerbi-service-publish-to-web/Publish_To_Web2_GA.PNG)

3.  Review the warning, shown in the following dialog, and confirm that the data is okay to embed in a public website. If so, select <bpt id="p1">**</bpt>Publish<ept id="p1">**</ept>.

    ![](media/powerbi-service-publish-to-web/Publish_To_Web3_GA.PNG)

4.  A dialog appears that provides a link that can be sent in email, embedded in code (such as an iFrame), or that you can paste directly into your web page or blog.

    ![](media/powerbi-service-publish-to-web/Publish_To_Web4.png)

5.  If you’ve previously created an embed code for the report, the embed code quickly appears. You can only create one embed code for each report.

    ![](media/powerbi-service-publish-to-web/Publish_To_Web5.png)


## Tips and Tricks for View modes

When you embed content within a blog post, you typically need to fit it within a specific size of the screen.  You can also adjust the height and the width in the iFrame tag as needed, but you may also need to ensure your report fits within the given area of the iFrame, so you also need to set an appropriate View Mode when editing the report.

The following table provides guidance about the View Mode, and how it will appear when embedded.


|View Mode|How it looks when embedded|
|---|---|
|![](media/powerbi-service-publish-to-web/Publish_To_Web6b.png)| <bpt id="p1">**</bpt>Fit to page<ept id="p1">**</ept> will respect the page height and width of your report. If you set your page to 'Dynamic' ratios like 16:9 or 4:3 your content will scale to fit within the iFrame you provided. When embedded in an iFrame, using <bpt id="p1">**</bpt>Fit to page<ept id="p1">**</ept> can result in <bpt id="p2">**</bpt>letterboxing<ept id="p2">**</ept>, where a gray background is shown in areas of the iFrame after the content as scaled to fit within the iFrame. To minimize letterboxing, set your iFrame height/width appropriately.|
|![](media/powerbi-service-publish-to-web/Publish_To_Web6d.png)| <bpt id="p1">**</bpt>Actual size<ept id="p1">**</ept> will ensure the report preserves its size as set on the report page. This can result in scrollbars being present in your iFrame. Set the iFrame height and width to avoid the scrollbars. |
|![](media/powerbi-service-publish-to-web/Publish_To_Web6c.png)| <bpt id="p1">**</bpt>Fit to width<ept id="p1">**</ept> ensures the content fits within the horizontal area for your iFrame. A border will still be shown, but the content will scale to use all the horizontal space available.  |

## Tips and tricks for iFrame height and width

The embed code you receive after you Publish to web will look like the following:

![](media/powerbi-service-publish-to-web/Publish_To_Web7.png)

You can edit the width and height manually to ensure it is precisely how you want it to fit onto the page into which you're embedding it.

To achieve a more perfect fit, you can try adding 56 pixels to the height dimension of the iFrame. This accomodates the current size of the bottom bar. If your report page uses the Dynamic size, the table below provides some sizes you can use to achieve a fit without letterboxing.

|Ratio|Tamaño|Dimension (Width x Height)|
|---|---|---|
|16:9|Pequeña|640 x 416 px|
|16:9|Mediana|800 x 506 px|
|16:9|Grande|960 x 596 px|
|4:3|Pequeña|640 x 536 px|
|4:3|Mediana|800 x 656 px|
|4:3|Grande|960 x 776 px|


## Managing embed codes

Once you create a <bpt id="p1">**</bpt>Publish to web<ept id="p1">**</ept> embed code, you can manage the codes you create from the <bpt id="p2">**</bpt>Settings<ept id="p2">**</ept> menu of the Power BI service. Managing embed codes includes the ability to remove the destination visual or report for a code (rendering the embed code unusable), or getting the embed code again.

1.  To manage your <bpt id="p1">**</bpt>Publish to web<ept id="p1">**</ept> embed codes, open the <bpt id="p2">**</bpt>Settings<ept id="p2">**</ept> gear and select <bpt id="p3">**</bpt>Manage embed codes<ept id="p3">**</ept>.

    ![](media/powerbi-service-publish-to-web/Publish_To_Web8.png)

2.  The list of embed codes you’ve created appears, as shown in the following image.

    ![](media/powerbi-service-publish-to-web/Publish_To_Web9.png)

3.  For each <bpt id="p1">**</bpt>Publish to web<ept id="p1">**</ept> embed code in the list, you can either retrieve the embed code, or delete the embed code and thus make any links to that report or visual no longer work.

    ![](media/powerbi-service-publish-to-web/Publish_To_Web10.png)

4.  If you select <bpt id="p1">**</bpt>Delete<ept id="p1">**</ept>, you’re asked if you’re sure you want to delete the embed code.

    ![](media/powerbi-service-publish-to-web/Publish_To_Web11.png)


## Updates to reports, and data refresh

After you create your <bpt id="p1">**</bpt>Publish to web<ept id="p1">**</ept> embed code and share it, the report is updated with any changes you make. However, it’s important to know that it can take a while for update to be visible to your users. Updates to a report or visual take approximately one hour to be reflected in Publish to web embed codes.

When you initially use <bpt id="p1">**</bpt>Publish to web<ept id="p1">**</ept> to get an embed code, the embed code link is immediately active and can be viewed by anyone who opens the link.  After the initial Publish to web action, subsequent updates to reports or visuals to which a Publish to web link points can take approximately one hour to be visible to your users.

To learn more, see the <bpt id="p1">**</bpt>How it works<ept id="p1">**</ept> section later in this article. If you need your updates to be immediately available, you can delete the embed code and create a new one.

## Data refresh

Data refreshes are automatically reflected in your embedded report or visual. It can take approximately 1 hour for refreshed data to be visible from embed codes. You can disable automatic refresh by selecting <bpt id="p1">**</bpt>do not refresh<ept id="p1">**</ept> on the schedule for the dataset used by the report.  

## Custom visuals

Custom visuals are supported in <bpt id="p1">**</bpt>Publish to web<ept id="p1">**</ept>. When you use Publish to web, users with whom you share your published visual do not need to enable custom visuals to view the report.

## Limitaciones

<bpt id="p1">**</bpt>Publish to web<ept id="p1">**</ept> is supported for the vast majority of data sources and reports in the Power BI service, however, the following are not currently supported or available with Publish to web:


1.  Reports using real-time data sources.

2.  Reports using row level security.

3.  Reports using Analysis Services Tablular hosted on premises.

4.  Reports shared to you directly or through an organizational content pack.

5.  Reports in a group in which you are not an edit member.

6.  "R" Visuals are not currently supported in Publish to web reports.


## Understanding the embed code status column

When viewing the <bpt id="p1">**</bpt>Manage embed codes<ept id="p1">**</ept> page for your <bpt id="p2">**</bpt>Publish to web<ept id="p2">**</ept> embed codes, a status column is provided. Embed codes are active by default, but you may encounter any of the states listed below.  

|Estado|Descripción|
|---|---|
|**Activo**|The report is available for Internet users to view and interact with.|
|**Bloqueado**|The content of the report violates the <bpt id="p1">[</bpt>Power BI Terms of Service<ept id="p1">](https://powerbi.microsoft.com/terms-of-service)</ept>. It has been blocked by Microsoft. Contact support if you believe the content was blocked in error.|
|**No compatible**|The report's data set is using row level security, or another unsupported configuration. See the <bpt id="p1">**</bpt>Limitations<ept id="p1">**</ept> section for a complete list.|


## How to report a concern with Publish to web content

To report a concern related to <bpt id="p1">**</bpt>Publish to web<ept id="p1">**</ept> content embedded in a website or blog, use the <bpt id="p2">**</bpt>Flag<ept id="p2">**</ept> icon in the bottom bar, shown in the following image. You’ll be asked to send an email to Microsoft explaining the concern. Microsoft will evaluate the content based on the Power BI Terms of Service, and take appropriate action.

To report a concern, select the <bpt id="p1">**</bpt>flag<ept id="p1">**</ept> icon in the bottom bar of the Publish to web report you see.

![](media/powerbi-service-publish-to-web/Publish_To_Web12_GA.PNG)

## Licensing and Pricing

You need to be a Microsoft Power BI user to use <bpt id="p1">**</bpt>Publish to web<ept id="p1">**</ept>. The consumers of your report (the readers, viewers) do not need to be Power BI users.

## How it works (technical details)

When you create an embed code using <bpt id="p1">**</bpt>Publish to web<ept id="p1">**</ept>, the report is made visible to users on the Internet. It’s publicly available so you can expect viewers to easily share the report through social media in the future. As users view the report, either by opening the direct public URL or viewing it embedded in a web page or blog, Power BI caches the report definition and the results of the queries required to view the report. This approach ensures the report can be viewed by thousands of concurrent users without any impact on performance.  

The cache is long-lived, so if you update the report definition (for example, if you change its View mode) or refresh the report data, it can take approximately one hour before changes are reflected in the version of the report viewed by your users. It is therefore recommended that you stage your work ahead of time, and create the <bpt id="p1">**</bpt>Publish to web<ept id="p1">**</ept> embed code only when you’re satisfied with the settings.

More questions? [Try the Power BI Community](http://community.powerbi.com/)
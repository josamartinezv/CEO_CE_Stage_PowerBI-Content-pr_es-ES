<properties 
   pageTitle="Capturing additional diagnostic information for Power BI"
   description="Capturing additional diagnostic information for Power BI"
   services="powerbi" 
   documentationCenter="" 
   authors="guyinacube" 
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
   ms.date="10/10/2016"
   ms.author="asaxton"/>

# Capturing additional diagnostic information for Power BI  

## Capturing Additional Diagnostic Information for Power BI  
These instructions provide two potential options for manually collecting additional diagnostic information from the Power BI web client.  Only one of these options needs to be followed.

## Network Capture - Edge &amp; Internet Explorer 
1.  Browse to <bpt id="p1">[</bpt>Power BI<ept id="p1">](https://app.powerbi.com)</ept> with Edge or Internet Explorer.

2.  Open the Edge developer tools by pressing F12.

3.  That will bring up the Developer Tools window: 

    ![](media/powerbi-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)

4.  Switch to the Network tab. It will list traffic it has already captured. 

    ![](media/powerbi-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)

5.  You can browse within the window and reproduce any problem you may be encountering. You can hide and show the developer tools window at any time during the session by pressing F12.

6.  To stop the capture, you can select the red square on the network tab of the developer tools area.

    ![](media/powerbi-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)

7.  Select on the diskette icon to <bpt id="p1">**</bpt>Export as HAR<ept id="p1">**</ept>

    ![](media/powerbi-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)

8. Provide a file name and save the HAR file.

    The HAR file will contain all the information about network requests between the browser window and Power BI.  This will include the activity IDs for each request, the precise timestamp for each request, and any error information returned to the client.  This trace will also contain the data used to populate the visuals shown on the screen.

9. You can provide the HAR file to support for review.

More questions? [Try the Power BI Community](http://community.powerbi.com/)
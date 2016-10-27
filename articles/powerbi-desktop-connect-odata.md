<properties
   pageTitle="Connect to an OData feed in Power BI Desktop"
   description="Easily connect to and use an OData feed in Power BI Desktop"
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

# Connect to OData feeds in Power BI Desktop

In Power BI Desktop, you can connect to an <bpt id="p1">**</bpt>OData feed<ept id="p1">**</ept> and use the underlying data just like any other data source in Power BI Desktop.

To connect to an OData feed, select <bpt id="p1">**</bpt>Get Data &gt; OData Feed<ept id="p1">**</ept> from the <bpt id="p2">**</bpt>Home<ept id="p2">**</ept> ribbon in Power BI Desktop.

![](media/powerbi-desktop-connect-odata/connect-to-odata_1.png)

In the <bpt id="p1">**</bpt>OData Feed<ept id="p1">**</ept> window that appears, type or paste your OData feed URL into the box, and select <bpt id="p2">**</bpt>OK<ept id="p2">**</ept>.

![](media/powerbi-desktop-connect-odata/connect-to-odata_2.png)

Power BI Desktop connects to the OData feed, and displays the available tables and other data elements in the <bpt id="p1">**</bpt>Navigator<ept id="p1">**</ept> window. When you select an element, the right pane of the <bpt id="p1">**</bpt>Navigator<ept id="p1">**</ept> window displays a preview of the data. You can select as many tables as you want to import. The <bpt id="p1">**</bpt>Navigator<ept id="p1">**</ept> window shows a preview of the currently selected table.

![](media/powerbi-desktop-connect-odata/connect-to-odata_3.png)

You can choose the <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept> button, which launches <bpt id="p2">**</bpt>Query Editor<ept id="p2">**</ept>, where you can shape and transform the data from the OData feed before importing it into Power BI Desktop. Or you can select the <bpt id="p1">**</bpt>Load<ept id="p1">**</ept> button, and import all of the data elements you selected in the left pane.

When we select <bpt id="p1">**</bpt>Load<ept id="p1">**</ept>, Power BI Desktop imports the selected items, and displays a <bpt id="p2">**</bpt>Load<ept id="p2">**</ept> window of the import progress.


![](media/powerbi-desktop-connect-odata/connect-to-odata_4.png)

Once complete, Power BI Desktop makes the selected tables and other data elements available in the <bpt id="p1">**</bpt>Fields<ept id="p1">**</ept> pane, found on the right side of the <bpt id="p2">*</bpt>Reports<ept id="p2">*</ept> view in Power BI Desktop.

![](media/powerbi-desktop-connect-odata/connect-to-odata_5.png)

And that’s it!

You’re now ready to use the imported data from the OData feed in Power BI Desktop to create visuals, reports, or interact with any other data you might want to connect with and import, such as other Excel workbooks, databases, or any other data source.


## Más información

﻿There are all sorts of data you can connect to using Power BI Desktop. For more information on data sources, check out the following resources:

-   [Getting Started with Power BI Desktop](powerbi-desktop-getting-started.md)

-   [Data Sources in Power BI Desktop](powerbi-desktop-data-sources.md)

-   [Shape and Combine Data with Power BI Desktop](powerbi-desktop-shape-and-combine-data.md)

-   [Connect to Excel workbooks in Power BI Desktop](powerbi-desktop-connect-excel.md)   

-   [Enter data directly into Power BI Desktop](powerbi-desktop-enter-data-directly-into-desktop.md)   

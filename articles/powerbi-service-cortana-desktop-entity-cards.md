<properties
   pageTitle="Create custom Power BI answer cards for Cortana"
   description="Create custom answer cards for Cortana in Power BI"
   services="powerbi"
   documentationCenter=""
   authors="mihart"  
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
   ms.date="09/30/2016"
   ms.author="mihart"/>


# Use Power BI to create a custom Answer Page for Cortana

Use the full capabilities of Power BI to create reports designed specifically to answer Cortana questions.

## Antes de comenzar

Before you can begin creating custom Answer Pages for Cortana, <bpt id="p1">[</bpt>enable Cortana for Power BI<ept id="p1">](powerbi-service-cortana-enable.md)</ept>.  

## Create an Answer Page for Cortana
An <bpt id="p1">*</bpt>Answer Page<ept id="p1">*</ept> in a report is sized specifically for Cortana so that Cortana can show it as an answer to a question.  To create an Answer Page for Cortana:

1. We recommend starting with a <bpt id="p1">[</bpt>blank report page<ept id="p1">](powerbi-service-add-a-page-to-a-report.md)</ept>.

2. In the <bpt id="p1">**</bpt>Visualizations<ept id="p1">**</ept> pane, select the paintbrush icon and choose <bpt id="p2">**</bpt>Page Size &gt; Cortana<ept id="p2">**</ept>.

    ![](media/powerbi-service-cortana-desktop-entity-cards/PBI-cortana-page-size.png)

3. Create a visual or a set of visuals that you want to appear in Cortana in response to a particular question (or set of questions).

4. Ensure that all visuals fit within the page borders.  Optionally, modify display settings, data labels, colors, and backgrounds.  

    ![](media/powerbi-service-cortana-desktop-entity-cards/PBI_Cortana_modify.png)

5. Name the page and add alternate names.  Cortana uses these names when it searches for results. In the <bpt id="p1">**</bpt>Visualizations<ept id="p1">**</ept> pane, select the paintbrush icon and choose <bpt id="p2">**</bpt>Page Information<ept id="p2">**</ept>. Enable Q&amp;A for this visual by moving the slider to <bpt id="p1">**</bpt>On<ept id="p1">**</ept>.

    ![](media/powerbi-service-cortana-desktop-entity-cards/powerbi-cortana-name.png)

    >[AZURE.TIP] To improve results, avoid using words that are also column names.

6. Optionally, if your report has page level filters, you can set <bpt id="p1">**</bpt>Require single selection<ept id="p1">**</ept>. Cortana will only display this report as an answer if one, and only one, of the filter items is specified in the question.

    ![](media/powerbi-service-cortana-desktop-entity-cards/PBI-cortana-single-selection.png)

      For example, if you ask Cortana:

      - "show sales by store name," this Answer Page will not appear because you did not include any of the items in the required page level filter.

      - "show sales for Cary Lindseys and Charlotte Lindseys," this Answer Page will not appear because you specified more than one item from the required page level filter.

      - "show sales for Charlotte Lindseys," this Answer Page will display.

    Now, asking a question including the name of a Cortana-sized page will return results from Cortana.

    >[AZURE.IMPORTANT]  Before your Answer Page can be accessed by Cortana, you will need to <bpt id="p1">[</bpt>Enable the dataset for Cortana<ept id="p1">](powerbi-service-cortana-enable.md)</ept>.

## How does Cortana order the results?

Results with high scoring answers (such as a complete match of a specified page name) will appear first as a <bpt id="p1">*</bpt>best match<ept id="p1">*</ept> in Cortana. Multiple best matches can appear if there are multiple answers in Power BI. Medium or lower scoring answers, such as answers not based on a named page for Cortana or a question with words not understood by Power BI, are listed as links below best matches in Cortana.

>[AZURE.NOTE] When a new dataset or custom Cortana Answer Page is added to Power BI and enabled for Cortana it can take up to 30 minutes for results to begin appearing in Cortana. Logging in and out of Windows 10, or otherwise restarting the Cortana process in Windows 10, will allow new content to appear immediately.


## Consulte también

[Using Cortana with Power BI](powerbi-service-cortana-intro.md)

[Get started with Power BI Desktop](powerbi-desktop-getting-started.md)

More questions? [Try the Power BI Community](http://community.powerbi.com/)

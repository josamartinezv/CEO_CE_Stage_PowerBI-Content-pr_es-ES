<properties
   pageTitle="Retail Analysis sample for Power BI: Take a tour"
   description="Retail Analysis sample for Power BI: Take a tour"
   services="powerbi"
   documentationCenter=""
   authors="amandacofsky"
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
   ms.date="07/18/2016"
   ms.author="amac"/>

# <a name="retail-analysis-sample-for-power-bi:-take-a-tour"></a>Retail Analysis sample for Power BI: Take a tour

##  <a name="about-the-retail-analysis-sample"></a>About the Retail Analysis sample

This industry sample dashboard and underlying report analyze retail sales data of items sold across multiple stores and districts. The metrics compare this year’s performance to last year’s in these areas:  sales, units, gross margin, and variance, as well as new store analysis. This is real data from obviEnce (<bpt id="p1">[</bpt>www.obvience.com<ept id="p1">](http://www.obvience.com)</ept>) that has been anonymized.

You can also <bpt id="p1">[</bpt>download just the dataset (Excel workbook) for this sample<ept id="p1">](http://go.microsoft.com/fwlink/?LinkId=528592)</ept>.

![](media/powerbi-sample-retail-analysis-take-a-tour/retail1.png)

##  <a name="start-on-the-dashboard-and-open-the-report"></a>Start on the dashboard and open the report

1.  On the dashboard, select the "Total Stores" tile:

    ![](media/powerbi-sample-retail-analysis-take-a-tour/retail-analysis-7.png)  

    This takes you to the "Store Sales Overview" page in the report. You see we have 104 total stores, 10 of them new. We have two chains, Fashions Direct and Lindseys. Fashions Direct stores are larger on average.

2.  In the pie chart, select <bpt id="p1">**</bpt>Fashions Direct<ept id="p1">**</ept>.

    ![](media/powerbi-sample-retail-analysis-take-a-tour/retail3.png)  

    Notice the result in the bubble chart:

    ![](media/powerbi-sample-retail-analysis-take-a-tour/PBI_Sample_RetAnlBubbles.png)  

    FD-01 district has the highest Average Sales per Square Foot, FD-02 has the lowest Variance in Sales compared to last year, FD-03 and FD-04 are worst performers overall.

3.  Select individual bubbles or other charts to see cross highlighting, revealing the impact of your selections.

4.  Select Power BI in the top navigation bar to return to the dashboard.

    ![](media/powerbi-sample-retail-analysis-take-a-tour/retail-analysis.png)

5.  On the dashboard, select the tile that has "This Year’s Sales."

    ![](media/powerbi-sample-retail-analysis-take-a-tour/PBI_Sample_RetAnlThisYrSales.png)

    This is equivalent to typing "This year sales" in the question box.

    You see this screen:

    ![](media/powerbi-sample-retail-analysis-take-a-tour/retail7.png)

##  <a name="review-a-tile-created-with-power-bi-q&a"></a>Review a tile created with Power BI Q&amp;A

Let’s get more specific.

1.  Add “this year sales <bpt id="p1">**</bpt>by district<ept id="p1">**</ept>” onto the question. Observe the result: It automatically put the answer in a bar chart and suggests other phrases:

    ![](media/powerbi-sample-retail-analysis-take-a-tour/retail8.png)

2.  Now change the question to “this year sales <bpt id="p1">**</bpt>by zip and chain<ept id="p1">**</ept>”.

    Notice how it answers the question as you type with the appropriate charts.

3.  Play around with more questions and see what kind of results you get.

4.  When you’re ready, return to the dashboard by selecting Power BI in the upper-left corner.

##  <a name="dive-deeper-into-the-data"></a>Dive deeper into the data

Now let's explore on a more detailed level, looking at the districts' performances.

1.  On the dashboard, select the tile comparing this year's sales to last year’s.

    ![](media/powerbi-sample-retail-analysis-take-a-tour/PBI_Sample_RetAnlAreaCht.png)

    Notice the large variability on Variance % to last year, with Jan, Apr, and Jul being particularly bad months.

    ![](media/powerbi-sample-retail-analysis-take-a-tour/PBI_Sample_RetAnlSalesVarCol.png)

    Let’s see if we can narrow down where the issues might be.

2.  Select the bubble chart, and choose <bpt id="p1">**</bpt>020-Mens<ept id="p1">**</ept>.

    ![](media/powerbi-sample-retail-analysis-take-a-tour/retail11.png)  

    Observe the men's category wasn't as severely affected in April as the business overall, but January and July were still problem months.

3.  Now, select the <bpt id="p1">**</bpt>010-Womens’ bubble<ept id="p1">**</ept>.

    ![](media/powerbi-sample-retail-analysis-take-a-tour/retail12.png)

    Notice the women's category performed much worse than business overall across all months, and much worse in almost every month compared to the previous year.

4.  Select the bubble again to clear the filter.

##  <a name="try-out-the-slicer"></a>Try out the Slicer

Let’s look at how specific districts are doing.

1.  Select Allan Guinot in the slicer on the top left.

    ![](media/powerbi-sample-retail-analysis-take-a-tour/retail13.png)

    Note that Allan’s district outperformed Last Year in March and June.

2.  Now, while Allan is still selected, select the Women’s bubble.

    ![](media/powerbi-sample-retail-analysis-take-a-tour/retail14.png)

    Note that for the Women’s category, his district never met last year’s volume.

3.  3.Explore the other district managers and categories – what other insights can you find?

4.  When you are ready – return to the dashboard.

## <a name="what-is-our-data-telling-us-about-sales-growth-this-year?"></a>What is our data telling us about sales growth this year?

The last area we want to explore is our growth – new stores opened this year.

1.  Select the 'Stores Opened This Year’ tile.

    ![](media/powerbi-sample-retail-analysis-take-a-tour/retail15.png)

    As evident from the tile – more Fashions Direct stores than Lindseys stores opened this year.

2.  Observe the Sales Per Sq Ft by Name chart:

    ![](media/powerbi-sample-retail-analysis-take-a-tour/15.png)

     There is quite a bit of difference in Average Sales per SQF across the new stores.

3.  Click on the Fashions Direct legend item in the top right chart. Notice, even for the same chain, the best store (Winchester Fashions Direct) significantly outperforms the worst store (Cincinnati 2 Fashions Direct) $21.22 vs $12.86 respectively.

    ![](media/powerbi-sample-retail-analysis-take-a-tour/17b.png)

4.  Click Winchester Fashions Direct in the slicer and observe the line chart. The first sales numbers were reported in February and is a leading store in terms of volume for almost every month.

5.  Click on Cincinnati 2 Fashions Direct in the slicer and you will see in the line chart that it was opened in June and it seems to be the worst performing store.

6.  As before, explore by clicking on other bars, lines and bubbles throughout the charts and see what insights you can discover.

This is a safe environment to play in. You can always choose not to save your changes. But if you do save them, you can always go to Get Data for a new copy of this sample.

## <a name="next-steps:-connect-to-your-data"></a>Next steps: Connect to your data

We hope this tour has shown how Power BI dashboards, Q&amp;A, and reports can provide insights into retail data. Now it’s your turn — connect to your own data. With Power BI you can connect to a wide variety of data sources. Learn more about <bpt id="p1">[</bpt>getting started with Power BI<ept id="p1">](https://support.office.com/article/Get-Started-with-Power-BI-Preview-0f0237e2-f74f-49ab-82ea-1990c3c3deb8)</ept>.

## <a name="see-also"></a>Consulte también

-   <bpt id="p1">[</bpt>Download the Retail Analysis sample content pack<ept id="p1">](powerbi-sample-tutorial-connect-to-the-samples.md)</ept>
-   <bpt id="p1">[</bpt>Download the Excel workbook for this Power BI sample<ept id="p1">](http://go.microsoft.com/fwlink/?LinkId=528592)</ept>
-   <bpt id="p1">[</bpt>Get data (for Power BI)<ept id="p1">](powerbi-service-get-data.md)</ept>
-   <bpt id="p1">[</bpt>Power BI - Basic Concepts<ept id="p1">](powerbi-service-basic-concepts.md)</ept>
-  More questions? <bpt id="p1">[</bpt>Try the Power BI Community<ept id="p1">](http://community.powerbi.com/)</ept>

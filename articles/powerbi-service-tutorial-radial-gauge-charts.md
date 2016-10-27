<properties
   pageTitle="Tutorial: Radial Gauge charts in Power BI"
   description="Tutorial: Radial Gauge charts in Power BI"
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   featuredVideoId="xmja6Epqa"
   qualityFocus="no"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/22/2016"
   ms.author="mihart"/>

# Tutorial: radial gauge charts in Power BI

A radial gauge chart has a circular arc and displays a single value that measures progress toward a goal/KPI.  The goal, or target value, is represented by the line (needle). Progress toward that goal is represented by the shading.  And the value that represents that progress is shown in bold inside the arc. All possible values are spread evenly along the arc, from the minimum (left-most value) to the maximum (right-most value).

In the example below, we are a car retailer, tracking our Sales team's average sales per month. Our goal is 140 and represented by the black needle.  The minimum possible average sales is 0 and we've set the maximum as 200.  The blue shading shows that we're currently averaging approximately 120 sales this month. Luckily, we still have another week to reach our goal.

![](media/powerbi-service-tutorial-radial-gauge-charts/gauge_m.PNG)

## When to use a radial gauge

Radial gauges are a great choice to:

-   show progress toward a goal.

-   represent a percentile measure, like a KPI.

-   show the health of a single measure.

-   display information that can be quickly scanned and understood.

## Create a basic radial gauge

These instructions use the Financial Sample. To follow along, <bpt id="p1">[</bpt>download the sample<ept id="p1">](http://go.microsoft.com/fwlink/?LinkID=521962)</ept> to your computer, sign in to Power BI and select <bpt id="p2">**</bpt>Get Data <ph id="ph1">\&gt;</ph> Files <ph id="ph2">\&gt;</ph>  Local File &gt; Open<ept id="p2">**</ept>. 

Or watch Will show you how to create single metric visuals: gauges, cards, and KPIs.
<iframe width="560" height="315" src="https://www.youtube.com/embed/xmja6EpqaO0?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

### Step 1: Open the Financial Sample Excel file.

1.  Open the file in Power BI by selecting <bpt id="p1">**</bpt>Get Data <ph id="ph1">\&gt;</ph> Files<ept id="p1">**</ept> and browsing to the location where you saved the file. Select <bpt id="p1">**</bpt>Import<ept id="p1">**</ept>. The Financial Sample is added to your workspace as a dataset.

2.  Select <bpt id="p1">**</bpt>Financial Sample<ept id="p1">**</ept> to open it in Explore mode.

### Step 2: Create a gauge to track Gross Sales

1.  In the <bpt id="p1">**</bpt>Fields<ept id="p1">**</ept> pane, select <bpt id="p2">**</bpt>Gross Sales<ept id="p2">**</ept>.

    ![](media/powerbi-service-tutorial-radial-gauge-charts/GrossSalesValue_new.png)

2.  Change the aggregation to <bpt id="p1">**</bpt>Average<ept id="p1">**</ept>.

    ![](media/powerbi-service-tutorial-radial-gauge-charts/changeToAverage_new.png)

3.  Select the gauge icon <ph id="ph1">![](media/powerbi-service-tutorial-radial-gauge-charts/gaugeIcon_new.png)</ph> to convert the Column Chart to a gauge.

  By default, Power BI creates a Gauge chart where the current value (in this case, Average of Gross Sales) is assumed to be at the halfway point on the gauge. Since the Average Gross Sales is $182.76K, the start value (Minimum) is set to 0 and the end value (Maximum) is set to double the current value.

  ![](media/powerbi-service-tutorial-radial-gauge-charts/gauge_no_target.png)

### Step 3: Set a target value

1. Drag <bpt id="p1">**</bpt>COGS<ept id="p1">**</ept> to the <bpt id="p2">**</bpt>Target value<ept id="p2">**</ept> well.

2.  Change the aggregation to <bpt id="p1">**</bpt>Average<ept id="p1">**</ept>.
  Power BI adds a needle to represent our target value of <bpt id="p1">**</bpt>$145.48K<ept id="p1">**</ept>. Notice that we've exceeded our target.

    ![](media/powerbi-service-tutorial-radial-gauge-charts/GaugeInProgress_new.png)

    >[AZURE.NOTE] You can also manually enter a target value.  See "Use formatting options to manually set Minimum, Maximum, and Target values" below.

### Step 4: Set a maximum value

In Step 2, Power BI used the Value field to automatically set minimum (start) and maximum (end).  But what if you want to set your own maximum value?  Let's say that instead of using double the current value as the maximum possible value, you want to set it to the highest Gross Sales number in your dataset? 

2.  Drag <bpt id="p1">**</bpt>Gross Sales<ept id="p1">**</ept> from the <bpt id="p2">**</bpt>Fields<ept id="p2">**</ept> list to the <bpt id="p3">**</bpt>Maximum Value<ept id="p3">**</ept> well.

2.  Change the aggregation to <bpt id="p1">**</bpt>Maximum<ept id="p1">**</ept>.

    ![](media/powerbi-service-tutorial-radial-gauge-charts/SetMaximum_new.png)

    The gauge is redrawn with a new end value, 1.21 million in gross sales.

### Step 5: Save your report

6.  <bpt id="p1">[</bpt>Save the report<ept id="p1">](powerbi-service-save-a-report.md)</ept>.

7. <bpt id="p1">[</bpt>Add the gauge chart as a dashboard tile<ept id="p1">](powerbi-service-dashboard-tiles.md)</ept>. 

## Use formatting options to manually set Minimum, Maximum, and Target values

1. Remove <bpt id="p1">**</bpt>Max of Gross Sales<ept id="p1">**</ept> from the <bpt id="p2">**</bpt>Maximum value<ept id="p2">**</ept> well.

2.  Open the formatting pane by selecting the paintbrush icon.

    ![](media/powerbi-service-tutorial-radial-gauge-charts/PBI_format.png)

2. Expand the <bpt id="p1">**</bpt>Gauge axis<ept id="p1">**</ept> and enter values for <bpt id="p2">**</bpt>Min<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Max<ept id="p3">**</ept>.

    ![](media/powerbi-service-tutorial-radial-gauge-charts/PBI_gauge_axis.png)

3. Remove the current target value by removing the checkmark next to <bpt id="p1">**</bpt>COGS<ept id="p1">**</ept>.

    ![](media/powerbi-service-tutorial-radial-gauge-charts/PBI_remove_target.png)

4. When the <bpt id="p1">**</bpt>Target<ept id="p1">**</ept> field appears under <bpt id="p2">**</bpt>Gauge axis<ept id="p2">**</ept>, enter a value.

    ![](media/powerbi-service-tutorial-radial-gauge-charts/PBI_new_target.png)

5. Optionally, continue formatting your gauge chart.


## Consulte también

[Reports in Power BI](powerbi-service-reports.md)

[Visualization types in Power BI](powerbi-service-visualization-types-for-reports-and-q-and-a.md)

[Add a visualization to a report](https://powerbi.uservoice.com/knowledgebase/articles/441777)

[Pin a visualization to a dashboard](powerbi-service-pin-a-tile-to-a-dashboard-from-a-report.md)

[ Power BI - Basic Concepts](powerbi-service-basic-concepts.md)

More questions? [Try the Power BI Community](http://community.powerbi.com/)

<properties
   pageTitle="Create Calculated Columns"
   description="Calculated columns let you create unique keys, and more"
   services="powerbi"
   documentationCenter=""
   authors="davidiseminger"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="no"
   qualityDate=""
   featuredVideoId="GarBXef0Vew"
   featuredVideoThumb=""
   courseDuration="9m"/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="get-started-article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="09/29/2016"
   ms.author="davidi"/>

# Create Calculated Columns

Creating calculated columns is a simple way to enrich and enhance your data. A <bpt id="p1">**</bpt>calculated column<ept id="p1">**</ept> is a new column that you create by defining a calculation that transforms or combines two or more elements of existing data. For example, you can create a new column by combining two columns into one.

One useful reason for creating a calculated column is to establish a relationship between tables, when no unique fields exist that can be used to establish a relationship. The lack of a relationship becomes apparent when you create a simple table visual in Power BI Desktop, and you get the same value for all entries, yet you know the underlying data is different.

![](media/powerbi-learning-2-3-create-calculated-columns/2-3_1.png)

To create a relationship with unique fields in data, you can, for example, create a new calculated column for "Full Phone Number" by combining the values from the "Area Code" and "Local Number" columns when those values exist in your data. Calculated columns are a useful tool for quickly creating models and visualizations.

To create a calculated column, select the <bpt id="p1">**</bpt>Data view<ept id="p1">**</ept> in Power BI Desktop from the left side of the report canvas.

![](media/powerbi-learning-2-3-create-calculated-columns/2-3_2.png)

From the Modeling tab, select <bpt id="p1">**</bpt>New Column<ept id="p1">**</ept>. This will enable the formula bar where you can enter calculations using DAX (Data Analysis Expressions) language. DAX is a powerful formula language, also found in Excel, that lets you build robust calculations. As you type a formula, Power BI Desktop displays matching formulas or data elements to assist and accelerate the creation of your formula.

The Power BI formula bar will suggest specific DAX functions and related data columns as you enter your expression.

![](media/powerbi-learning-2-3-create-calculated-columns/2-3_3.png)

Once the calculated columns are created in each table, they can be used as a unique key to establish a relationship between them. Going to <bpt id="p1">**</bpt>Relationship<ept id="p1">**</ept> view, you can then drag the field from one table to the other to create the relationship.

![](media/powerbi-learning-2-3-create-calculated-columns/2-3_4.png)

Returning to <bpt id="p1">**</bpt>Report<ept id="p1">**</ept> view, you now see a different value for each district.

![](media/powerbi-learning-2-3-create-calculated-columns/2-3_5.png)

There are all sorts of other things you can do by creating calculated columns, too.

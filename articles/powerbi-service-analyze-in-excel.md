<properties
   pageTitle="Analyze in Excel"
   description="Learn about how to analyze Power BI datasets in Excel"
   services="powerbi"
   documentationCenter=""
   authors="davidiseminger"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="complete"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="09/27/2016"
   ms.author="davidi"/>

# Analyze in Excel
With <bpt id="p1">**</bpt>Analyze in Excel<ept id="p1">**</ept>, you can view and interact with a dataset you have access to in Power BI, and thereby access PivotTable, chart, and slicer features directly in Excel, based on the dataset that exists in Power BI.

## Requisitos
There are a few requirements for using <bpt id="p1">**</bpt>Analyze in Excel<ept id="p1">**</ept>:
- <bpt id="p1">**</bpt>Analyze in Excel<ept id="p1">**</ept> is supported for Microsoft Excel 2010 SP1 and later.
- Excel PivotTables do not support drag-and-drop aggregation of numeric fields. Your dataset in Power BI <bpt id="p1">*</bpt>must have pre-defined measures<ept id="p1">*</ept>.
- Some organizations may have Group Policy rules that prevent installing the required <bpt id="p1">**</bpt>Analyze in Excel<ept id="p1">**</ept> updates to Excel. If you’re unable to install the updates, check with your administrator.

## ¿Cómo funciona?
When you select <bpt id="p1">**</bpt>Analyze in Excel<ept id="p1">**</ept> from the ellipses menu (the ...) associated with a dataset or report in <bpt id="p2">**</bpt>Power BI<ept id="p2">**</ept>, Power BI creates an .ODC file and downloads it from the browser to your computer.

![](media/powerbi-service-analyze-in-excel/pbi_anlz_excel_menu.png)

When you open the file in Excel, an empty <bpt id="p1">**</bpt>PivotTable<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Fields<ept id="p2">**</ept> list appears with the tables, fields, and measures from the Power BI dataset. You can create PivotTables, charts, and analyze that dataset just as you would work with a local dataset in Excel.

The .ODC file has an MSOLAP connection string that connects to your dataset in Power BI. When you analyze or work with the data, Excel queries that dataset in Power BI and returns the results to Excel. If that dataset connects to a live data source using DirectQuery, Power BI queries the data source and returns the result to Excel.

<bpt id="p1">**</bpt>Analyze in Excel<ept id="p1">**</ept> is very useful for datasets and reports that connect to <bpt id="p2">*</bpt>Analysis Services Tabular<ept id="p2">*</ept> or <bpt id="p3">*</bpt>Multidimensional<ept id="p3">*</ept> databases, or from Power BI Desktop files or Excel workbooks with data models that have explicit measures created using Data Analysis Expressions (DAX).

## Get started with Analyze in Excel

In Power BI, select the ellipses menu beside a report or dataset (the ... beside the report or dataset name), and from the menu that appears, select <bpt id="p1">**</bpt>Analyze in Excel<ept id="p1">**</ept>.

![](media/powerbi-service-analyze-in-excel/pbi_anlz_excel_menu.png)


### Install Excel updates
When you first use <bpt id="p1">**</bpt>Analyze in Excel<ept id="p1">**</ept>, you need to install updates to the Excel libraries. You’ll be prompted to download and run Excel updates (this initiates installation of the <bpt id="p1">*</bpt>SQL_AS_OLEDDB.msi<ept id="p1">*</ept> Windows installer package). This package installs <bpt id="p1">**</bpt>Microsoft AS OLE DB Provider for SQL Server 2016 RC0 (Preview)<ept id="p1">**</ept>.

> <bpt id="p1">**</bpt>Note:<ept id="p1">**</ept> Be sure to check <bpt id="p2">**</bpt>Don’t show this again<ept id="p2">**</ept> in the <bpt id="p3">**</bpt>Install Excel updates<ept id="p3">**</ept> dialog. You only need to install the update once.

![](media/powerbi-service-analyze-in-excel/pbi_anlz_excel_dontshow.png)

If you do need to install the Excel updates for <bpt id="p1">**</bpt>Analyze in Excel<ept id="p1">**</ept> again, you can download the update from the <bpt id="p2">**</bpt>Download<ept id="p2">**</ept> icon in Power BI, as shown in the following image.

![](media/powerbi-service-analyze-in-excel/pbi_anlz_excel_download_again.png)

### Sign in to Power BI
Although you’re signed in to Power BI in your browser, the first time you open a new .ODC file in Excel you must sign in to Power BI with your Power BI account. This authenticates the connection from Excel to Power BI.

### Users with multiple Power BI accounts
Some users have multiple Power BI accounts, and those users may encounter a situation where they're logged into Power BI with one account, but the account that has access to the dataset being used in Analyze in Excel is a different account. In those situations, you may get a <bpt id="p1">**</bpt>Forbidden<ept id="p1">**</ept> error or a sign-in failure when attempting to access a dataset that's being used in an Analyze in Excel workbook.

You'll be provided an opportunity to sign in again, at which time you can sign in with the Power BI account that has access to the dataset being accessed by Analyze in Excel.

![](media/powerbi-service-analyze-in-excel/pbi_anlz_excel_AADlogin.png)

For other errors you might encounter, take a look at the <bpt id="p1">[</bpt>Troubleshooting Analyze in Excel<ept id="p1">](powerbi-desktop-troubleshooting-analyze-in-excel.md)</ept> article.

### Enable data connections
In order to analyze your Power BI data in Excel, you are prompted to verify the file name and path for the .odc file, and then select <bpt id="p1">**</bpt>Enable<ept id="p1">**</ept>.

![](media/powerbi-service-analyze-in-excel/pbi_anlz_excel_enable.png)

You can also connect to on-premises Analysis Services (AS) databases using <bpt id="p1">*</bpt>DirectQuery<ept id="p1">*</ept>, and include data in reports created using Analyze in Excel. You must be on the same Active Directory domain as the AS database, and it must be on-premises. Administrators for a Power BI deployment can enable or disable the ability to connect to AS databases in the <bpt id="p1">**</bpt>Admin portal<ept id="p1">**</ept>.

## Analyze away
Now that Excel has opened and you have an empty PivotTable, you're ready to do all sorts of analysis with your Power BI dataset. Just as with other local workbooks, with Analyze with Excel you can create PivotTables, charts, add data from other sources, and so on. And of course, you can create different worksheets with all sorts of views into your data.

![](media/powerbi-service-analyze-in-excel/pbi_anlz_excel_chart.png)

## Guardar
You can save this Power BI dataset connected workbook just like any other workbook. However, you cannot publish or import the workbook back into Power BI because you can only publish or import workbooks into Power BI that have data in tables, or that have a data model. Since the new workbook simply has a connection to the dataset in Power BI, publishing or importing it into Power BI would be going in circles!

## Compartir
Once your workbook is saved, you can share it with other Power BI users in your organization. In order to share your workbook with other Power BI users, you must share the dataset (the workbook) by doing one of the following:

-   Share the Power BI dashboard that hosts a pinned element from your Power BI report with the user
-   Share a content pack that contains the dataset with the user
-   Add the user with whom you want to share to the group that owns the dataset

When a user with whom you’ve shared your workbook opens the workbook, they’ll see your PivotTables and data as they appeared when the workbook was last saved, which may not be the latest version of the data. To get the latest data, users must use the <bpt id="p1">**</bpt>Refresh<ept id="p1">**</ept> button on the <bpt id="p2">**</bpt>Data<ept id="p2">**</ept> ribbon. And since the workbook is connecting to a dataset in Power BI, users attempting to refresh the workbook must sign into Power BI and install the Excel updates the first time they attempt to update using this method.

You can also set the workbook file to refresh the data upon opening, which refreshes the data whenever anyone accesses the dataset. To refresh the workbook each time it's opened, in Excel select <bpt id="p1">**</bpt>Connections<ept id="p1">**</ept> from the <bpt id="p2">**</bpt>Data<ept id="p2">**</ept> ribbon, select the connection used for the workbook, then select <bpt id="p3">**</bpt>Properties<ept id="p3">**</ept> and set <bpt id="p4">*</bpt>Refresh data when opening the file<ept id="p4">*</ept> to <bpt id="p5">**</bpt>True<ept id="p5">**</ept>, then select <bpt id="p6">**</bpt>OK<ept id="p6">**</ept>.

Since users will need to refresh the dataset, and refresh for external connections is not supported in Excel Online, it’s recommended that users open the workbook in the desktop version of Excel on their computer.

## Véase también  

[Troubleshooting Analyze in Excel](powerbi-desktop-troubleshooting-analyze-in-excel.md)

More questions? [Try the Power BI Community](http://community.powerbi.com/)

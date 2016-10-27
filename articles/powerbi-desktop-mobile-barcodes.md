<properties 
   pageTitle="Tag a barcode field in Power BI Desktop for the Power BI mobile apps"
   description="When you tag a barcode field in your model in Power BI Desktop, you can filter data for barcodes automatically in the Power BI app on your iPhone."
   services="powerbi" 
   documentationCenter="" 
   authors="maggiesMSFT" 
   manager="mblythe" 
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
   ms.author="maggies"/>

# Tag barcodes in Power BI Desktop for the Power BI mobile apps

In Power BI Desktop, you can <bpt id="p1">[</bpt>categorize data<ept id="p1">](powerbi-desktop-data-categorization.md)</ept> in a column, so Power BI Desktop knows how to treat values in visuals in a report. You can also categorize a column as <bpt id="p1">**</bpt>Barcode<ept id="p1">**</ept>. When you or your colleagues <bpt id="p1">[</bpt>scan a barcode on a product with the Power BI app<ept id="p1">](powerbi-mobile-scan-barcode-for-report.md)</ept> on the iPhone, you see any report that includes that barcode. When you open the report in the mobile app, Power BI automatically filters the report to data related to that barcode.

1. In Power BI Desktop, switch to Data View.

2. Select a column with barcode data. See the list of <bpt id="p1">[</bpt>supported barcode formats<ept id="p1">](#supported-barcode-formats)</ept> below.

3. On the <bpt id="p1">**</bpt>Modeling<ept id="p1">**</ept> tab, select <bpt id="p2">**</bpt>Data Category<ept id="p2">**</ept><ph id="ph1"> &gt; </ph><bpt id="p3">**</bpt>Barcode<ept id="p3">**</ept>.

    ![](media/powerbi-desktop-mobile-barcodes/power-bi-desktop-barcode.png)

4. In Report view, add this field to the visuals you want filtered by the barcode.

5. Save the report and publish it to the Power BI service.

Now when you open the scanner on the <bpt id="p1">[</bpt>Power BI app for iPhone<ept id="p1">](powerbi-mobile-ipad-iphone-apps.md)</ept> and scan a barcode, you see this report in the list of reports. When you open the report, its visuals are filtered by the product barcode you scanned.

## Supported barcode formats
These are the barcodes Power BI recognizes if you can tag them in a Power BI report: 

- UPCECode 
- Code39Code  
- A39Mod43Code 
- EAN13Code 
- EAN8Code  
- 93Code  
- 128Code 
- PDF417Code 
- Interleaved2of5Code 
- ITF14Code 

### Consulte también  
- [Scan a barcode from the Power BI app on your iPhone](powerbi-mobile-scan-barcode-for-report.md)
- [Issue with scanning barcodes on an iPhone](powerbi-mobile-scan-barcode-for-report.md#issues-with-scanning-a-barcode)
- [Data categorization in Power BI Desktop](powerbi-desktop-data-categorization.md)  
- [Get started with the iPhone app for Power BI](powerbi-mobile-iphone-app-get-started.md)  
- [Get started with Power BI](powerbi-service-get-started.md)  
- Questions? [Try asking the Power BI Community](http://community.powerbi.com/)

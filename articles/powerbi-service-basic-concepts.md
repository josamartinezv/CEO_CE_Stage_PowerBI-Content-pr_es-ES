<properties
   pageTitle="Power BI - basic concepts"
   description="Power BI - basic concepts"
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   featuredVideoId="Y4sRWbo8JcE"
   qualityFocus="no"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="get-started-article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="10/05/2016"
   ms.author="mihart"/>

# Power BI - basic concepts for Power BI service

When you first open Power BI service, you'll see your workspace. Prominently displayed will be your <bpt id="p1">***</bpt>dashboard<ept id="p1">***</ept>, which is something that differentiates Power BI service from Power BI Desktop.

![](media/powerbi-service-basic-concepts/completeNewer.png)
Your Power BI service workspace is made up of:

1.  barra de navegación
2.  dashboard with tiles
3.  Q&amp;A question box
4.  help and feedback buttons
5.  dashboard title
6.  Office 365 app launcher
7.  Power BI home buttons
8. Additional dashboard actions

We'll dig into these later, but first let's review some Power BI concepts.

Or, you might want to watch this video first before reading the rest of this article.  In the video, Will reviews the basic concepts and gives a tour of Power BI service.

<iframe width="560" height="315" src="https://www.youtube.com/embed/Y4sRWbo8JcE?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## Power BI concepts

The 3 major building blocks of Power BI are: <bpt id="p1">***</bpt>dashboards<ept id="p1">***</ept>, <bpt id="p2">***</bpt>reports<ept id="p2">***</ept>, and <bpt id="p3">***</bpt>datasets<ept id="p3">***</ept>. You can't have dashboards or reports without data (well, you can have empty dashboards and empty reports, but they're not very useful until they have data), so let's start with <bpt id="p1">**</bpt>datasets<ept id="p1">**</ept>.

## Conjuntos de datos

A <bpt id="p1">*</bpt>dataset<ept id="p1">*</ept> is something that you <bpt id="p2">*</bpt>import<ept id="p2">*</ept> or <bpt id="p3">*</bpt>connect<ept id="p3">*</ept> to. Power BI lets you connect to all sorts of datasets and bring all of it together in one place.  

In the navigation bar, the datasets you've connected to are listed under the <bpt id="p1">**</bpt>Datasets<ept id="p1">**</ept> heading. Each listed dataset represents a single source of data, for example, an Excel workbook on OneDrive, or an on-premises SSAS tabular dataset, or a Salesforce dataset. There are many different data sources supported, and we’re adding new ones all the time. <bpt id="p1">[</bpt>See the list of dataset types that can be used with Power BI<ept id="p1">](powerbi-service-get-data.md)</ept>.

<bpt id="p1">**</bpt>ONE<ept id="p1">**</ept> dataset...
- can be used over and over.
- can be used in many different reports.
- Visualizations from that one dataset can display on many different dashboards.

  ![](media/powerbi-service-basic-concepts/Drawing2.png)

To <bpt id="p1">[</bpt>connect to a dataset<ept id="p1">](powerbi-service-get-data.md)</ept>, select <bpt id="p2">**</bpt>Get Data<ept id="p2">**</ept> (at the bottom of the navigation bar) or select the plus icon next to the <bpt id="p3">**</bpt>Datasets<ept id="p3">**</ept> heading. Follow the instructions to connect to the specific source and add the dataset to your workspace. New datasets are added to the left navigation bar and marked with a yellow asterisk. The work you do in Power BI does not change the underlying dataset.

Datasets can be refreshed, renamed, explored and removed. To explore a dataset, select it. What you're actually doing is opening the dataset in the report editor where you can really start digging into the data and creating visualizations. So, let's move on to the next topic -- reports. 

### Dig deeper:

-   [Power BI Pro content - what is it?](powerbi-power-bi-pro-content-what-is-it.md)
-   [Get data for Power BI](powerbi-service-get-data.md)
-   [Sample datasets and content packs for Power BI](powerbi-sample-datasets.md)

## Reports

A Power BI report is one or more pages of visualizations (charts, graphs and images). All of the visualizations in a report come from a single dataset. Reports can be created from scratch within Power BI, can be imported with dashboards that colleagues share with you, or can be created for you when you connect to datasets from Excel, Power BI Desktop, databases, SaaS applications and <bpt id="p1">[</bpt>content packs<ept id="p1">](powerbi-service-organizational-content-packs-introduction.md)</ept>.  For example, when you connect to an Excel workbook that contains Power View sheets, Power BI creates a report based on those sheets. And when you connect to an SaaS application, Power BI imports a pre-built report.

There are 2 modes to view and interact with reports: <bpt id="p1">[</bpt>Reading View<ept id="p1">](powerbi-service-open-a-report-in-reading-view.md)</ept> and <bpt id="p2">[</bpt>Editing View<ept id="p2">](powerbi-service-interact-with-a-report-in-editing-view.md)</ept>.  Only the person who created the report, co-owners, and those granted permission, have access to all of the exploring, designing, building, and sharing capabilities of <bpt id="p1">***</bpt>Editing View<ept id="p1">***</ept> for that report. And the people they share the report with can explore and interact with the report using <bpt id="p1">***</bpt>Reading View<ept id="p1">***</ept>.   

In the navigation pane, your reports are listed under the <bpt id="p1">**</bpt>Reports heading<ept id="p1">**</ept>. Each listed report represents 1 or more pages of visualizations based on 1 of the underlying datasets. All of the reports listed here can be opened in both Reading View and Editing View. To open a report, simply select it. By default, the report opens in Reading View first.  Just select <bpt id="p1">**</bpt>Edit report<ept id="p1">**</ept> to open it in Editing View.  If a shared dashboard has reports, you will NOT see the report listed in the navigation bar. 

<bpt id="p1">**</bpt>ONE<ept id="p1">**</ept> report...
-  can be associated with multiple dashboards (tiles pinned from that one report can appear on multiple dashboards).
-  can be created using data from one dataset. (the slight exception to this is that Power BI Desktop can combine more than 1 dataset into a single report and that report can be imported into Power BI)

  ![](media/powerbi-service-basic-concepts/Drawing3new.png)

## Paneles

A <bpt id="p1">*</bpt>dashboard<ept id="p1">*</ept> is something you create or something a colleague creates and shares with you. It is a single canvas that contains zero or more tiles and widgets. Each tile displays a single <bpt id="p1">[</bpt>visualization<ept id="p1">](powerbi-service-visualizations-for-reports.md)</ept> that was created from a dataset and pinned to the dashboard. There are many ways to add tiles to your dashboard; too many to be covered in this overview topic. To learn more, see <bpt id="p1">[</bpt>Dashboard tiles in Power BI<ept id="p1">](powerbi-service-dashboard-tiles.md)</ept>. 

In the navigation bar, "your" dashboards are listed under the <bpt id="p1">**</bpt>Dashboards<ept id="p1">**</ept> heading. "Your" means that you have access to them, not necessarily that you created them. Each  dashboard represents a customized view of some subset of the underlying datasets.  If you own the dashboard, you'll also have access to the underlying dataset(s) and they'll appear in the navbar under <bpt id="p1">**</bpt>Datasets<ept id="p1">**</ept>.  If the dashboard was shared with you, it has a sharing icon <ph id="ph1">![](media/powerbi-service-basic-concepts/sharing-icon.png)</ph> next to it, and depending on how it was shared, you may or may not see the underlying datasets listed in your navbar.

><bpt id="p1">**</bpt>NOTE<ept id="p1">**</ept>: Pinning and tiles are covered in more detail below under the heading "Dashboard tiles."

<bpt id="p1">**</bpt>ONE<ept id="p1">**</ept> dashboard...
- can display visualizations from many different datasets
- can display visualizations from many different reports

![](media/powerbi-service-basic-concepts/Drawing1.png)

### Dig deeper:

<bpt id="p1">**</bpt>A dashboard can be <bpt id="p2">[</bpt>created from scratch<ept id="p2">](powerbi-service-create-a-dashboard.md)</ept><ept id="p1">**</ept> -- create a new blank dashboard and then get some data. 

<bpt id="p1">**</bpt>You, or a colleague, can create a dashboard and <bpt id="p2">[</bpt>share it<ept id="p2">](powerbi-service-share-unshare-dashboard.md)</ept><ept id="p1">**</ept> -  when you accept the invitation, the shared dashboard (and any associated report and dataset) is added to your navigation bar. 

<bpt id="p1">**</bpt>Sometimes dashboards are imported with the dataset or are created as you connect to the dataset<ept id="p1">**</ept>. For example, the <bpt id="p1">**</bpt>Get Data<ept id="p1">**</ept> wizard for Salesforce asks you if you'd like a dashboard and/or report to be created from the dataset. 

**Why do people create dashboards?**  Here are just some of the reasons:

-   to see, in one glance, all the information needed to make decisions
-   to monitor the most-important information about their business
-   to ensure all colleagues are on the same page, viewing and using the same information
-   to monitor the health of a business or product or business unit or marketing campaign, etc.
-   to create a personalized view of a larger dashboard -- all the metrics that matter to me

## My Workspace
We've circled back to your Power BI dashboard and workspace. Let's take a closer look at the pieces that make up the top-level page for Power BI service; we call it <bpt id="p1">**</bpt>My Workspace<ept id="p1">**</ept>.

![](media/powerbi-service-basic-concepts/completeNewer.png)

### 1. 

Use the navbar to move between the Power BI building blocks: dashboards, reports, and datasets.  

  ![](media/powerbi-service-basic-concepts/navpane-new.png)

-   Select <bpt id="p1">**</bpt>Get Data<ept id="p1">**</ept> to <bpt id="p2">[</bpt>add datasets to Power BI<ept id="p2">](powerbi-service-get-data.md)</ept>.

- Expand and collapse the navbar with this icon <ph id="ph1">![](media/powerbi-service-basic-concepts/expand-icon.png)</ph>.

-   Use <bpt id="p1">**</bpt>Search<ept id="p1">**</ept> to find specific items in the navbar.

-   Select a plus icon <ph id="ph1">![](media/powerbi-service-basic-concepts/pbi_Nancy_plus.png)</ph> to create a new dashboard or get a new dataset.

-   The listed <bpt id="p1">**</bpt>Dashboards, Reports,<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Datasets<ept id="p2">**</ept> are available for you to use.  Shared dashboards are read-only and display the shared icon <ph id="ph1">![](media/powerbi-service-basic-concepts/sharing-icon.png)</ph> .

-   Dashboard, report, and dataset names usually match the name of the underlying dataset file -- but you can <bpt id="p1">[</bpt>rename them<ept id="p1">](powerbi-service-rename-a-dashboard.md)</ept>.

-   Right-click a dashboard, report or dataset to display the context-sensitive menu. 

    ![](media/powerbi-service-basic-concepts/menu.png)


Single-click

-   a heading to collapse or expand it
-   a dashboard to display it
-   a report to open it in Reading View
-   a dataset to explore it

### 2. 

Dashboards are composed of <bpt id="p1">[</bpt>tiles<ept id="p1">](powerbi-service-dashboard-tiles.md)</ept>.  Tiles are created either in report Editing View or Q&amp;A. A special type of tile called a <bpt id="p1">[</bpt>widget<ept id="p1">](powerbi-service-add-a-widget-to-a-dashboard.md)</ept> is added directly onto the dashboard. The tiles that appear on a dashboard were specifically put there by a report creator/owner.  The act of adding a tile to a dashboard is called <bpt id="p1">*</bpt>pinning<ept id="p1">*</ept>.

![](media/powerbi-service-basic-concepts/canvas.png)

For more information, see <bpt id="p1">**</bpt>[Dashboards]<ept id="p1">**</ept> (above).

### 3. 

One way to explore your data is to ask a question and let Power BI Q&amp;A give you an answer, in the form of a visualization. Q&amp;A cannot be used to add content to a report -- only to add content, in the form of tiles, to dashboards.

Q&amp;A looks for an answer in the dataset(s) connected to the dashboard.  A connected dataset is one that has at least one tile pinned to that dashboard.

![](media/powerbi-service-basic-concepts/qna.png)

As soon as you start to type your question, Q&amp;A takes you to the Q&amp;A page. As you type, Q&amp;A helps you ask the right question and find the best answer with rephrasings, autofill, suggestions, and more. When you have a visualization (answer) you like, pin it to your dashboard. For more information, see <bpt id="p1">[</bpt>Q&amp;A in Power BI<ept id="p1">](powerbi-service-q-and-a.md)</ept>.

### 4. 

The icons in the top right corner are your resources for settings, downloads, getting help, and providing feedback to the Power BI team. Select the double arrow to open the dashboard in <bpt id="p1">**</bpt>Full screen<ept id="p1">**</ept> m.  

![](media/powerbi-service-basic-concepts/help-new.png)

### 5. 

It's not always easy to figure out which dashboard is active.  The dashboard title appears on the dashboard view page, on the Q&amp;A page, in report Editing View and report Reading View, and when you open a dataset.   

![](media/powerbi-service-basic-concepts/dash-title-new.png)

### 6. 

The app launcher is designed to help you get to your Office 365 apps.

![](media/powerbi-service-basic-concepts/basicconcepts2-newer.png)

### 7. 

Selecting this returns you to the dashboard that you viewed most recently.

   ![](media/powerbi-service-basic-concepts/version-new.png)

### 8. **Opciones**

This area of the workspace contains icons for interacting with the dashboard.  Besides <bpt id="p1">**</bpt>add widget<ept id="p1">**</ept> and <bpt id="p2">**</bpt>share dashboard<ept id="p2">**</ept> selecting the ellipses reveals options for duplicating, printing, and refreshing the dashboard and more.

   ![](media/powerbi-service-basic-concepts/options.png)

## Consulte también

[Get started with Power BI](powerbi-service-get-started.md)

[Power BI videos](powerbi-videos.md)

More questions? [Try the Power BI Community](http://community.powerbi.com/)

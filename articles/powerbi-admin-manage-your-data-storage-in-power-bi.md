<properties 
   pageTitle="Manage your data capacity in Power BI"
   description="Manage your data capacity and storage in Power BI"
   services="powerbi" 
   documentationCenter="" 
   authors="guyinacube" 
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
   ms.date="08/15/2016"
   ms.author="asaxton"/>
# Manage your data capacity in Power BI

Power BI offers two licenses, Power BI (free) and Power BI Pro, with different data capacity limits:

-   Free users have a maximum 1 GB data capacity.

-   Pro users of Power BI Pro have 10 GB maximum capacity.

-   Pro users can create groups, with a maximum 10 GB data capacity each.

At the tenant level, total usage can’t exceed 10 GB per Pro user across all Pro users and groups in the tenant. 

Read about other features of the <bpt id="p1">[</bpt>Power BI pricing model<ept id="p1">](https://powerbi.microsoft.com/pricing)</ept>.

Included in your data capacity are your own datasets and Excel reports, and those that someone has shared with you. Datasets are any of the data sources you’ve uploaded or connected to, including Power BI Desktop files and Excel workbooks you’re using. The following are also included in your data capacity.

-   Excel ranges pinned to dashboard.

-   Reporting Services on-premises visualizations pinned to a Power BI dashboard.

-   Uploaded images.

The size of a dashboard that you share will vary depending on what is pinned to it. For example, if you pin items from two reports that are part of two different datasets, the size will include both datasets.

<a name="manage"/>
## Manage items owned by you

See how much data capacity you’re using in your Power BI account, and manage your account.

1.  To manage your own storage, go to <bpt id="p1">**</bpt>My Workspace<ept id="p1">**</ept> at the top of the left navigation pane. 

    ![](media/powerbi-admin-manage-your-data-storage-in-power-bi/PBI_MyWorkspace.png)

2.  Select the gear icon <ph id="ph1">![](media/powerbi-admin-manage-your-data-storage-in-power-bi/PBI_GearIcon.png)</ph> in the upper-right corner <ph id="ph2">\&gt;</ph> <bpt id="p1">**</bpt>Manage Personal Storage<ept id="p1">**</ept>. 

    The top bar shows how much of your storage limit you’ve used.

    ![](media/powerbi-admin-manage-your-data-storage-in-power-bi/PBI_PersnlStorage.png)

    The datasets and reports are separated onto two tabs:

    <bpt id="p1">**</bpt>Owned by Me:<ept id="p1">**</ept> These are reports and datasets you’ve uploaded to your Power BI account, including service datasets such as Salesforce and Dynamics CRM.
    <bpt id="p1">**</bpt>Owned by Others:<ept id="p1">**</ept> Others have shared these reports and datasets with you.

3.  To delete a dataset or report, select the trash can icon <ph id="ph1">![](media/powerbi-admin-manage-your-data-storage-in-power-bi/PBI_DeleteIcon.png)</ph>.


Keep in mind that you or someone else may have reports and dashboards based on a dataset. If you delete the dataset, those reports and dashboards won’t work anymore.

## Manage your group

1.  Select the arrow next to <bpt id="p1">**</bpt>My Workspace<ept id="p1">**</ept> <ph id="ph1">\&gt;</ph> select the name of the group.

    ![](media/powerbi-admin-manage-your-data-storage-in-power-bi/PBI_GroupWorkspaces.png)

2.  Select the gear icon <ph id="ph1">![](media/powerbi-admin-manage-your-data-storage-in-power-bi/PBI_GearIcon.png)</ph> in the upper-right corner <ph id="ph2">\&gt;</ph> <bpt id="p1">**</bpt>Manage Group Storage<ept id="p1">**</ept>.

    The top bar shows how much of the group’s storage limit is used.

    ![](media/powerbi-admin-manage-your-data-storage-in-power-bi/PBI_GroupStorage.png)

    The datasets and reports are separated onto two tabs:

    <bpt id="p1">**</bpt>Owned by Us:<ept id="p1">**</ept> These are reports and datasets you or someone else has uploaded to the group’s Power BI account, including service datasets such as Salesforce and Dynamics CRM.
    <bpt id="p1">**</bpt>Owned by Others:<ept id="p1">**</ept> Others have shared these reports and datasets with your group.

3.  To delete a dataset or report, select the trash can icon <ph id="ph1">![](media/powerbi-admin-manage-your-data-storage-in-power-bi/PBI_DeleteIcon.png)</ph>.
    ><bpt id="p1">**</bpt>Note:<ept id="p1">**</ept> Any member of the group has permissions to delete datasets and reports from the group storage.

Keep in mind that you or someone else in the group may have reports and dashboards based on a dataset. If you delete the dataset, those reports and dashboards won’t work anymore.

## Dataset limits

There is a 1 GB limit, per dataset, that is imported into Power BI. If you have chosen to keep the Excel experience, instead of importing the data, you will be limited to 250 MB for the dataset.

## What happens when you hit a limit

When you hit the data capacity limit of what you can do, you will see prompts within the service. 

When you select the gear icon <ph id="ph1">![](media/powerbi-admin-manage-your-data-storage-in-power-bi/PBI_GearIcon.png)</ph>, you will see a red bar indicating you are over your data capacity limit.

![](media/powerbi-admin-manage-your-data-storage-in-power-bi/manage-storage-limit.png)

You will also see this indicated within <bpt id="p1">**</bpt>Manage personal storage<ept id="p1">**</ept>.

 ![](media/powerbi-admin-manage-your-data-storage-in-power-bi/manage-storage-limit2.png)
 
 When you try to perform an action that will hit one of the limits, you will see a prompt indicating you are over the limit. For free users, you will have an opportunity to try Pro. Both free and pro users will be able to <bpt id="p1">[</bpt>manage<ept id="p1">](#manage)</ept> their storage.
 
 **Free dialog**
 
 ![](media/powerbi-admin-manage-your-data-storage-in-power-bi/powerbi-free-over-limit.png)
 
 **Pro dialog** 
 
 ![](media/powerbi-admin-manage-your-data-storage-in-power-bi/powerbi-pro-over-limit.png)

 More questions? [Try the Power BI Community](http://community.powerbi.com/)
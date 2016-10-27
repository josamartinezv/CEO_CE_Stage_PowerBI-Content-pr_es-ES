<properties
   pageTitle="Administering Power BI in your organization"
   description="Administering Power BI in your organization"
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
   ms.date="09/16/2016"
   ms.author="asaxton"/>

# Administering Power BI in your organization

Microsoft Power BI enables users to visualize data, share discoveries, and collaborate in intuitive new ways. To learn more, see <bpt id="p1">[</bpt>Get started with Power BI<ept id="p1">](powerbi-service-get-started.md)</ept>.

Administration of Power BI can occur in several locations. Here are two common locations.

> [AZURE.NOTE] Your account needs to be marked as a <bpt id="p1">**</bpt>Global Admin<ept id="p1">**</ept>, within Office 365 or Azure Active Directory, to get access to the Power BI admin portal.

- [Power BI Admin portal](https://app.powerbi.com/admin-portal)
- [Office 365 Admin Center](https://portal.office.com/adminportal/home)

## What's in this article

**Sign up for Power BI**

- [How do users sign up for Power BI?](#how-do-users-sign-up-for-power-bi)

- [How do individual users in my organization sign up?](#how-do-individual-users-in-my-organization-sign-up)

- [How can I prevent users from joining my existing Office 365 tenant?](#how-can-i-prevent-users-from-joining-my-existing-office-365-tenant)

- [How can I allow users to join my existing Office 365 tenant?](#how-can-i-allow-users-to-join-my-existing-office-365-tenant)

- [How do I verify if I have the block on in the tenant?](#how-do-i-verify-if-i-have-the-block-on-in-the-tenant)

- [How can I prevent my existing users from starting to use Power BI?](#how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi)

- [How can I allow my existing users to sign up for Power BI?](#how-can-i-allow-my-existing-users-to-sign-up-for-power-bi)

**Administration of Power BI**

- [How will this change the way I manage identities for users in my organization today?](#how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today)

- [How do we manage Power BI?](#how-do-we-manage-power-bi)

- [What is the process to manage a tenant created by Microsoft for my users?](#what-is-the-process-to-manage-a-tenant-created-by-Microsoft-for-my-users)
   
- [If I have multiple domains, can I control the Office 365 tenant that users are added to?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to)

- [How do I remove Power BI for users that already signed up?](#how-do-i-remove-power-bi-for-users-that-already-signed-up)

- [How do I know when new users have joined my tenant?](#how-do-i-know-when-new-users-have-joined-my-tenant)

- [Are there any additional things I should be prepared for?](#are-there-any-additional-things-i-should-be-prepared-for)

- [Is this free? Will I be charged for these licenses?](#is-this-free-will-i-be-charged-for-these-licenses)

- [Where is my Power BI tenant located?](#where-is-my-power-bi-tenant-located)

**Security in Power BI**

- [Does Power BI meet national, regional, and industry-specific compliance requirements?](#does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements)

- [How does security work in Power BI?](#how-does-security-work-in-power-bi?)

## Sign up for Power BI

### How do users sign up for Power BI?

You can sign up for Power BI through the <bpt id="p1">[</bpt>Power BI web site<ept id="p1">](https://powerbi.microsoft.com)</ept>. You can also sign up through the purchase services page on the Office 365 admin center. When an administrator signs up for Power BI, they can assign user licenses to users who should have access.

Additionally, individual users in your organization may be able to sign up for Power BI through the <bpt id="p1">[</bpt>Power BI web site<ept id="p1">](https://powerbi.microsoft.com)</ept>. When a user in your organization signs up for Power BI, that user is assigned a Power BI license automatically. [Obtener más información](powerbi-service-self-service-signup-for-power-bi.md)

### How do individual users in my organization sign up?

There are three scenarios that might apply to users in your organization:

Scenario 1: Your organization already has an existing Office 365 environment and the user signing up for Power BI already has an Office 365 account.
In this scenario, if a user already has a work or school account in the tenant (for example, contoso.com) but does not yet have Power BI, Microsoft will simply activate the plan for that account, and the user will automatically be notified of how to use the Power BI service.

Scenario 2: Your organization has an existing Office 365 environment and the user signing up for Power BI doesn’t have an Office 365 account.
In this scenario, the user has an email address in your organization’s domain (for example, contoso.com) but does not yet have an Office 365 account. In this case, the user can sign up for Power BI and will automatically be given an account. This lets the user access the Power BI service. For example, if an employee named Nancy uses her work email address (for example, Nancy@contoso.com) to sign up, Microsoft will automatically add Nancy as a user in Contoso’s Office 365 environment and activate Power BI for that account.

Scenario 3: Your organization does not have an Office 365 environment connected to your email domain.
There are no administrative actions your organization needs to take to take advantage of Power BI. Users will be added to a new, cloud-only user directory, and you will have the option to elect to take over as the tenant admin and manage them.

> [AZURE.IMPORTANT] If your organization has multiple email domains and you prefer all email address extensions to be in the same tenant, add all email address domains to an Azure Active Directory tenant before any users sign up. There is no automated mechanism to move users across tenants after they have been created. For more information on this process, see <bpt id="p1">[</bpt>If I have multiple domains, can I control the Office 365 tenant that users are added to?<ept id="p1">](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to)</ept> later in this article and <bpt id="p2">[</bpt>Add your domain to Office 365<ept id="p2">](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</ept> online.

### How can I prevent users from joining my existing Office 365 tenant?

There are steps you can take, as an admin, to prevent users from joining your existing Office 365 tenant. If you do block this, users’ attempts to sign up will fail and they will be directed to contact their organization’s admin. You do not need to repeat this process if you have already disabled automatic license distribution (e.g. Office 365 for Education for Students, Faculty, and Staff).

These steps require the use of Windows PowerShell. To get started with Windows PowerShell, see the <bpt id="p1">[</bpt>PowerShell getting started guide<ept id="p1">](http://go.microsoft.com/fwlink/p/?LinkID=286814)</ept>.

To perform the following steps, you must install the latest 64-bit version of the <bpt id="p1">[</bpt>Azure Active Directory Module for Windows PowerShell<ept id="p1">](http://go.microsoft.com/fwlink/p/?LinkID=236297)</ept>.

After you select the link, select <bpt id="p1">**</bpt>Run<ept id="p1">**</ept> to run the installer package.

<bpt id="p1">**</bpt>Disable automatic tenant join<ept id="p1">**</ept>: Use this Windows PowerShell command to prevent new users from joining a managed tenant:

- To disable automatic tenant join for new users:

    Set-MsolCompanySettings -AllowEmailVerifiedUsers $false

- To enable automatic tenant join for new users:

    Set-MsolCompanySettings -AllowEmailVerifiedUsers $true

> [AZURE.NOTE] This blocking prevents new users in your organization from signing up for Power BI. Users that sign up for Power BI prior to disabling new signups for your organization will still retain their licenses. See the [How Can I Remove Licenses?] section for instructions on how you can remove access to Power BI for users that had previously signed up for the service.

### How can I allow users to join my existing Office 365 tenant?

To allow users to join your tenant, run the opposite command as described in the question above:

    Set-MsolCompanySettings -AllowEmailVerifiedUsers $true

### How do I verify if I have the block on in the tenant?

Use the following PowerShell script:

    Get-MsolCompanyInformation | fl allow*

### How can I prevent my existing users from starting to use Power BI?

There are steps you can take, as an admin, to prevent users from signing up for Power BI. If you do block this, users’ attempts to sign up will fail and they will be directed to contact their organization’s admin. You do not need to repeat this process if you have already disabled automatic license distribution (e.g. Office 365 for Education for Students, Faculty, and Staff). [Obtener más información](powerbi-admin-powerbi-free-in-your-organization.md#enable-or-disable-individual-user-sign-up-in-Azure-Active-Directory)

> [AZURE.NOTE] The AllowAdHocSubscriptions flag is used to control several user capabilities in your organization, including the ability for users to sign up for the Azure Rights Management Service. Changing this flag will affect all of these capabilities.

### How can I allow my existing users to sign up for Power BI?

To allow your existing users to sign up for Power BI, run the command listed for the above question, but pass true instead of false. [Obtener más información](powerbi-admin-powerbi-free-in-your-organization.md#enable-or-disable-individual-user-sign-up-in-Azure-Active-Directory)

## Administration of Power BI

### How will this change the way I manage identities for users in my organization today?

If your organization already has an existing Office 365 environment and all users in your organization have Office 365 accounts, identity management will not change.

If your organization already has an existing Office 365 environment but not all users in your organization have Office 365 accounts, we will create a user in the tenant and assign licenses based on the user’s work, or school, email address. This means that the number of users you are managing at any particular time will grow as users in your organization sign up for the service.

If you are managing your directory on-premises, and use Active Directory Federation Services (AD FS), Microsoft will not add users to your tenant, and users attempting to join your tenant will receive a message to contact their organization’s admin.

If your organization does not have an Office 365 environment connected to your email domain, there will be no change in how you manage identity. Users will be added to a new, cloud-only user directory, and you will have the option to elect to take over as the tenant admin and manage them.

### How do we manage Power BI?

Power BI provides an admin portal that allows you to view usage statistics, provides a link to the Office 365 admin center to manage users and groups, and the ability to control tenant wide settings. 

> [AZURE.NOTE] Your account needs to be marked as a <bpt id="p1">**</bpt>Global Admin<ept id="p1">**</ept>, within Office 365 or Azure Active Directory, to get access to the Power BI admin portal.

For more information, see <bpt id="p1">[</bpt>Power BI Admin Portal<ept id="p1">](powerbi-admin-portal.md)</ept>.

### What is the process to manage a tenant created by Microsoft for my users?

If a tenant was created by Microsoft, you can claim and manage that tenant by following these steps:

1. Join the tenant, by signing up for Power BI, using an email address domain that matches the tenant domain you want to manage. For example, if Microsoft created the contoso.com tenant, you will need to join the tenant with an email address ending with @contoso.com.

2. Claim admin control by verifying domain ownership: once you are in the tenant, you can promote yourself to a <bpt id="p1">*</bpt>Global Admin<ept id="p1">*</ept> role by verifying domain ownership. Para hacerlo, siga estos pasos:

    1. Go to <bpt id="p1">[</bpt>https://portal.office.com<ept id="p1">](https://portal.office.com)</ept>.

    2. Select the app launcher icon in the upper-left and choose <bpt id="p1">**</bpt>Admin<ept id="p1">**</ept>.

    3. Read the instructions on the <bpt id="p1">**</bpt>Become the admin<ept id="p1">**</ept> page and then choose <bpt id="p2">**</bpt>Yes, I want to be the admin<ept id="p2">**</ept>.

    > [AZURE.NOTE] If this option doesn’t appear, there is already an Office 365 administrator in place.
    
### If I have multiple domains, can I control the Office 365 tenant that users are added to?

If you do nothing, a tenant will be created for each user email domain and subdomain.

If you want all users to be in the same tenant regardless of their email address extensions:

- Create a target tenant ahead of time, or use an existing tenant, and add all the existing domains and subdomains that you want consolidated within that tenant. Then all the users with email addresses ending in those domains and subdomains will automatically join the target tenant when they sign up.

> [AZURE.IMPORTANT] There is no supported automated mechanism to move users across tenants once they have been created. To learn about adding domains to a single Office 365 tenant, see <bpt id="p1">[</bpt>Add your users and domain to Office 365<ept id="p1">](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</ept>.

### How do I remove Power BI for users that already signed up?

If a user signed up for Power BI, but you no longer want them to have access to Power BI, you can remove the Power BI license for that user.

1. Navigate to the Office 365 admin center.

2. In the left navigation bar, select <bpt id="p1">**</bpt>Users<ept id="p1">**</ept><ph id="ph1"> &gt; </ph><bpt id="p2">**</bpt>Active Users<ept id="p2">**</ept>.

3. Find the user you want to remove the license for, then select their name &gt; <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept>.

4. On the user details page, select <bpt id="p1">**</bpt>Licenses<ept id="p1">**</ept> in the left navigation bar.

5. Uncheck <bpt id="p1">**</bpt>Power BI (free)<ept id="p1">**</ept>, or <bpt id="p2">**</bpt>Power BI Pro<ept id="p2">**</ept>, depending on what license is applied to their account.

6. Select <bpt id="p1">**</bpt>Save<ept id="p1">**</ept>.

> [AZURE.NOTE] You can perform bulk license management to users as well. To do that, select multiple users and select <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept>.

### How do I know when new users have joined my tenant?

Users who have joined your tenant as part of this program are assigned a unique license that you can filter on within your active user pane in the admin dashboard.

To create this new view, in the Office 365 admin center, go to <bpt id="p1">**</bpt>Users<ept id="p1">**</ept><ph id="ph1"> &gt; </ph><bpt id="p2">**</bpt>Active Users<ept id="p2">**</ept>, and on the <bpt id="p3">**</bpt>Select a View<ept id="p3">**</ept> menu, select <bpt id="p4">**</bpt>New View<ept id="p4">**</ept>. Name your new view, and under <bpt id="p1">**</bpt>Assigned license<ept id="p1">**</ept>, select <bpt id="p2">**</bpt>Power BI (free)<ept id="p2">**</ept> or <bpt id="p3">**</bpt>Power BI Pro<ept id="p3">**</ept>. You can only have one license selected per view. If you have both <bpt id="p1">**</bpt>Power BI (free)<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Power BI Pro<ept id="p2">**</ept> licenses in your organization, you would need to create two views. Once the new view has been created, you will be able to see all the users in your tenant who have enrolled in this program.

### Are there any additional things I should be prepared for?

You might experience an increase in password reset requests. For information about this process, see <bpt id="p1">[</bpt>Reset a user's password<ept id="p1">](https://support.office.com/article/Reset-a-users-password-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)</ept>.

You can remove a user from your tenant via the standard process in the Office 365 admin center. However, if the user still has an active email address from your organization, they will be able to rejoin unless you block all users from joining.

### Is this free? Will I be charged for these licenses?

The <bpt id="p1">**</bpt>Power BI (free)<ept id="p1">**</ept> licenses are for the free version of Power BI. If you're interested in additional capabilities, take a look at the <bpt id="p1">[</bpt>Power BI Pro version<ept id="p1">](powerbi-power-bi-pro-content-what-is-it.md)</ept>.

### Where is my Power BI tenant located?

To learn how to find where your Power BI tenant is located, also known as a data region, see <bpt id="p1">[</bpt>Where is my Power BI tenant located?<ept id="p1">](powerbi-admin-where-is-my-tenant-located.md)</ept>

## Security in Power BI

### Does Power BI meet national, regional, and industry-specific compliance requirements?

To learn more about Power BI compliance, see the <bpt id="p1">[</bpt>Microsoft Trust Center<ept id="p1">](http://go.microsoft.com/fwlink/?LinkId=785324)</ept>.

### How does security work in Power BI?

Power BI is built on the foundation of Office 365, which in turn builds on Azure services like Azure Active Directory. For an overview of Power BI architecture, see <bpt id="p1">[</bpt>Power BI Security<ept id="p1">](powerbi-admin-power-bi-security.md)</ept>. 

## Consulte también

[Power BI admin portal](powerbi-admin-portal.md)  
[Self-service sign up for Power BI](powerbi-service-self-service-signup-for-power-bi.md)  
[Power BI (free) in your organization](powerbi-admin-powerbi-free-in-your-organization.md)  
[Purchasing Power BI Pro](powerbi-admin-purchasing-power-bi-pro.md)  
[Office 365 user account management](https://technet.microsoft.com/library/office-365-user-account-management.aspx)  
[Office 365 group management](https://support.office.com/Article/Find-help-about-Groups-in-Office-365-7a9b321f-b76a-4d53-b98b-a2b0b7946de1)  
<bpt id="p1">[</bpt>Manage your group in Power BI and Office 365<ept id="p1">](powerbi-service-manage-your-group-in-power-bi-and-office-365.md)</ept> More questions? [Try the Power BI Community](http://community.powerbi.com/)
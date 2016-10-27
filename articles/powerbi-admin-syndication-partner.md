<properties
pageTitle="Unable to add Power BI to O365 partner"
description="Unable to add Power BI to an Office 365 syndication partner. The syndicated model is a purchasing model used by Office 365."
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
ms.tgt_pltfrm="na"
ms.workload="powerbi"
ms.date="08/15/2016"
ms.author="asaxton"/>
# Unable to add Power BI to Office 365 partner subscription

Office 365 allows companies to resell Office 365 bundled and integrated with their own solutions, providing end-customers with a single point of contact for purchasing, billing, and support.

If you are interested in acquiring Power BI, alongside your Office 365 subscription, we recommend you contact your partner to do so. If your partner does not offer Power BI, you have different options you can consider.

1. You are able to buy the service from another channel, either directly from Microsoft or another partner. This option is not available to all customers depending on their relationship with the partner. You can verify this by going to the <bpt id="p1">**</bpt>Office 365 Admin Portal<ept id="p1">**</ept><ph id="ph1"> &gt; </ph><bpt id="p2">**</bpt>Billing<ept id="p2">**</ept><ph id="ph2"> &gt; </ph><bpt id="p3">**</bpt>Subscriptions<ept id="p3">**</ept>. If you do see <bpt id="p1">**</bpt>Subscriptions<ept id="p1">**</ept>, you can acquire the service from Microsoft directly, or you can also contact a partner that is offering Power BI.

    ![](media/powerbi-admin-syndication-partner/billingsub.png)

2.  If you do not see <bpt id="p1">**</bpt>Subscriptions<ept id="p1">**</ept> listed under <bpt id="p2">**</bpt>Billing<ept id="p2">**</ept>, you cannot buy from Microsoft directly or another partner. 

    ![](media/powerbi-admin-syndication-partner/billing.png)

If you are not able to purchase Power BI directly, and depending on what type of Power BI subscription you are interested in, you still have some options.

[Power BI (free)](#power-bi-free)

[Power BI Pro](#power-bi-pro)

## Power BI (free)

If you are happy with the free offering for Power BI, you can sign up for the free service. By default, individual sign-ups, also known as ad-hoc subscriptions, are disabled. When you try to sign up for Power BI, you will see a message indicating that your IT department has turned off sign up for Microsoft Power BI.

    Your IT department has turned off signup for Microsoft Power BI.

![](media/powerbi-admin-syndication-partner/sorry.png)

To enable ad-hoc subscriptions, you can contact your partner and request that they turn it on. If you are an Administrator of your tenant, and know how to leverage Azure Active Directory PowerShell commands, you can enable ad-hoc subscriptions yourself. [Obtener más información](https://technet.microsoft.com/library/jj151815.aspx)

1. You need to first sign into Azure Active Directory using your Office 365 credential. The first line will prompt you for your credentials. The second line connects to Azure Active Directory.

        $msolcred = get-credential
        connect-msolservice -credential $msolcred

    ![](media/powerbi-admin-syndication-partner/aad-signin.png)

2. Once you are signed in, you can issue the following command to enable free sign ups.

        Set-MsolCompanySettings -AllowAdHocSubscriptions $true


## Power BI Pro

If you want to buy a subscription to Power BI Pro, you will have to work with your partner to consider what options you have.

- Your partner agrees to add Power BI to their portfolio so that you can purchase from them.
- Your partner is able to transition you to a model where you can buy Power BI directly from Microsoft or another partner who offers Power BI.

This video looks at Office 365 syndication and purchasing Power BI:

<iframe width="560" height="315" src="https://www.youtube.com/embed/C357phT94A8" frameborder="0" allowfullscreen></iframe>

## Consulte también

[Administrar Azure AD mediante Windows PowerShell](https://technet.microsoft.com/library/jj151815.aspx)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)

<properties
pageTitle="Configuring proxy settings for the On-premises Data Gateway"
description="Information regarding configuration of proxy settings for the on-premises data gateway."
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
ms.tgt_pltfrm="na"
ms.workload="powerbi"
ms.date="10/01/2016"
ms.author="asaxton"/>
# Configuring proxy settings for the On-premises Data Gateway

Your work environment may require that you go through a proxy to access the internet. This could prevent the On Premises Data Gateway from connecting to the service.

## Does your network use a proxy?

The following post on superuser.com discusses how you can try to determine if you have a proxy on your network.

[How do I know what proxy server I'm using? (SuperUser.com)](https://superuser.com/questions/346372/how-do-i-know-what-proxy-server-im-using)

## Configuration file location and default configuration

Proxy information is configured within a .NET configuration file. The location, and file names, will be different depending on the gateway you are using.

### On-premises data gateway

There are two main configuration files that are involved with the on-premises data gateway.

**Configuración**

The first is for the configuration screens that actually configure the gateway. If you are having issues configuring the gateway, this is the file you will want to look at.

    C:\Program Files\On-premises data gateway\enterprisegatewayconfigurator.exe.config

**Servicio de Windows**

The second is for the actual windows service that interacts with the Power BI service, and handles the requests.

    C:\Program Files\On-premises data gateway\Microsoft.PowerBI.EnterpriseGateway.exe.config

### Power BI Gateway - Personal

The personal gateway can be installed in one of two ways. As a windows service (admin) or as a user mode application. This is determined during installation. As a result, your configuration files may be in one of two locations depending on how the gateway was installed. You will want to check both locations.

**Configuración**

The first is for the configuration screens that actually configure the gateway. If you are having issues configuring the gateway, this is the file you will want to look at.

For the <bpt id="p1">*</bpt>windows service<ept id="p1">*</ept>, it will be the following.

    C:\Program Files\Power BI Personal Gateway\1.0\Configurator\GWConfig.exe.config
    C:\Program Files\Power BI Personal Gateway\1.0\Configurator\PowerBIGatewayAgentCmdLine.exe.config

For the <bpt id="p1">*</bpt>user mode application<ept id="p1">*</ept>, it will be the following.

    C:\Users\<user>\AppData\Local\Power BI Gateway - Personal \1.0\Configurator\GWConfig.exe.config
    C:\Users\<user>\AppData\Local\Power BI Gateway - Personal \1.0\Configurator\PowerBIGatewayAgentCmdLine.exe.config

**Servicio de Windows**

The second is for the actual windows service that interacts with the Power BI service, and handles the requests.

For the <bpt id="p1">*</bpt>windows service<ept id="p1">*</ept>, it will be the following.

    C:\Program Files\Power BI Personal Gateway\1.0\Gateway\diawp.exe.config

For the <bpt id="p1">*</bpt>user mode application<ept id="p1">*</ept>, it will be the following.

    C:\Users\<user>\AppData\Local\Power BI Gateway - Personal \1.0\Gateway\diawp.exe.config

## Configuración de los ajustes del proxy

The default proxy configuration is the following.

    <system.net>
        <defaultProxy useDefaultCredentials="true" />
    </system.net>

The default configuration works with windows authentication. If your proxy uses another form of authentication, you will need to change the settings. If you are not sure, you should contact your network administrator.

To learn more about the configuration of the proxy elements for .NET configuration files, see <bpt id="p1">[</bpt>defaultProxy Element (Network Settings)<ept id="p1">](https://msdn.microsoft.com/library/kd3cf2ex.aspx)</ept>

## Changing the gateway service account to a domain user

When configuring the proxy settings to use default credentials, as explained above, you may encounter authentication issues with your proxy. This is because the default service account is the Service SID and not an authenticated domain user. You can change the service account of the gateway to allow proper authentication with your proxy.

> [AZURE.NOTE] It is recommended that you use a managed service account to avoid having to reset passwords. Learn how to create a <bpt id="p1">[</bpt>managed service account<ept id="p1">](https://technet.microsoft.com/library/dd548356.aspx)</ept> within Active Directory.

### Change the On-Premises Data Gateway service account

1. Change the Windows service account for the <bpt id="p1">**</bpt>On-premises Data Gateway service<ept id="p1">**</ept>. 

    The default account for this service is <bpt id="p1">*</bpt>NT SERVICE\PBIEgwService<ept id="p1">*</ept>. You will want to change this to a domain user account within your Active Directory domain. Or, you will want to use a managed service account to avoid having to change the password.

    You will want to change the account on the <bpt id="p1">**</bpt>Log On<ept id="p1">**</ept> tab within the properties of the Windows service.

2. Restart the <bpt id="p1">**</bpt>On-premises Data Gateway service<ept id="p1">**</ept>.

    From an admin command prompt, issue the following commands.

        net stop PBIEgwService

        net start PBIEgwService

3. Start the <bpt id="p1">**</bpt>On-premises Data Gateway configurator<ept id="p1">**</ept>. You can select the windows start button and search for <bpt id="p1">*</bpt>On-premises Data Gateway<ept id="p1">*</ept>.

4. Sign in to Power BI.

5. Restore the gateway using your recovery key.

    This will allow the new service account to be able to decrypt stored credentials for data sources.

## Consulte también

[Firewall information](powerbi-gateway-onprem-tshoot.md#firewall-or-proxy)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)
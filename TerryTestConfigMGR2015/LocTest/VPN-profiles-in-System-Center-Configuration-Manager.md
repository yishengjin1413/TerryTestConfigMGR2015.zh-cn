---
title: "System Center Configuration Manager 中的 VPN 配置文件"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-other
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: c0f094f1-852e-4606-91db-97846d8f0772
caps.latest.revision: 6
caps.handback.revision: 3
translationtype: Human Translation
---
# System Center Configuration Manager 中的 VPN 配置文件
使用 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的 VPN 配置文件以将 VPN 设置部署到机构中的用户。 通过部署这些设置，你可以最大限度减少最终用户连接到公司网络资源需要进行的工作。  
  
 例如，你想要用连接到公司网络上的文件共享所需的设置来设置所有运行 IOS 操作系统的设备。 你可以创建一个 VPN 配置文件，在其中包含连接到公司网络所需的设置，然后将此配置文件部署到你的层次结构中使用运行 IOS 的设备的所有用户。 IOS 设备用户可在可用网络列表中看到 VPN 连接，并可通过最少量的工作连接到此网络。  
  
 你可以使用 VPN 配置文件配置下列设备类型：  
  
-   运行 Windows 8.1 32 位的设备  
  
-   运行 Windows 8.1 64 位的设备  
  
-   运行 Windows RT 8.1 的设备  
  
-   运行 Windows Phone 8.1 的设备  
  
-   运行 iOS 5、iOS 6、iOS 7 和 iOS 8 的设备  
  
-   运行 Android 4.0 和更高版本的设备  
  
> [!IMPORTANT]  
>  若要将配置文件部署到 iOS、Android、Windows Phone 和注册的 Windows 8.1 设备，则必须将该设备注册到 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)]。 有关如何注册设备的信息，请参阅[使用 Microsoft Intune 管理移动设备](https://technet.microsoft.com/en-us/library/dn646962.aspx)。  
  
 在创建 VPN 配置文件时，你可以纳入各种各样的安全设置，其中包括已通过使用 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 证书配置文件设置的服务器验证和客户端身份验证证书。 有关证书配置文件的详细信息，请参阅 [System Center Configuration Manager 中的证书配置文件](../LocTest/Certificate-profiles-in-System-Center-Configuration-Manager.md)。  
  
## 本节内容  
 使用下列主题来帮助你规划、配置、操作和维护 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的 VPN 配置文件。  
  
-   [System Center Configuration Manager 中 VPN 配置文件的先决条件](../LocTest/Prerequisites-for-VPN-profiles-in-System-Center-Configuration-Manager.md)  
  
-   [System Center Configuration Manager 中 VPN 配置文件的操作和维护](../LocTest/Operations-and-maintenance-for-VPN-profiles-in-System-Center-Configuration-Manager.md)  
  
-   [System Center Configuration Manager 中 VPN 配置文件的安全和隐私](../LocTest/Security-and-privacy-for-VPN-profiles-in-System-Center-Configuration-Manager.md)
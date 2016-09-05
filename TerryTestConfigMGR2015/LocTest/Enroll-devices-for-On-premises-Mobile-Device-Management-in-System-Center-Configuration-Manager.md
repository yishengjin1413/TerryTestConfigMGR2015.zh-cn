---
title: "在 System Center Configuration Manager 中为本地移动设备管理注册设备"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-client
ms.tgt_pltfrm: na
ms.topic: get-started-article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: b58472e3-31a5-4305-8eb6-2522befebe02
caps.latest.revision: 6
caps.handback.revision: 5
translationtype: Human Translation
---
# 在 System Center Configuration Manager 中为本地移动设备管理注册设备
若要使用 [!INCLUDE[onprem_first](../LocTest/includes/onprem_first_md.md)] 管理计算机和设备，设备需要先进行注册以便 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 能够与管理任务的设备通信。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 提供了两种注册设备的方法：  
  
-   “用户注册” \- 在这种方法中，用户启动其设备上的注册过程。 为了使用户注册成功，必须在设备上安装受信任的根证书且用户必须设置为由 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 进行注册。  若要注册设备，用户只需提供工作凭据，设备就被注册为可管理状态。  
  
     有关详细信息，请参阅[用户如何在 System Center Configuration Manager 中向本地移动设备管理注册设备](../LocTest/How-users-enroll-devices-with-On-premises-Mobile-Device-Management-in-System-Center-Configuration-Manager.md)。  
  
-   “批量注册” \- 这种方法中，设备用户不需要启动注册。 取而代之的是在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 内创建批量注册程序包，然后将其放置到设备上并打开。 打开时，此包提供注册设备所需的信息。  
  
     有关详细信息，请参阅[如何在 System Center Configuration Manager 中向本地移动设备管理批量注册设备](../LocTest/How-to-bulk-enroll-devices-with-On-premises-Mobile-Device-Management-in-System-Center-Configuration-Manager.md)。  
  
 [!INCLUDE[onprem_devices](../LocTest/includes/onprem_devices_md.md)]   
## 请参阅  
 [在 System Center Configuration Manager 中使用本地基础结构管理移动设备](../LocTest/Manage-mobile-devices-with-on-premises-infrastructure-in-System-Center-Configuration-Manager.md)
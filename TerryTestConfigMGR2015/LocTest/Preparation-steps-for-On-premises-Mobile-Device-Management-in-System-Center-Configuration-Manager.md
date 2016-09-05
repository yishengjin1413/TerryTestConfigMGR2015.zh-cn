---
title: "用于 System Center Configuration Manager 中本地移动设备管理的准备步骤"
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
ms.assetid: 1ef60106-8f31-46d6-95a6-25a6495f22c7
caps.latest.revision: 4
caps.handback.revision: 3
translationtype: Human Translation
---
# 用于 System Center Configuration Manager 中本地移动设备管理的准备步骤
使用 [!INCLUDE[onprem_first](../LocTest/includes/onprem_first_md.md)] 管理设备需要设置 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 基础结构，以便所需的站点系统角色（注册代理点、注册点、设备管理点和分发点）可以跨整个受信任通道与要管理的移动设备进行通信。  
  
 要准备 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 系统，需要执行以下高级任务：  
  
-   [在 System Center Configuration Manager 中为本地移动设备管理设置 Microsoft Intune 订阅](../LocTest/Set-up-a-Microsoft-Intune-subscription-for-On-premises-Mobile-Device-Management-in-System-Center-Configuration-Manager.md)  
  
     在此任务中，注册 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)]，然后通过 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台将订阅添加到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]。 此步骤仅需用于许可授权的目的。[!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 不用于管理设备或存储管理信息。 所有设备的协调和管理均由你组织的企业通过使用本地 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 基础结构实施。  
  
-   [在 System Center Configuration Manager 中为本地移动设备管理安装站点系统角色](../LocTest/Install-site-system-roles-for-On-premises-Mobile-Device-Management-in-System-Center-Configuration-Manager.md)  
  
     在此任务中，安装和配置使用本地 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 基础结构管理设备所需的站点系统角色。[!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 至少需要注册代理点、注册点、设备管理点和分发点这些站点系统角色。  
  
-   [为 System Center Configuration Manager 中的本地移动设备管理的受信任通信设置证书](../LocTest/Set-up-certificates-for-trusted-communications-for-On-premises-Mobile-Device-Management-in-System-Center-Configuration-Manager.md)  
  
     在本任务中，配置本地 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 基础结构，以允许被管理的设备和托管所需站点系统角色的服务器之间能够进行受信任的通信 \(HTTPS\)。  
  
-   [为 System Center Configuration Manager 中的本地移动设备管理设置设备注册](../LocTest/Set-up-device-enrollment-for-On-premises-Mobile-Device-Management-in-System-Center-Configuration-Manager.md)  
  
     在此任务中，向用户授予注册计算机和设备的权限，并在设备（通常是未加入域的设备）上安装受信任的根证书，以允许 HTTPS 连接到站点系统服务。  
  
## 请参阅  
 [在 System Center Configuration Manager 中使用本地基础结构管理移动设备](../LocTest/Manage-mobile-devices-with-on-premises-infrastructure-in-System-Center-Configuration-Manager.md)
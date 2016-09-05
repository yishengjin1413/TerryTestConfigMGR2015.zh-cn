---
title: "使用多播与 System Center Configuration Manager 一起通过网络部署 Windows"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-osd
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 4cafb7fc-380b-41b1-b83e-045aebfb7131
caps.latest.revision: 13
caps.handback.revision: 12
translationtype: Human Translation
---
# 使用多播与 System Center Configuration Manager 一起通过网络部署 Windows
在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 环境中，多个客户端可能会同时下载同一个操作系统映像，而多播是一种可以在此环境中使用的网络优化方法。 在使用多播时，多台计算机同时下载操作系统映像，这是因为分发点多播此映像，而不是通过单独的连接将此数据的副本发送给每个客户端。  
  
 通过在以下操作系统部署方案中使用多播，你可以通过网络部署操作系统：  
  
-   [通过 System Center Configuration Manager，使用新版本的 Windows 刷新现有的计算机](../LocTest/Refresh-an-existing-computer-with-a-new-version-of-Windows-using-System-Center-Configuration-Manager.md)  
  
-   [使用 System Center Configuration Manager 在新计算机（裸机）上安装新版本的 Windows](../LocTest/Install-a-new-version-of-Windows-on-a-new-computer--bare-metal--with-System-Center-Configuration-Manager.md)  
  
 完成其中一个操作系统部署方案中的步骤，然后使用以下部分来支持多播。  
  
##  <a name="BKMK_Configure"></a> 配置分发点以支持多播  
 若要在部署操作系统时使用多播，必须将分发点配置为支持多播。 有关详细信息，请参阅 [配置分发点以支持多播](../LocTest/Prepare-site-system-roles-for-operating-system-deployments-with-System-Center-Configuration-Manager.md#BKMK_DPMulticast)。  
  
## 为多播部署准备操作系统映像  
 要将操作系统映像包配置为支持多播，请参阅 [Prepare the operating system image for multicast deployments](../LocTest/Manage-operating-system-images-with-System-Center-Configuration-Manager.md#BKMK_OSImageMulticast).  
  
##  <a name="BKMK_Deploy"></a> 部署任务序列  
 将操作系统部署到目标集合。 有关详细信息，请参阅 [部署任务序列](../LocTest/Manage-task-sequences-to-automate-tasks-in-System-Center-Configuration-Manager.md#BKMK_DeployTS)。  
  
## 请参阅  
 [使用 System Center Configuration Manager 部署企业版操作系统的方法](../LocTest/Methods-to-deploy-enterprise-operating-systems-using-System-Center-Configuration-Manager.md)
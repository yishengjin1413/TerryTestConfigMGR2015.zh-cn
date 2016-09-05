---
title: "使用可启动媒体与 System Center Configuration Manager 一起通过网络部署 Windows"
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
ms.assetid: 999b5409-7e72-48d2-8554-4d44427ce383
caps.latest.revision: 5
caps.handback.revision: 4
---
# 使用可启动媒体与 System Center Configuration Manager 一起通过网络部署 Windows
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的可启动媒体部署允许在启动目标计算机时部署操作系统。 在目标计算机启动时，它从网络中检索任务序列、操作系统映像包和任何其他必需的内容。 由于媒体上未包括该内容，因此，你无需重新创建媒体就能更新内容。  
  
 通过在以下操作系统部署方案中使用多播，你可以通过网络部署操作系统：  
  
-   [通过 System Center Configuration Manager，使用新版本的 Windows 刷新现有的计算机](../LocTest/Refresh-an-existing-computer-with-a-new-version-of-Windows-using-System-Center-Configuration-Manager.md)  
  
-   [使用 System Center Configuration Manager 在新计算机（裸机）上安装新版本的 Windows](../LocTest/Install-a-new-version-of-Windows-on-a-new-computer--bare-metal--with-System-Center-Configuration-Manager.md)  
  
-   [使用 System Center Configuration Manager 替换现有计算机和传输设置](../LocTest/Replace-an-existing-computer-and-transfer-settings-with-System-Center-Configuration-Manager.md)  
  
 完成其中一个操作系统部署方案中的步骤，然后运行以下部分来使用可启动媒体部署操作系统。  
  
## 配置部署设置  
 当你使用可启动媒体来启动操作系统部署过程时，必须配置该部署才能使操作系统对媒体可用。 可以在“部署软件向导”的“部署设置”页面或部署属性的“部署设置”选项卡上配置这一选项。  对于“可用于以下项目”设置，请配置下述内容之一：  
  
-   **Configuration Manager 客户端、媒体和 PXE**  
  
-   **仅媒体和 PXE**  
  
-   **仅媒体和 PXE（隐藏）**  
  
## 创建可启动媒体  
 你可以指定可启动媒体是 U 盘还是 CD\/DVD 集。 将启动媒体的计算机必须支持选为可启动驱动器的选项。 有关详细信息，请参阅[使用 System Center Configuration Manager 创建可启动媒体](../LocTest/Create-bootable-media-with-System-Center-Configuration-Manager.md)。  
  
##  <a name="BKMK_Deploy"></a> 从可启动媒体安装操作系统  
 在计算机的可启动驱动器中插入可启动媒体，然后再启动它以安装操作系统。  
  
## 请参阅  
 [使用 System Center Configuration Manager 部署企业版操作系统的方法](../LocTest/Methods-to-deploy-enterprise-operating-systems-using-System-Center-Configuration-Manager.md)
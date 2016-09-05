---
title: "使用软件中心与 System Center Configuration Manager 一起通过网络部署 Windows"
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
ms.assetid: 919e3636-53fe-4119-ad14-2d03702b391b
caps.latest.revision: 5
caps.handback.revision: 5
translationtype: Human Translation
---
# 使用软件中心与 System Center Configuration Manager 一起通过网络部署 Windows
可将要在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中安装操作系统的任务序列设置为在软件中心中可用。 你可以在以下操作系统部署方案中将操作系统部署到软件中心：  
  
-   [通过 System Center Configuration Manager，使用新版本的 Windows 刷新现有的计算机](../LocTest/Refresh-an-existing-computer-with-a-new-version-of-Windows-using-System-Center-Configuration-Manager.md)  
  
-   [使用 System Center Configuration Manager 将 Windows 升级到最新版本](../LocTest/Upgrade-Windows-to-the-latest-version-with-System-Center-Configuration-Manager.md)  
  
 完成其中一个操作系统部署方案中的步骤，然后运行以下部分来准备在软件中心中可用的部署。  
  
## 配置部署设置  
 当要将操作系统部署设置为在软件中心可用时，必须配置该部署才能使操作系统对 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端可用。 可以在“部署软件向导”的“部署设置”  页面或部署属性的“部署设置”  选项卡上配置这一选项。  对于“可用于以下项目”  设置，请配置“仅 Configuration Manager 客户端”  或“Configuration Manager 客户端、媒体和 PXE” 。 在部署操作系统后，它将在目标集合成员的软件中心内显示。  
  
##  <a name="BKMK_Deploy"></a> 将任务序列部署到计算机  
 将操作系统部署到目标集合。 有关详细信息，请参阅 [Deploy a task sequence](../LocTest/Manage-task-sequences-to-automate-tasks-in-System-Center-Configuration-Manager.md#BKMK_DeployTS)。 在为软件中心部署操作系统时，你可以将部署配置为必需或可用。  
  
-   **必需部署**：必需部署将使操作系统在软件中心可用，但会按配置的分配计划自动启动。  
  
-   **可用部署**：操作系统将在软件中心内可用，且用户可根据需要进行安装。  
  
## 另请参阅  
 [使用 System Center Configuration Manager 部署企业版操作系统的方法](../LocTest/Methods-to-deploy-enterprise-operating-systems-using-System-Center-Configuration-Manager.md)
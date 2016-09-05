---
title: "使用 System Center Configuration Manager 部署企业版操作系统的方案"
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
ms.assetid: f74fdb86-c7c2-447f-91f6-b42df6370d7f
caps.latest.revision: 11
caps.handback.revision: 11
translationtype: Human Translation
---
# 使用 System Center Configuration Manager 部署企业版操作系统的方案
以下操作系统部署方案在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]中可用：  
  
-   [Upgrade Windows to the latest version with System Center Configuration Manager](../LocTest/Upgrade-Windows-to-the-latest-version-with-System-Center-Configuration-Manager.md)：此方案将升级当前运行 Windows 7、Windows 8、Windows 8.1 或 Windows 10 的计算机上的操作系统。 此升级过程将保留计算机上的应用程序、设置和用户数据。 不存在 Windows ADK 等外部依赖关系，并且此过程比传统的操作系统部署更快、更具弹性。  
  
-   [Refresh an existing computer with a new version of Windows using System Center Configuration Manager](../LocTest/Refresh-an-existing-computer-with-a-new-version-of-Windows-using-System-Center-Configuration-Manager.md)：此方案将对现有计算机进行分区和格式化（擦除），并在该计算机上安装新的操作系统。 你可以在安装操作系统后迁移设置和用户数据。  
  
-   [Install a new version of Windows on a new computer (bare metal) with System Center Configuration Manager](../LocTest/Install-a-new-version-of-Windows-on-a-new-computer--bare-metal--with-System-Center-Configuration-Manager.md)：此方案将在新计算机上安装操作系统。 这是操作系统的全新安装，且不包括任何设置或用户数据迁移。  
  
-   [Replace an existing computer and transfer settings with System Center Configuration Manager](../LocTest/Replace-an-existing-computer-and-transfer-settings-with-System-Center-Configuration-Manager.md)：此方案将在新计算机上安装操作系统。 （可选）你可以将设置和用户数据从旧计算机迁移到新计算机。  
  
## 在部署操作系统映像之前应注意的事项  
 在部署操作系统之前应注意的某些事项。  
  
### 操作系统映像大小  
 操作系统映像的大小可能会很大。 例如，Windows 7 的映像大小为 3 GB 或更大。 映像的大小和你向其中同时部署操作系统的计算机的数量影响网络性能和可用带宽。 确保测试了网络性能，以更好地衡量映像部署可能产生的影响以及完成部署所需的时间。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 活动包括将映像分发到分发点、将映像从一个站点分发到另一个站点以及将映像下载到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端。  
  
 还要确保在承载操作系统映像的分发点上规划足够的磁盘存储空间。  
  
### 客户端缓存大小  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端在下载内容时会自动使用后台智能传输服务 (BITS)（如果该服务可用）。 在部署用于安装操作系统的任务序列时，你可以针对部署设置选项，以便 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端在任务序列运行之前将完整映像下载到本地缓存。  
  
 通常，当 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端必须下载操作系统映像（或任何其他包），但缓存中没有足够的空间时，客户端将检查缓存中的其他包以确定删除任意或全部最旧的包是否可释放足够的磁盘空间来容纳新映像。 如果删除包无法释放足够的磁盘空间，则客户端不会下载映像，并且部署失败。 如果缓存中有配置为保留在缓存中的大型包，则会发生这种情况。 如果删除包可在缓存中释放足够的空间，则客户端将删除这些包，然后将映像下载到缓存中。  
  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端上的默认缓存大小对于大多数操作系统映像部署而言可能不够大。 如果计划将完整映像下载到客户端缓存，你必须在目标计算机上调整 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端缓存大小以适应所部署的映像的大小。  
  
 有关详细信息，请参阅 [Configure the Client Cache for Configuration Manager Clients](../LocTest/How-to-manage-clients-in-System-Center-Configuration-Manager.md#BKMK_ClientCache)。  
  
## 任务序列部署  
 你创建的任务序列可通过下列方式之一在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端计算机上部署操作系统映像：  
  
-   从分发点将映像及其内容先下载到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端缓存，然后安装映像。  
  
-   直接从分发点安装映像及其内容。  
  
-   在需要时从分发点安装映像及其内容  
  
 默认情况下，当你为任务序列创建部署时，会将映像先下载到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端缓存，然后安装映像。 如果选择在运行映像之前将映像下载到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端缓存，并且任务序列包含对硬盘驱动器重新分区的步骤，则重新分区步骤会失败，因为对硬盘驱动器分区会擦除 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端缓存的内容。 如果任务序列必须对硬盘驱动器重新分区，则你必须通过在部署任务序列时使用“从分发点运行程序”   选项，从分发点运行映像安装。  
  
 有关详细信息，请参阅 [Deploy a task sequence](../LocTest/Manage-task-sequences-to-automate-tasks-in-System-Center-Configuration-Manager.md#BKMK_DeployTS)。  
  
## 另请参阅  
 [使用 System Center Configuration Manager 管理企业操作系统](../LocTest/Manage-enterprise-operating-systems-with-System-Center-Configuration-Manager.md)
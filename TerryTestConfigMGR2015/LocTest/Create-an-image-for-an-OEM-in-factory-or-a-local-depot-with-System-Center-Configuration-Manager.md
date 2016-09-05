---
title: "使用 System Center Configuration Manager 为工厂中的 OEM 或本地 depot 创建映像"
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
ms.assetid: a7d3df90-062d-4d57-9e9d-e137d3e7cd7f
caps.latest.revision: 8
caps.handback.revision: 8
translationtype: Human Translation
---
# 使用 System Center Configuration Manager 为工厂中的 OEM 或本地 depot 创建映像
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的预留媒体部署允许将操作系统部署到未完全设置的计算机。 预留媒体是 Windows 映像格式 (WIM) 文件，可以由制造商 (OEM) 安装在裸机上，也可以安装在未连接到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 环境的企业暂存中心。 之后在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 环境中，计算机使用媒体提供的启动映像启动，预留媒体上会运行哈希检查以确保其有效性，然后计算机连接到站点管理点以执行完成下载过程可用的任务序列。 

  
此部署方法可以减少网络流量，因为启动映像和操作系统映像包已在目标计算机上。 你可以指定要包含在预留媒体中的应用程序、包和驱动程序包。 在计算机上安装操作系统后，首先检查应用程序、包或驱动程序包的本地任务序列缓存，如果找不到内容或内容已被修改，则从在预留媒体中配置的分发点下载内容，然后进行安装。  
  
 可在以下操作系统部署方案中使用预留媒体：  
  
-   [使用 System Center Configuration Manager 在新计算机（裸机）上安装新版本的 Windows](../LocTest/Install-a-new-version-of-Windows-on-a-new-computer--bare-metal--with-System-Center-Configuration-Manager.md)  
  
-   [使用 System Center Configuration Manager 替换现有计算机和传输设置](../LocTest/Replace-an-existing-computer-and-transfer-settings-with-System-Center-Configuration-Manager.md)  
  
 完成其中一个操作系统部署方案中的步骤，然后使用以下部分来准备并创建预留媒体。  
  
## 配置部署设置  
 当你使用预留媒体来启动操作系统部署过程时，必须配置该部署才能使操作系统对媒体可用。 可以在“部署软件向导”的“部署设置”  页面或部署属性的“部署设置”  选项卡上配置这一选项。  对于“可用于以下项目”  设置，请配置下述内容之一：  
  
-   **Configuration Manager 客户端、媒体和 PXE**  
  
-   **仅媒体和 PXE**  
  
-   **仅媒体和 PXE（隐藏）**  
  
## 创建预留媒体  
 创建要发送到的 OEM 或本地 depot 的预留媒体文件。 有关详细信息，请参阅 [Create prestaged media with System Center Configuration Manager](../LocTest/Create-prestaged-media-with-System-Center-Configuration-Manager.md)。  
  
## 将预留媒体文件发送到 OEM 或本地 depot  
 将该媒体发送到 OEM 或本地 depot 以预留计算机。 预留媒体文件应用于计算机上已格式化的硬盘。  
  
## 启动计算机以安装操作系统  
 预留媒体文件应用于计算机。 第一次启动计算机时，将启动操作系统安装过程。  
  
## 另请参阅  
 [使用 System Center Configuration Manager 部署企业版操作系统的方法](../LocTest/Methods-to-deploy-enterprise-operating-systems-using-System-Center-Configuration-Manager.md)
---
title: "在 System Center Configuration Manager 中规划 Mac 计算机的客户端部署"
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
ms.assetid: 8d15ae3f-de42-461f-a907-c43873da22d2
caps.latest.revision: 6
caps.handback.revision: 3
---
# 在 System Center Configuration Manager 中规划 Mac 计算机的客户端部署
你可以在运行 Mac OS X 操作系统并使用以下管理功能的 Mac 计算机上安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端：  
  
|功能|更多信息|  
|--------|----------|  
|硬件清单|你可以使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 硬件清单收集关于 Mac 计算机上的硬件和所安装的应用程序的信息。 然后可以在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台内的资源浏览器中查看此信息，并且可以使用此信息创建集合、查询和报表。 有关详细信息，请参阅[如何使用资源浏览器来查看 System Center Configuration Manager 中的硬件清单](../LocTest/How-to-use-Resource-Explorer-to-view-hardware-inventory-in-System-Center-Configuration-Manager.md)。<br /><br /> [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 从 Mac 计算机中收集下列硬件信息：<br /><br /> -   处理器<br />-   计算机系统<br />-   磁盘驱动器<br />-   磁盘分区<br />-   网络适配器<br />-   操作系统<br />-   服务<br />-   过程<br />-   已安装的软件<br />-   计算机系统产品<br />-   USB 控制器<br />-   USB 设备<br />-   CDROM 驱动器<br />-   视频控制器<br />-   桌面监视器<br />-   便携式电池<br />-   物理内存<br />-   打印机 **Important:**  在硬件清点过程中，你无法扩展从 Mac 计算机收集的硬件信息。|  
|符合性设置|你可以使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 符合性设置查看 Mac OS X 首选项 \(.plist\) 设置的符合性以及修正这些设置。 例如，你可以在 Safari Web 浏览器中强制主页设置，或者确保启用 Apple 防火墙。 也可以使用外壳脚本在 MAC OS X 中监视和修正设置。|  
|应用程序管理|[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 可以将软件部署到 Mac 计算机。 你可以将以下软件格式部署到 Mac 计算机：<br /><br /> -   Apple 磁盘映像 \(.DMG\)<br />-   元包文件 \(.MPKG\)<br />-   Mac OS X 安装程序包 \(.PKG\)<br />-   Mac OS X 应用程序 \(.APP\)|  
  
 在 Mac 计算机上安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端时，无法使用基于 Windows 的计算机上 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端支持的以下管理功能：  
  
-   客户端请求安装  
  
-   操作系统部署  
  
-   软件更新  
  
    > [!NOTE]  
    >  你可以使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 应用程序管理将所需的 Mac OS X 软件更新部署到 Mac 计算机。 此外，可以使用符合性设置来确保计算机具有任何所需的软件更新。  
  
-   维护时段  
  
-   远程控制  
  
-   电源管理  
  
-   客户端状态客户端检查和修正  
  
 有关如何安装和配置 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] Mac 客户端的详细信息，请参阅 [如何在 System Center Configuration Manager 中将客户端部署到 Mac 计算机](../LocTest/How-to-deploy-clients-to-Macs-in-System-Center-Configuration-Manager.md)。
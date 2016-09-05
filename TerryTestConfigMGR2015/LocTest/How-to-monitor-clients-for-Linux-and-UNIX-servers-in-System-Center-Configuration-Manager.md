---
title: "如何在 System Center Configuration Manager 中监视 Linux 和 UNIX 服务器的客户端"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-client
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: d827cf91-b18f-4ee7-b538-24ba6f003ab9
caps.latest.revision: 6
caps.handback.revision: 5
translationtype: Human Translation
---
# 如何在 System Center Configuration Manager 中监视 Linux 和 UNIX 服务器的客户端
可以使用查看基于 Windows 的客户端的信息的相同方法在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 控制台中查看来自于 Linux 和 UNIX 服务器的信息。  
  
 可以查看的信息包括:  
  
-   客户端的状态详细信息，在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台仪表板中  
  
-   默认 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 报表中关于客户端的详细信息  
  
-   资源浏览器中的清单详细信息  
  
 以下部分提供关于使用资源浏览器和报表以查看有关 Linux 和 UNIX 服务器的详细信息的信息。  
  
##  <a name="BKMK_UseResourceExpforLnU"></a> 如何使用资源浏览器查看适用于 Linux 和 UNIX 服务器的清单  
 可以使用资源浏览器查看 Linux 和 UNIX 服务器上的硬件和已安装软件的详细信息。  
  
 在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端向 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点提交硬件清单后，可以使用资源浏览器查看此信息。 适用于 Linux 和 UNIX 的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端不会向资源浏览器添加新的清单类或视图。 Linux 和 UNIX 清单数据映射到现有的 WMI 类。 可以使用资源浏览器在基于 Windows 的分类中查看 Linux 和 UNIX 服务器的详细清单信息。  
  
 例如，可以收集在 Linux 和 UNIX 服务器上找到的所有以本机方式安装的程序的列表。 以本机方式安装的程序的示例包括 Linux 中的 **.rpms** 或 Solaris 中的 **.pkgs**。 在 Linux 或 UNIX 客户端提交清单后，可以在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台内资源浏览器中查看所有以本机方式安装的 Linux 或 UNIX 程序列表。  
  
 有关如何使用资源浏览器的信息，请参阅[如何使用资源浏览器来查看 System Center Configuration Manager 中的硬件清单](../LocTest/How-to-use-Resource-Explorer-to-view-hardware-inventory-in-System-Center-Configuration-Manager.md)。  
  
##  <a name="BKMK_UseReportsforLnU"></a> 如何使用报表来查看 Linux 和 UNIX 服务器的信息  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的报表包括来自 Linux 和 UNIX 服务器的信息以及来自基于 Windows 的计算机的信息。 无需其他配置就可将 Linux 和 UNIX 数据集成到报表中。  
  
 例如，如果运行名为“操作系统版本计数”的报表，该报表会显示不同操作系统的列表和运行每个操作系统的客户端数目。 报表基于运行于不同操作系统的不同 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端所发送的硬件清单信息。  
  
 还可以创建特定于 Linux 和 UNIX 服务器数据的自定义报表。 硬件清单类“操作系统”的“标题”属性的是一个有用的属性，可用于在报表查询中标识特定的操作系统。  
  
 有关 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中报表的详细信息，请参阅 [System Center Configuration Manager 中的报表](../LocTest/Reporting-in-System-Center-Configuration-Manager.md)。  
  
## 请参阅  
 [如何在 System Center Configuration Manager 中监视客户端](../LocTest/How-to-monitor-clients-in-System-Center-Configuration-Manager.md)   
 [在 System Center Configuration Manager 中监视和管理客户端](../LocTest/Monitor-and-manage-clients-in-System-Center-Configuration-Manager.md)
---
title: "如何将诊断和使用情况数据用于 System Center Configuration Manager"
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
ms.assetid: a8021bc8-2799-41f4-83c2-e27d1242028c
caps.latest.revision: 5
caps.handback.revision: 4
---
# 如何将诊断和使用情况数据用于 System Center Configuration Manager
为 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 收集的诊断和使用情况数据针对产品工作（或未工作）的方式为 Microsoft 提供近乎即时的反馈，并用于调整将来的更新。 我们也能查看配置数据，这些数据可帮助我们设计并测试生产中的配置。 例如：  
  
-   站点服务器使用的 Windows Server 版本  
  
-   安装的语言包  
  
-   SQL 架构针对产品默认值的增量  
  
 此数据帮助工程团队计划将来的测试，以确保在最常见的配置下获得最佳体验。 由于将以更快的频率发布 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的更新（以便更好地支持 Windows 10 和 Microsoft Intune 等快速发展的技术），因此，此数据对于快速调整和适应至关重要。  
  
 如何不使用诊断和使用情况数据同样重要。 Microsoft 不会将此数据用于以下方面：  
  
-   许可审核，例如按照许可协议比较客户使用情况  
  
-   不支持的产品的审核  
  
-   基于可用的数据（如功能使用情况或地理位置（时区））进行广告\)  
  
##  <a name="bkmk_improve"></a> 诊断和使用情况数据如何改进产品的示例  
 Microsoft 使用可用数据来改进产品。 以下是如何进行改进的几个示例：  
  
-   **修订了对较旧服务器操作系统的支持：**  
  
     [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 的当前分支提供的初始支持对于 Windows Server 2008 R2 包含支持时间线方面的限制。 检查已升级到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 当前分支的客户的使用情况数据之后，我们发现需要修订和扩展此时间线，以支持仍使用此服务器操作系统承载站点服务器和站点系统角色的大量客户。  
  
-   **改进了先决条件检查：**  
  
     基于使用情况数据，我们改进了先决条件检查以便安装更新，从而删除过时的规则、负责处理其他情况以及在某些情况下自动修正某些问题。  
  
## 另请参阅  
 [System Center Configuration Manager 的诊断和使用情况数据](../LocTest/Diagnostics-and-usage-data-for-System-Center-Configuration-Manager.md)   
 [System Center Configuration Manager 的诊断使用情况数据收集的级别](../LocTest/Levels-of-diagnostic-usage-data-collection-for-System-Center-Configuration-Manager.md)   
 [System Center Configuration Manager 如何收集诊断和使用情况数据](../LocTest/How-diagnostics-and-usage-data-is-collected-by-System-Center-Configuration-Manager.md)   
 [如何查看 System Center Configuration Manager 的诊断和使用情况数据](../LocTest/How-to-view-diagnostics-and-usage-data-for-System-Center-Configuration-Manager.md)
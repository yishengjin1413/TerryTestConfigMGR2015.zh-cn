---
title: "规划迁移到 System Center Configuration Manager"
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
ms.assetid: b2bf493e-1e10-496f-a139-2646522703ed
caps.latest.revision: 7
caps.handback.revision: 6
---
# 规划迁移到 System Center Configuration Manager
在将数据迁移到 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 目标层次结构之前，请确保你熟知 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的站点和层次结构。 有关站点和层次结构的详细信息，请参阅[System Center Configuration Manager 基础知识](../LocTest/Fundamentals-of-System-Center-Configuration-Manager.md)。  
  
 在可以从受支持的源层次结构迁移数据之前，必须安装将成为目标层次结构的 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 层次结构。  
  
 安装目标层次结构之后，配置你想在目标层次结构中使用的管理特性和功能，然后再开始迁移数据。  
  
 此外，可能还必须规划源层次结构与目标层次结构之间的重叠。 例如，假设源层次结构配置为使用相同网络位置或边界作为目标层次结构，并且你随后将新客户端安装到目标层次结构并使用自动站点分配。 在这种情况下，因为新安装的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端可以从任一层次结构中选择要加入的站点，所以，该客户端可能会错误地分配到源层次结构。 为此，应计划将目标层次结构中的每个新客户端分配到该层次结构中的特定站点，而不是使用自动站点分配。  
  
 有关站点分配的详细信息，请参阅 [客户端站点分配注意事项](../LocTest/Interoperability-between-different-versions-of-System-Center-Configuration-Manager.md#BKMK_SupConfigSiteAssignment)主题中的[System Center Configuration Manager 不同版本之间的互操作性](../LocTest/Interoperability-between-different-versions-of-System-Center-Configuration-Manager.md)部分。  
  
## 规划主题  
 使用下列主题来帮助你规划如何将支持的源层次结构迁移到 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 目标层次结构：  
  
-   [System Center Configuration Manager 中迁移的先决条件](../LocTest/Prerequisites-for-migration-in-System-Center-Configuration-Manager.md)  
  
-   [System Center Configuration Manager 中针对迁移规划的管理员清单](../LocTest/Administrator-checklists-for-migration-planning-in-System-Center-Configuration-Manager.md)  
  
-   [确定是否将数据迁移到 System Center Configuration Manager](../LocTest/Determine-whether-to-migrate-data-to-System-Center-Configuration-Manager.md)  
  
-   [在 System Center Configuration Manager 中规划源层次结构策略](../LocTest/Planning-a-source-hierarchy-strategy-in-System-Center-Configuration-Manager.md)  
  
-   [System Center Configuration Manager 中针对迁移规划的管理员清单](../LocTest/Administrator-checklists-for-migration-planning-in-System-Center-Configuration-Manager.md)  
  
-   [在 System Center Configuration Manager 中规划客户端迁移策略](../LocTest/Planning-a-client-migration-strategy-in-System-Center-Configuration-Manager.md)  
  
-   [在 System Center Configuration Manager 中规划内容部署迁移策略](../LocTest/Planning-a-content-deployment-migration-strategy-in-System-Center-Configuration-Manager.md)  
  
-   [规划将 Configuration Manager 对象迁移到 System Center Configuration Manager](../LocTest/Planning-for-the-migration-of-Configuration-Manager-objects-to-System-Center-Configuration-Manager.md)  
  
-   [在 System Center Configuration Manager 中规划监视迁移活动](../LocTest/Planning-to-monitor-migration-activity-in-System-Center-Configuration-Manager.md)  
  
-   [规划在 System Center Configuration Manager 中完成迁移](../LocTest/Planning-to-complete-migration-in-System-Center-Configuration-Manager.md)  
  
## 请参阅  
 [在 System Center Configuration Manager 中层次结构之间迁移数据](../LocTest/Migrate-data-between-hierarchies-in-System-Center-Configuration-Manager.md)
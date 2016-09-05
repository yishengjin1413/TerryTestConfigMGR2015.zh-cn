---
title: "System Center Configuration Manager 中的查询简介"
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
ms.assetid: 03d1b3a9-41db-4d3a-a70e-e05ab5dc8141
caps.latest.revision: 5
caps.handback.revision: 4
---
# System Center Configuration Manager 中的查询简介
可以创建和运行查询，以便在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 层次结构中查找与查询条件相匹配的对象。 这些对象包括特定类型的计算机或用户组等项目。 查询可以返回大部分类型的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 对象，包括站点、集合、应用程序和清单数据。  
  
 创建查询时，必须至少指定两个参数：搜索位置和搜索内容。 例如，若要查找 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点中所有计算机上的可用硬盘空间量，可以创建一个查询，搜索“逻辑磁盘”属性类以及可用硬盘空间的“可用空间\(MB\)”属性。  
  
 在创建初始查询之后，可以指定其他查询条件。 例如，可以指定查询结果仅包括分配给指定站点的计算机。 还可以修改结果的显示方式，以便按照有意义的顺序查看结果。 例如，可以指定按可用硬盘空间量的升序或降序对结果进行排序。  
  
 创建查询时，它会由 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 存储并显示在“监视”工作区中的“查询”节点中。 从此位置可以创建新查询，然后运行、更新或管理现有查询。  
  
 还可以将查询导入 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 集合中的导入规则中。 有关详细信息，请参阅 [如何在 System Center Configuration Manager 中创建集合](../LocTest/How-to-create-collections-in-System-Center-Configuration-Manager.md)。  
  
## 请参阅  
 [System Center Configuration Manager 中查询的技术参考](../LocTest/Queries-technical-reference-for-System-Center-Configuration-Manager.md)
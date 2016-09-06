---
title: "System Center Configuration Manager 的国际支持"
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
ms.assetid: 46dd9cb2-a812-4b6a-a747-b840f92fef8b
caps.latest.revision: 6
caps.handback.revision: 5
translationtype: Human Translation
---
# System Center Configuration Manager 的国际支持
下列部分提供技术详细信息，以帮助你配置 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]，使其符合特定的国际要求。  
  
## GB18030 要求  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 符合在 GB18030 中定义的标准，因此，你可以在中国使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 部署必须具有下列配置才能符合 GB18030 要求：  
  
-   与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 一起使用的每台站点服务器计算机和 SQL Server 计算机都必须使用中文操作系统。  
  
-   层次结构中的每个站点数据库和 SQL Server 的每个实例都必须使用相同的排序规则，而且必须是下列排序规则之一：  
  
    -   Chinese\_Simplified\_Pinyin\_100\_CI\_AI  
  
    -   Chinese\_Simplified\_Stroke\_Order\_100\_CI\_AI  
  
    > [!NOTE]  
    >  这些数据库集合是 [对 System Center Configuration Manager 的 SQL Server 版本的支持](../LocTest/Support-for-SQL-Server-versions-for-System-Center-Configuration-Manager.md) 中所述要求的一个例外。  
  
-   必须将名为 **GB18030.SMS** 的文件放在层次结构中的每台站点服务器计算机的系统卷根文件夹下。 此文件不包含任何数据，而且可能是按照此要求命名的空白文本文件。  
  
## 请参阅  
 [System Center Configuration Manager 的站点和层级结构基础结构技术参考](../LocTest/Site-and-hierarchy-infrastructure-technical-reference-for-System-Center-Configuration-Manager.md)
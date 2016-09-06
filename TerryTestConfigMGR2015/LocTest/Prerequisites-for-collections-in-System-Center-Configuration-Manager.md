---
title: "System Center Configuration Manager 中集合的先决条件"
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
ms.assetid: a53e4cf1-518a-4210-9c16-022c4261d2fe
caps.latest.revision: 7
caps.handback.revision: 3
author: barlanmsft
translationtype: Human Translation
---
# System Center Configuration Manager 中集合的先决条件
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的集合只包含产品内部的依赖关系。  
  
## [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 依赖关系  
  
|依赖关系|更多信息|  
|----------|----------|  
|Reporting Services 点|在运行集合的报表前，必须先安装 Reporting Services 点站点系统角色。 有关详细信息，请参阅 [System Center Configuration Manager 中的报表](../LocTest/Reporting-in-System-Center-Configuration-Manager.md)。|  
|必须授予特定的安全权限来管理集合|必须具有以下安全权限才能管理符合性设置：<br /><br /> -   若要创建和管理集合：“集合”对象的“创建”、“删除”、“修改”、“修改文件夹”、“移动对象”、“读取”和“读取资源”。<br />-   若要管理集合设置：“集合”对象的“修改集合设置”。 **Note:**  所有集合文件夹（包括根文件夹）都需要“修改文件夹”权限。|  
  
## 请参阅  
 [在 System Center Configuration Manager 中规划集合](../LocTest/Planning-for-collections-in-System-Center-Configuration-Manager.md)
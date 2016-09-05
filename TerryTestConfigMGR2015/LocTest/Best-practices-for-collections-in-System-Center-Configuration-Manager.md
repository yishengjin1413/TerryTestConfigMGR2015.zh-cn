---
title: "在 System Center Configuration Manager 中集合的最佳实践"
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
ms.assetid: 7a2abb79-9ae5-4a25-9e18-5dcf528de3bf
caps.latest.revision: 4
caps.handback.revision: 4
author: barlanmsft
---
# 在 System Center Configuration Manager 中集合的最佳实践
在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中使用以下集合的最佳实践。  
  
## 不要为大量集合使用增量更新  
 如果启用“为此集合使用增量更新”选项，为多个集合启用此配置时可能导致评估延迟。 在你的层次结构中，阈值为大约 200 个集合。 确切的数目取决于以下因素：  
  
-   集合总数  
  
-   在层次结构中添加和更改新资源的频率  
  
-   层次结构中的客户端数目  
  
-   层次结构中的集合成员身份规则的复杂性  
  
## 确保维护时段足够大以部署关键的软件更新  
 你可以为设备集合配置维护时段，以限制 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 可在这些设备上安装软件的次数。 如果你将该维护时段配置得太小，则客户端可能无法安装关键的软件更新，这使客户端容易遭受可由软件更新减轻的攻击。  
  
## 请参阅  
 [System Center Configuration Manager 中集合的技术参考](../LocTest/Collections-technical-reference-for-System-Center-Configuration-Manager.md)
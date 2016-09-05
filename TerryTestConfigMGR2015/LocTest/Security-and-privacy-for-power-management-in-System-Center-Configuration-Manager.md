---
title: "System Center Configuration Manager 中电源管理的安全和隐私"
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
ms.assetid: 469ff35f-59a1-484d-902b-107dd6070baf
caps.latest.revision: 5
caps.handback.revision: 4
translationtype: Human Translation
---
# System Center Configuration Manager 中电源管理的安全和隐私
此部分包含 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中电源管理的安全和隐私信息。  
  
## 电源管理的最佳安全方案  
 电源管理没有相关的最佳安全方案。  
  
## 电源管理的隐私信息  
 电源管理利用 Windows 中的内置功能在营业时间和非营业时间监视电源使用情况并将电源设置应用于计算机。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 收集计算机的电源使用情况信息，其中包括用户使用计算机时间的相关数据。 虽然 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 针对集合而不是每台计算机监视电源使用情况，但集合可以只包含一台计算机。 默认情况下不启用电源管理，必须由管理员配置。  
  
 电源使用情况信息存储在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 数据库中，不会发送给 Microsoft。 详细信息在数据库中保留 31 天，摘要信息保留 13 个月。 不能配置删除时间间隔。  
  
 在配置电源管理之前，请考虑隐私要求。  
  
## 请参阅  
 [System Center Configuration Manager 中电源管理的技术参考](../LocTest/Power-management-technical-reference-for-System-Center-Configuration-Manager.md)
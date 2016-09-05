---
title: "System Center Configuration Manager 中电源管理的先决条件"
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
ms.assetid: 9c062f13-3c1f-4621-9cae-de0e322aa03f
caps.latest.revision: 4
caps.handback.revision: 4
translationtype: Human Translation
---
# System Center Configuration Manager 中电源管理的先决条件
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的电源管理具有外部依赖关系和产品内部的依赖关系。  
  
## Configuration Manager 的外部依赖关系  
 下表针对使用电源管理列出了 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的外部依赖关系。  
  
|依赖关系|更多信息|  
|----------|----------|  
|客户端计算机必须能够支持所需的电源状态|若要使用电源管理的所有功能，客户端计算机必须能够支持睡眠、休眠、从睡眠状态唤醒，以及从休眠状态唤醒操作。 可以使用“电源功能” 报表来确定计算机是否可以支持这些操作。 有关详细信息，请参阅[如何在 System Center Configuration Manager 中监视和计划电源管理](../LocTest/How-to-monitor-and-plan-for-power-management-in-System-Center-Configuration-Manager.md)主题中的[电源功能报表](../LocTest/How-to-monitor-and-plan-for-power-management-in-System-Center-Configuration-Manager.md#BKMK_Capabilites)。|  
  
## Configuration Manager 依赖关系  
 下表针对使用电源管理列出了 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 内的依赖关系。  
  
|依赖关系|更多信息|  
|----------|----------|  
|必须先启用电源管理才能创建和监视电源计划。|有关如何启用和配置电源管理的详细信息，请参阅[在 System Center Configuration Manager 中配置电源管理](../LocTest/Configuring-power-management-in-System-Center-Configuration-Manager.md)。|  
|Reporting Services 点|在查看电源管理报表前，必须先配置一个 Reporting Services 点。 有关详细信息，请参阅 [System Center Configuration Manager 中的报表](../LocTest/Reporting-in-System-Center-Configuration-Manager.md)。|  
  
## 请参阅  
 [System Center Configuration Manager 中的电源管理计划](../LocTest/Planning-for-power-management-in-System-Center-Configuration-Manager.md)
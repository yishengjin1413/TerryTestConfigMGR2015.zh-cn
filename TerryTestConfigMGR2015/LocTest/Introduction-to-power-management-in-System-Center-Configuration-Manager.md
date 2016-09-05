---
title: "System Center Configuration Manager 中的电源管理简介"
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
ms.assetid: 3ddff2a7-99eb-4ef8-b969-f3f7f24053db
caps.latest.revision: 4
caps.handback.revision: 4
translationtype: Human Translation
---
# System Center Configuration Manager 中的电源管理简介
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的电源管理可满足众多组织监视和减少其计算机功耗的需求。 该功能利用 Windows 中的内置电源管理功能对组织中的计算机应用相关且一致的设置。 你可以在营业时间和非营业时间对计算机应用不同的电源设置。 例如，你可能想要在非营业时间对计算机应用限制性更强的电源计划。 在计算机必须始终保持开机状态的情况下，可以禁止应用电源管理设置。  
  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的电源管理包括多种报表，可帮助分析贵组织的功耗情况和计算机电源设置。 你还可使用报表来帮助诊断电源管理问题。  
  
 有关如何配置和使用电源管理的详细工作流，请参阅 [System Center Configuration Manager 中电源管理的管理员清单](../LocTest/Administrator-checklist-for-power-management-in-System-Center-Configuration-Manager.md)。  
  
> [!IMPORTANT]  
>  虚拟机不支持 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 电源管理。 不能对虚拟机应用电源计划，也不能报告虚拟机的电源数据。  
  
## 电源管理工作流  
 使用以下三个阶段来计划和实施 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的电源管理。  
  
### 监控和规划阶段  
 电源管理使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 硬件清单来收集有关站点中计算机使用情况和电源设置的数据。 可以使用大量报表来分析此数据并确定计算机的最佳电源管理设置。 例如，在电源管理工作流的监控和规划阶段，你可以创建基于“电源功能”报表中所含数据的集合并使用该数据来标识不能使用电源管理的计算机。 然后，可以从电源管理中排除这些计算机。  
  
> [!IMPORTANT]  
>  在收集并分析客户端计算机上的电源数据后，才能将电源计划应用于站点中的计算机。 如果不首先检查现有设置就将新的电源管理设置应用于计算机，这可能导致功耗变大。  
  
### 实施阶段  
 通过电源管理，你可以创建可应用到站点中计算机集合的电源计划。 这些电源计划在计算机上配置 Windows 电源管理设置。 可以使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]附带的电源计划，或者可以配置自己的自定义电源计划。 可以将监控和规划阶段收集的电源数据用作基线来帮助你评估对计算机应用电源计划之后的节能情况。 有关详细信息，请参阅[System Center Configuration Manager 中电源管理的管理员清单](../LocTest/Administrator-checklist-for-power-management-in-System-Center-Configuration-Manager.md)。  
  
### 符合性阶段  
 在符合性阶段中，可以运行帮助评估贵组织中电源使用情况和电源成本节省的报表。 还可以运行用于描述计算机产生的 CO2 量改善情况的报表。 此外，报表还可帮助验证计算机是否已正确应用电源设置，并且帮助诊断电源管理功能问题。  
  
## 请参阅  
 [System Center Configuration Manager 中电源管理的技术参考](../LocTest/Power-management-technical-reference-for-System-Center-Configuration-Manager.md)
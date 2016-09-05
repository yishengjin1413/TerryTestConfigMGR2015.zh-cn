---
title: "System Center Configuration Manager 中电源管理的管理员清单"
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
ms.assetid: 94e42cbe-9df8-4228-a04e-0ad7626180ca
caps.latest.revision: 6
caps.handback.revision: 3
---
# System Center Configuration Manager 中电源管理的管理员清单
此管理员清单提供了在你的组织中使用 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 电源管理的建议步骤。  
  
## 配置电源管理  
 使用下列步骤可帮助你将你的层次结构配置为收集客户端计算机的电源管理信息。  
  
> [!IMPORTANT]  
>  在收集并分析客户端计算机的电源数据前，请勿将电源计划应用于层次结构中的计算机。 如果不先检查现有设置就将新的电源管理设置应用于计算机，这可能导致功率消耗变大。  
  
|任务|详细信息|  
|--------|----------|  
|在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 文档库中查看电源管理概念。|请参阅[System Center Configuration Manager 中的电源管理简介](../LocTest/Introduction-to-power-management-in-System-Center-Configuration-Manager.md)。|  
|在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 文档库中查看电源管理的先决条件。|请参阅[System Center Configuration Manager 中电源管理的先决条件](../LocTest/Prerequisites-for-power-management-in-System-Center-Configuration-Manager.md)。|  
|查看电源管理的最佳方案信息。|请参阅[System Center Configuration Manager 中电源管理的最佳方案](../LocTest/Best-practices-for-power-management-in-System-Center-Configuration-Manager.md)。|  
|针对电源管理配置下列集合：<br /><br /> -   用于报告基准数据的集合。<br />-   要从电源管理中排除的计算机的集合。<br />-   不支持电源管理的计算机的集合。<br />-   将应用电源计划的计算机的集合。<br />-   运行 Windows Server 的计算机的集合。|使用列出的集合帮助你管理层次结构中的计算机的电源设置。 你可以创建多个集合，并对每个集合应用不同的电源计划。|  
|启用电源管理。|必须先启用电源管理并配置所需客户端设置，然后才可开始使用电源管理。 有关详细信息，请参阅 [在 System Center Configuration Manager 中配置电源管理](../LocTest/Configuring-power-management-in-System-Center-Configuration-Manager.md)。|  
|收集客户端计算机的电源管理信息。|电源管理数据由客户端通过 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 硬件清单报告。 根据已配置的硬件清单计划，可能需要一些时间来检索来自所有客户端计算机的清单。|  
  
## 监控和规划阶段  
  
|任务|详细信息|  
|--------|----------|  
|运行报表“计算机活动”。|“计算机活动”报表显示一个图形，该图形显示指定集合在指定时间段内的监视器、计算机和用户活动。 此报表链接到“计算机活动详细信息”报表，后者显示指定集合中计算机的睡眠和唤醒功能。 有关详细信息，请参阅 [如何在 System Center Configuration Manager 中监视和计划电源管理](../LocTest/How-to-monitor-and-plan-for-power-management-in-System-Center-Configuration-Manager.md)。|  
|运行报表“能耗”或“每日能耗”。|“能耗”或“每日能耗”报表显示指定集合在指定时间段内每月的总功率消耗（以千瓦时 \(kWh\) 为单位）。 有关详细信息，请参阅[如何在 System Center Configuration Manager 中监视和计划电源管理](../LocTest/How-to-monitor-and-plan-for-power-management-in-System-Center-Configuration-Manager.md)。|  
|运行报表“环境影响”或”每日环境影响”。|“环境影响”或”每日环境影响”报表显示了一张图表，该图表显示指定的计算机集合在指定时间段内减少的二氧化碳 \(CO2\) 排放量。 有关详细信息，请参阅 [如何在 System Center Configuration Manager 中监视和计划电源管理](../LocTest/How-to-monitor-and-plan-for-power-management-in-System-Center-Configuration-Manager.md)。|  
|运行报表“能源成本”或“每日能源成本”。|“能源成本”或“每日能源成本”报表显示指定时间段内的总功率消耗成本。 有关详细信息，请参阅[如何在 System Center Configuration Manager 中监视和计划电源管理](../LocTest/How-to-monitor-and-plan-for-power-management-in-System-Center-Configuration-Manager.md)。|  
|运行报表“电源功能”。|“电源功能”报表显示指定集合中的计算机的电源管理功能。 有关详细信息，请参阅[如何在 System Center Configuration Manager 中监视和计划电源管理](../LocTest/How-to-monitor-and-plan-for-power-management-in-System-Center-Configuration-Manager.md)。|  
|运行报表“电源设置”。|“电源设置”显示指定集合中的计算机所使用的当前电源设置的聚合列表。 有关详细信息，请参阅[如何在 System Center Configuration Manager 中监视和计划电源管理](../LocTest/How-to-monitor-and-plan-for-power-management-in-System-Center-Configuration-Manager.md)。|  
|从电源管理中排除任何所需的计算机集合。|请参阅[在 System Center Configuration Manager 中配置电源管理](../LocTest/Configuring-power-management-in-System-Center-Configuration-Manager.md)。|  
  
> [!IMPORTANT]  
>  请确保你保存了在监控和规划阶段生成的电源管理报表中的信息。 你可以将此数据与实施和符合性阶段生成的电源管理信息进行比较，以帮助你评估对层次结构中的计算机应用电源计划后实现的电源使用量减小、电力成本节省和环境影响改进。  
  
## 实施阶段  
  
|任务|详细信息|  
|--------|----------|  
|选择现有电源计划或为组织中的计算机集合创建新的电源计划。|请参阅[如何在 System Center Configuration Manager 中创建并应用电源计划](../LocTest/How-to-create-and-apply-power-plans-in-System-Center-Configuration-Manager.md)。|  
|将这些电源计划应用于计算机。|请参阅[如何在 System Center Configuration Manager 中创建并应用电源计划](../LocTest/How-to-create-and-apply-power-plans-in-System-Center-Configuration-Manager.md)。|  
  
## 符合性阶段  
  
|任务|详细信息|  
|--------|----------|  
|运行报表“计算机活动”。|“计算机活动”报表显示一个图形，该图形显示指定集合在指定时间段内的监视器、计算机和用户活动。 此报表链接到“电源计算机活动详细信息”报表，后者显示指定集合中计算机的睡眠和唤醒功能。 有关详细信息，请参阅 [如何在 System Center Configuration Manager 中监视和计划电源管理](../LocTest/How-to-monitor-and-plan-for-power-management-in-System-Center-Configuration-Manager.md)。|  
|运行报表“能耗”或“每日能耗”。|“能耗”或“每日能耗”报表显示指定集合在指定时间段内每月的总功率消耗（以千瓦时 \(kWh\) 为单位）。 有关详细信息，请参阅 [如何在 System Center Configuration Manager 中监视和计划电源管理](../LocTest/How-to-monitor-and-plan-for-power-management-in-System-Center-Configuration-Manager.md)。|  
|运行报表“环境影响”或”每日环境影响”。|“环境影响”或”每日环境影响”报表显示了一张图表，该图表显示指定的计算机集合在指定时间段内减少的二氧化碳 \(CO2\) 排放量。 有关详细信息，请参阅 [如何在 System Center Configuration Manager 中监视和计划电源管理](../LocTest/How-to-monitor-and-plan-for-power-management-in-System-Center-Configuration-Manager.md)。|  
|运行报表“能源成本”或“每日能源成本”。|“能源成本”或“每日能源成本”报表显示指定时间段内的总功率消耗成本。 有关详细信息，请参阅 [如何在 System Center Configuration Manager 中监视和计划电源管理](../LocTest/How-to-monitor-and-plan-for-power-management-in-System-Center-Configuration-Manager.md)。|  
  
## 故障排除  
  
|任务|详细信息|  
|--------|----------|  
|如果层次结构中的计算机未进入睡眠或休眠状态，请运行报表“失眠报表”以显示可能的原因。|“失眠报表”显示了一个列表，该列表列出了阻止计算机进入睡眠或休眠状态的常见原因以及指定时间段内受每种原因影响的计算机数量。 有关详细信息，请参阅 [如何在 System Center Configuration Manager 中监视和计划电源管理](../LocTest/How-to-monitor-and-plan-for-power-management-in-System-Center-Configuration-Manager.md)。|  
|如果多个电源计划应用于一台计算机，则将应用限制性最弱的电源计划。 运行报表“具有多个电源计划的计算机”以查看应用了多个电源计划的计算机。|请参阅[如何在 System Center Configuration Manager 中监视和计划电源管理](../LocTest/How-to-monitor-and-plan-for-power-management-in-System-Center-Configuration-Manager.md)中的“具有多个电源计划的计算机”。|  
  
## 请参阅  
 [System Center Configuration Manager 中的电源管理计划](../LocTest/Planning-for-power-management-in-System-Center-Configuration-Manager.md)
---
title: "System Center Configuration Manager 中电源管理的最佳方案"
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
ms.assetid: 9f7142e1-c972-4384-853b-2da1568cb3e3
caps.latest.revision: 5
caps.handback.revision: 4
---
# System Center Configuration Manager 中电源管理的最佳方案
下列最佳方案适用于 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的电源管理。  
  
## 在具有代表性的时间执行监视阶段  
 电源管理的监视阶段为你提供有关组织中计算机的功率消耗、活动、电源管理功能和环境影响的信息。 确保你选择一个具有代表性的时间来执行监视阶段。 例如，在公休假日期间执行监视阶段不会提供关于计算机电源使用情况的真实报表。  
  
## 创建未应用任何电源计划的计算机的控件集合  
 创建两个计算机集合以帮助你监视向计算机应用电源计划的效果。 第一个集合应包括要对其应用电源设置的大多数计算机，另一个集合（即控件集合）应包含剩余的计算机。 将所需电源管理计划应用与包含大多数计算机的集合。 然后可以运行报表，将应用了电源设置的计算机与未应用电源设置的控件集合的的电力成本、电源使用情况以及环境影响进行比较。  
  
## 先运行电源设置报表，然后再应用电源管理计划  
 将电源管理计划应用到计算机的集合之前，请运行“电源设置”报表，帮助你了解已在集合中的计算机上配置的电源管理设置。 如果不先检查现有设置就将新的电源管理设置应用于计算机，这可能导致功率消耗变大。  
  
## 从电源管理中排除服务器  
 运行 Windows Server 的计算机不支持电源管理（尽管已收集电源使用情况数据）。 确保将服务器添加到集合，并从电源管理中将其排除。  
  
## 排除你不希望管理的计算机  
 如果你有不希望使用电源管理进行管理的计算机，请将它们添加到集合，并确保该集合已从电源管理中排除。  
  
 你可能想要从电源管理中排除的计算机的示例包括：  
  
-   必须保持开机状态的计算机。  
  
-   用户需要通过使用远程桌面连接来连接的计算机。  
  
-   不能使用电源管理的计算机。  
  
-   具有分发点站点系统角色的计算机。  
  
-   其中的计算机和监视器必须保持开启状态的公用计算机（如网亭计算机、信息显示器或监视控制台）。  
  
 有关详细信息，请参阅 [在 System Center Configuration Manager 中配置电源管理](../LocTest/Configuring-power-management-in-System-Center-Configuration-Manager.md)。  
  
## 首先，向计算机的测试集合应用电源计划  
 在将电源计划应用于较大的计算机集合前，务必测试对计算机测试集合应用电源管理计划的效果。  
  
 应用于运行 Windows XP 或 Windows Server 2003 的计算机的电源设置不会还原为其原始值，即使从电源管理中排除该计算机。 在更高版本的 Windows 中，从电源管理中排除一台计算机会导致所有电源设置还原到其原始值。 无法将单个电源设置还原为其初始值。  
  
## 单独应用电源计划设置  
 先监视应用每个电源设置的效果，然后再应用下一个设置，以确保每个设置都具有所需的效果。 有关电源计划设置的详细信息，请参阅[如何在 System Center Configuration Manager 中创建并应用电源计划](../LocTest/How-to-create-and-apply-power-plans-in-System-Center-Configuration-Manager.md)主题中的[可用的电源管理计划设置](../LocTest/How-to-create-and-apply-power-plans-in-System-Center-Configuration-Manager.md#BKMK_Plans)。  
  
## 定期监视计算机以查看它们是否应用多个电源计划  
 电源管理包括显示应用了多个电源计划的计算机的报告。  
  
 如果某台计算机是多个集合的成员，且每个集合应用不同的电源计划，则应执行以下操作：  
  
-   电源计划：如果对某计算机应用了电源设置的多个值，则使用限制最少的值。  
  
-   唤醒时间：如果对台式计算机应用多个唤醒时间，则将使用最接近午夜的时间。  
  
     有关详细信息，请参阅[如何在 System Center Configuration Manager 中监视和计划电源管理](../LocTest/How-to-monitor-and-plan-for-power-management-in-System-Center-Configuration-Manager.md)主题中的[具有多个电源计划的计算机](../LocTest/How-to-monitor-and-plan-for-power-management-in-System-Center-Configuration-Manager.md#BKMK_Multiple)。 有关电源管理如何解决冲突的详细信息，请参阅[如何在 System Center Configuration Manager 中创建并应用电源计划](../LocTest/How-to-create-and-apply-power-plans-in-System-Center-Configuration-Manager.md)。  
  
## 在电源管理的监控和规划阶段保存或导出电源管理信息  
 每日报告所使用的电源管理信息将在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点数据库中保留 31 天。  
  
 每月报表所使用的电源管理信息将在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点数据库中保留 13 个月。  
  
 在电源管理的监控和规划阶段以及符合性阶段运行报表时，请从你想要为将来对比保留数据的报表保存或导出结果，以免以后被 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 删除。  
  
## 请参阅  
 [System Center Configuration Manager 中的电源管理计划](../LocTest/Planning-for-power-management-in-System-Center-Configuration-Manager.md)
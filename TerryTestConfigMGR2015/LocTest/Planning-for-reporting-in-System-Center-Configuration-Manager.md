---
title: "规划 System Center Configuration Manager 中的报告"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-other
ms.tgt_pltfrm: na
ms.topic: get-started-article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: ff920c84-d5c8-458c-b67f-bc7219b05690
caps.latest.revision: 6
caps.handback.revision: 5
---
# 规划 System Center Configuration Manager 中的报告
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的报表功能提供了一组工具和资源，可帮助你使用 SQL Server Reporting Services 的高级报表功能。 使用下列部分来帮助你在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中规划报表。  
  
##  <a name="BKMK_InstallReportingServicesPoint"></a> 确定 Reporting Services 点的安装位置  
 当在站点中运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 报表时，报表可以访问所连接的站点数据库中的信息。 使用下列部分来帮助你确定 Reporting Services 点的安装位置和要使用的数据源。  
  
> [!NOTE]  
>  有关在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中规划站点系统的详细信息，请参阅[添加 System Center Configuration Manager 的站点系统角色](../LocTest/Add-site-system-roles-for-System-Center-Configuration-Manager.md)。  
  
###  <a name="BKMK_SupportedSiteServers"></a> 支持的站点系统服务器  
 可以将 Reporting Services 点安装在管理中心站点和主站点上，以及安装在层次结构中的某个站点和其他站点的多个站点系统上。 在辅助站点上不支持 Reporting Services 点。 站点中的第一个 Reporting Services 点被配置为默认报表服务器。 可以在一个站点中添加更多的 Reporting Services 点，但 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 报表主要使用每个站点中的默认报表服务器。 可以将 Reporting Services 点安装在站点服务器或远程站点系统上。 但是，出于性能方面的原因，最佳方案是在远程站点系统服务器上使用 Reporting Services。  
  
###  <a name="BKMK_DataReplication"></a> 数据复制注意事项  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将它复制的数据分为全局数据和站点数据两类。 全局数据是指由管理用户创建并复制到整个层次结构中的所有站点的对象，不过辅助站点仅会获得部分全局数据。 全局数据的例子包括：软件部署、软件更新、集合和基于角色的管理安全作用域。 站点数据是指 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 主站点和向主站点报告的客户端创建的操作信息。 站点数据复制到管理中心站点，但不复制到其他主站点。 站点数据的例子包括：硬件清单数据、状态消息、警报和基于查询的集合的结果。 站点数据仅在管理中心站点和它源自的主站点中可见。  
  
 请考虑下列因素，以帮助你确定 Reporting Services 点的安装位置：  
  
-   使用管理中心站点数据库作为报表数据源的 Reporting Services 点可以访问 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 层次结构中的所有全局和站点数据。 如果需要包含层次结构中多个站点的站点数据的报表，请考虑在管理中心站点中的站点系统上安装 Reporting Services 点，并使用管理中心站点的数据库作为报表数据源。  
  
-   使用子主站点数据库作为报表数据源的 Reporting Services 点只能访问本地主站点和任何子辅助站点的全局数据及站点数据。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 层次结构中的其他主站点的站点数据均不会复制到主站点，因此 Reporting Services 无法访问这些数据。 如果需要包含特定主站点的站点数据或全局数据的报表，但不希望报表用户能够访问其他主站点中的站点数据，请在主站点中的站点系统上安装 Reporting Services 点，并使用主站点的数据库作为报表数据源。  
  
###  <a name="BKMK_NetworkBandwidth"></a> 网络带宽注意事项  
 同一个站点中的站点系统服务器使用服务器消息块 \(SMB\)、HTTP 或 HTTPS 相互通信，具体取决于你如何配置站点。 由于这些通信不受管理，而且可能随时发生，同时不会对网络带宽进行控制，因此，在将 Reporting Services 点角色安装到站点系统上之前，请查看可用的网络带宽。  
  
> [!NOTE]  
>  有关规划站点系统的详细信息，请参阅[添加 System Center Configuration Manager 的站点系统角色](../LocTest/Add-site-system-roles-for-System-Center-Configuration-Manager.md)。  
  
##  <a name="BKMK_RoleBaseAdministration"></a> 针对报告规划基于角色的管理  
 报表安全与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的其他角色很相似，具体而言，你可以将安全角色和权限分配给管理用户。 管理用户只能运行和修改他们具有相应安全权限的报表。 要运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中的报表，你必须具有对“站点”许可和为特定对象配置的许可的“读取”权限。  
  
 但是，与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的其他对象不同的是，对于你在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中为管理用户设置的安全权限，也必须在 Reporting Services 中配置这些权限。 当你在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中配置安全权限时，Reporting Services 点会连接到 Reporting Services 并为报表设置适当的权限。 例如，“软件更新管理员”安全角色具有关联的“运行报表”和“修改报表”权限。 仅获分配“软件更新管理员”角色的管理用户只能运行和修改软件更新的报表。 其他对象的报表不会显示在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中。 这方面的例外是，某些报表并未与特定的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 安全对象关联。 对于这些报表，管理用户必须具有“站点”权限的“读取”权才能运行报表，以及“站点”权限的“修改”权才能修改报表。  
  
 对于基于角色的管理，报表已完全启用。 将根据运行报表的管理用户的权限对 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 附带的所有报表的数据进行筛选。 具有特定角色的管理用户只能查看为其角色定义的信息。  
  
 有关报告的安全权限的详细信息，请参阅 [配置 System Center Configuration Manager 中的报表](../LocTest/Configuring-reporting-in-System-Center-Configuration-Manager.md)。  
  
 有关 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中基于角色的管理的详细信息，请参阅，请参阅 [为 System Center Configuration Manager 配置基于角色的管理](../LocTest/Configure-role-based-administration-for-System-Center-Configuration-Manager.md)。  
  
## 有关报表规划的补充性主题  
 下列的附加主题可帮助你在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中规划报表：  
  
-   [System Center Configuration Manager 中报告的先决条件](../LocTest/Prerequisites-for-reporting-in-System-Center-Configuration-Manager.md)  
  
-   [System Center Configuration Manager 中报告的最佳做法](../LocTest/Best-practices-for-reporting-in-System-Center-Configuration-Manager.md)  
  
## 请参阅  
 [System Center Configuration Manager 中的报表](../LocTest/Reporting-in-System-Center-Configuration-Manager.md)
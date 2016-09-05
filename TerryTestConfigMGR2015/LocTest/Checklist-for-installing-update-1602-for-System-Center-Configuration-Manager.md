---
title: "为 System Center Configuration Manager 安装更新 1602 的清单"
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
ms.assetid: b63ef197-01f0-4894-b929-5ef8403c5195
caps.latest.revision: 13
caps.handback.revision: 13
---
# 为 System Center Configuration Manager 安装更新 1602 的清单
从 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 版本 1511 更新为版本 1602 之前，请查看以下信息和清单以了解在开始更新之前要执行的操作。  
  
 **关于安装更新 1602：**  
  
 只能在层次结构的顶层站点上安装更新 1602。 这意味着会从管理中心站点（如果有）或从独立主站点启动安装。  
  
-   管理中心站点完成更新安装之后，子主站点会自动安装更新。 可以使用维护时段控制站点安装更新的时间。 从 1602 更新发布开始，维护时段重命名为服务时段。 有关详细信息，请参阅[站点服务器的服务时段](../LocTest/Install-in-console-updates-for-System-Center-Configuration-Manager.md#bkmk_ServiceWindow)。  
  
-   在主父站点完成更新安装之后，必须从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中手动更新辅助站点。 不支持辅助站点服务器的自动更新。  
  
 站点服务器安装更新时，站点服务器上安装的站点系统角色和远程计算机上安装的那些角色会自动更新。 因此，安装更新之前，请确保每个站点系统服务器满足使用新更新版本进行操作的任何新的先决条件。  
  
 更新完成之后首次使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台时，系统会提示你更新该控制台。  为此，必须在承载该控制台的计算机上运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 安装程序，并选择用于更新该控制台的选项。 我们建议不要延迟将更新安装到该控制台。  
  
 **清单：**  
  
 **确保所有站点都运行支持的 System Center Configuration Manager 版本：**层次结构中的每个站点服务器都必须运行 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 版本 1511，然后才能开始安装更新 1602。  
  
 **查看站点系统服务器上安装的 .NET 版本：**站点安装更新 1602 时，如果尚未安装 .NET Framework 4.5 或更高版本，则 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 会在托管以下站点系统角色之一的每台计算机上自动安装 .NET Framework 4.5.2：  
  
-   注册代理点  
  
-   注册点  
  
-   管理点  
  
-   服务连接点  
  
 此安装可以将站点系统服务器置于重新启动挂起状态，并向 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 组件状态查看器报告错误。 此外，服务器上的 .NET 应用程序可能具有随机故障，直到重新启动服务器。  
  
 有关详细信息，请参阅[站点和站点系统先决条件](Site%20and%20site%20system%20prerequisites%20for%20System%20Center%20Configuration%20Manager.md)  
  
 **查看站点和层次结构状态，并确认没有未解决的问题：**更新站点之前，请解决远程计算机上安装的站点服务器、站点数据库服务器和站点系统角色的所有操作问题。 由于现有的操作问题，站点更新可能会失败。  
 有关详细信息，请参阅[使用 System Center Configuration Manager 的警报和状态系统](../LocTest/Use-alerts-and-the-status-system-for-System-Center-Configuration-Manager.md)  
  
 **查看站点之间的文件和数据复制：**确保站点之间的文件和数据库复制正常运行并且处于最新状态。 延迟或积压工作可能会阻止平稳或成功更新。    
对于数据库复制，可以在开始更新之前，使用复制链接分析器来帮助解决问题。    
 有关详细信息，请参阅   
[System Center Configuration Manager 中的监视层次结构和复制基础结构](../LocTest/Monitor-hierarchy-and-replication-infrastructure-in-System-Center-Configuration-Manager.md)主题中的[关于复制链接分析器](../LocTest/Monitor-hierarchy-and-replication-infrastructure-in-System-Center-Configuration-Manager.md#BKMK_RLA)。  
  
 **为托管站点、站点数据库服务器和远程站点系统角色的计算机上的操作系统安装所有合适的关键更新：**为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 安装更新之前，请为每个适用的站点系统安装任何关键更新。 如果安装的更新需要重启，请在开始升级之前重启合适的计算机。  
  
 **在主站点上禁用管理点数据库副本：**[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 无法成功更新启用了管理点数据库副本的主站点。 禁用数据库复制，然后：  
  
-   创建站点数据库的备份以测试数据库升级  
  
-   安装更新 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]  
  
 有关详细信息，请参阅   
[System Center Configuration Manager 管理点的数据库副本](../LocTest/Database-replicas-for-management-points-for-System-Center-Configuration-Manager.md)  
  
 **重新配置使用 NLB 的软件更新点：**[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 无法更新使用网络负载平衡 (NLB) 群集来托管软件更新点的站点。  
如果为软件更新点使用 NLB 群集，请使用 PowerShell 删除 NLB 群集。    
 有关详细信息，请参阅[在 System Center Configuration Manager 中规划软件更新](../LocTest/Plan-for-software-updates-in-System-Center-Configuration-Manager.md)  
  
 **在站点上的更新安装过程中，禁用每个站点上的所有站点维护任务：**安装更新之前，请禁用可能会在升级过程进行时运行的任何站点维护任务。 这包括但不限于以下各项：  
  
-   备份站点服务器  
  
-   删除过期的客户端操作  
  
-   删除过期的发现数据  
  
 站点数据库维护任务在更新安装过程中运行时，更新安装可能会失败。 在禁用任务之前，请记录该任务的计划，以便可以在安装更新之后恢复其配置。  
 有关详细信息，请参阅 [System Center Configuration Manager 的维护任务](../LocTest/Maintenance-tasks-for-System-Center-Configuration-Manager.md)和 [System Center Configuration Manager 维护任务参考](../LocTest/Reference-for-maintenance-tasks-for-System-Center-Configuration-Manager.md)  
  
 **在管理中心站点和主站点上创建站点数据库备份：**更新站点之前，请备份站点数据库，以确保具有用于灾难恢复的成功备份。   
有关详细信息，请参阅 [Backup and recovery for System Center Configuration Manager](../LocTest/Backup-and-recovery-for-System-Center-Configuration-Manager.md)。  
  
 **备份自定义 Configuration.mof 文件：**如果使用自定义 Configuration.mof 文件定义与硬件清单一起使用的数据类，则在更新站点之前创建此文件的备份。 随后在进行更新之后，将此文件还原到版本 1602 站点。 更新站点时，当前文件会覆盖为文件的原始（默认值）版本。 有关使用此文件的详细信息，请参阅[如何在 System Center Configuration Manager 中扩展硬件清单](../LocTest/How-to-extend-hardware-inventory-in-System-Center-Configuration-Manager.md)  
  
 **在最近的站点数据库备份副本上测试数据库升级：**更新 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 管理中心站点或主站点之前，请在站点数据库副本上测试站点数据库升级过程。  
  
-   你应该测试站点数据库升级过程，因为当你升级站点时，可能会修改站点数据库  
  
-   虽然测试数据库升级不是必需的，但可以在生产数据库受到影响之前先行确定升级的问题  
  
-   失败的站点数据库升级可能会使站点数据库无法运行，并且可能需要进行站点恢复以还原功能  
  
-   虽然在层次结构的站点之间共享了站点数据库，但是，请在升级每个合适的站点之前计划在该站点上测试数据库  
  
-   如果在主站点上对管理点使用数据库副本，请在创建站点数据库备份之前禁用复制  
  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不支持辅助站点备份，也不支持辅助站点数据库的测试升级。   
不支持在生产站点数据库上运行测试数据库升级。 执行此任务会升级站点数据库，并可能导致你的站点无法运行。 有关详细信息，请参阅[升级到 System Center Configuration Manager](../LocTest/Upgrade-to-System-Center-Configuration-Manager.md) 中的[测试站点数据库升级](../LocTest/Upgrade-to-System-Center-Configuration-Manager.md#bkmk_test)部分。  
  
 **规划客户端试点：**安装更新客户端的更新后，可以在部署和升级所有活动客户端前在预生产中测试新的客户端更新。   
 若要利用此选项，在开始更新安装之前必须配置站点，以便对预生产支持自动升级。 有关详细信息，请参阅[在 System Center Configuration Manager 中升级客户端](../LocTest/Upgrade-clients-in-System-Center-Configuration-Manager.md)和   
[如何在 System Center Configuration Manager 中的预生产集合中测试客户端升级](../LocTest/How-to-test-client-upgrades-in-a-preproduction-collection-in-System-Center-Configuration-Manager.md)  
  
 **计划使用维护时段**  
 **控制站点服务器安装更新的时间：**可以使用维护时段定义应用于主站点服务器的时间段，在此期间可以安装该站点的更新。   
这可以帮助你控制层次结构中的站点安装更新的时间。   
从 1602 更新发布开始，维护时段重命名为服务时段。 有关详细信息，请参阅[站点服务器的服务时段](../LocTest/Install-in-console-updates-for-System-Center-Configuration-Manager.md#bkmk_ServiceWindow)。  
  
 **运行安装程序先决条件检查程序：**安装更新 1602 之前，可以独立于更新安装来运行先决条件检查程序。 在站点上升级更新时，会再次运行先决条件检查程序。  
有关详细信息，请参阅 [System Center Configuration Manager 的更新](../LocTest/Updates-for-System-Center-Configuration-Manager.md)主题中的**步骤 3：安装更新之前运行先决条件检查程序**。  
  
> [!IMPORTANT]  
>  先决条件检查程序作为更新安装的一部分运行或独立运行时，该过程会更新某些用于站点维护任务的产品源文件。 因此，在运行先决条件检查程序之后，但是在安装 1602 更新之前，如果必须执行站点维护任务，则从站点服务器上的 CD.Latest 文件夹运行 **Setupwfe.exe**（[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 安装程序）。  
  
 **更新站点：**现已准备好可以为层次结构开始更新安装。  
  我们建议你计划在正常营业时间之外为每个站点安装更新，此时安装更新的过程以及用于重新安装站点组件和站点系统角色的操作对业务运营的影响最小。 有关详细信息，请参阅 [ System Center Configuration Manager 的更新](../LocTest/Updates-for-System-Center-Configuration-Manager.md)。  
  
## 另请参阅  
 [System Center Configuration Manager 的更新](../LocTest/Updates-for-System-Center-Configuration-Manager.md)
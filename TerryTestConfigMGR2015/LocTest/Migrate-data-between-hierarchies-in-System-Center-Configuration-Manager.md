---
title: "在 System Center Configuration Manager 中层次结构之间迁移数据"
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
ms.assetid: cf014eb0-f8c2-4d37-b8d7-368d63a10b89
caps.latest.revision: 11
caps.handback.revision: 9
---
# 在 System Center Configuration Manager 中层次结构之间迁移数据
使用迁移将数据从支持的源层次结构迁移到 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 目标层次结构。 从源层次结构迁移数据时：  
  
-   从你在源基础结构中标识的站点数据库访问数据，然后将数据传输到当前环境  
  
-   迁移不会更改源层次结构中的数据，而是会发现数据，并将副本存储在目标层次结构的数据库  
  
 规划迁移策略时，请考虑以下事项：  
  
-   可以将现有的 [!INCLUDE[cm4short](../LocTest/includes/cm4short_md.md)] SP2 基础结构迁移到 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]。  
  
-   可以从源站点迁移部分或全部受支持的数据。  
  
-   可以将数据从单个源站点迁移到目标层次结构中的多个不同站点。  
  
-   可以将数据从多个源站点移到目标层次结构中的单个站点。  
  
## <a name="BKMK_MigrationConcepts"></a>有关迁移的概念  
以下信息说明了你在使用迁移时可能遇到的概念和术语。  
  
|概念或术语|更多信息|  
|---------|--------|  
|源层次结构|一种层次结构，其运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的支持版本并包含你想要迁移的数据。 在配置迁移时，在指定源层次结构的顶层站点时标识源层次结构。 在指定源层次结构之后，目标层次结构的顶层站点从指定的源站点的数据库中收集数据，以确定可迁移的数据。<br /><br />有关详细信息，请参阅[源层次结构](../LocTest/Planning-a-source-hierarchy-strategy-in-System-Center-Configuration-Manager.md#BKMK_Source_Hierarchies)主题中的[在 System Center Configuration Manager 中规划源层次结构策略](../LocTest/Planning-a-source-hierarchy-strategy-in-System-Center-Configuration-Manager.md)部分。|  
|源站点|源层次结构中的站点，具有可迁移到目标层次结构中的数据。<br /><br />有关详细信息，请参阅[源站点](../LocTest/Planning-a-source-hierarchy-strategy-in-System-Center-Configuration-Manager.md#BKMK_Source_Sites)主题中的[在 System Center Configuration Manager 中规划源层次结构策略](../LocTest/Planning-a-source-hierarchy-strategy-in-System-Center-Configuration-Manager.md)部分。|  
|目标层次结构|[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 层次结构，迁移在其中运行以从源层次结构导入数据。|  
|数据收集|确定源层次结构中可迁移到目标层次结构的信息的持续过程。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将按计划检查源层次结构，以确定对源层次结构中先前迁移的信息和目标层次结构中可能需要更新的信息的任何更改。<br /><br />有关详细信息，请参阅[数据收集](../LocTest/Planning-a-source-hierarchy-strategy-in-System-Center-Configuration-Manager.md#BKMK_Data_Gathering)主题中的[在 System Center Configuration Manager 中规划源层次结构策略](../LocTest/Planning-a-source-hierarchy-strategy-in-System-Center-Configuration-Manager.md)部分。|  
|迁移作业|配置要迁移的特定对象，然后管理将这些对象迁移到目标层次结构的过程。<br /><br />有关详细信息，请参阅[在 System Center Configuration Manager 中规划迁移作业策略](../LocTest/Planning-a-migration-job-strategy-in-System-Center-Configuration-Manager.md)。|  
|客户端迁移|将客户端使用的信息从源站点的数据库传输到目标层次结构的数据库的过程。 在进行此数据迁移之后，将设备上的客户端软件升级到目标层次结构中的客户端软件版本。<br /><br />有关详细信息，请参阅 [在 System Center Configuration Manager 中规划客户端迁移策略](../LocTest/Planning-a-client-migration-strategy-in-System-Center-Configuration-Manager.md)。|  
|共享的分发点|源层次结构中的分发点，它们在迁移期间与目标层次结构共享。<br /><br />在迁移期间，分配到目标层次结构中的站点的客户端可以获得共享的分发点中的内容。<br /><br />有关详细信息，请参阅[在源和目标层次结构之间共享分发点](../LocTest/Planning-a-content-deployment-migration-strategy-in-System-Center-Configuration-Manager.md#About_Shared_DPs_in_Migration)主题中的[在 System Center Configuration Manager 中规划内容部署迁移策略](../LocTest/Planning-a-content-deployment-migration-strategy-in-System-Center-Configuration-Manager.md)部分|  
|监视迁移|监视迁移活动的过程。 通过“管理”工作区中的“迁移”节点监视迁移的进度和成功情况。<br /><br />有关详细信息，请参阅[在 System Center Configuration Manager 中规划监视迁移活动](../LocTest/Planning-to-monitor-migration-activity-in-System-Center-Configuration-Manager.md)。|  
|停止收集数据|停止从源站点收集数据的过程。 如果不再具有要从源层次结构迁移的数据，或者，如果要临时暂停与迁移相关的活动，则可以将目标层次结构配置为停止从该源层次结构收集数据。<br /><br />有关详细信息，请参阅[数据收集](../LocTest/Planning-a-source-hierarchy-strategy-in-System-Center-Configuration-Manager.md#BKMK_Data_Gathering)主题中的[在 System Center Configuration Manager 中规划源层次结构策略](../LocTest/Planning-a-source-hierarchy-strategy-in-System-Center-Configuration-Manager.md)部分。|  
|清理迁移数据|通过从目标层次结构数据库中删除有关迁移的信息来完成从源层次结构进行的迁移的过程。<br /><br />有关详细信息，请参阅[规划在 System Center Configuration Manager 中完成迁移](../LocTest/Planning-to-complete-migration-in-System-Center-Configuration-Manager.md)。|  
  
## 迁移的典型工作流  
  
1.  指定支持的源层次结构。  
  
2.  配置数据收集。 数据收集能让 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 收集有关可以从源层次结构迁移的数据的信息。  
  
    [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 会自动按照简单的计划重复这个数据收集过程，直到你停止此过程为止。 默认情况下，数据收集过程每小时重复一次，因此，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 可以识别对源层次结构中你可能想迁移的数据所做的更改。 如果将分发点从源层次结构共享到目标层次结构，则也要进行数据收集。  
  
3.  创建迁移作业以在源和目标层次结构之间迁移数据。  
  
4.  你随时都可以使用“停止收集数据”命令来停止数据收集过程。 在停止数据收集时，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不再识别对源层次结构中的数据所做的更改，而且再不能够在源和目标层次结构之间共享分发点。 通常，在你不再计划迁移数据或共享源层次结构中的分发点时使用此操作。  
  
5.  在源层次结构的所有站点均已停止数据收集之后，你可以根据需要使用“清理迁移数据”命令来清理迁移数据。 此命令将从目标层次结构的数据库中删除有关从源层次结构进行的迁移的历史数据。  
  
在从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 源层次结构中迁移了你不再用于管理环境的数据之后，可以计划解除该源层次结构和基础结构的授权。  
  
## <a name="BKMK_MigrationScenarios"></a>迁移方案  
[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 支持以下迁移方案。  
  
> [!NOTE]  
> 将包含独立站点的层次结构扩展为包含管理中心站点的层次结构并不归类为迁移。 有关层次结构扩展的信息，请参阅[扩展独立主站点](../Topic/Install%20System%20Center%20Configuration%20Manager%20sites.md#bkmk_Expand)主题中的[安装 System Center Configuration Manager 站点](../Topic/Install%20System%20Center%20Configuration%20Manager%20sites.md)部分。  
  
### 从 Configuration Manager 2007 层次结构进行迁移  
在使用迁移方法从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 2007 迁移数据时，你可以保留在现有站点基础结构中的投资，并获得以下好处：  
  
|好处|更多信息|  
|------|--------|  
|站点数据库的改进|[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 数据库支持完整的 Unicode。|  
|站点之间的数据库复制|[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的复制基于 Microsoft SQL Server。 这能改善站点间数据传输的性能。|  
|以用户为中心的管理|用户是 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的管理任务的焦点。 例如，即使你不知道某用户的设备名称，也可以将软件分发给该用户。 此外，[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 还能让用户在更大程度上控制在其设备上安装哪个软件，以及何时安装该软件。|  
|层次结构简化|在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中，管理中心站点类型以及主站点和辅助站点的行为的更改可让你建立使用较少网络带宽和需要较少服务器的更简单的站点层次结构。|  
|基于角色的管理|这是 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的中央安全模型，它提供了与你的管理要求和业务要求相对应的、覆盖整个层次结构的安全性和管理。|  
  
> [!NOTE]  
> 由于 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 中首次引入的设计更改，你无法将 [!INCLUDE[cm4short](../LocTest/includes/cm4short_md.md)] 基础架构升级到 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]。 但是，支持从 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 到 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 就地升级。  
  
### 从 Configuration Manager 2012 或另一个 System Center Configuration Manager 层次结构的迁移  
从 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 或 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 层次结构迁移数据的过程相同。 这包括将数据从多个源层次结构迁移到一个目标层次结构，例如在贵公司获得了已经由 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 管理的额外资源时。 此外，还可以将数据从测试环境迁移到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 生产环境。 这可让你保留在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 测试环境中的投资。  
  
## 关于迁移的的其他主题：  
  
-   [规划迁移到 System Center Configuration Manager](../LocTest/Planning-for-migration-to-System-Center-Configuration-Manager.md)  
  
-   [配置源层次结构和源站点以迁移到 System Center Configuration Manager](../LocTest/Configuring-source-hierarchies-and-source-sites-for-migration-to-System-Center-Configuration-Manager.md)  
  
-   [用于迁移到 System Center Configuration Manager 的操作](../LocTest/Operations-for-migrating-to-System-Center-Configuration-Manager.md)  
  
-   [有关迁移到 System Center Configuration Manager 的安全性和隐私](../LocTest/Security-and-privacy-for-migration-to-System-Center-Configuration-Manager.md)  
  
## 请参阅  
[开始使用 System Center Configuration Manager](../LocTest/Start-using-System-Center-Configuration-Manager.md)
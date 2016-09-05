---
title: "System Center Configuration Manager 中针对迁移规划的管理员清单"
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
ms.assetid: 295fdf07-93cc-490c-acdd-ce3ee88cb36f
caps.latest.revision: 7
caps.handback.revision: 6
translationtype: Human Translation
---
# System Center Configuration Manager 中针对迁移规划的管理员清单
使用以下管理员清单帮助你规划迁移到 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]的策略：  
  
-   [针对迁移规划的管理员清单](#Checklist_Migraiton_Planning)  
  
-   [针对层次结构迁移的管理员清单](#Checklist_Hierarchy_for_migration)  
  
-   [针对迁移的管理员清单](#Checklisit_Migration)  
  
##  <a name="Checklist_Migraiton_Planning"></a> 针对迁移规划的管理员清单  
 使用以下清单来执行迁移前的规划步骤。  
  
-   **评估当前环境：**  
  
     确定源层次结构满足的现有业务要求，并制定计划以便在目标层次结构中继续满足这些要求。  
  
-   **查看可以通过你使用的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 版本实现的功能和变化，并使用此信息帮助你设计目标层次结构：**  
  
     有关详细信息，请参阅 [Fundamentals of System Center Configuration Manager](../LocTest/Fundamentals-of-System-Center-Configuration-Manager.md) 和 [What's new in System Center Configuration Manager](../Topic/What's%20new%20in%20System%20Center%20Configuration%20Manager.md)。  
  
-   **确定要用于基于角色的管理的管理安全模型：**  
  
     有关详细信息，请参阅 [System Center Configuration Manager 基于角色的管理基础](../LocTest/Fundamentals-of-role-based-administration-for-System-Center-Configuration-Manager.md)。  
  
-   **评估网络和 Active Directory 拓扑：**  
  
     查看现有的域结构和网络拓扑，并考虑它们如何影响层次结构的设计和迁移任务。  
  
-   **最终确定目标层次结构的设计：**  
  
     确定管理中心站点、主站点、辅助站点和内容分发选项的布局。  
  
-   **将层次结构映射到你将用于目标层次结构中的站点和站点服务器的计算机：**  
  
     确定站点和站点系统服务器将在目标层次结构中使用的计算机，并确保它们有足够的能力满足目前和未来的操作要求。  
  
-   **规划对象迁移策略：**  
  
     制定计划以使用可用的迁移作业来迁移不同的对象，包括站点边界、集合、播发和部署。 有关详细信息，请参阅[在 System Center Configuration Manager 中规划迁移作业策略](../LocTest/Planning-a-migration-job-strategy-in-System-Center-Configuration-Manager.md)中的[迁移作业的类型](../LocTest/Planning-a-migration-job-strategy-in-System-Center-Configuration-Manager.md#Types_of_Migration)  
  
     [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 仅迁移你选择的对象。 对于未迁移但在目标层次结构中需要的任何对象，必须在目标层次结构中重新创建这些对象。  
  
     在你配置迁移作业时，会显示可以迁移的对象。  
  
-   **规划客户端迁移策略：**  
  
     制定计划以使用受控的方法来迁移客户端，此方法在你将客户端迁移到目标层次结构时限制网络带宽和服务器处理要求。 有关规划客户端迁移策略的详细信息，请参阅 [Planning a client migration strategy in System Center Configuration Manager](../LocTest/Planning-a-client-migration-strategy-in-System-Center-Configuration-Manager.md)。  
  
-   **规划清单和符合性数据：**  
  
     [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不支持迁移硬件清单、软件清单或者软件更新或客户端所需的配置管理符合性数据。  
  
     实际上，当客户端迁移到它在目标层次结构中的新站点并获得这些配置的策略之后，客户端将此信息提交给为它分配的站点。 此操作将当前的清单和符合性数据填充到目标站点数据库中。  
  
-   **为完成从源层次结构进行的迁移制定计划：**  
  
     确定何时迁移对象和客户端。 在迁移完成后，可以计划解除源层次结构中的站点服务器的授权。  
  
##  <a name="Checklist_Hierarchy_for_migration"></a> 针对层次结构迁移的管理员清单  
 使用以下清单帮助你在开始迁移之前规划目标层次结构。  
  
-   **确定要在目标层次结构中使用的计算机：**  
  
     [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不支持 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 2007 基础结构的就地升级。 而是使用迁移来将数据从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 2007 移动到 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]。 这要求你使用并排部署并在新计算机上安装 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]。  
  
     类似地，在从另一个 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 层次结构进行迁移时，必须安装与源层次结构成为并排部署的新目标层次结构。  
  
-   **创建目标层次结构：**  
  
     为了准备迁移，要安装和配置包含一个主站点的 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 目标层次结构。 例如：  
  
    -   安装一个管理中心站点，然后安装至少一个子主站点  
  
    -   如果未计划使用管理中心站点，则安装一个独立主站点。  
  
-   **如果想迁移与软件更新相关的信息，则在目标层次结构中配置软件更新点，然后同步软件更新：**  
  
     在可以从源层次结构迁移软件更新信息之前，必须配置和同步目标层次结构中的软件更新。  
  
     有关详细信息，请参阅[在 System Center Configuration Manager 中配置软件更新](../LocTest/Configure-software-updates-in-System-Center-Configuration-Manager.md)。  
  
-   **在目标层次结构中安装和配置其他站点系统角色：**  
  
     配置你需要的其他站点系统角色和站点系统。  
  
-   **在目标层次结构中验证操作功能：**  
  
     检查下列项目：  
  
    -   如果目标层次结构包含多个站点，则确认数据库复制在站点之间有效。 数据库复制不适用于独立主站点。  
  
    -   验证所有已安装的站点系统角色是否正常工作。  
  
    -   验证你安装到目标层次结构中的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端是否可以成功地与为它们分配的站点通信。  
  
> [!NOTE]  
>  有关如何规划 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 层次结构的详细信息，请参阅 [System Center Configuration Manager 基础结构的规划](../LocTest/Plan-for-System-Center-Configuration-Manager-infrastructure.md)。  
  
##  <a name="Checklisit_Migration"></a> 针对迁移的管理员清单  
 使用以下清单帮助将数据从源层次结构迁移到目标层次结构。  
  
-   **在目标层次结构中启用迁移：**  
  
     通过指定源层次结构的顶层站点来配置源层次结构。 有关指定源站点的详细信息，请参阅 [Planning a source hierarchy strategy in System Center Configuration Manager](../LocTest/Planning-a-source-hierarchy-strategy-in-System-Center-Configuration-Manager.md)。  
  
-   **在源层次结构运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 2007 SP2 时，选择并配置源层次结构中的其他站点：**  
  
     对于 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 2007 SP2 源层次结构中你想从其中收集数据的每个其他站点，必须配置用于数据收集的凭据。 在配置每个源站点时，数据收集过程会立即开始，并在整个迁移期间持续进行，直到你停止收集该站点的数据为止。 数据收集确保你可以从源层次结构中迁移自上次数据收集过程之后更新或新创建的对象。  
  
    > [!NOTE]  
    >  在源层次结构运行 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 或更高版本时，你无需配置其他源站点。  
  
-   **配置分发点共享：**  
  
     可以在两个层次结构之间共享分发点，以使目标层次结构中的客户端可以使用你迁移的对象的内容。 这确保了两个层次结构中的客户端仍然可以使用相同的内容，而且你可以在停止收集数据和完成迁移之前保留这些内容。  
  
     有关共享的分发点的信息，请参阅 [Share Distribution Points Between Source and Destination Hierarchies](../LocTest/Planning-a-content-deployment-migration-strategy-in-System-Center-Configuration-Manager.md#About_Shared_DPs_in_Migration) 主题中的 [Planning a content deployment migration strategy in System Center Configuration Manager](../LocTest/Planning-a-content-deployment-migration-strategy-in-System-Center-Configuration-Manager.md) 部分。  
  
-   **创建并运行迁移作业，以迁移与源层次结构中的客户端关联的对象：**  
  
     创建迁移作业，以在层次结构之间迁移对象。 每个迁移作业所需的配置可能会因作业迁移的数据而异。  
  
     例如，在迁移内容时，无论使用哪个迁移作业，都必须分配目标层次结构中的站点来负责管理该内容。 分配的站点将访问内容的原始源文件位置，并负责将该内容分发到目标层次结构中的分发点。  
  
     有关详细信息，请参阅 [Create and Edit Migration Jobs for System Center Configuration Manager](../LocTest/Operations-for-migrating-to-System-Center-Configuration-Manager.md#Create_Edit_migration_Jobs) 主题中的 [Operations for migrating to System Center Configuration Manager](../LocTest/Operations-for-migrating-to-System-Center-Configuration-Manager.md) 部分。  
  
-   **将客户端迁移到目标层次结构：**  
  
     迁移客户端的过程取决于迁移方案：  
  
    -   在迁移具有与目标层次结构不同的客户端版本的客户端时，客户端软件必须升级。 升级需要删除当前的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端，然后安装与目标站点匹配的新客户端版本。  
  
    -   在迁移具有与目标层次结构的版本匹配的客户端版本的客户端时，客户端不会升级或重新安装， 而是重新分配到目标层次结构中的主站点。  
  
     在将客户端迁移到目标层次结构时，客户端与它以前被你迁移到该目标层次结构的数据关联。  
  
     有关详细信息，请参阅 [Planning a client migration strategy in System Center Configuration Manager](../LocTest/Planning-a-client-migration-strategy-in-System-Center-Configuration-Manager.md)。  
  
-   **升级或重新分配共享分发点：**  
  
     当不再必须支持源层次结构中的客户端时，你可以升级 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 2007 源站点中的共享分发点，或重新分配 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 或 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 源站点中的共享分发点。 在升级或重新分配分发点时，站点系统角色传输到目标层次结构中的主站点，同时会从源层次结构的源站点中删除该分发点。 在升级或重新分配共享的分发点时，内容保留在分发点计算机上，并且你不必将内容重新部署到目标层次结构中的新分发点。  
  
     还可以升级在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 2007 辅助站点服务器上共存的分发点。 这将删除辅助站点，并导致目标层次结构中只有一个分发点。  
  
     有关共享的分发点的信息，请参阅 [Share Distribution Points Between Source and Destination Hierarchies](../LocTest/Planning-a-content-deployment-migration-strategy-in-System-Center-Configuration-Manager.md#About_Shared_DPs_in_Migration) 主题中的 [Planning a content deployment migration strategy in System Center Configuration Manager](../LocTest/Planning-a-content-deployment-migration-strategy-in-System-Center-Configuration-Manager.md) 部分。  
  
-   **完成迁移：**  
  
     在从源层次结构中的所有站点迁移了数据和客户端且升级了适用的分发点之后，就可以完成迁移。 若要完成迁移，请停止为源层次结构中的每个源站点收集数据。 之后，可以删除不需要的迁移信息，并解除源层次结构的基础结构的授权。 有关详细信息，请参阅 [Planning to complete migration in System Center Configuration Manager](../LocTest/Planning-to-complete-migration-in-System-Center-Configuration-Manager.md)。  
  
## 另请参阅  
 [规划迁移到 System Center Configuration Manager](../LocTest/Planning-for-migration-to-System-Center-Configuration-Manager.md)
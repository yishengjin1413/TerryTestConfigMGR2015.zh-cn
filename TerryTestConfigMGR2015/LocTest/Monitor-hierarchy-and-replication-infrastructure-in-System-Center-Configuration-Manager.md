---
title: "System Center Configuration Manager 中的监视层次结构和复制基础结构"
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
ms.assetid: 3fab4d67-8d2a-45ce-8b06-471280102cf6
caps.latest.revision: 11
caps.handback.revision: 10
translationtype: Human Translation
---
# System Center Configuration Manager 中的监视层次结构和复制基础结构
要在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]中监视基础架构和操作，请使用 **控制台中的“监视”**[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 工作区。  
  
> [!NOTE]  
>  此位置的例外是“迁移”，迁移是从“管理”  工作区的“迁移”  节点中直接监视的。 有关详细信息，请参阅 [Operations for migrating to System Center Configuration Manager](../LocTest/Operations-for-migrating-to-System-Center-Configuration-Manager.md)。  
  
 除了使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台进行监视外，你还可以使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 报表，或查看 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 组件的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 日志文件。 有关使用报表的详细信息，请参阅 [System Center Configuration Manager 中的报表](../LocTest/Reporting-in-System-Center-Configuration-Manager.md)。 有关日志文件的详细信息，请参阅 [System Center Configuration Manager 中的日志文件](../LocTest/Log-files-in-System-Center-Configuration-Manager.md)。  
  
 在监视站点时，请查看指示需要你采取措施的问题的迹象。 例如：  
  
-   站点服务器和站点系统上的文件积压。  
  
-   指示错误或问题的状态消息。  
  
-   失败的站点内通信。  
  
-   服务器上系统事件日志中的错误和警告消息。  
  
-   Microsoft SQL Server 错误日志中的错误和警告消息。  
  
-   长时间未报告的站点或客户端。  
  
-   SQL Server 数据库响应缓慢。  
  
-   硬件故障的迹象。  
  
 为了最大程度地降低站点故障的风险，如果监视任务暴露出任何问题迹象，请尽快调整问题根源并将其修复。  
  
 使用下列部分中的信息来帮助你监视 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]的基础架构和常见操作。  
  
-   [监视 Configuration Manager 的常用管理任务](#BKMK_MonintorMgmtTasks)  
  
-   [监视 Configuration Manager 的层次结构基础结构](#BKMK_MonitorInfrastructure)  
  
    -   [关于站点层次结构节点](#BKMK_SH_Node)  
  
    -   [如何监视数据库复制链接和复制状态](#BKMK_MonitorRepLinksAndStatuss)  
  
    -   [关于复制链接分析器](#BKMK_RLA)  
  
    -   [用于监视数据库复制的过程](#BKMK_ProcsforMonitoringReplication)  
  
-   [使用 System Center Configuration Manager 的警报和状态系统](../LocTest/Use-alerts-and-the-status-system-for-System-Center-Configuration-Manager.md)中的[监视 Configuration Manager 的状态系统](../LocTest/Use-alerts-and-the-status-system-for-System-Center-Configuration-Manager.md#BKMK_MonitorSystemStatus)部分  
  
-   [使用 System Center Configuration Manager 的警报和状态系统](../LocTest/Use-alerts-and-the-status-system-for-System-Center-Configuration-Manager.md)中的[监视警报](../LocTest/Use-alerts-and-the-status-system-for-System-Center-Configuration-Manager.md#BKMK_MonitorAlerts)  
  
##  <a name="BKMK_MonintorMgmtTasks"></a> 监视 Configuration Manager 的常用管理任务  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台内提供内置监视。 你可以监视许多任务，其中包括与整个层次结构中的软件更新、电源管理以及内容部署相关的那些任务。  
  
 使用下列信息来帮助你监视常见的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 任务。  
  
 **警报**  
  
 请参阅 [Monitor alerts](../LocTest/Use-alerts-and-the-status-system-for-System-Center-Configuration-Manager.md#BKMK_MonitorAlerts) 中的 [Use alerts and the status system for System Center Configuration Manager](../LocTest/Use-alerts-and-the-status-system-for-System-Center-Configuration-Manager.md)。  
  
 **符合性设置**  
  
 请参阅[如何在 System Center Configuration Manager 中监视符合性设置](../LocTest/How-to-monitor-compliance-settings-in-System-Center-Configuration-Manager.md)。  
  
 **内容部署**  
  
 有关监视内容的常规信息，请参阅[为 System Center Configuration Manager 管理内容和内容基础结构](../LocTest/Manage-content-and-content-infrastructure-for-System-Center-Configuration-Manager.md)。  
  
 有关监视特定类型的内容部署的信息：  
  
-   若要监视应用程序，请参阅[使用 System Center Configuration Manager 监视应用程序](../LocTest/Monitor-applications-with-System-Center-Configuration-Manager.md)。  
  
-   若要监视包和程序，请参阅 [System Center Configuration Manager 中的包和程序](../LocTest/Packages-and-programs-in-System-Center-Configuration-Manager.md)中的“如何管理包和程序”。  
  
 **Endpoint Protection**  
  
 请参阅[如何在 System Center Configuration Manager 中监视 Endpoint Protection](../LocTest/How-to-monitor-Endpoint-Protection-in-System-Center-Configuration-Manager.md)。  
  
 **监视电源管理**  
  
 请参阅[如何在 System Center Configuration Manager 中监视和规划电源管理](../LocTest/How-to-monitor-and-plan-for-power-management-in-System-Center-Configuration-Manager.md)。  
  
 **监视软件计数**  
  
 请参阅[在 System Center Configuration Manager 中使用软件计数监视应用使用情况](../LocTest/Monitor-app-usage-with-software-metering-in-System-Center-Configuration-Manager.md)。  
  
 **监视软件更新**  
  
 请参阅[在 System Center Configuration Manager 中管理软件更新](../LocTest/Manage-software-updates-in-System-Center-Configuration-Manager.md)。  
  
##  <a name="BKMK_MonitorInfrastructure"></a> 监视 Configuration Manager 的层次结构基础结构  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 提供了若干方法来监视层次结构的状态和操作。 你可以检查整个层次结构中站点的系统状态、通过站点层次结构或地理视图监视站点内复制、针对数据库复制监视站点之间的复制链接，并使用复制链接分析器工具来修正复制问题。  
  
###  <a name="BKMK_SH_Node"></a> 关于站点层次结构节点  
 “监视”  工作区中的“站点层次结构”  节点提供 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 层次结构和站点间链接的概述。 你可以使用两个视图：  
  
-   **层次结构关系图**：此视图将层次结构显示为一个拓扑图，该拓扑图经过简化，仅显示重要信息。  
  
-   **地理视图**：此视图在显示你配置的站点位置的地图上显示你的站点。  
  
 使用“站点层次结构”  节点来监视每个站点的运行状况，以及站点内复制链接及它们与外部因素（例如地理位置）的关系。  
  
 由于站点状态和站点内链接状态以站点数据（而不是全局数据）形式复制，因此当你将 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台连接到子主站点时，将无法查看其他主站点或其子辅助站点的站点或链接状态。 例如，在多主站点层次结构中，当 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台连接到主站点时，你可以查看子辅助站点、主站点和管理中心站点的状态，但看不到管理中心站点下层次结构的其他节点的状态。  
  
 使用“配置设置”  命令来控制站点层次结构显示的呈现方式。 你在 **控制台连接到一个站点时对“站点层次结构”**[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 节点进行的配置将被复制到所有其他站点。  
  
#### 层次结构关系图  
 层次结构关系图在拓扑图中显示你的站点。 在此视图中，你可以选择站点并查看该站点中的状态消息摘要，向下钻取以查看状态消息，以及访问站点的“属性”  对话框。  
  
 此外，你可以将鼠标指针悬停在站点或站点之间的复制链接上以查看该对象的高级状态。 由于复制链接状态不会全局复制，因此，在包含多个主站点的层次结构中，你必须将 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台连接到管理中心站点才能查看所有站点之间的复制链接详细信息。  
  
 下列选项会修改层次结构关系图：  
  
-   **组**：你可以配置在层次结构关系图显示中触发更改的主站点和辅助站点的数量，该关系图将这些站点合并为一个对象。 如果站点合并为一个对象，你将看到站点的总数，以及状态消息和站点状态的高级汇总。 组配置不影响地理视图。  
  
-   **收藏站点**：你可以将单独的站点指定为收藏站点。 星形图标在层次结构关系图中标识收藏站点。 当你使用组时，收藏站点不会与其他站点合并，并始终会单独显示。  
  
#### 地理视图  
 地理视图显示每个站点在地图上的位置。 只会显示与位置一起配置的站点。 在此视图中选择站点时，将显示指向父站点或子站点的复制链接。 与层次结构关系图视图不同，你无法在此视图中显示站点状态消息或复制链接详细信息。  
  
> [!NOTE]  
>  要使用地理视图， [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台所连接到的计算机必须安装 Internet Explorer，并且必须能够通过使用 HTTP 协议来访问 Bing 地图。  
  
 下列选项修改地理视图。  
  
-   **站点位置**：你可以指定每个站点的地理位置。 你可以将位置指定为街道地址、位置名称（例如城市名称），或者通过经纬度坐标来指定位置。 例如，要使用华盛顿雷蒙德市的经纬度，你将指定 **N 47 40 26.3572 W 122 7 17.4432** 作为站点位置。 你无需为经纬度的度、分或秒指定符号。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 使用必应地图在地理视图上显示位置。 这样，你将能选择相对于某个地理位置查看你的层次结构，从而可深入了解可能影响特定站点或站点内复制的区域问题。  
  
     在指定位置时，你可以使用“位置”  框来搜索层次结构中的特定站点。 选中站点后，在“位置”  列中输入城市名或街道地址作为位置。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 使用必应地图解析位置。  
  
###  <a name="BKMK_MonitorRepLinksAndStatuss"></a> 如何监视数据库复制链接和复制状态  
 除了可从“监视”  工作区“站点层次结构”  节点访问的高层详细信息。 还可在使用“监视”  工作区中的“数据复制”  节点时监视数据库复制的详细信息。 从“数据库复制”  中，可以监视站点之间的复制链接的状态，以及你的  [!INCLUDE[cmconsole](../LocTest/includes/cmconsole_md.md)] 所连接到的站点上的复制组的初始化详细信息和复制详细信息。  
  
> [!TIP]  
>  尽管“数据库复制”  节点还出现在“管理”  工作区的“层次结构配置”  节点下，但你无法从该位置中查看数据库复制链接的复制状态。  
  
####  <a name="BKMK_MonitorReplicationLinks"></a> 复制链接状态  
 站点之间的数据库复制涉及到若干组信息的复制，称为复制组。 每个复制组都使用不同的复制优先级进行复制。 默认情况下，无法修改复制组中包含的数据以及复制的频率。  
  
 当复制链接处于活动状态，并且没有失败或降级状态时，所有复制组都将及时进行复制。 如果一个或多个复制组在预期的时间段中无法完成复制，则链接将显示为降级。 降级的链接仍然起作用，但你应对其进行监视以确保其恢复为活动状态，或对其进行调查以确保不会出现其他降级或复制失败情况。  
  
 你可以为每个复制链接指定未成功复制的复制组在链接状态设置为降级或失败之前重试复制的次数。 即使除了一个复制组外的所有复制组都成功复制，但由于一个复制组无法在指定的尝试次数内完成复制，链接的状态仍会设置为降级或失败。 有关复制阈值的信息，请参阅 [System Center Configuration Manager 中的站点间数据传输](../LocTest/Data-transfers-between-sites-in-System-Center-Configuration-Manager.md)中的[数据库复制阈值](../LocTest/Data-transfers-between-sites-in-System-Center-Configuration-Manager.md#BKMK_DBRepThresholds)部分。  
  
 使用下表中的信息来了解可能需要进一步调查的复制链接的状态。  
  
|链接描述|更多信息|  
|----------------------|----------------------|  
|**链接处于活动状态**|未检测到任何问题，并且链接上的通信正在进行。|  
|**链接已降级**|复制正常运行，但至少一个复制对象或组已延迟。 监视处于此状态的链接，并查看链接上两个站点中的信息了解链接可能失败的迹象。<br /><br /> 当收到复制的数据的站点无法将数据快速提交到数据库时，链接也可能显示降级状态。 在复制大量数据时，可能会发生这种情况。 例如，你将软件更新部署到大量的计算机，则链接上的父站点可能要花费一段时间来处理复制的数据量。 父站点上的处理延迟可能会导致将链接状态设置为降级，直至父站点可成功处理积压的数据为止。|  
|**链接已失败**|复制无法正常工作。 复制链接可能无需进行进一步操作便可恢复。 你可以使用复制链接分析器来调查并帮助修正此链接上的复制。<br /><br /> 此状态也可能指示复制链接上父站点和子站点之间的物理网络的问题。|  
  
 当父站点正在升级到新的 Service Pack，并且你从子站点中查看链接状态时，链接状态将显示为活动。 升级之后，在子站点也升级到与父站点相同的 Service Pack 之前，如果从父站点中进行查看，链接状态将显示为活动，如果从子站点中进行查看，链接状态将显示为正在配置。  
  
####  <a name="BKMK_MonitorReplicationStatus"></a> 复制状态  
 你可以使用“监视”  工作区的“数据库复制”  节点来查看复制链接的复制状态，并查看复制链接上每个站点中的站点数据库的详细信息。 你还可以查看有关复制组的详细信息。 要查看详细信息，请选择复制链接，然后为要查看的复制状态选择相应的选项卡。 下面是有关复制状态的不同选项卡的详细信息。  
  
 **摘要**  
  
 查看有关链接上两个站点之间的站点数据和全局数据复制的高级信息。  
  
 你也可以单击“查看历史流量数据报表”  来查看一个报表，其中显示有关复制链接上的复制所使用的网络带宽的详细信息。  
  
 **父站点**  
  
 对于复制链接上的父站点，查看有关数据库的详细信息，其中包括：  
  
-   SQL Server 的防火墙端口  
  
-   可用磁盘空间  
  
-   数据库文件位置  
  
-   证书  
  
 **子站点**  
  
 对于复制链接上的子站点，查看有关数据库的详细信息，其中包括：  
  
-   SQL Server 的防火墙端口  
  
-   可用磁盘空间  
  
-   数据库文件位置  
  
-   证书  
  
 **初始化详细信息**  
  
 查看通过复制链接进行复制的复制组的初始化状态。 此信息可帮助你确定复制数据的初始化何时正在进行或已失败。  
  
 此外，你可以使用此信息来确定站点何时可能处于互操作性模式。 当子站点运行的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 版本与父站点不同时，将会出现互操作性模式。  
  
 **复制详细信息**  
  
 查看通过链接进行复制的每个复制组的复制状态。 使用此信息来帮助确定特定数据复制的问题或延迟，并帮助确定此链接的相应数据库复制阈值。 有关数据库复制阈值的信息，请参阅 [System Center Configuration Manager 中的站点间数据传输](../LocTest/Data-transfers-between-sites-in-System-Center-Configuration-Manager.md)中的[数据库复制阈值](../LocTest/Data-transfers-between-sites-in-System-Center-Configuration-Manager.md#BKMK_DBRepThresholds)部分。  
  
> [!TIP]  
>  站点数据的复制组只会从子站点发送到父站点。 全局数据的复制组则以双向方式复制。  
  
###  <a name="BKMK_RLA"></a> 关于复制链接分析器  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 包括 **复制链接分析器** ，你使用该分析器来分析和修复复制问题。 你可以使用复制链接分析器在复制失败以及复制停止工作但尚未报告为失败时修正复制链接故障。 复制链接分析器可用于修正 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 层次结构中以下计算机之间的复制问题（复制故障的方向并不重要）：  
  
-   站点服务器和站点数据库服务器之间。  
  
-   站点的站点数据库服务器和另一个站点的站点数据库计算机之间（站点间复制）。  
  
 你可以在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中或命令提示符处运行复制链接分析器：  
  
-   在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中运行：在“监视”  工作区中，单击“数据库复制”  节点，选择要分析的复制链接，然后在“主页”  选项卡上的“数据库复制”  组中选择“复制链接分析器” 。  
  
-   若要在命令提示符处运行，请键入以下命令： **%path%\\Microsoft Configuration Manager\\AdminConsole\\bin\\Microsoft.ConfigurationManager.ReplicationLinkAnalyzer.Wizard.exe \<source site server FQDN\> \<destination site server FQDN\>**  
  
 当你运行复制链接分析器时，它将使用一系列诊断规则和检查来检测问题。 该工具运行时，你可以查看该工具确定的问题。 如果用于解决某个问题的说明已知，则会显示出来。 如果复制链接分析器可自动修正问题，则会向你呈现该选项。 当复制链接分析器完成时，它将结果保存在以下基于 XML 的报表以及运行该工具的用户桌面上的一个日志文件中：  
  
-   ReplicationAnalysis.xml  
  
-   ReplicationLinkAnalysis.log  
  
 当复制链接分析器运行时，它会在修正某些问题时停止以下服务，并在修正完成时重启这些服务：  
  
-   SMS\_SITE\_COMPONENT\_MANAGER  
  
-   SMS\_EXECUTIVE  
  
 如果复制链接分析器未能完成修正，请查看站点服务器并重启这些服务（如果它们已停止）。  
  
 成功和未成功的调查和修正操作会被记录下来，以提供工具界面中未呈现的附加详细信息。  
  
 **使用复制链接分析器的先决条件：**  
  
-   你用于运行复制链接分析器的帐户在复制链接中涉及的每台计算机上必须具有本地管理员权限。 此帐户不需要特定的基于角色的管理安全角色。 因此，有权访问“数据库复制”  节点的管理用户可以在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中运行该工具，或者对每台计算机具有足够权限的系统管理员可以在命令提示符处运行该工具。  
  
-   你用于运行复制链接分析器的帐户对复制链接中涉及的每个 SQL Server 数据库必须具有 sysadmin 权限。  
  
 **复制链接分析器的已知问题：**  
  
-   随着 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 1511 版本的发布，复制链接分析器针对从 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)]升级的主站点会产生 SQL Server Service Broker 证书错误。 这是因为 1511 版本引入的证书名称发生更改，而复制链接分析器尚未对其进行更新。 可以安全忽略这些错误。  
  
###  <a name="BKMK_ProcsforMonitoringReplication"></a> 用于监视数据库复制的过程  
  
##### 监视高级别站点到站点数据库复制状态  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“监视” 。  
  
2.  在“监视”  工作区中，单击“站点层次结构”  以打开“层次结构图表”  视图。  
  
3.  将鼠标指针短暂停留在两个站点之间的线条上以查看这些站点的全局和站点数据复制的状态。  
  
##### 监视复制链接的复制状态  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“监视” 。  
  
2.  在“监视”  工作区中，单击“数据库复制” ，然后选择要监视的链接的复制链接。 然后，在工作区中选择相应的选项卡以查看有关该链接的复制状态的不同详细信息。  
  
## 另请参阅  
 [监视和维护 System Center Configuration Manager](../LocTest/Monitor-and-maintain-System-Center-Configuration-Manager.md)
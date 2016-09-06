---
title: "System Center Configuration Manager 中的软件更新简介"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-sum
ms.tgt_pltfrm: na
ms.topic: get-started-article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: e9778b13-c8a3-40eb-8655-34ac8ce9cdaa
caps.latest.revision: 12
caps.handback.revision: 6
translationtype: Human Translation
---
# System Center Configuration Manager 中的软件更新简介
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的软件更新提供了一组工具和资源，可帮助管理跟踪软件更新并将其应用到企业中的客户端计算机的复杂任务。 要维持运行效率、克服安全问题和保持网络基础结构的稳定性，有效的软件更新管理过程是必不可少的。 但是，由于技术日新月异，并且新的安全威胁不断出现，因此需要始终如一地持续关注有效的软件更新管理。  
  
 有关软件更新的详细信息，请参阅下列部分：  
  
-   [软件更新同步](#BKMK_Synchronization)  
  
-   [软件更新符合性评估](#BKMK_SUMCompliance)  
  
-   [软件更新部署包](#BKMK_DeploymentPackages)  
  
-   [软件更新部署工作流](#BKMK_DeploymentWorkflows)  
  
-   [软件更新部署过程](#BKMK_DeploymentProcess)  
  
-   [在 Configuration Manager 中扩展软件更新](#BKMK_ExtendSoftwareUpdates)  
  
-   [对使用写入筛选器的 Windows Embedded 设备的支持](#BKMK_EmbeddedDevices)  
  
 有关演示如何能在你的环境中部署软件更新的示例方案，请参阅 [使用 System Center Configuration Manager 部署和监视 Microsoft 每月发布的安全软件更新的示例方案](../LocTest/Example-scenario-for-using-System-Center-Configuration-Manager-to-deploy-and-monitor-the-security-software-updates-released-monthly-by-Microsoft.md)。  
  
##  <a name="BKMK_Synchronization"></a> 软件更新同步  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的软件更新同步使用 Microsoft 更新来检索软件更新元数据。 顶层站点（管理中心站点或独立主站点）按计划或在你从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中手动启动同步时与 Microsoft 更新同步。 当 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 在顶层站点上完成软件更新同步时，软件更新同步将在子站点（如果存在）上开始。 当同步在每个主站点或辅助站点上完成时，将会创建一个站点范围的策略，该策略向客户端计算机提供软件更新点的位置。  
  
> [!NOTE]  
>  默认情况下，软件更新在客户端设置中启用。 但是，如果将“在客户端上启用软件更新”客户端设置设置为“否”以禁用集合上或默认设置中的软件更新，软件更新点的位置不会发送到关联客户端。 有关软件更新客户端设置的详细信息，请参阅 [Software Updates](../LocTest/About-client-settings-in-System-Center-Configuration-Manager.md#BKMK_SoftwareUpdatesDeviceSetting) 主题中的 [关于 System Center Configuration Manager 中的客户端设置](../LocTest/About-client-settings-in-System-Center-Configuration-Manager.md) 部分。  
  
 客户端收到策略后，将启动软件更新符合性扫描，并将信息写入到 Windows Management Instrumentation \(WMI\)。 然后，符合性信息将发送到管理点，后者随后将该信息发送到站点服务器。 有关符合性评估的详细信息，请参阅本主题中的 [软件更新符合性评估](#BKMK_SUMCompliance) 部分。  
  
 你可以在主站点上安装多个软件更新点。 你安装的第一个软件更新点配置为同步源。 此同步源通过不在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 层次结构中的 Microsoft 更新或 WSUS 服务器进行同步。 站点上的其他软件更新点使用第一个软件更新点作为同步源。  
  
> [!NOTE]  
>  当软件更新同步过程在顶层站点上完成时，将通过使用数据库复制将软件更新元数据复制到子站点。 将 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台连接到子站点时，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将显示软件更新元数据。 但是，在你在站点上安装和配置软件更新点之前，客户端将不会扫描软件更新符合性，客户端将不会向 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 报告符合性信息，并且你无法成功部署软件更新。  
  
### 顶层站点上的同步  
 顶层站点上的软件更新同步过程从 Microsoft 更新中检索满足你在软件更新点组件属性中所指定条件的软件更新元数据。 你只能在顶层站点上配置条件。  
  
> [!NOTE]  
>  你可以将不在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 层次结构中的现有 WSUS 服务器（而不是 Microsoft 更新）指定为同步源。  
  
 以下列表描述顶层站点上的同步过程的基本步骤：  
  
1.  软件更新同步开始。  
  
2.  WSUS Synchronization Manager 向运行在软件更新点上的 WSUS 发送请求，以开始与 Microsoft 更新的同步。  
  
3.  将从 Microsoft 更新同步软件更新元数据，并在 WSUS 数据库中插入或更新任何更改。  
  
4.  当 WSUS 完成同步时，WSUS Synchronization Manager 会将软件更新元数据从 WSUS 数据库同步到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 数据库，并在站点数据库中插入或更新上一次同步后的任何更改。 软件更新元数据以配置项目的形式存储在站点数据库中。  
  
5.  将使用数据库复制将软件更新配置项目发送到子站点。  
  
6.  同步成功完成后，WSUS Synchronization Manager 将创建状态消息 6702。  
  
7.  WSUS Synchronization Manager 将同步请求发送到所有子站点。  
  
8.  WSUS Synchronization Manager 以一次一个的形式将请求发送到运行在站点的其他软件更新点上的 WSUS。 其他软件更新点上的 WSUS 服务器被配置为运行在站点的默认软件更新点上的 WSUS 的副本。  
  
### 子主站点和辅助站点上的同步  
 在顶层站点上的软件更新同步过程中，将通过使用数据库复制将软件更新配置项目复制到子站点。 该过程结束时，顶层站点会向子站点发送同步请求，并且子站点将开始 WSUS 同步。 以下列表提供子主站点或辅助站点上的同步过程的基本步骤：  
  
1.  WSUS Synchronization Manager 收到来自顶层站点的同步请求。  
  
2.  软件更新同步开始。  
  
3.  WSUS Synchronization Manager 向运行在软件更新点上的 WSUS 发送请求以开始同步。  
  
4.  运行在子站点的软件更新点上的 WSUS 从运行在父站点的软件更新点上的 WSUS 中同步软件更新元数据。  
  
5.  同步成功完成后，WSUS Synchronization Manager 将创建状态消息 6702。  
  
6.  WSUS Synchronization Manager 从主站点中向任何子辅助站点发送同步请求。 辅助站点开始与父主站点的软件更新同步。 辅助站点被配置为运行在父站点上的 WSUS 的副本。  
  
7.  WSUS Synchronization Manager 以一次一个的形式将请求发送到运行在站点的其他软件更新点上的 WSUS。 其他软件更新点上的 WSUS 服务器被配置为运行在站点的默认软件更新点上的 WSUS 的副本。  
  
##  <a name="BKMK_SUMCompliance"></a> 软件更新符合性评估  
 在将软件更新部署到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的客户端计算机之前，请在客户端计算机上启动软件更新符合性扫描。 对于每个软件更新，将创建一条状态消息，其中包含该更新的符合性状态。 状态消息将成批发送到管理点，并随后发送到站点服务器，在站点服务器中，会将符合性状态插入站点数据库。 软件更新的符合性状态显示在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中。 你可以在需要更新的计算机上部署和安装软件更新。 下列部分提供有关符合性状态的信息，并描述用于扫描软件更新符合性的过程。  
  
### 软件更新符合性状态  
 下表列出并描述了为软件更新在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中显示的每个符合性状态。  
  
|状态|描述|  
|--------|--------|  
|**必需**|指定软件更新在客户端计算机上适用且为必需。 如果软件更新状态为“必需”，则可能存在以下情况：<br /><br /> -   软件更新未部署到客户端计算机。<br />-   软件更新已安装在客户端计算机上。 但尚未将最新的状态消息插入站点服务器上的数据库。 客户端计算机将在安装完成后重新扫描更新。 在客户端将更新的状态发送到管理点（管理点随后将更新的状态转发到站点服务器）之前，可能会有最多两分钟的延迟。<br />-   软件更新已安装在客户端计算机上。 但在更新完成之前软件更新安装要求计算机重启。<br />-   软件更新已部署到客户端计算机，但尚未安装。|  
|**不需要**|指定软件更新在客户端计算机上不适用。 因此不需要该软件更新。|  
|**已安装**|指定软件更新在客户端计算机上适用，并且客户端计算机已安装了该软件更新。|  
|**未知**|指定站点服务器尚未收到来自客户端计算机的状态消息，通常是下列原因之一导致的：<br /><br /> -   客户端计算机未成功扫描软件更新符合性。<br />-   扫描已在客户端计算机上成功完成。 但由于状态消息积压的原因，状态消息尚未在站点服务器上得到处理。<br />-   扫描在客户端计算机上成功完成，但尚未收到来自子站点的状态消息。<br />-   扫描在客户端计算机上成功完成，但状态消息文件在某些方面已损坏并且无法处理。|  
  
### 扫描软件更新符合性过程  
 安装并同步了软件更新点之后，将创建一个站点范围的计算机策略，该策略告知客户端计算机已为站点启用了 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 软件更新。 客户端收到该计算机策略后，会计划在接下来的两个小时内随机启动符合性评估扫描。 扫描启动后，软件更新客户端代理过程将清除扫描历史记录，提交请求以查找应用于扫描的 WSUS 服务器，并使用 WSUS 服务器位置更新本地组策略。  
  
> [!NOTE]  
>  基于 Internet 的客户端必须使用 SSL 连接到 WSUS 服务器。  
  
 扫描请求传递到 Windows 更新代理 \(WUA\)。 然后，WUA 连接到本地策略中列出的 WSUS 服务器位置，检索在 WSUS 服务器上同步的软件更新元数据，并在客户端计算机中扫描更新。 软件更新客户端代理进程检测到符合性扫描已完成，并且会为上次扫描之后符合性状态发生更改的每个软件更新创建状态消息。 状态消息每 15 分钟向管理点批量发送一次。 然后管理点将状态消息转发给站点服务器，在站点服务器中，会将状态消息插入站点服务器数据库。  
  
 初次扫描软件更新符合性之后，会按照配置的扫描计划开始扫描。 但是，如果客户端在生存时间 \(TTL\) 值所指明的时间范围内扫描了软件更新符合性，则客户端会使用本地存储的软件更新元数据。 当上一次扫描在 TTL 之外时，客户端必须连接到在软件更新点上运行的 WSUS，并更新存储在客户端上的软件更新元数据。  
  
 包括扫描计划，软件更新符合性扫描可以用下列方法启动：  
  
-   **软件更新扫描计划**：软件更新符合性扫描按照软件更新客户端代理设置中配置的扫描计划开始。 有关如何配置软件更新客户端设置的详细信息，请参阅[Software Updates](../LocTest/About-client-settings-in-System-Center-Configuration-Manager.md#BKMK_SoftwareUpdatesDeviceSetting)主题中的[关于 System Center Configuration Manager 中的客户端设置](../LocTest/About-client-settings-in-System-Center-Configuration-Manager.md)部分。  
  
-   **Configuration Manager 属性操作**：用户可以在客户端计算机上的“Configuration Manager 属性”对话框内的“操作”选项卡上启动“软件更新扫描周期”或“软件更新部署评估周期”操作。  
  
-   **部署重估计划**：软件更新符合性的部署重估和扫描按照软件更新客户端代理设置中配置的部署重估计划开始。 有关软件更新客户端设置的详细信息，请参阅[Software Updates](../LocTest/About-client-settings-in-System-Center-Configuration-Manager.md#BKMK_SoftwareUpdatesDeviceSetting)主题中的[关于 System Center Configuration Manager 中的客户端设置](../LocTest/About-client-settings-in-System-Center-Configuration-Manager.md)部分。  
  
-   **下载更新文件之前**：当客户端计算机收到新的所需部署的分配策略时，软件更新客户端代理会将软件更新文件下载到本地客户端缓存。 下载软件更新文件之前，客户端代理将启动扫描以验证是否仍然需要软件更新。  
  
-   **在软件更新安装之前**：在软件更新安装之前，软件更新客户端代理将启动扫描以验证是否仍然需要软件更新。  
  
-   **在软件更新安装之后**：软件更新安装完成之后，软件更新客户端代理将启动扫描以验证是否不再需要软件更新，并创建新状态消息来表明已安装了软件更新。 如果完成了安装，但需要重启，则状态消息会指明客户端计算机正在等待重启。  
  
-   **在系统重启之后**：当客户端计算机等待系统重启以完成软件更新安装时，软件更新客户端代理将在重启后启动扫描以验证是否不再需要软件更新，并创建一条状态消息来表明已安装了软件更新。  
  
#### 生存时间值  
 扫描软件更新符合性所需的软件更新元数据存储在本地客户端计算机上，默认情况下其相关性时间最长为 24 小时。 此值称为生成时间 \(TTL\)。  
  
#### 扫描软件更新符合性类型  
 客户端将使用联机或脱机扫描以及强制或非强制扫描来扫描软件更新符合性，具体取决于启动软件更新符合性扫描的方式。 下表描述哪些扫描启动方法是联机或脱机方法，那些扫描是强制或非强制扫描。  
  
|扫描方法|扫描类型|描述|  
|----------|----------|--------|  
|软件更新扫描计划|非强制联机扫描|按照配置的扫描计划，客户端将连接到在软件更新点上运行的 WSUS，以仅当上次扫描在 TTL 外时检索软件更新元数据。|  
|软件更新扫描周期<br /><br /> 或<br /><br /> 软件更新部署评估周期|强制联机扫描|客户端计算机始终连接到在软件更新点上运行的 WSUS，以在客户端计算机扫描软件更新符合性之前检索软件更新元数据。 完成扫描后，TTL 计数器将重置。 例如，TTL 为 24 小时，在用户启动软件更新符合性扫描之后，TTL 将重置为 24 小时。|  
|部署重估计划|非强制联机扫描|按照配置的部署重估计划，客户端将连接到在软件更新点上运行的 WSUS，以仅当上次扫描在 TTL 外时检索软件更新元数据。|  
|下载更新文件之前|非强制联机扫描|在客户端能够下载所需部署中的更新之前，客户端将连接到在软件更新点上运行的 WSUS，以仅当上次扫描在 TTL 外时检索软件更新元数据。|  
|在软件更新安装之前|非强制联机扫描|在客户端安装所需部署中的软件更新之前，客户端将连接到在软件更新点上运行的 WSUS，以仅当上次扫描在 TTL 外时检索软件更新元数据。|  
|在软件更新安装之后：|强制脱机扫描|安装了软件更新之后，软件更新客户端代理使用本地元数据启动扫描。 客户端从不连接到在软件更新点上运行的 WSUS 以检索软件更新元数据。|  
|在系统重启之后|强制脱机扫描|安装了软件更新并且重启计算机之后，软件更新客户端代理使用本地元数据启动扫描。 客户端从不连接到在软件更新点上运行的 WSUS 以检索软件更新元数据。|  
  
##  <a name="BKMK_DeploymentPackages"></a> 软件更新部署包  
 软件更新部署包是用于将软件更新下载到网络共享文件夹的载体，并将软件更新源文件复制到站点服务器上的内容库，以及部署中定义的分发点上的内容库。 通过使用下载更新向导，你可以下载软件更新并在部署它们之前将其添加到部署包。 此向导允许你设置分发点上的软件更新，以及在将软件更新部署到客户端之前验证此部分部署过程是否成功。  
  
 使用部署软件更新向导来部署下载的软件更新之前，部署会自动使用包含软件更新的部署包。 部署尚未下载的软件更新时，你必须在部署软件更新向导中指定新的或现有的部署包，完成向导时将下载软件更新。  
  
> [!IMPORTANT]  
>  在向导中指定共享网络文件夹之前，必须为部署包源文件创建该文件夹。 每个部署包必须使用不同的共享网络文件夹。  
  
> [!IMPORTANT]  
>  SMS 提供程序计算机帐户和实际下载软件更新的管理用户都需要对包源具有“写” 权限。 限制对此包源的访问，以减少攻击者在包源中篡改软件更新源文件的风险。  
  
 如果创建新部署包，则在下载任何软件更新之前会将内容版本设置为 1。 使用包下载软件更新文件时，内容版本递增至 2。 因此，所有新部署包从内容版本 2 开始。 每次部署包中内容更改时，内容版本值递增 1。 有关 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中内容管理的详细信息，请参阅[System Center Configuration Manager 中内容管理的基本概念](../LocTest/Fundamental-concepts-for-content-management-in-System-Center-Configuration-Manager.md)。  
  
 客户端使用具有可用软件更新的任何分发点来安装部署中的软件更新，无部署包无关。 即使为活动部署删除了部署包，只要每个更新已至少下载到一个其他部署包，并且在可从客户端访问的分发点上可用，客户端也仍然可以在部署中安装软件更新。 如果删除了包含软件更新的上一个部署包，则在将更新下载到部署包之前，客户端计算机无法检索软件更新。 当更新文件不在任何部署包中时，将在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中用红色箭头来显示软件更新。 如果部署在此条件下包含任何更新，则用双红色箭头来显示部署。  
  
##  <a name="BKMK_DeploymentWorkflows"></a> 软件更新部署工作流  
 在你的环境中部署软件更新有两个主要方案，即手动部署和自动部署。 通常，你手动部署软件更新以为客户端计算机创建基线，然后使用自动部署在客户端上管理软件更新。 下列部分提供有关软件更新的手动和自动部署工作流的概要。  
  
###  <a name="BKMK_ManualDeployment"></a> 软件更新的手动部署  
 软件更新手动部署是在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中选择软件更新并手动启动部署过程的过程。 在创建将管理进行中的每月软件更新部署的自动部署规则之前，你通常将使用此部署方法以用所需的软件更新使客户端计算机保持最新，并部署带外软件更新要求。 以下列表提供手动部署软件更新的一般工作流：  
  
1.  使用特定要求的软件更新的筛选。 例如，你可以提供条件，以检索在 50 多台客户端设备上所需要的所有安全或严重软件更新。  
  
2.  创建包含软件更新的软件更新组。  
  
3.  下载软件更新组中的软件更新的内容。  
  
4.  手动部署软件更新组。  
  
###  <a name="BKMK_AutomaticDeployment"></a> 软件更新的自动部署  
 通过使用自动部署规则 \(ADR\).配置自动软件更新部署。 你通常将此部署方法用于每月软件更新（通称为周二补丁日）以及管理定义更新。 规则运行时，软件更新将从软件更新组中删除（如果使用现有组），将符合指定条件（例如，在最后一周中发布的所有安全软件更新）的软件更新添加到软件更新组中，软件更新的内容文件将下载和复制到分发点，并将软件更新部署到目标集合中的客户端计算机。 以下列表提供自动部署软件更新的一般工作流：  
  
1.  创建 ADR 以指定部署设置，如：  
  
    -   目标集合  
  
    -   确定对目标集合中的客户端计算机是启用部署还是报告软件更新符合性  
  
    -   软件更新条件  
  
    -   评估和部署计划  
  
    -   用户体验  
  
    -   下载属性  
  
2.  软件更新会添加到软件更新组中。  
  
3.  如果已指定软件更新组，则将其部署到目标集合中的客户端计算机。  
  
 必须确定要在环境中使用的部署策略。 例如，你可以创建 ADR 并以测试客户端集合为目标。 验证在测试组上是否安装了软件更新之后，你可以在规则中添加新部署或将现有部署中的集合更改为包含更大客户端集的目标集合。 ADR 所创建的软件更新对象具有交互性。  
  
-   使用 ADR 部署的软件更新会自动部署到已添加到目标集合的新客户端。  
  
-   添加到软件更新组的新软件更新会自动部署到目标集合中的客户端。  
  
-   你可以针对 ADR 随时启用或禁用部署。  
  
 创建 ADR 后，可以将其他部署添加到规则。 这可以帮助你管理将不同更新部署到不同集合的复杂性。 每个新部署均具有完整的功能和部署监视体验，且你添加的每个新部署具有以下特性：  
  
-   使用的更新组和包与在 ADR 首次运行时创建的更新组和包相同  
  
-   可以指定不同的集合  
  
-   支持唯一部署属性，包括：  
  
    -   激活时间  
  
    -   截止时间  
  
    -   显示或隐藏最终用户体验  
  
    -   针对此部署的单独警报  
  
##  <a name="BKMK_DeploymentProcess"></a> 软件更新部署过程  
 部署软件更新之后或在自动部署规则运行和部署软件更新时，会将部署分配策略添加到站点的计算机策略中。 系统会将软件更新从下载位置（Internet 或网络共享文件夹）下载到包源。 系统会从包源中将软件更新复制到站点服务器上的内容库，然后复制到分发点上的内容库。  
  
 当部署的目标集合中的客户端计算机收到计算机策略时，软件更新客户端代理会启动评估扫描。 客户端代理在收到部署后不久会将分发点中所需软件更新的内容下载到本地客户端缓存，但会等到部署的“软件可用时间”设置之后才能安装软件更新。 在用户手动启动安装之前，不会下载可选部署（没有安装截止时间的部署）中的软件更新。  
  
 过了配置的截止时间之后，软件更新客户端代理将执行扫描以验证是否仍然需要软件更新。 然后，它会检查客户端计算机上的本地缓存，以验证软件更新源文件是否仍然可用。 最后，客户端安装软件更新。 如果为了为其他部署腾出空间而从客户端缓存中删除了内容，则客户端会将分发点中的软件更新重新下载到客户端缓存。 软件更新将始终下载到客户端缓存，而不考虑配置的最大客户端缓存大小。 当安装完成时，客户端代理会验证是否不再需要软件更新，然后将状态消息发送给管理点，以指明客户端上现在已经安装了软件更新。  
  
### 需要重启系统  
 默认情况下，如果在客户端计算机上安装了所需部署中的软件更新，并且需要重启系统才能完成安装，则会开始系统重启。 对于在截止时间之前安装的软件更新，自动系统重启会延迟到截止时间进行，除非由于其他原因在该时间之前重启了计算机。 对于服务器和工作站，可以抑制系统重启。 这些设置是在部署软件更新向导或创建自动更新规则向导的“用户体验”页中配置的。  
  
### 部署重估周期  
 默认情况下，客户端计算机每 7 天开始部署重估周期。 在此评估周期期间，客户端计算机会扫描以前部署和安装的软件更新。 如果缺少任何软件更新，则会从本地缓存中重新安装软件更新。 如果软件更新在本地缓存中不再可用，则会从分发点中下载软件更新，然后安装该软件更新。 你可以在“软件更新”页上的站点客户端设置中配置重新评估计划。  
  
##  <a name="BKMK_EmbeddedDevices"></a> 对使用写入筛选器的 Windows Embedded 设备的支持  
 将软件更新部署到启用了写入筛选器的 Windows Embedded 设备时，你可以指定是否在部署过程中对设备禁用写入筛选器，然后在部署后重启设备。 如果未禁用写入筛选器，则软件会部署到临时覆盖区，并且重启设备后将不再安装软件，除非另一部署强制保留更改。  
  
> [!NOTE]  
>  将软件更新部署到 Windows Embedded 设备时，确保设备是配置了维护时段的集合的成员。 这样，你可以管理禁用和启用写入筛选器的时间，以及设备重启的时间。  
  
 控制写入筛选器行为的用户体验设置是一个名为“在截止时间或在维护时段内提交更改\(需要重启\)”的复选框。  
  
 有关 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 如何管理使用写入筛选器的嵌入式设备的详细信息，请参阅[在 System Center Configuration Manager 中计划 Windows Embedded 设备的客户端部署](../LocTest/Planning-for-client-deployment-to-Windows-Embedded-devices-in-System-Center-Configuration-Manager.md)。  
  
##  <a name="BKMK_ExtendSoftwareUpdates"></a> 在 Configuration Manager 中扩展软件更新  
 使用 [!INCLUDE[scuplong](../Token/scuplong_md.md)] 管理 Microsoft 更新中不可用的软件更新。 将软件更新发布到更新服务器并在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中同步软件更新之后，你可以将软件更新部署到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端。 有关 [!INCLUDE[scupshort](../Token/scupshort_md.md)] 的详细信息，请参阅 [Updates Publisher 2011（更新 Publisher 2011）](http://go.microsoft.com/fwlink/p/?LinkId=252947)。  
  
## 请参阅  
 [在 System Center Configuration Manager 中部署并管理软件更新](../LocTest/Deploy-and-manage-software-updates-in-System-Center-Configuration-Manager.md)
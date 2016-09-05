---
title: "使用 System Center Configuration Manager 将 Windows 作为服务进行管理"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-osd
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: da1e687b-28f6-43c4-b14a-ff2b76e60d24
caps.latest.revision: 26
caps.handback.revision: 24
---
# 使用 System Center Configuration Manager 将 Windows 作为服务进行管理
||  
|-|  
|[!INCLUDE[cm1602disclaimer](../LocTest/includes/cm1602disclaimer_md.md)]|  
  
 在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]中，可以将 Windows 作为环境中的服务查看其状态、创建维护服务计划以形成部署环并确保 Windows 10 当前分支系统在新的内部版本发布时保持最新状态，以及在 Windows 10 客户端接近其当前分支 (CB) 或当前业务分支 (CBB) 内部版本的支持期结尾时查看警报。  
  
 有关 Windows 10 维护服务选项的详细信息，请参阅  [用于更新和升级的 Windows 10 维护服务选项](https://technet.microsoft.com/library/mt598226\(v=vs.85\).aspx)。  
  
 使用下列部分将 Windows 作为服务进行管理：  
  
-   [先决条件](#BKMK_Prerequisites)  
  
-   [Windows 10 维护服务仪表板](#BKMK_ServicingDashboard)  
  
-   [Windows 10 维护服务计划](#BKMK_ServicingPlan)  
  
-   [修改维护服务计划](#BKMK_ModifyServicingPlan)  
  
##  <a name="BKMK_Prerequisites"></a> 先决条件  
 要在 Windows 10 维护服务仪表板中查看数据，必须执行以下操作：  
  
-   Windows 10 计算机必须使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 软件更新和 Windows Server Update Services (WSUS) 进行软件更新管理。 当计算机使用适用于企业的 Windows 更新（或 Windows 预览体验）进行软件更新管理时，将不在 Windows 10 维护服务计划中评估计算机。 有关详细信息，请参阅 [Integration with Windows Update for Business in Windows 10](../LocTest/Integration-with-Windows-Update-for-Business-in-Windows-10.md)。  
  
-   必须在软件更新点和站点服务器上安装具有 [修补程序 3095113](https://support.microsoft.com/kb/3095113) 的 WSUS 4.0。 这将添加“升级”软件更新分类。 有关详细信息，请参阅 [System Center Configuration Manager 中软件更新的先决条件](../LocTest/Prerequisites-for-software-updates-in-System-Center-Configuration-Manager.md)。  
  
-   启用检测信号发现。 可使用发现找到 Windows 10 维护仪表板中显示的数据。 有关详细信息，请参阅 [Configure Heartbeat Discovery](../LocTest/Run-discovery-for-System-Center-Configuration-Manager.md#BKMK_ConfigHBDisc)。  
  
     可在以下属性中发现和存储下面的 Windows 10 分支和生成信息：  
  
    -   **OSBranch**：0 = CB，1 = CBB，2 = LTSB  
  
    -   **Build**：例如  **10.0.10240** (RTM) 或 **10.0.10586** （1511 版）  
  
-   必须安装服务连接点并将其配置为“联机，持续连接”  模式，才能在 Windows 10 维护服务仪表板上查看数据。 当处于脱机模式时，在获得 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 维护服务更新前，你将无法仪表板中查看数据更新。   
     有关详细信息，请参阅 [About the service connection point in System Center Configuration Manager](../LocTest/About-the-service-connection-point-in-System-Center-Configuration-Manager.md)。  
  
-   将组策略设置指定为“推迟升级和更新” ，以确定计算机是 CB 还是 CBB。  
  
-   必须在运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台的计算机上安装 Internet Explorer 9 或更高版本。  
  
-   必须配置和同步软件更新。 必须先选择“升级”分类并同步软件更新，才能在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中使用 Windows 10 功能升级。 有关详细信息，请参阅[在 System Center Configuration Manager 中配置软件更新](../LocTest/Configure-software-updates-in-System-Center-Configuration-Manager.md)。  
  
##  <a name="BKMK_ServicingDashboard"></a> Windows 10 维护服务仪表板  
 Windows 10 维护服务仪表板提供了有关环境中的 Windows 10 计算机和活动维护服务计划的信息以及符合性信息等。 Windows 10 维护服务仪表板中的数据依赖于安装服务连接点。 该仪表板具有以下磁贴：  
  
-   **“Windows 10 使用情况”磁贴**：提供 Windows 10 公共内部版本的细分。 将 Windows 预览体验内部版本和对你的站点为未知的任何内部版本列为 **其他** 。 服务连接点将下载告知其 Windows 内部版本的元数据，然后将此数据与发现数据进行比较。  
  
-   **“Windows 10 环”磁贴**：按分支和就绪状态提供 Windows 10 的细分。 Long Term Servicing Branch (LTSB) 段将全为 LTSB 版本（而第一个磁贴将分解特定版本。 例如，Windows 10 LTSB 2015）。 “可以发布”  段对应于 CB，而“可用于业务”  段为 CBB。  
  
-   **“创建服务计划”磁贴**：提供创建维护服务计划的快速方法。 指定名称、集合（仅显示从小到大的前 10 个集合）、部署包（仅显示最近修改的前 10 个包）和就绪状态。 其他设置使用默认值。 单击“高级设置”  以启动“创建维护服务计划向导”，可在该向导中配置所有服务计划设置。  
  
-   **“已过期”磁贴**：显示运行已超过其使用期限的 Windows 10 版本的设备的百分比。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 从服务连接点下载的元数据确定百分比，并将其与发现数据比较。 超过其使用期限的内部版本将不再接收月度累计更新（包括安全更新）。 应将此类别中的计算机升级到下一个内部版本。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将进一成为整数。 例如，如果你有 10,000 台计算机而只有一台运行已过期的内部版本，则该磁贴将显示 1%。  
  
-   **“即将过期”磁贴**：显示运行接近使用期限（将在约四个月内过期）的内部版本的计算机的百分比，与“已过期”  磁贴类似。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将进一成为整数。  
  
-   **“警报”磁贴**：显示活动警报。  
  
-   **“服务计划监视”磁贴**：显示已创建的维护服务计划，以及每个计划的符合性图表。 它能够提供维护服务计划部署当前状态的简要概述。 如果较早的部署环满足你对符合性的期望，则可以选择较晚的维护服务计划（部署环）然后单击“立即部署”  ，而不必等待自动触发维护服务计划规则。  
  
-   **“Windows 10 内部版本”磁贴**：显示固定的映像时间线，它提供当前发布的 Windows 10 内部版本的概述，以及内部版本将转换为各状态的大致时间。  
  
> [!IMPORTANT]  
>  Windows 10 维护服务仪表板中显示的信息（例如 Windows 10 版本的支持使用期限）是出于方便考虑而提供的，仅供公司内部使用。 不应仅依赖此信息来确认更新符合性。 请务必验证所提供信息的准确性。  
  
## 维护服务计划工作流  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的 Windows 10 维护服务计划非常类似于软件更新的自动部署规则。 可使用以下条件创建维护服务计划， [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将评估这些条件：  
  
-   **升级分类**：仅限评估“升级”分类中的更新。  
  
-   **就绪状态**：将比较维护服务计划中定义的就绪状态与升级的就绪状态。 服务连接点检查更新时，将检索升级的元数据。  
  
-   **时间延迟**：在维护服务计划中，你为“Microsoft 发布新升级后，你希望等待多少天再在新环境中进行部署”  指定的天数。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将评估是否在部署中包含升级。  
  
 当升级符合条件时，维护服务计划会将升级添加到部署包并将包分发到分发点，然后基于在维护服务计划中配置的设置将升级部署到集合。  你可以在 Windows 10 维护服务仪表板上的“服务计划监视”磁贴中监视部署。 有关详细信息，请参阅[在 System Center Configuration Manager 中监视软件更新](../LocTest/Monitor-software-updates-in-System-Center-Configuration-Manager.md)。  
  
##  <a name="BKMK_ServicingPlan"></a> Windows 10 维护服务计划  
 部署 Windows 10 CB 时，可以创建一个或多个维护服务计划，以定义你的环境中所需的部署环，然后在 Windows 10 维护服务仪表板中监视它们。   
维护服务计划仅使用“升级”软件更新分类，而不使用 Windows 10 的累积更新。 这些更新将仍需要使用软件更新工作流进行部署。  维修服务计划的最终用户体验与软件更新体验相同，包括你在维护服务计划中配置的设置。  
  
> [!NOTE]  
>  可以使用任务序列来为每个 Windows 10 内部版本部署升级，但这样做需要进行更多手动操作。 你需要将更新的源文件作为操作系统升级包导入，然后创建任务序列并将其部署到适当计算机组。 但是，任务序列提供其他自定义选项，如部署前和部署后操作。  
  
 可以从 Windows 10 维护服务仪表板创建基本维护服务计划。 你指定名称、集合（仅显示从小到大的前 10 个集合）、部署包（仅显示最近修改的前 10 个包）和就绪状态后， [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将使用其他设置的默认值创建维护服务计划。 也可以启动“创建维护服务计划向导”来配置所有设置。 使用“创建使用维护服务计划向导”，通过以下过程创建维护服务计划。  
  
> [!NOTE]  
>  从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 版本 1602 开始，你可以管理高风险部署的行为。 高风险部署是自动安装、可能产生意外结果的部署。 例如，其用途为**必需**部署 Windows 10 的任务序列被认为是高风险部署。 有关详细信息，请参阅 [Settings to manage high-risk deployments for System Center Configuration Manager](../LocTest/Settings-to-manage-high-risk-deployments-for-System-Center-Configuration-Manager.md)。  
  
#### 创建 Windows 10 维护服务计划  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击 **软件库**。  
  
2.  在“软件库”工作区中，展开“Windows 10 维护服务” ，然后单击“维护服务计划” 。  
  
3.  在“主页”  选项卡上的“创建”  组中，单击“创建维护服务计划” 。 将打开“创建维护服务计划向导”。  
  
4.  在“常规”  页上，配置下列设置：  
  
    -   **名称**：指定维护服务计划的名称。 此名称必须唯一并且有助于描述规则的目的，并且应与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点中的其他名称区分开来。  
  
    -   **描述**：指定维护服务计划的描述。 描述概述了维护服务计划和任何其他相关信息，以帮助在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点内的其他项中标识和区分该计划。 描述字段是可选字段，最多不超过 256 个字符，默认情况下具有空白值。  
  
5.  在“维护服务计划”页上，配置下列设置：  
  
    -   **目标集合**：指定要用于维护服务计划的目标集合。 集合的成员将接收维护服务计划中定义的 Windows 10 升级。  
  
    > [!NOTE]  
    >  从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 版本 1602 开始，部署高风险部署（例如维护服务计划）时，“选择集合”窗口中将仅显示满足站点属性中配置的部署验证设置的自定义集合。 高风险部署始终局限于自定义集合、你所创建的集合和内置“未知计算机”  集合。 创建高风险部署时，无法选择“所有系统” 等内置集合。 取消选中“隐藏成员数大于站点最低大小配置的集合”  以查看所含客户端少于配置的最大大小的全部自定义集合。 有关详细信息，请参阅 [Settings to manage high-risk deployments for System Center Configuration Manager](../LocTest/Settings-to-manage-high-risk-deployments-for-System-Center-Configuration-Manager.md)。  
    > 部署验证设置基于集合的当前成员身份。 部署维护服务计划后，不会重新评估高风险部署设置的集合成员身份。  
    > 例如，假设将“默认大小”  设置为 100，将“最大大小”  设置为 1000。 当创建高风险部署时，“选择集合”  窗口将仅显示其客户端少于 100 个的集合。 如果清除“隐藏成员数大于站点最低大小配置的集合”  设置，则该窗口将显示其客户端少于 1000 个的集合。  
    > 选择包含站点角色的集合时，以下情况适用：  
    >   
    >  -   如果集合包含站点系统服务器，而你在部署验证设置中配置为阻止具有站点系统服务器的集合，则将出现错误且无法继续操作。  
    > -   如果集合包含站点系统服务器，而你在部署验证设置中配置为在集合具有站点系统服务器、超过默认大小值或包含服务器时发出警告，则部署软件向导将显示高风险警告。 你必须同意创建高风险部署，这时将创建审核状态消息。  
  
6.  在“部署环”页上配置下列设置：  
  
    -   **指定此服务维护服务计划将应用到的 Windows 就绪状态**：选择下列项之一：  
  
        -   **可以发布(Current Branch)**：  
  
        -   **可用于业务(Current Branch for Business)**：  
  
    -   **Microsoft 发布新升级后，你希望等待多少天再在新环境中进行部署**：  
  
    -   在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 版本 1602 之前，单击“预览”可查看与就绪状态关联的 Windows 10 更新。  
  
7.  从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 版本 1602 开始，可在“升级”页面上配置搜索条件可筛选将添加到服务计划的升级。 只有满足指定条件的升级项才会添加到关联部署中。  
  
     单击“预览”可查看符合指定条件的升级。  
  
8.  在“部署计划”页上配置下列设置：  
  
    -   “计划评估”：指定 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 是使用 UTC 还是使用运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台的计算机的本地时间来计算可用的时间和安装截止时间。  
  
        > [!NOTE]  
        >  当你选择本地时间，并为“软件可用时间”  或“安装截止时间”  选择“尽快” ，则将使用运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台的计算机上的当前时间来计算更新可用的时间或在客户端上安装更新的时间。 如果客户端位于其他时区，当客户端的时间达到评估时间时将发生这些操作。  
  
    -   “软件可用时间”：选择以下设置之一以指定向客户端提供软件更新的时间：  
  
        -   “尽快”：选择此设置以尽快向客户端计算机提供部署中所包括的软件更新。 创建部署并选择此设置后， [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将更新客户端策略。 然后在下一个客户端策略轮询周期，客户端将注意部署并且可以获得可安装的更新。  
  
        -   “特定时间”：选择此设置以在特定日期和时间向客户端计算机提供部署中所包括的软件更新。 创建部署并启用此设置后， [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将更新客户端策略。 然后在下一个客户端策略轮询周期，客户端将注意部署。 但是，直到过了配置的日期和时间，才可以安装部署中的软件更新。  
  
    -   “安装截止时间”：选择以下设置之一以指定部署中的软件更新的安装截止时间：  
  
        -   “尽快”：选择此设置以尽快自动安装部署中的软件更新。  
  
        -   “特定时间”：选择此设置以在特定日期和时间自动安装部署中的软件更新。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 通过将已配置的“特定时间”间隔添加到“软件可用时间”可确定安装软件更新的截止时间。  
  
        > [!NOTE]  
        >  实际安装截止时间是显示的截止时间加上随机的一段时间（最多为 2 小时）。 这可以减少目标集合中同时在部署中安装软件更新的所有客户端计算机的潜在影响。  
        >   
        >  你可以配置“计算机代理”  客户端设置，“禁用截止时间随机化”  ，以对所需的更新禁用安装随机化延迟。 有关详细信息，请参阅 [Computer Agent](../LocTest/About-client-settings-in-System-Center-Configuration-Manager.md#BKMK_ComputerAgentDeviceSettings)。  
  
9. 在“用户体验”页上，请配置下列设置：  
  
    -   **用户通知**：指定是否于配置的“软件可用时间”  在客户端计算机上的软件中心中显示更新通知，以及是否在客户端计算机上显示用户通知。  
  
    -   **截止时间行为**：指定到达更新部署的截止时间时要发生的行为。 指定是否在部署中安装更新。 另外，指定是否在安装更新后执行系统重启而不考虑配置的维护时段。 有关维护时段的详细信息，请参阅[如何在 System Center Configuration Manager 中使用维护时段](../LocTest/How-to-use-maintenance-windows-in-System-Center-Configuration-Manager.md)。  
  
    -   **设备重新启动行为**：指定安装更新后是否在服务器和工作站上抑制系统重启，以及是否需要重启系统以完成安装。  
  
    -   **Windows Embedded 设备的写入筛选器处理**：将更新部署到启用了写入筛选器的 Windows Embedded 设备时，你可以指定将更新安装在临时覆盖区上并稍后提交更改，或者在安装截止时或在维护时段内提交更改。 如果在安装截止时或在维护时段内提交更改，则需要重新启动，而且更改将保留在设备上。  
  
        > [!NOTE]  
        >  将更新部署到 Windows Embedded 设备时，确保设备是配置了维护时段的集合的成员。  
  
10. 在“部署包”页上，选择现有部署包，或者配置以下设置以创建新部署包：  
  
    1.  “名称”：指定部署包的名称。 这必须是描述包内容的唯一名称。 它被限制为不超过 50 个字符。  
  
    2.  “说明”：指定提供有关该部署包的信息的说明。 该说明仅限于 127 个字符。  
  
    3.  “包源”：指定软件更新源文件的位置。  键入源位置的网络路径，例如 **\\\server\sharename\path**，或单击“浏览”来查找网络位置。 在进入到下一页之前，必须为部署包源文件创建共享文件夹。  
  
        > [!NOTE]  
        >  其他软件部署包不能使用你指定的部署包源位置。  
  
        > [!IMPORTANT]  
        >  SMS 提供程序计算机帐户和运行向导下载软件更新的用户都必须对下载位置具有“写”  NTFS 权限。 你应该仔细限制对此下载位置的访问，以减少攻击者篡改软件更新源文件的风险。  
  
        > [!IMPORTANT]  
        >  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 创建了部署包之后，可以在部署包属性中更改包源位置。 但是，如果你执行此操作，则必须首先将原始包源中的内容复制到新包源位置。  
  
    4.  “发送优先级”：指定部署包的发送优先级。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 在将包发送到分发点时将使用部署包的发送优先级。 部署包按优先级顺序发送：高、中或低。 具有相同优先级的包按照其创建顺序发送。 如果没有囤积，则将立即处理包，而不考虑其优先级。  
  
11. 在“分发点”页上，指定将承载更新文件的分发点或分发点组。 有关分发点的详细信息，请参阅 [Distribution point configurations](../LocTest/Manage-content-and-content-infrastructure-for-System-Center-Configuration-Manager.md#bkmk_DBtable)。  
  
    > [!NOTE]  
    >  只有当你在创建新的软件更新部署包时才能使用本页。  
  
12. 在“下载位置”页上，指定是从 Internet 还是从本地网络下载更新文件。 配置下列设置：  
  
    -   **从 Internet 下载软件更新**：选择此设置以从 Internet 上的指定位置下载更新。 默认情况下将启用此设置。  
  
    -   **从本地网络上的位置下载软件更新**：选择此设置以从本地目录或共享的文件夹下载更新。 当运行向导的计算机无法访问 Internet 时，此设置很有用。 能够访问 Internet 的任何计算机可以先下载更新，然后将它们存储在可从运行向导的计算机中访问的本地网络上的某个位置。  
  
13. 在“语言选择”页上，为已选定要下载的更新选择语言。 只有在提供了与所选语言对应的更新时才下载更新。 始终会下载非特定于语言的更新。 默认情况下，向导会选择你已在软件更新点的属性中配置的语言。 在继续进入下一页之前，必须选择至少一种语言。 如果仅选择更新不支持的语言，则更新的下载将会失败。  
  
14. 在“摘要”页上查看设置，然后单击“下一步”  以创建维护服务计划。  
  
 完成向导后，将会运行维护服务计划。 它会将符合指定条件的更新添加到软件更新组中、将更新下载到站点服务器上的内容库、将更新分发到已配置的分发点，然后将软件更新组部署到目标集合中的客户端。  
  
##  <a name="BKMK_ModifyServicingPlan"></a> 修改维护服务计划  
 从 Windows 10 维护服务仪表板创建基本维护服务计划后，或需要更改现有维护服务计划的设置时，可以转到维护服务计划属性。 使用以下过程来修改维护服务计划的属性。  
  
#### 修改维护服务计划的属性  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击 **软件库**。  
  
2.  在“软件库”工作区中，展开“Windows 10 维护服务” ，单击“维护服务计划” ，然后选择要修改的维护服务计划。  
  
3.  在“主页”  选项卡上，单击“属性”  以打开所选维护计划的属性。  
  
## 另请参阅  
 [使用 System Center Configuration Manager 管理企业操作系统](assetId:///c6b0ff4c-235a-4e4c-99c0-d14d202de478)
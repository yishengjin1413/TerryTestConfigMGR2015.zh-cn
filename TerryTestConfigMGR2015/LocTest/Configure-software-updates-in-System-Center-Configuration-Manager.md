---
title: "在 System Center Configuration Manager 中配置软件更新"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-sum
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 40380e25-f563-40f8-b5ad-01c9a9698754
caps.latest.revision: 16
caps.handback.revision: 16
---
# 在 System Center Configuration Manager 中配置软件更新
在软件更新的符合性评估数据显示在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 控制台中并且可将软件更新部署到客户端计算机之前，你必须完成下列步骤：安装和配置软件更新点、同步软件更新元数据并验证与软件更新关联的设置的配置。  
  
 如果有 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 层次结构，请先在管理中心站点上安装和配置软件更新点，然后在其他站点上安装和配置软件更新点。 只有当你在顶层站点（管理中心站点或独立主站点）上配置软件更新点时，某些设置才可用。 视软件更新点安装在何处而定，你必须考虑不同的配置选项。 使用下表中的步骤来安装和配置软件更新点、同步软件更新并配置与软件更新关联的设置。  
  
##  <a name="BKMK_TopOfPage"></a> 配置软件更新  
 使用本主题中的下列步骤和过程在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]中配置软件更新。  
  
|步骤|详细信息|  
|----------|-------------|  
|[步骤 1：安装并配置软件更新点](#BKMK_InstallSUP)|管理中心站点和主站点上需要软件更新点以便启用软件更新符合性评估和将软件更新部署到客户端。 软件更新点在辅助站点上是可选的。|  
|[步骤 2：同步软件更新](#BKMK_SUMSync)|根据从软件更新点到更新源的连接选择同步方法：<br /><br /> <br /><br /> **从连接的软件更新点同步软件更新**<br /><br /> 软件更新同步是从 Microsoft 更新站点中检索软件更新元数据并将该元数据复制到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 层次结构中为软件更新启用的所有站点的过程。 管理中心站点或独立主站点上的软件更新点从 Microsoft 更新中检索软件更新元数据。 子主站点和辅助站点从标识为上游更新源的软件更新点检索软件更新元数据。 你必须具有上游更新源的访问权限才能成功同步软件更新。 请参阅 [从连接的软件更新点同步软件更新](#BKMK_SyncConnected)。<br /><br /> <br /><br /> **从断开连接的软件更新点中同步软件更新**<br /><br /> 如果管理中心站点或独立主站点上的软件更新点从 Internet 断开连接，则无法进行软件更新的自动同步。 要为断开连接的软件更新点检索最新的软件更新，你必须使用 WSUSUtil 工具从软件更新源中导出软件更新元数据和许可条款文件，然后必须将元数据和文件导入到断开连接的软件更新点。  请参阅[从断开连接的软件更新点同步软件更新](#BKMK_SyncDisconnected)。|  
|[步骤 3：配置要同步的分类和产品](#BKMK_ConfigureClassesProducts)|在管理中心站点或独立主站点上执行此配置。<br /><br /> 在未选择任何分类或产品的情况下同步软件更新后，你必须在软件更新点组件属性中配置软件更新分类和产品。 配置属性之后，重复步骤 2 启动软件更新同步以检索满足配置的分类和产品条件的软件更新。|  
|[步骤 4：验证软件更新客户端设置和组策略配置](#BKMK_AssociatedSettings)|有一些与软件更新关联的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端设置和组策略配置，在部署软件更新之前，你必须验证这些设置和配置。|  
  
##  <a name="BKMK_InstallSUP"></a> 步骤 1：安装并配置软件更新点  
  
> [!IMPORTANT]  
>  在安装软件更新点站点系统角色之前，你必须验证服务器是否满足所需的依赖关系，并确定站点上的软件更新点基础结构。 有关如何规划软件更新和确定软件更新点基础结构的详细信息，请参阅[在 System Center Configuration Manager 中规划软件更新](../LocTest/Plan-for-software-updates-in-System-Center-Configuration-Manager.md)。  
  
 管理中心站点和主站点上需要软件更新点以便启用软件更新符合性评估和将软件更新部署到客户端。 软件更新点在辅助站点上是可选的。 必须在安装了 WSUS 的服务器上创建软件更新点站点系统角色。 软件更新点与 WSUS 服务交互以配置软件更新设置，并请求软件更新元数据的同步。 如果有 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 层次结构，请先在管理中心站点上安装和配置软件更新点，然后依次在子主站点上和根据需要在辅助站点上安装和配置软件更新点。 如果有独立主站点（而不是管理中心站点），请先在主站点上安装和配置软件更新点，然后根据需要在辅助站点上安装和配置软件更新点。 只有当你在顶层站点上配置软件更新点时，某些设置才可用。 视软件更新点安装在何处而定，你必须考虑不同的选项。  
  
> [!IMPORTANT]  
>  你可以在站点上安装多个软件更新点。 你安装的第一个软件更新点配置为同步源，它从 Microsoft 更新或上游同步源中同步更新。 站点上的其他软件更新点配置为第一个软件更新点的副本。 因此，在你安装和配置初始软件更新点之后，某些设置不可用。  
  
 你可以将软件更新点站点系统角色添加到现有站点系统服务器，或者可以创建新站点系统服务器。 在“创建站点系统服务器向导”  或“添加站点系统角色向导”  的“系统角色选择”  页上，根据你是将站点系统角色添加到新站点服务器还是现有站点服务器，选择“软件更新点” ，然后在向导中配置软件更新点设置。 根据所使用的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的版本，设置会有所不同。 有关如何安装站点系统角色的详细信息，请参阅[安装 System Center Configuration Manager 的站点系统角色](../Topic/Install%20site%20system%20roles%20for%20System%20Center%20Configuration%20Manager.md)。  
  
 使用下列部分来了解有关站点上的软件更新点设置的信息。  
  
### 代理服务器设置  
 你可以配置“创建站点系统服务器向导”  或“添加站点系统角色向导”  不同页上的代理服务器设置，具体取决于你使用的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的版本。  
  
-   你必须配置代理服务器，然后指定何时为软件更新使用代理服务器。 配置下列设置：  
  
    -   在向导的“代理”  页上或“站点系统属性”的“代理”  选项卡上配置代理服务器设置。 代理服务器设置特定于站点系统，这意味着所有站点系统角色都使用你指定的代理服务器设置。  
  
    -   指定是否在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 同步软件更新或通过使用自动部署规则下载内容时使用代理服务器。 在向导的“代理和帐户设置”  页上或“软件更新点属性”中的“代理和帐户设置”  选项卡上配置软件更新点代理服务器设置。  
  
        > [!NOTE]  
        >  辅助站点上提供了“使用自动部署规则下载内容时使用代理服务器”  设置，但不用于软件更新点。 只有管理中心站点和主站点上的软件更新点才从 Microsoft 更新页下载内容。  
  
> [!IMPORTANT]  
>  默认情况下，当自动部署规则运行时，将使用在其上创建自动部署规则的服务器的“本地系统”  帐户连接到 Internet 并下载软件更新。 当此帐户没有 Internet 访问权限时，软件更新将无法下载并且以下条目会被记录在 ruleengine.log 中：**无法从 Internet 下载更新。错误 = 12007**。 当“本地系统”帐户没有 Internet 访问权限时，配置凭据以连接到代理服务器。  
  
### WSUS 设置  
 必须在“创建站点系统服务器向导”或“添加站点系统角色向导”的不同页上配置 WSUS 设置，具体取决于你使用的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的版本，在某些情况下，必须仅在软件更新点的属性（也称为软件更新点组件属性）中进行配置。 使用下列部分中的信息来配置 WSUS 设置。  
  
#### WSUS 端口设置  
 你必须在向导的“软件更新点”页上或软件更新点的属性中配置 WSUS 端口设置。  
  
 若确定 WSUS 中的网站和端口配置，请参阅[如何确定 WSUS System Center Configuration Manager 中 WSUS 使用的端口设置](../LocTest/How-to-determine-the-port-settings-used-by-WSUS-in-System-Center-Configuration-Manager.md)。  
  
#### 配置与 WSUS 的 SSL 通信  
 你可以在向导的“常规”  页上或软件更新点属性的“常规”  选项卡上配置 SSL 通信。  
  
 有关如何使用 SSL 的详细信息，请参阅 [Decide whether to configure WSUS to use SSL](../LocTest/Plan-for-software-updates-in-System-Center-Configuration-Manager.md#BKMK_WSUSandSSL)。  
  
#### WSUS 服务器连接帐户  
 你可以配置要在站点服务器连接到软件更新点上运行的 WSUS 时使用的帐户。 如果不配置此帐户， [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将使用要连接到 WSUS 的站点服务器的计算机帐户。 在向导的“代理和帐户设置”  页上或“软件更新点属性”中的“代理和帐户设置”  选项卡上配置 WSUS 服务器连接帐户。  你可以在向导的不同位置中配置帐户，具体情况视你使用的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 版本而定。  
  
 有关 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 帐户的详细信息，请参阅 [System Center Configuration Manager 中使用的帐户](../LocTest/Accounts-used-in-System-Center-Configuration-Manager.md)。  
  
### 同步源  
 在向导的“同步源”  页上，或者在“软件更新点组件属性”中的“同步设置”  选项卡上，你可以配置软件更新同步的上游同步源。 同步源的选项因站点而异。 有关详细信息，请参阅 [Synchronization source](../LocTest/Plan-for-software-updates-in-System-Center-Configuration-Manager.md#BKMK_SyncSource)。  
  
 使用下表以了解配置站点中的软件更新点时的可用选项。  
  
|站点|可用的同步源选项|  
|----------|----------------------------------------------|  
|-   管理中心站点<br />-   独立主站点|-   从 Microsoft 更新网站同步<br />-   从上游数据源位置同步<br />-   不从 Microsoft 更新或上游数据源同步|  
|-   站点中的附加软件更新点<br />-   子主站点<br />-   辅助站点|-   从上游数据源位置同步|  
  
 以下列表提供了有关可用作同步源的每个选项的详细信息：  
  
-   “从 Microsoft 更新同步”：使用此设置以从 Microsoft 更新同步软件更新元数据。 管理中心站点必须具有 Internet 访问权限。否则，同步将失败。 只有在配置顶层站点的软件更新点后才可以使用此设置。  
  
    > [!NOTE]  
    >  如果软件更新点与 Internet 之间存在防火墙，则可能需要将防火墙配置为接受用于 WSUS 网站的 HTTP 和 HTTPS 端口。 你也可以选择将防火墙上的访问权限局限于受限制的域。 有关如何规划支持软件更新的防火墙的详细信息，请参阅 [Configure firewalls](../LocTest/Plan-for-software-updates-in-System-Center-Configuration-Manager.md#BKMK_ConfigureFirewalls)。  
  
-   **从上游数据源位置同步**：使用此设置以从上游同步源同步软件更新元数据。 系统会将子主站点和辅助站点自动配置为将父站点 URL 用于此设置。 你可以选择将从现有的 WSUS 服务器同步软件更新。 指定 URL，如 https://WSUSServer:8531，其中 8531 是用于连接到 WSUS 服务器的端口。  
  
-   “不要从 Microsoft 更新或上游数据源同步”：使用此设置以在顶层站点上的软件更新点从 Ineternet 断开连接时手动同步软件更新。 有关详细信息，请参阅本主题中的[从断开连接的软件更新点中同步软件更新](#BKMK_SyncDisconnected)部分。  
  
> [!NOTE]  
>  如果软件更新点与 Internet 之间存在防火墙，则可能需要将防火墙配置为接受用于 WSUS 网站的 HTTP 和 HTTPS 端口。 你也可以选择将防火墙上的访问权限局限于受限制的域。 有关如何规划支持软件更新的防火墙的详细信息，请参阅[在 System Center Configuration Manager 中规划软件更新](../LocTest/Plan-for-software-updates-in-System-Center-Configuration-Manager.md)主题中的[配置防火墙](../LocTest/Plan-for-software-updates-in-System-Center-Configuration-Manager.md#BKMK_ConfigureFirewalls)部分。  
  
 你还可配置是在向导“同步源”  页上还是在“软件更新点组件属性”的“同步设置”  选项卡上创建 WSUS 报告事件。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不使用这些事件；因此，你通常选择默认设置“不创建 WSUS 报告事件” 。  
  
### 同步计划  
 在向导的“同步计划”  页上或者在“软件更新点组件属性”中配置同步计划。 仅在顶层站点的软件更新点上配置此设置。  
  
 如果启用计划，则可以配置一个简单或自定义的定期同步计划。 如果配置简单的计划，则开始时间基于在你创建计划时运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台的计算机的本地时间。 如果配置自定义计划的开始时间，则此开始时间基于运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台的计算机的本地时间。  
  
> [!TIP]  
>  使用适合你的环境的时间范围来计划运行软件更新同步。 常见的一种情况是将软件更新同步计划设置为在每月第二个星期二发布了 Microsoft 定期安全更新（这通常称为周二补丁日）之后立即运行。 另一种常见的情况是将软件更新同步计划设置为每天使用软件更新提供 Endpoint Protection 定义和引擎更新时运行。  
  
> [!NOTE]  
>  如果选择不按计划启用软件更新同步，则可以从“软件库”工作区内的“所有软件更新”  或“软件更新组”  节点中手动同步软件更新。 有关详细信息，请参阅 [步骤 2：同步软件更新](#BKMK_SUMSync)。  
  
### 取代规则  
 在向导的“取代规则”  页上或者在“软件更新点组件属性”中的“取代规则”  选项卡上配置取代设置。 只能在顶层站点上配置取代规则。  
  
 在此页上，你可以指定被取代的软件更新立即过期，这会阻止将它们包含在新部署中并标记现有部署，以指明被取代的软件更新包含一个或多个过期的软件更新。 或者，你可以指定被取代软件更新过期之前的时间段，从而允许你继续部署这些更新。 有关详细信息，请参阅 [Supersedence rules](../LocTest/Plan-for-software-updates-in-System-Center-Configuration-Manager.md#BKMK_SupersedenceRules)。  
  
> [!NOTE]  
>  向导的“取代规则”  页仅当在站点配置第一个软件更新点时可用。 当你安装其他软件更新点时，此页不会显示。  
  
### 分类  
 在向导的“分类”  页上或者在“软件更新点组件属性”中的“分类”  选项卡上配置分类设置。 有关软件更新分类的详细信息，请参阅[在 System Center Configuration Manager 中规划软件更新](../LocTest/Plan-for-software-updates-in-System-Center-Configuration-Manager.md)主题中的[更新分类](../LocTest/Plan-for-software-updates-in-System-Center-Configuration-Manager.md#BKMK_UpdateClassifications)部分。  
  
> [!NOTE]  
>  向导的“分类”  页仅当在站点配置第一个软件更新点时可用。 当你安装其他软件更新点时，此页不会显示。  
  
> [!TIP]  
>  当你首次在顶层站点上安装软件更新点时，请清除所有软件更新分类。 初次软件更新同步之后，请配置更新的列表中的分类，然后重新启动同步。 仅在顶层站点的软件更新点上配置此设置。  
  
### 产品  
 在向导的“产品”  页上或者在“软件更新点组件属性”中的“产品”  选项卡上配置产品设置。  
  
> [!NOTE]  
>  向导的“产品”  页仅当在站点配置第一个软件更新点时可用。 当你安装其他软件更新点时，此页不会显示。  
  
> [!TIP]  
>  当你首次在顶层站点上安装软件更新点时，请清除所有产品。 初次软件更新同步之后，请配置更新的列表中的产品，然后重新启动同步。 仅在顶层站点的软件更新点上配置此设置。  
  
### 语言  
 在向导的“语言”  页上或者在“软件更新点组件属性”中的“语言”  选项卡上配置语言设置。 指定想要对其同步软件更新文件和摘要详细信息的语言。 在 **层次结构中的每个软件更新点上配置“软件更新文件”**[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 设置。 “摘要详细信息”  设置仅在顶层软件更新点上配置。 有关详细信息，请参阅 [Languages](../LocTest/Plan-for-software-updates-in-System-Center-Configuration-Manager.md#BKMK_UpdateLanguages)。  
  
> [!NOTE]  
>  向导的“语言”  页仅在安装管理中心站点的软件更新点时可用。 你可以在“软件更新点组件属性”内的“语言”  选项卡中配置子站点中的软件更新文件语言。  
  
##  <a name="BKMK_SUMSync"></a> 步骤 2：同步软件更新  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的软件更新同步是指检索满足你对顶层站点配置的条件的软件更新元数据的过程。 顶层站点上的软件更新点按计划从 Microsoft 更新网站或现有的 WSUS 服务器中检索元数据，或者你可以从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中手动启动同步。 要成功完成同步，软件更新点必须能够访问其上游同步源。 从上游同步源中断开软件更新点后，你必须使用 WSUSUtil 工具从软件更新源中导出软件更新元数据，并将元数据导入到断开连接的软件更新点中。 下表列出了软件更新点类型以及软件更新点需要其访问权限的上游同步源。  
  
|软件更新点|上游同步源|  
|---------------------------|-------------------------------------|  
|管理中心站点|Microsoft 更新 (Internet)<sup>1</sup><br /><br /> 现有 WSUS 服务器|  
|独立主站点|Microsoft 更新 (Internet)<sup>1</sup><br /><br /> 现有 WSUS 服务器|  
|子主站点|管理中心站点|  
|辅助站点|父主站点|  
  
 <sup>1</sup>当软件更新点从上游更新源断开连接时，你可以手动执行软件更新同步。 有关详细信息，请参阅本主题中的[从断开连接的软件更新点中同步软件更新](#BKMK_SyncDisconnected)部分。  
  
###  <a name="BKMK_SyncConnected"></a> 从连接的软件更新点同步软件更新  
 通常， [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 层次结构中的软件更新点将拥有上游更新源的访问权限。 在这种情况下，顶层站点上的软件更新点将连接到 Internet，并从 Microsoft 更新站点同步软件更新，然后顶层站点将向其他站点发送同步请求以启动同步过程。 当站点收到来自顶层站点的同步请求时，站点的软件更新点将从其上游同步源检索软件更新元数据。  
  
> [!NOTE]  
>  子主站点和辅助站点上的软件更新点必须连接到其上游同步源来同步软件更新。 当软件更新点从其上游同步源断开连接时，你可以使用导出和导入方法来同步软件更新。 有关详细信息，请参阅本主题中的[从断开连接的软件更新点中同步软件更新](#BKMK_SyncDisconnected)部分。  
  
 按配置的计划启动软件更新同步时，顶层软件更新点将按计划的日期和时间启动与 Microsoft 更新的同步。 自定义的计划允许你在 WSUS 服务器、站点服务器和网络的需求较低的日期和时间同步软件更新，例如每周在凌晨 2:00 进行同步。 在按计划同步期间，自上次计划的同步以来对软件更新元数据所做的所有更改将被插入到站点数据库。 这包括新的软件更新元数据，或已修改、删除或者现在已过期的元数据。 与上游同步源的同步完成后，将向子主站点或辅助站点上的软件更新点发送一个同步请求。 你也可以从“软件库” [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]**工作区的“所有软件更新”****节点手动启动** 控制台中顶层站点上的软件更新同步。  
  
 在顶层站点上使用下列过程来计划或手动启动软件更新同步。  
  
##### 计划软件更新同步  
  
1.  在 Configuration Manager 控制台中，单击“管理” 。  
  
2.  在“管理”工作区中，展开“站点配置” ，然后单击“站点” 。  
  
3.  在结果窗格中，单击管理中心站点或独立主站点。  
  
4.  在“主页”  选项卡上的“设置”  组中，展开“配置站点组件” ，然后单击“软件更新点” 。  
  
5.  在“软件更新点组件属性”对话框中，选择“按计划启用同步” ，然后指定同步计划。  
  
##### 手动启动软件更新同步  
  
1.  在连接到管理中心站点或独立主站点的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“软件库” 。  
  
2.  在“软件库”工作区中，展开“软件更新”  ，并单击“所有软件更新”  或“软件更新组” 。  
  
3.  在“主页”  选项卡上的“创建”  组中，单击“同步软件更新” 。 在对话框中单击“是”  确认要启动同步过程。  
  
 在软件更新点上启动同步过程之后，可以通过 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台监视层次结构中的所有软件更新点的同步过程。 使用下列过程来监视软件更新同步过程。  
  
##### 监视软件更新同步过程  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“监视” 。  
  
2.  在“监视”  工作区中，单击“软件更新点同步状态” 。  
  
     [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 层次结构中的软件更新点显示在结果窗格中。 从此视图中，你可以监视所有软件更新点的同步状态。 如果要了解有关同步过程的更多详细信息，请查看位于每台站点服务器上的 <*ConfigMgrInstallationPath*>\Logs 中的 wsyncmgr.log 文件。  
  
###  <a name="BKMK_SyncDisconnected"></a> 从断开连接的软件更新点中同步软件更新  
 如果顶层站点上的软件更新点从 Internet 断开连接，你必须使用 WSUSUtil 工具的导出和导入功能来同步软件更新元数据。 你可以选择不属于 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 层次结构的现有 WSUS 作为同步源。 本部分提供有关如何使用 WSUSUtil 工具的导出和导入功能的信息。  
  
 要导出和导入软件更新元数据，你必须从指定导出服务器上的 WSUS 数据库中导出软件更新元数据，接着将本地存储的许可条款文件复制到断开连接的软件更新点，然后将软件更新元数据导入断开连接的软件更新点上的 WSUS 数据库。  
  
 使用下表来确定要在其中导出软件更新元数据的导出服务器。  
  
|软件更新点|连接的软件更新点的上游更新源|断开连接的软件更新点的导出服务器|  
|---------------------------|-----------------------------------------------------------------|------------------------------------------------------------|  
|管理中心站点|Microsoft 更新 (Internet)<br /><br /> 现有 WSUS 服务器|通过使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 环境中所需的软件更新分类、产品和语言选择与 Microsoft 更新同步的 WSUS 服务器。|  
|独立主站点|Microsoft 更新 (Internet)<br /><br /> 现有 WSUS 服务器|通过使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 环境中所需的软件更新分类、产品和语言选择与 Microsoft 更新同步的 WSUS 服务器。|  
  
 在开始导出过程之前，请验证软件更新同步是否已在所选导出服务器上完成，以确保同步最新的软件更新元数据。 要验证软件更新同步是否已成功完成，请使用下列过程。  
  
##### 验证软件更新同步是否已在导出服务器上成功完成  
  
1.  在导出服务器上打开 WSUS 管理控制台并连接到 WSUS 数据库。  
  
2.  在 WSUS 管理控制台中，单击“同步” 。 软件更新同步尝试的列表将显示在结果窗格中。  
  
3.  在结果窗格中，找到最新的软件更新同步尝试并验证该尝试是否已成功完成。  
  
> [!IMPORTANT]  
>  WSUSUtil 工具必须以本地方式在导出服务器上运行才能导出软件更新元数据，并且它还必须在断开连接的软件更新点服务器上运行才能导入软件更新元数据。 此外，运行 WSUSUtil 工具的用户必须是每个服务器上的本地管理员组的成员。  
  
#### 软件更新的导出过程  
 软件更新导出过程包括两个主要步骤：将本地存储的许可条款文件复制到断开连接的软件更新点，以及从导出服务器上的 WSUS 数据库中导出软件更新元数据。  
  
 使用下列过程将本地许可条款元数据复制到断开连接的软件更新点。  
  
###### 将本地文件从导出服务器复制到断开连接的软件更新点服务器  
  
1.  在导出服务器上，导航到存储软件更新和软件更新许可条款的文件夹。 默认情况下，WSUS 服务器将文件存储在 <*WSUSInstallationDrive*>\WSUS\WSUSContent\\ 下，其中 *WSUSInstallationDrive* 是安装了 WSUS 的驱动器。  
  
2.  将所有文件和文件夹从此位置复制到断开连接的软件更新点服务器上的 WSUSContent 文件夹。  
  
 使用下列过程从导出服务器上的 WSUS 数据库中导出软件更新元数据。  
  
###### 从导出服务器上的 WSUS 数据库中导出软件更新元数据  
  
1.  在导出服务器上的命令提示符处，导航到包含 WSUSutil.exe 的文件夹。 默认情况下，该工具位于 %*ProgramFiles*%\Update Services\Tools。 例如，如果该工具位于默认位置中，则键入 **cd %ProgramFiles%\Update Services\Tools**。  
  
2.  键入下列命令以将软件更新元数据导出为一个包文件：  
  
     **wsusutil.exe export**  *packagename*  *logfile*  
  
     例如：  
  
     **wsusutil.exe export export.cab export.log**  
  
     此格式可以汇总为如下：WSUSutil.exe 后跟导出选项、在导出操作过程中创建的导出 .cab 文件的名称，以及日志文件的名称。 WSUSutil.exe 从导出服务器中导出元数据，并创建操作的日志文件。  
  
    > [!NOTE]  
    >  包（.cab 文件）和日志文件名称在当前文件夹中必须唯一。  
  
3.  将导出包移动到导入 WSUS 服务器上包含 WSUSutil.exe 的文件夹。  
  
    > [!NOTE]  
    >  如果将包移动到此文件夹，导入体验可能会更加轻松。 你可以将包移动到导入服务器可访问的任何位置，然后在运行 WSUSutil.exe 时指定该位置。  
  
#### 导入软件更新元数据  
 使用下列过程将软件更新元数据从导出服务器导入到断开连接的软件更新点。  
  
> [!IMPORTANT]  
>  决不要导入从你不信任的源中导出的任何数据。 如果导入你不信任的源中的内容，将可能会危害 WSUS 服务器的安全性。  
  
###### 将元数据导入到导入服务器的数据库  
  
1.  在导入 WSUS 服务器上的命令提示符下，导航到包含 WSUSutil.exe 的文件夹。 默认情况下，该工具位于 %*ProgramFiles*%\Update Services\Tools。  
  
2.  键入下列命令：  
  
     **wsusutil.exe import**  *packagename*  *logfile*  
  
     例如：  
  
     **wsusutil.exe import export.cab import.log**  
  
     此格式可以汇总为如下：WSUSutil.exe 后跟导入命令、在导出操作过程中创建的包文件 (.cab) 的名称、包文件的路径（如果该文件位于其他文件夹中），以及日志文件的名称。 WSUSutil.exe 从导出服务器中导入元数据，并创建操作的日志文件。  
  
## 分类  
 在向导的“分类”  页上或软件更新点组件属性的“分类”  选项卡上配置分类设置。 有关软件更新分类的详细信息，请参阅 [Update classifications](../LocTest/Plan-for-software-updates-in-System-Center-Configuration-Manager.md#BKMK_UpdateClassifications)。  
  
> [!NOTE]  
>  向导的“分类”  页仅在配置在独立主站点上所配置的第一个软件更新点时可用。 当你安装其他软件更新点时，此页不会显示。  
  
> [!TIP]  
>  当你首次在顶层站点上安装软件更新点时，请清除所有软件更新分类。 初始软件更新同步之后，你必须依据更新的列表配置分类，然后重新启动同步。 仅在顶层站点的软件更新点上配置此设置。  
  
## 产品  
 在向导的“产品”  页上或软件更新点组件属性的“产品”  选项卡上配置产品设置。  
  
> [!NOTE]  
>  向导的“产品”页  仅在配置在独立主站点上所配置的第一个软件更新点时可用。 当你安装其他软件更新点时，此页不会显示。  
  
> [!TIP]  
>  当你首次在顶层站点上安装软件更新点时，请清除所有产品。 初始软件更新同步之后，你必须依据更新的列表配置产品，然后重新启动同步。 仅在顶层站点的软件更新点上配置此设置。  
  
##  <a name="BKMK_ConfigureClassesProducts"></a> 步骤 3：配置要同步的分类和产品  
  
> [!NOTE]  
>  请仅在顶层站点上使用本部分中的过程。  
  
 在步骤 1 中，你清除了分类和产品列表。 在步骤 2 中，你启动了软件更新同步，以更新 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 和 WSUS 中的分类和产品列表。 在步骤 3 中，你必须选择要同步的分类和产品。  
  
 使用下列过程来配置要同步的分类和产品。  
  
#### 配置要同步的分类和产品  
  
1.  在“Configuration Manager”  控制台中，单击“管理” 。  
  
2.  在“管理”工作区中，展开“站点配置” ，单击“站点” ，然后选择管理中心站点或独立主站点。  
  
3.  在“主页”  选项卡上的“设置”  组中，单击“配置站点组件” ，再单击“软件更新点” 。  
  
4.  在“分类”  选项卡上，指定要为其同步软件更新的软件更新分类。  
  
    > [!NOTE]  
    >  每个软件更新都是利用更新分类定义的，此分类能帮助组织不同的更新类型。 同步过程中，将对指定的分类的软件更新元数据进行同步。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 使你可将软件更新与下列更新分类进行同步：  
    >   
    >  -   关键更新：针对特定的问题指定广泛发布的更新，以解决与安全性无关的关键错误。  
    > -   定义更新：指定对病毒定义文件或其他定义文件的更新。  
    > -   功能包：指定新的产品功能，这些功能在产品版本以外分配，而且通常包含在下一个完整的产品版本中。  
    > -   安全更新：针对特定于产品而且与安全性相关的问题指定广泛发布的更新。  
    > -   服务包：指定一组累积的将应用于应用程序的修补程序。 这些修补程序可以包括：安全更新、关键更新、软件更新等。  
    > -   工具：指定可帮助完成一项或多项任务的实用工具或功能。  
    > -   更新汇总：指定一组累积的修补程序，它们打包在一起以便于部署。 这些修补程序可以包括安全更新、关键更新、其他更新等。 更新汇总通常解决特定领域的问题，例如安全性或产品组件问题。  
    > -   更新：指定对已安装的应用程序或文件的更新。  
    > -   升级：为 Windows 10 特性和功能指定升级。  
    >   
    >      软件更新点和站点必须运行具有[ 3095113](https://support.microsoft.com/kb/3095113) 的 WSUS 4.0 来获取升级分类。  
  
5.  在“产品”  选项卡上，指定要为其同步软件更新的产品，然后单击“关闭” 。  
  
    > [!NOTE]  
    >  每个软件更新的元数据都定义了更新适用于的产品。 产品是指特定版本的操作系统或应用程序，例如 Microsoft Windows Server 2012。 产品家族是指从中派生单个产品的基本操作系统或应用程序。 产品系列的示例是 Windows，而 Windows Server 2012 是其成员之一。 可以指定产品系列或产品系列中的各个产品。 你选择的产品越多，同步软件更新所需的时间就越长。  
    >   
    >  在软件更新适用于多个产品，而且至少选择了一个要同步的产品时，即使没有选择某些产品，所有产品都将出现在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中。 例如，Windows Server 2012 是你选择的唯一操作系统，而且软件更新应用于 Windows 8 和 Windows Server 2012，那么，这两个产品都将显示在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中。  
  
    > [!IMPORTANT]  
    >  [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 存储产品和产品系列的列表，你在初次安装软件更新点时可以选择此列表中的项目。 如果某些产品和产品系列是在发布 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 之后发布的，那么，在你完成软件更新同步（这将更新可供你从中选择项目的可用产品和产品系列的列表）之前，可能无法选择它们。  
  
6.  重复 [步骤 2：同步软件更新](#BKMK_SUMSync) 以手动启动软件更新同步。  
  
##  <a name="BKMK_AssociatedSettings"></a> 步骤 4：验证软件更新客户端设置和组策略配置  
 在部署软件更新之前，必须验证一些客户端设置和组策略配置。  
  
###  <a name="BKMK_ClientSettings"></a> 软件更新的客户端设置  
 安装软件更新点之后，默认情况下会在客户端上启用软件更新，而且客户端设置中的  “软件更新”页上的设置具有默认值。 在部署软件更新之前，请验证此页上的客户端设置是否适用于站点中的软件更新。  
  
> [!IMPORTANT]  
>  默认情况下会启用“在客户端上启用软件更新”  设置。 如果清除此设置，则 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 会从客户端中删除现有的部署策略。  
  
 有关如何配置客户端设置的信息，请参阅 [How to configure client settings in System Center Configuration Manager](../LocTest/How-to-configure-client-settings-in-System-Center-Configuration-Manager.md)。  
  
 有关客户端设置的详细信息，请参阅 [About client settings in System Center Configuration Manager](../LocTest/About-client-settings-in-System-Center-Configuration-Manager.md)。  
  
###  <a name="BKMK_GroupPolicy"></a> 软件更新的组策略设置  
 客户端计算机上的 Windows 更新代理 (WUA) 使用特定的组策略设置来连接到在软件更新点上运行的 WSUS。 这些组策略设置还用于成功扫描软件更新的符合性，以及自动更新软件更新和 WUA。  
  
#### “指定 Intranet Microsoft 更新服务位置”本地策略  
 在为站点创建软件更新点时，客户端会获得计算机策略，此策略提供软件更新点服务器的名称，并且在计算机上配置“指定 Intranet Microsoft 更新服务位置”  本地策略。 WUA 检索在“设置检测更新的 Intranet 更新服务”  设置中指定的服务器名称，之后，它在扫描软件更新符合性时会连接到此服务器。 在为“指定 Intranet Microsoft 更新服务位置”  设置创建域策略时，它将替代本地策略，而且 WUA 可能会连接到软件更新点以外的服务器。 如果出现此情况，客户端可能会根据不同的产品、分类和语言扫描软件更新符合性。 因此，不应为客户端计算机配置 Active Directory 策略。  
  
#### “允许来自 Intranet Microsoft 更新服务位置的签名内容”组策略  
 在计算机上的 WUA 扫描已创建并利用 System Center Updates Publisher 发布的软件更新之前，你必须启用“允许来自 Intranet Microsoft 更新服务位置的签名内容”  组策略设置。 在启用此策略设置时，如果在本地计算机上的“受信任的发布者”  证书存储中签署软件更新，则 WUA 将接受通过 Intranet 位置收到的这些软件更新。 有关 Updates Publisher 所需的组策略设置的详细信息，请参阅 [Updates Publisher 2011 文档库](http://go.microsoft.com/fwlink/p/?LinkId=232476)。  
  
#### 自动更新的配置  
 自动更新允许在客户端计算机上接收安全更新和其他重要的下载内容。 若要配置自动更新，可通过“配置自动更新”  组策略设置或本地计算机上的“控制面板”进行。 在启用自动更新时，客户端计算机将收到更新通知，而且，视已配置的设置而定，客户端计算机将下载并安装所需的更新。 在自动更新与软件更新共存时，每台客户端计算机都可能会为同一个更新显示通知图标和弹出通知窗口。 而且，在需要重新启动时，每台客户端计算机都可能会为同一个更新显示重新启动对话框。  
  
#### 自我更新  
 在客户端计算机上启用自动更新时，如果有可用的更新版本，或者如果 WUA 组件出现问题，则 WUA 会自动执行自我更新。 在未配置或禁用自动更新，而且客户端计算机具有较早版本的 WUA 时，客户端计算机必须运行 WUA 安装文件。  
  
##  <a name="BKMK_RemoveSUP"></a> 删除软件更新点站点系统角色  
 可以通过 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台删除站点中的软件更新点站点系统角色。 客户端策略将更新，以便从列表中删除软件更新点。 在删除站点中的最后一个软件更新点时，软件更新点列表将不包含软件更新点，而且实质上将在站点中禁用软件更新。 如果主站点中有多个软件更新点，而且你删除了配置为同步源的软件更新点，则必须将站点中的另一个软件更新点选为新的同步源。  
  
> [!NOTE]  
>  从站点系统中删除软件更新点站点角色时，请等待至少 15 分钟，然后再重新安装软件更新点站点角色。  
  
 使用下列过程来删除软件更新点。  
  
#### 删除软件更新点  
  
1.  在“Configuration Manager”  控制台中，单击“管理” 。  
  
2.  在“管理”工作区中，展开“站点配置” ，然后单击“服务器和站点系统角色” 。  
  
3.  选择带有要删除的软件更新点的站点系统服务器，然后在“站点系统角色” 中选择“软件更新点” 。  
  
4.  在“站点角色”  选项卡上的“站点角色”  组中，单击“删除角色” 。 确认要删除软件更新点，或者在该站点为其他软件更新点选择新的同步源。  
  
## 另请参阅  
 [在 System Center Configuration Manager 中部署并管理软件更新](../LocTest/Deploy-and-manage-software-updates-in-System-Center-Configuration-Manager.md)
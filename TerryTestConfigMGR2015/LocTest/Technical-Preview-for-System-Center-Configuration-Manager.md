---
title: "System Center Configuration Manager Technical Preview"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-other
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid: 9ce0a8cb-f96c-4e41-834c-59ceb54ce44a
caps.latest.revision: 157
caps.handback.revision: 147
translationtype: Human Translation
---
# System Center Configuration Manager Technical Preview
**欢迎使用 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] Technical Preview**。 本主题提供了有关不断完善的预览版的详细信息，该版本包括我们正在开发的功能。 每个版本的技术预览版可用时，都会引入尚未包含在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 的当前分支中的新功能。 这些功能最终可能会包含在当前分支版本的更新中，但在确定和添加功能之前，我们希望你有机会试用它们并向我们提供反馈。  
  
 由于这是技术预览版，因此详细信息和功能可能有所更改。  
  
 本主题包含适用于所有的技术预览版本的信息，并且列出了每个新功能及功能首次在其中出现的技术预览版本，例如，版本 1512 表示 2015 年 12 月。 这些功能的详细信息将专门在各预览版本的单独主题中详细介绍。  
  
 有关 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的当前分支中新增功能的信息，请参阅 [System Center Configuration Manager 中的新增功能](../LocTest\What’s-new-in-System-Center-Configuration-Manager-incremental-versions.md)。
  
> [!NOTE]  
>  有关 System Center Configuration Manager Technical Preview 4（以及更早的预览版）中功能的信息，请参阅 [System Center Configuration Manager 的预发行版的 Technical Preview](https://technet.microsoft.com/library/dn965439.aspx)  
  
 **本主题内容：**  
  
-   [Technical Preview 的要求和限制](#bkmk_reqs)  
  
-   [安装并更新技术预览版](#bkmk_install)  
  
-   [提供反馈](#BKMK_TPFeedback)  
  
-   [技术预览版中引入的一般性更改](#bdmk_tpknownissues)  
  
-   [技术预览版中提供的功能](#bkmk_tpCaps)  
  
##  <a name="bkmk_reqs"></a> Technical Preview 的要求和限制  
  
> [!IMPORTANT]  
>  Technical Preview 仅授权用于实验室环境。  Microsoft 可能无法提供支持服务，预览软件中某些功能可能不可用。 此外，相对于面向市场提供的软件，预览版软件可能采用简化的或不同的安全性、隐私性、可访问性、可用性和可靠性标准。  
  
 有关大多数产品的先决条件，请使用 [!INCLUDE[cm6long] (../Token/cm6long_md.md)] [System Center Configuration Manager 支持的配置文档](../LocTest/Supported-configurations-for-System-Center-Configuration-Manager.md)中的信息。 以下是适用于技术预览版本的例外情况：  
  
-   每次安装在保持活动状态 90 天后变为非活动状态。  
  
-   英语是唯一受支持的语言。  
  
-   仅支持独立主站点。 不支持管理中心站点、多个主站点或辅助站点。  
  
-   仅支持以下 SQL Server 版本：  
  
    -   带累积更新 2 的 SQL Server 2012 或更高版本  
  
    -   SQL Server 2014  
  
-   站点最多支持 10 个客户端，这些客户端必须在以下操作系统之一上运行：  
  
    -   Windows 7  
  
    -   Windows 8  
  
    -   Windows 8.1  
  
    -   Windows 10  
  
-   仅支持以下安装标志（开关）：  
  
    -   **/Silent**  
  
    -   **/testdbupgrade**  
  
-   Technical Preview 的每个特定版本的详细信息中会随附其他限制或要求（如果适用）  
  
-   不支持迁移到此预览版或从此预览版进行迁移。  
  
-   不支持升级到此预览版。  
  
-   不支持从此预览版升级到生产版本（当前分支）。 但是，当更新可用于预览版本时，你可以从 **的“更新和服务”**[!INCLUDE[cmconsole](../LocTest/includes/cmconsole_md.md)]节点查找和安装它们。 有关控制台中升级过程的视频，请观看 youtube.com 上的 [Installing ConfigMgr Update Packages（安装 ConfigMgr 更新包）](https://www.youtube.com/embed/KBd_EGFbUT8) 。  
  
##  <a name="bkmk_install"></a> 安装并更新技术预览版  
 此 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 技术预览版与当前版本的 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]不同。  
  
 若要使用技术预览版，必须先安装技术预览版内部版本的**基线版本**。 安装基线版本之后，可使用**控制台内部更新**来升级此内部版本，以便使用最新预览版使你的安装程序保持最新。     通常，每个月都会提供新版本的 Technical Preview。  
  
> [!TIP]  
>  当你将更新安装到技术预览版时，即可将预览安装更新到此新的技术预览版。    技术预览版安装绝不会升级到当前的分支安装，也不会从当前分支版本获取更新。  
  
 **Technical Preview 的活动基线版本：**  
  
-   **Technical Preview 1603** 作为 **System Center Technical Preview 5** 的一部分 - [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] Technical Preview 1603 可作为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] Technical Preview 的控制台内部更新，以及作为随 System Center Technical Preview 5 附带的新基线版本提供。    只有随 System Center Technical Preview 5 附带的版本才能用于基线安装。  
  
     关于[来自 System Center Technical Preview 5 的 Configuration Manager Technical Preview](https://www.microsoft.com/en-us/evalcenter/evaluate-system-center-configuration-manager-and-endpoint-protection-technical-preview) 的基线版本：  
  
    -   安装程序和 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台都将该版本列为 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] Technical Preview 1603。  
  
    -   此基线版本的作用与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] Technical Preview 1603 一样（包括对控制台内部更新的支持）。  
  
    -   可以在 System Center Technical Preview 5 发布之后的最多 9 个月内安装此基线版本。  
  
    -   可以运行此基准版本 90 天，之后必须将它更新为更高版本。 （通常，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] Technical Preview 的版本会运行 60 天，之后必须将其更新为更高版本。）  
  
##  <a name="BKMK_TPFeedback"></a> 提供反馈  
 我们希望收到有关技术预览版的反馈。 若要提交关于每个预览版中的功能的反馈，请使用指向我们的反馈表的链接，该反馈表位于 Microsoft Connect 站点上的 [Configuration Manager 反馈计划](https://connect.microsoft.com/ConfigurationManagervnext/ConfigMgr%20Customer%20Feedback) 页中。  
  
 此外，如果你对于想要看到的新功能有任何想法，也请让我们知道。 若要提交新的想法，并为他人提交的想法投票，请 [访问我们的用户之声页面](http://configurationmanager.uservoice.com)。  
  
##  <a name="bdmk_tpknownissues"></a> 技术预览版中引入的一般性更改  
  
-   “Technical Preview 1601” ：默认情况下，在安装时，服务连接点设置为联机模式，且不支持更改为脱机模式。  
  
-   “Technical Preview 1602” ：从 Technical Preview 1602 开始，你可以将运行 Windows 2008 Server R2 的站点系统服务器的操作系统就地升级为 Windows 2012 Server R2。  当你使用 Windows Server 2012 R2 升级过程时，在升级后不需要运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点服务器还原。  有关升级过程，请参阅 [Windows Server 2012 R2 的升级选项](https://technet.microsoft.com/library/dn303416.aspx)。  
  
    > [!WARNING]  
    >  升级到 Windows Server 2012 R2 之前，**必须从服务器中卸载 WSUS 3.2**。  
    >   
    >  有关此关键步骤的信息，请参阅 Windows Server 文档中 [Windows Server 更新服务概述](https://technet.microsoft.com/library/hh852345.aspx) 中的“新增和更改的功能”部分。  
  
-   **Technical Preview 1603：**  
  
    -   从 Technical Preview 1603 开始，可以配置软件更新部署，以便让客户端在客户端安装软件更新并重新启动之后立即运行软件更新符合性扫描。 这使客户端可以检查在客户端重新启动之后成为适用状态的其他软件更新，以及随后在相同维护时段期间安装它们（并成为符合状态）。  
  
         若要为部署配置这一项，请在部署软件更新向导的“用户体验”页上，选择选项“如果此部署中的任何更新需要重新启动系统，则在重新启动之后运行更新部署评估周期”。  
  
    -   从 Technical Preview 1603 开始，SMSTSRebootDelay 任务序列变量的行为已更改。 SMSTSRebootDelay 变量指定在计算机重新启动之前要等待多少秒。 如果此变量没有设置为 0，则任务序列管理器将在重新启动之前显示通知对话框。  
        为此变量配置值时，该值会一直保持到配置新值。 所有后续计算机重新启动的延迟都具有相同值。 在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 版本 1602 及更早版本中，该变量会在计算机重启之后重置为默认值（30 秒）。   有关详细信息，请参阅 [Task sequence built-in variables in System Center Configuration Manager](../LocTest/Task-sequence-built-in-variables-in-System-Center-Configuration-Manager.md)。  
  
##  <a name="bkmk_tpCaps"></a> 技术预览版中提供的功能  
 以下是为每个 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 技术预览版提供的功能。  从某一技术预览版开始提供的功能，在其后的版本中将保持可用。 同样，已添加到 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 发行版本的功能（当前分支）在后续的技术预览版中将保持可用。  请单击查看每个预览版本的内容，了解有关特定功能的详细信息。  
  
|功能|从...中起开始提供|  
|----------------|----------------------------|  
|[在 Windows 10 中与 Windows Update for Business 集成](../LocTest\Capabilities-in-Technical-Preview-1511-for-System-Center-Configuration-Manager.md#BKMK_WUfB)|[1511](https://technet.microsoft.com/library/mt706225.aspx)|  
|[通过 System Center Configuration Manager 管理 Office 365 ProPlus 客户端更新](../LocTest\Capabilities-in-Technical-Preview-1511-for-System-Center-Configuration-Manager.md#BKMK_Office365ProPlus)|[1511](https://technet.microsoft.com/library/mt706225.aspx)|  
|[支持 SQL Server AlwaysOn，实现数据库的高度可用性](../LocTest\Capabilities-in-Technical-Preview-1511-for-System-Center-Configuration-Manager.md#BKMK_AlwasyOn)|[1511](https://technet.microsoft.com/library/mt706225.aspx)|  
|[为服务器群集提供服务](../LocTest\Capabilities-in-Technical-Preview-1511-for-System-Center-Configuration-Manager.md#BKMK_ClusterServerUpdates)|[1511](https://technet.microsoft.com/library/mt706225.aspx)|  
|[设备运行状况证明](../LocTest\Capabilities-in-Technical-Preview-1512-for-System-Center-Configuration-Manager.md#bkmk_devicehealth)|[1512](https://technet.microsoft.com/library/mt706223.aspx)|  
|[条款和条件的控制台中监视](../LocTest\Capabilities-in-Technical-Preview-1512-for-System-Center-Configuration-Manager.md#bkmk_viewterms)|[1512](https://technet.microsoft.com/library/mt706223.aspx)|  
|[Endpoint Protection 策略设置的改进](../LocTest\Capabilities-in-Technical-Preview-1512-for-System-Center-Configuration-Manager.md#bkmk_EPpolicy)|[1512](https://technet.microsoft.com/library/mt706223.aspx)|  
|[对 Microsoft Intune 集成的改进](../LocTest\Capabilities-in-Technical-Preview-1601-for-System-Center-Configuration-Manager.md#bkmk_hybrid1)|[1601](https://technet.microsoft.com/library/mt706226.aspx)|  
|[客户端联机状态](../LocTest\Capabilities-in-Technical-Preview-1601-for-System-Center-Configuration-Manager.md#bkmk_clientStatus)|[1601](https://technet.microsoft.com/library/mt706226.aspx)|  
|[对应用程序管理的改进](../LocTest\Capabilities-in-Technical-Preview-1601-for-System-Center-Configuration-Manager.md#bkmk_appmgmt1601)|[1601](https://technet.microsoft.com/library/mt706226.aspx)|  
|[对合规性设置的改进](../LocTest\Capabilities-in-Technical-Preview-1601-for-System-Center-Configuration-Manager.md#bkmk_compliance1601)|[1601](https://technet.microsoft.com/library/mt706226.aspx)|  
|[对移动设备管理的改进](../LocTest\Capabilities-in-Technical-Preview-1602-for-System-Center-Configuration-Manager.md#BKMK_MDM)|[1602](https://technet.microsoft.com/library/mt706221.aspx)|  
|[1602 版本中对软件中心的改进](../LocTest\Capabilities-in-Technical-Preview-1602-for-System-Center-Configuration-Manager.md#BKMK_SC1601)|[1602](https://technet.microsoft.com/library/mt706221.aspx)|  
|[对 Windows 10 维护服务的改进](../LocTest\Capabilities-in-Technical-Preview-1602-for-System-Center-Configuration-Manager.md#BKMK_Win10Servicing)|[1602](https://technet.microsoft.com/library/mt706221.aspx)|  
|[1603 版本中对软件中心的改进](../LocTest\Capabilities-in-Technical-Preview-1603-for-System-Center-Configuration-Manager.md#BKMK_SC1603)|[1603](https://technet.microsoft.com/library/mt706227.aspx)|  
|[对远程控制的改进](../LocTest\Capabilities-in-Technical-Preview-1603-for-System-Center-Configuration-Manager.md#BKMK_RC1603)|[1603](https://technet.microsoft.com/library/mt706227.aspx)|  
|[在启用 PXE 的分发点上自定义 RamDisk TFTP 块大小和窗口大小](../LocTest\Capabilities-in-Technical-Preview-1603-for-System-Center-Configuration-Manager.md#BKMK_RamDiskTFTP)|[1603](https://technet.microsoft.com/library/mt706227.aspx)|  
|[管理从适用于企业的 Windows 应用商店批量采购的应用](../LocTest\Capabilities-in-Technical-Preview-1604-for-System-Center-Configuration-Manager.md#BKMK_WindowsVPP)|[1604](https://technet.microsoft.com/library/mt706224.aspx)|  
|[对 Microsoft Passport for Work 管理的改进](../LocTest\Capabilities-in-Technical-Preview-1604-for-System-Center-Configuration-Manager.md#BKMK_PFW)|[1604](https://technet.microsoft.com/library/mt706224.aspx)|  
|[供客户端切换到新软件更新点的选项](../LocTest\Capabilities-in-Technical-Preview-1604-for-System-Center-Configuration-Manager.md#bkmk_switchsup)|[1604](https://technet.microsoft.com/library/mt706224.aspx)|  
|[用于管理客户端缓存设置和客户端对等缓存的客户端设置](../LocTest\Capabilities-in-Technical-Preview-1604-for-System-Center-Configuration-Manager.md#bkmk_peercache)|[1604](https://technet.microsoft.com/library/mt706224.aspx)|  
|[支持将 Passport for Work 作为 KSP](../LocTest\Capabilities-in-Technical-Preview-1604-for-System-Center-Configuration-Manager.md#bkmk_passport)|[1604](https://technet.microsoft.com/library/mt706224.aspx)|  
|[本地设备运行状况证明](../LocTest\Capabilities-in-Technical-Preview-1604-for-System-Center-Configuration-Manager.md#bkmk_onpremdha)|[1604](https://technet.microsoft.com/library/mt706224.aspx)|  
|[适用于 Android 设备的 SmartLock 设置](../LocTest\Capabilities-in-Technical-Preview-1604-for-System-Center-Configuration-Manager.md#BKMK_Smart)|[1604](https://technet.microsoft.com/library/mt706224.aspx)|  
|[Windows 10 设备的每应用 VPN](../LocTest\Capabilities-in-Technical-Preview-1605-for-System-Center-Configuration-Manager.md#BKMK_PerAppVPN)|[1605](https://technet.microsoft.com/library/mt706220.aspx)|  
|[安装软件更新任务序列的改进](../LocTest\Capabilities-in-Technical-Preview-1605-for-System-Center-Configuration-Manager.md#BKMK_InstallSU)|[1605](https://technet.microsoft.com/library/mt706220.aspx)|  
|[准备 ConfigMgr 客户端以便捕获任务序列步骤的改进](../LocTest\Capabilities-in-Technical-Preview-1605-for-System-Center-Configuration-Manager.md#BKMK_PrepareConfigMgrClient)|[1605](https://technet.microsoft.com/library/mt706220.aspx)|  
|[所需的应用程序部署的宽限期](../LocTest\Capabilities-in-Technical-Preview-1605-for-System-Center-Configuration-Manager.md#BKMK_Grace)|[1605](https://technet.microsoft.com/library/mt706220.aspx)|  
|[远程设备操作的新体验](../LocTest\Capabilities-in-Technical-Preview-1605-for-System-Center-Configuration-Manager.md#BKMK_Remote)|[1605](https://technet.microsoft.com/library/mt706220.aspx)|  
|[适用于企业的 Windows 应用商店应用](../LocTest\Capabilities-in-Technical-Preview-1605-for-System-Center-Configuration-Manager.md#BKMK_WSFB)|[1605](https://technet.microsoft.com/library/mt706220.aspx)|  
|[批量采购应用的一般改进](../LocTest\Capabilities-in-Technical-Preview-1605-for-System-Center-Configuration-Manager.md#BKMK_VPP2)|[1605](https://technet.microsoft.com/library/mt706220.aspx)|  
|[企业数据保护 (EDP)](../LocTest\Capabilities-in-Technical-Preview-1605-for-System-Center-Configuration-Manager.md#BKMK_VPP)|[1605](https://technet.microsoft.com/library/mt706220.aspx)|  
|[最终用户可从公司门户安装应用](../LocTest\Capabilities-in-Technical-Preview-1605-for-System-Center-Configuration-Manager.md#BKMK_End)|[1605](https://technet.microsoft.com/library/mt706220.aspx)|  
|[软件中心中的更新和操作系统的新选项卡](../LocTest\Capabilities-in-Technical-Preview-1605-for-System-Center-Configuration-Manager.md#BKMK_SW1)|[1605](https://technet.microsoft.com/library/mt706220.aspx)|  
|[为服务器组提供服务](../LocTest\Capabilities-in-Technical-Preview-1605-for-System-Center-Configuration-Manager.md#BKMK_ServerGroups)|[1605](https://technet.microsoft.com/library/mt706220.aspx)|  
|[支持 Windows Defender 高级威胁防护服务](../LocTest\Capabilities-in-Technical-Preview-1605-for-System-Center-Configuration-Manager.md#BKMK_ATP)|[1605](https://technet.microsoft.com/library/mt706220.aspx)|  
|[在软件更新安装之后重启 Windows 10 客户端的新选项](../LocTest\Capabilities-in-Technical-Preview-1605-for-System-Center-Configuration-Manager.md#BKMK_RestartOptions)|[1605](https://technet.microsoft.com/library/mt706220.aspx)|  
|[本地设备运行状况证明](../LocTest\Capabilities-in-Technical-Preview-1605-for-System-Center-Configuration-Manager.md#BKMK_DHA)|[1605](https://technet.microsoft.com/library/mt706220.aspx)|  
|[预声明具有 IMEI 或 iOS 序列号的公司拥有的设备](../LocTest\Capabilities-in-Technical-Preview-1605-for-System-Center-Configuration-Manager.md#BKMK_IMEI)|[1605](https://technet.microsoft.com/library/mt706220.aspx)|  
|[本地移动设备管理的多个设备管理点](../LocTest\Capabilities-in-Technical-Preview-1606-for-System-Center-Configuration-Manager.md#dmp_onprem)|[1606](https://technet.microsoft.com/library/mt732696.aspx)|
|[自动将设备分类到集合](../LocTest\Capabilities-in-Technical-Preview-1606-for-System-Center-Configuration-Manager.md#dmp_category)|[1606](https://technet.microsoft.com/library/mt732696.aspx)|
|[所需的应用程序和软件更新部署的强制宽限期](../LocTest\Capabilities-in-Technical-Preview-1606-for-System-Center-Configuration-Manager.md#dmp_grace)|[1606](https://technet.microsoft.com/library/mt732696.aspx)|
|[通过 Device Guard 将 Configuration Manager 用作托管的安装程序](../LocTest\Capabilities-in-Technical-Preview-1606-for-System-Center-Configuration-Manager.md#dmp_devg)|[1606](https://technet.microsoft.com/library/mt732696.aspx)|
|[云代理服务](../LocTest\Capabilities-in-Technical-Preview-1606-for-System-Center-Configuration-Manager.md#cloud_proxy) | [1606](../LocTest\Capabilities-in-Technical-Preview-1606-for-System-Center-Configuration-Manager.md) |  
|[在 Configuration Manager 中管理 Office 365 客户端代理](../LocTest\Capabilities-in-Technical-Preview-1606-for-System-Center-Configuration-Manager.md#manage_o365) |[1606](../LocTest\Capabilities-in-Technical-Preview-1606-for-System-Center-Configuration-Manager.md) |
 |[已弃用 OSDPreserveDriveLetter 任务序列变量](../LocTest\Capabilities-in-Technical-Preview-1606-for-System-Center-Configuration-Manager.md#osdpreservedriveletter) |[1606](../LocTest\Capabilities-in-Technical-Preview-1606-for-System-Center-Configuration-Manager.md) |
[更新和维护节点的更改](../LocTest\Capabilities-in-Technical-Preview-1606-for-System-Center-Configuration-Manager.md#updatesandservicing)|[1606](../LocTest\Capabilities-in-Technical-Preview-1606-for-System-Center-Configuration-Manager.md) |
|[Windows 10 版本升级策略的改进](../LocTest\Capabilities-in-Technical-Preview-1607-for-System-Center-Configuration-Manager.md#dmp_edition)|[1607](../LocTest\Capabilities-in-Technical-Preview-1607-for-System-Center-Configuration-Manager.md)|
|[软件中心可自定义的品牌的对话框](../LocTest\Capabilities-in-Technical-Preview-1607-for-System-Center-Configuration-Manager.md#Customizable-Branding-for-Software-Center-Dialogs)|[1607](../LocTest\Capabilities-in-Technical-Preview-1607-for-System-Center-Configuration-Manager.md)|
  
## 另请参阅  
[System Center Configuration Manager 中的新增功能](../LocTest\What’s-new-in-System-Center-Configuration-Manager-incremental-versions.md)
 [System Center Configuration Manager 简介](../LocTest/Introduction-to-System-Center-Configuration-Manager.md)
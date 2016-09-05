---
title: "自 System Center 2012 Configuration Manager 以来 System Center Configuration Manager 中更改的内容"
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
ms.assetid: 3ae68fa6-8b30-45dd-9d12-50bb67cb4a9d
caps.latest.revision: 51
caps.handback.revision: 51
translationtype: Human Translation
---
# 自 System Center 2012 Configuration Manager 以来 System Center Configuration Manager 中更改的内容
 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 当前分支引入了自 System Center 2012 Configuration Manager 以来的重要更改。 本主题中的信息将帮助你识别 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 的基准版本 1511 中更显著的更改和新增功能。 若要了解有关 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 的后续更新中引入的其他更改，请参阅 [System Center Configuration Manager 增量版本中的新增功能](../LocTest/What’s-new-in-System-Center-Configuration-Manager-incremental-versions.md)。

  

 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 的 2015 年 12 月版本（版本 1511）是 Microsoft 的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的最新产品版本。   它通常称为 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 的当前分支。 *当前分支*指示这是支持对产品增量更新的版本，并且是 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的旧版本与该版本的一个重要区别。  
  
 使用此版本的 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]：  
  
-   请勿在产品名称中使用年份或产品标识符，这些常见于如 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 2007 或[!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 等旧版本中。
  
-   支持增量产品内更新，也称为更新版本。 初始版本是版本 1511。 一年发布几次作为控制台内更新的后续版本，如版本 1602 或 1606。 
  

  
  
##  <a name="bkmk_updates"></a> Configuration Manager 的控制台内更新  
 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 使用称为**更新和维护服务**的控制台内服务方法，可轻松为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 找到并安装推荐的更新。  
  
 某些版本仅可用作（[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台内）现有站点的更新，而不能用于安装新的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点。   
例如，1602 更新仅在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台内可用，并用于更新运行 1511 到 1602 版本的基准版本的站点。  

我们会定期发布更新版本作为新的基准版本（如更新 1606），此版本可用于在无需以较旧基准版本（如 1511）开始的情况下安装新的层次结构，并且将版本升级到最新版本。 

  
 有关使用更新的详细信息，请参阅 [ System Center Configuration Manager 的更新](../LocTest/Updates-for-System-Center-Configuration-Manager.md)  
  
##  <a name="bkmk_servicepoint"></a> 服务连接点替换 Microsoft Intune 连接器  
 **[!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 连接器**被启用附加功能的新站点系统角色（**服务连接点**）替换。 服务连接点：  
  
-   在集成 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 时替换 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 连接器 [!INCLUDE[onprem_first](../LocTest/includes/onprem_first_md.md)]  
  
-   用作管理设备的联系点  
  
-   将有关部署的使用情况数据上传到 Microsoft 云服务  
  
-   使应用到部署的更新可用 [!INCLUDE[cmconsole](../LocTest/includes/cmconsole_md.md)]  
  
 此站点系统角色支持可影响它其他用途的联机和脱机操作模式。 有关详细信息，请参阅[关于 System Center Configuration Manager 服务连接点](../LocTest/About-the-service-connection-point-in-System-Center-Configuration-Manager.md)。  
  
##  <a name="bkmk_usage"></a> 使用数据收集  
 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 收集有关你的站点和基础结构的使用数据。 服务连接点（新的站点系统角色）将此信息编译和提交至 Microsoft 云服务，而使 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 能够下载部署的更新需要此信息，这些更新应用于你使用的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的版本。 当配置服务连接点时，你可以配置收集到的数据级别以及它是自动提交（联机模式）还是手动提交（脱机模式）。  
  
 有关详细信息，请参阅 [Usage data levels and settings](../LocTest/Reference-for-System-Center-Configuration-Manager-Setup.md#bkmk_usage)。  
  
##  <a name="bkmk_AMT"></a> Intel 主动管理技术 (AMT) 的支持  
 有了 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]， [!INCLUDE[cmconsole](../LocTest/includes/cmconsole_md.md)] 中将不再提供对基于 AMT 的计算机的本机支持。  
  
-   使用 [适用于 Microsoft System Center Configuration Manager Intel SCS 外接程序](http://www.intel.com/content/www/us/en/software/setup-configuration-software.html)时，基于 AMT 的计算机保持完全托管  
  
-   在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 合并这些更改之前，可以使用外接程序来访问用于管理 AMT 的最新功能，同时删除引入的限制  
  
-   [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 中的带外管理不受此更改的影响  
  
 删除 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 的集成 AMT 包括：  
  
-   不再使用带外管理点站点系统角色或者该角色不再可用  
  
##  <a name="bkmk_out"></a> 弃用的功能  
 有了 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]时，一些功能（如基于本机 [Intel 主动管理技术 (AMT) 的支持](#bkmk_AMT) 的计算机）会从 [!INCLUDE[cmconsole](../LocTest/includes/cmconsole_md.md)]中删除，而像网络访问保护等其他功能则被完全删除。 此外，不再支持某些较旧的 Microsoft 产品，如 Windows Vista、Windows Server 2008 和 SQL Server 2008。  
  
 有关弃用功能的列表，请参阅 [Removed and deprecated features for System Center Configuration Manager](../LocTest/Removed-and-deprecated-features-for-System-Center-Configuration-Manager.md)  
  
 有关受支持的产品、操作系统和配置的详细信息，请参阅 [System Center Configuration Manager 支持的配置](../LocTest/Supported-configurations-for-System-Center-Configuration-Manager.md)  
  
## 客户端部署  
 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 引入了用于测试新版 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端的新功能。  这项新功能使你有机会设置能在其中试验新客户端的预生产集合。 你对预生产中的新客户端软件感到满意后，可以将客户端提升为使用新版本自动升级站点的其余部分。  
  
 有关如何测试客户端的详细信息，请参阅 [How to test client upgrades in a preproduction collection in System Center Configuration Manager](../LocTest/How-to-test-client-upgrades-in-a-preproduction-collection-in-System-Center-Configuration-Manager.md)。  
  
## 操作系统部署  
  
-   “创建任务序列向导”中提供了新的任务序列类型  **“从升级包中升级操作系统”**，其创建了将计算机从 Windows 7、Windows 8 或 Windows 8.1 升级到 Windows 10 的步骤。  有关详细信息，请参阅 [Upgrade Windows to the latest version with System Center Configuration Manager](../LocTest/Upgrade-Windows-to-the-latest-version-with-System-Center-Configuration-Manager.md)。  
  
-   当部署操作系统时，Windows PE 对等缓存则变为可用。 运行部署操作系统的任务序列的计算机可使用 Windows PE 对等缓存从本地对等计算机（对等缓存源）中获取内容，而无需从分发点下载内容。 这有助于最大限度减小没有本地分发点的分支机构场景中的广域网 (WAN) 流量。 有关详细信息，请参阅 [Prepare Windows PE peer cache to reduce WAN traffic in System Center Configuration Manager](../LocTest/Prepare-Windows-PE-peer-cache-to-reduce-WAN-traffic-in-System-Center-Configuration-Manager.md)。  
  
-   现在可以将 Windows 作为环境中的服务查看其状态、创建维护服务计划以形成部署环并确保 Windows 10 当前分支计算机在新的内部版本发布时保持最新状态，以及在 Windows 10 客户端接近其当前分支 (CB) 或当前业务分支 (CBB) 内部版本的支持期结尾时查看警报。 有关详细信息，请参阅 [Manage Windows as a service using System Center Configuration Manager](../LocTest/Manage-Windows-as-a-service-using-System-Center-Configuration-Manager.md)。  
  
## 应用程序管理  
  
-   [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 允许你部署运行 Windows 10 及更高版本的设备的通用 Windows 平台 (UWP) 应用。 请参阅[使用 System Center Configuration Manager 创建 Windows 应用程序](../LocTest/Creating-Windows-applications-with-System-Center-Configuration-Manager.md)。  
  
-   软件中心具有富有现代感的全新外观，并且此前仅出现在应用程序目录中的应用（用户可用的应用）现在将出现在“应用程序”选项卡下的软件中心中。 由此，用户便可以更容易地发现这些部署，并且无需再使用应用程序目录了。 此外，不再需要启用了 Silverlight 的浏览器了。 请参阅[规划和配置 System Center Configuration Manager 中的应用程序管理](../LocTest/Plan-for-and-configure-application-management-in-System-Center-Configuration-Manager.md)。  
  
-   通过 MDM 的新 Windows Installer 安装程序类型让你可以创建基于 Windows Installer 的应用并将其部署到运行 Windows 10 的已注册 PC 上。 请参阅[使用 System Center Configuration Manager 创建 Windows 应用程序](../LocTest/Creating-Windows-applications-with-System-Center-Configuration-Manager.md)。  
  
-   当为内部的 iOS 应用创建应用程序时，你只需要为该应用指定安装程序 (.ipa) 文件。 不再需要指定相应的属性列表 (.plist) 文件。 请参阅[使用 System Center Configuration Manager 创建 iOS 应用程序](../LocTest/Creating-iOS-applications-with-System-Center-Configuration-Manager.md)。  
  
-   在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 2012 中，若要在 Windows 商店中指定应用的链接，你可以直接指定该链接，或者浏览到安装有该应用的远程计算机。 在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]中，你仍然可以直接输入链接，但是现在你可以直接从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台浏览商店查找应用，而无需浏览到引用计算机。  
  
## 软件更新  
  
-   [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 现在能够区分出连接到用于软件更新管理的 Windows Update for Business (WUfB) 的 Windows 10 计算机和连接到用于软件更新管理的 WSUS 的计算机。 **UseWUServer** 属性为新属性，它指定了计算机是否由 WUfB 管理。 你可以在集合中使用此设置从软件更新管理中删除这些计算机。 有关详细信息，请参阅 [Integration with Windows Update for Business in Windows 10](../LocTest/Integration-with-Windows-Update-for-Business-in-Windows-10.md)。  
  
-   你现在可以从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台计划和运行 WSUS 清理任务。  
    你现在可以从软件更新点组件属性中手动运行 WSUS 清理任务。 当你选择运行 WSUS 清理任务时，它将在下一次软件更新同步时运行。 过期的软件更新将设置为在 WSUS 服务器上被拒绝的状态，计算机上的 Windows 更新代理将不再扫描这些软件更新。 有关详细信息，请参阅 [Schedule and run the WSUS clean up task](../LocTest/Manage-software-updates-in-System-Center-Configuration-Manager.md#BKMK_WSUSCleanUp)。  
  
## 符合性设置  
  
-   [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 引入了用于创建配置项目的改进的工作流。 现在，当创建配置项目并选择受支持的平台时，只有与该平台相关的设置才可用。 请参阅[System Center Configuration Manager 中的符合性设置入门](../LocTest/Get-started-with-compliance-settings-in-System-Center-Configuration-Manager.md)。  
  
-   创建配置项目向导现在可以更轻松地选择你想要创建的配置项目类型。 此外，新的和更新的配置项目可用于：  
  
    -   使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端管理的 Windows 10 设备  
  
    -   使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端管理的 Mac OS X 设备  
  
    -   使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端管理的 Windows 台式和服务器计算机  
  
    -   不使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端管理的 Windows 8.1 和 Windows 10 设备  
  
    -   不使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端管理的 Windows Phone 设备  
  
    -   不使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端管理的 iOS 和 Mac OS X 设备  
  
    -   不使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端管理的 Android 和 Samsung KNOX 设备  
  
     请参阅[如何在 System Center Configuration Manager 中创建配置项目](../LocTest/How-to-create-configuration-items-in-System-Center-Configuration-Manager.md)。  
  
-   支持使用 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 注册或使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端管理的 Mac OS X 计算机上的管理设置。 请参阅[如何为没有使用 System Center Configuration Manager 客户端管理的 iOS 和 Mac OS X 设备创建配置项目](../LocTest/How-to-create-configuration-items-for-iOS-and-Mac-OS-X-devices-managed-without-the-System-Center-Configuration-Manager-client.md)。  
  
## 保护数据和站点基础结构  
-   [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 允许集成 Windows Hello 企业版（之前是 Microsoft Passport for Work），它是在运行 Windows 10 的设备上使用 Active Directory 或 Azure Active Directory 帐户取代密码、智能卡或虚拟智能卡进行登录的一种替代方法。 请参阅 [System Center Configuration Manager 中的 Windows Hello 企业版设置](../LocTest/Windows-Hello-for-Business-settings-in-System-Center-Configuration-Manager.md)。
  
## 使用 Microsoft Intune 进行移动设备管理  
 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 引入了对移动设备管理体验的改善措施，其中包括：  
  
-   限制用户可以注册的设备数  
  
-   指定公司门户用户在注册或使用应用之前必须接受的条款和条件  
  
-   添加设备注册管理器角色，以帮助管理大量设备  
  
 有关 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 和 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 的移动设备管理功能的详细信息，请参阅[使用 System Center Configuration Manager 和 Microsoft Intune 的混合移动设备管理 (MDM)](../LocTest/Hybrid-mobile-device-management--MDM--with-System-Center-Configuration-Manager-and-Microsoft-Intune.md)。  
  
## 本地移动设备管理  
 凭借 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] ，你现在可以使用本地 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 基础结构管理移动设备。 所有设备管理和管理数据都在本地处理并且不是 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 或其他云设备的一部分。 这种类型的设备管理不需要客户端软件，因为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 用于管理设备的功能是内置于设备操作系统中的。  
  
 要了解详细信息，请参阅 [Manage mobile devices with on-premises infrastructure in System Center Configuration Manager](../LocTest/Manage-mobile-devices-with-on-premises-infrastructure-in-System-Center-Configuration-Manager.md)  
  
## 另请参阅
 [System Center Configuration Manager 简介](../LocTest/Introduction-to-System-Center-Configuration-Manager.md)
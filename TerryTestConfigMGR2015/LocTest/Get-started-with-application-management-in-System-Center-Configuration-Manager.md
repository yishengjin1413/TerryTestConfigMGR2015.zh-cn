---
title: "System Center Configuration Manager 中的应用程序管理入门"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-app
ms.tgt_pltfrm: na
ms.topic: get-started-article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 08f711ba-83bf-4b5f-9520-a0778c6ae7eb
caps.latest.revision: 18
caps.handback.revision: 18
author: barlanmsft
translationtype: Human Translation
---
# System Center Configuration Manager 中的应用程序管理入门
在本主题中，你将学习开始使用 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 应用程序之前需要了解的基础知识。  
  
> [!TIP]  
>  如果你已经熟悉如何在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]中管理应用程序，你可以随时跳过本主题并直接移跳至创建示例应用程序。 请参阅[使用 System Center Configuration Manager 创建和部署应用程序](../LocTest/Create-and-deploy-an-application-with-System-Center-Configuration-Manager.md)。  
  
## 什么是应用程序?  
 尽管“应用程序”在计算中、在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]中广泛使用，但它具有不同的含义。 将应用程序想象为一个框。 这个框包含一套或多套软件包的安装文件（称为“部署类型” ）以及如何部署软件的说明。  
  
 当应用程序部署到设备上时，“要求”  决定在设备上安装哪种部署类型。  
  
 当然，利用应用程序还可以做很多事情，读完本指南即可了解相关知识。 下表介绍了一些概念，你需要在深入学习前进行了解。 所有这些不必出现在你创建的每个应用程序中：  
  
|||  
|-|-|  
|概念|描述|  
|**惠?**|在之前版本的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]中，经常要创建包含你想要向其部署应用程序的设备的集合。 虽然你仍然可以这样做，但要求通过允许指定更详尽的条件（应用程序将按照此条件安装）来减少这种需求。<br /><br /> 例如，可以指定应用程序仅在运行 Windows 10 的计算机上安装。 接下来，你可以将应用程序部署到所有设备，但它只会在运行 Windows 10 的设备上安装。<br /><br /> [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 评估要求以确定是否安装应用程序以及它的任何部署类型。 然后，它会确定用于安装应用程序的正确部署类型。 默认情况下，根据“计划部署的重新评估” 客户端设置，每七天重新评估一次要求规则以确保符合性。<br /><br /> 有关详细信息，请参阅[使用 System Center Configuration Manager 创建和部署应用程序](../LocTest/Create-and-deploy-an-application-with-System-Center-Configuration-Manager.md)。|  
|**全局条件**|尽管要求用于单个应用程序中的特定部署类型，但你还可以创建全局条件，此全局条件是一个预定义要求库，你可以将它用于任何应用程序和部署类型。<br /><br /> [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 包含一套内置的全局条件，你也可以创建你自己的全局条件。<br /><br /> 有关详细信息，请参阅[如何在 System Center Configuration Manager 中创建全局条件](../LocTest/How-to-create-global-conditions-in-System-Center-Configuration-Manager.md)。|  
|**模拟部署**|评估应用程序的要求、检测方法和依赖关系，并在未实际安装应用程序的情况下报告结果。<br /><br /> 有关详细信息，请参阅[如何使用 System Center Configuration Manager 模拟应用程序部署](../LocTest/How-to-simulate-application-deployments-with-System-Center-Configuration-Manager.md)。|  
|**部署操作**|指定是否想要安装或卸载（如果支持）正在部署的应用程序。<br /><br /> 有关详细信息，请参阅[如何使用 System Center Configuration Manager 部署应用程序](../LocTest/How-to-deploy-applications-with-System-Center-Configuration-Manager.md)。|  
|**部署目的**|指定部署应用程序为“必需” 还是“可用” 。<br /><br /> “必需” 意味着依据配置的计划自动部署应用程序。 不过，用户可以跟踪应用程序部署状态（如果未隐藏），并且可使用软件中心在截止时间之前安装该应用程序。<br /><br /> “可用” 意味着如果将应用程序部署到用户，则用户将在软件中心看到发布的应用程序，并可根据需要进行请求。<br /><br /> 有关详细信息，请参阅[如何使用 System Center Configuration Manager 部署应用程序](../LocTest/How-to-deploy-applications-with-System-Center-Configuration-Manager.md)。|  
|**修订版本**|修订应用程序或应用程序中包含的部署类型时， [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 会创建应用程序的新版本。 你也可以显示每个应用程序的版本历史记录、查看其属性、还原应用程序的以前版本或删除旧版本。<br /><br /> 有关详细信息，请参阅[使用 System Center Configuration Manager 更新和停用应用程序](../LocTest/Update-and-retire-applications-with-System-Center-Configuration-Manager.md)。|  
|**检测方法**|检测方法用于发现是否已安装部署的应用程序。 如果检测方法指示已安装应用程序，则 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不会尝试重新安装。<br /><br /> 有关详细信息，请参阅[如何使用 System Center Configuration Manager 创建应用程序](../LocTest/How-to-create-applications-with-System-Center-Configuration-Manager.md)。|  
|**依赖关系**|依赖关系定义在安装部署类型之前必须先安装的另一应用程序中的部署类型。 你可以将相关部署类型配置为在安装部署类型之前自动安装。<br /><br /> 有关详细信息，请参阅[如何使用 System Center Configuration Manager 创建应用程序](../LocTest/How-to-create-applications-with-System-Center-Configuration-Manager.md)。|  
|**取代**|[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 让你可通过使用取代关系来升级或替换现有应用程序。 在取代应用程序时，你可以指定新部署类型来替换被取代应用程序的部署类型，还可配置是否在安装取代应用程序之前升级或卸载被取代应用程序。<br /><br /> 有关详细信息，请参阅[如何使用 System Center Configuration Manager 创建应用程序](../LocTest/How-to-create-applications-with-System-Center-Configuration-Manager.md)。|  
|**以用户为中心的管理**|[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 应用程序支持以用户为中心的管理，从而使你可以将特定用户与特定设备关联。 你可以将应用部署到用户和设备，而不必记住用户设备的名称。 此功能可帮助你确保在特定用户访问的每台设备上始终可以使用最重要的应用。 如果用户购买了新计算机，则在登录之前可在设备上自动安装用户的应用。<br /><br /> 有关详细信息，请参阅[在 System Center Configuration Manager 中将用户和设备与用户设备相关性相链接](../LocTest/Link-users-and-devices-with-user-device-affinity-in-System-Center-Configuration-Manager.md)。|  
  
## 可以部署哪些应用程序类型?  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 支持部署以下软件的类型：  
  
|类型|要求设备向 Intune 注册|  
|----------|------------------------------------------------|  
|Windows Installer（*.msi 文件）|否|  
|Windows 应用包（*.appx、\*.appxbundle）|否|  
|Windows 应用包（在 Windows 应用商店中）|否|  
|Microsoft Application Virtualization 4|否|  
|Microsoft Application Virtualization  5|否|  
|Windows Phone 应用包（*.xap 文件）|是|  
|Windows Phone 应用包（在 Windows Phone 应用商店中）|是|  
|Windows Mobile Cabinet|否|  
|iOS 应用包（*.ipa 文件）|是|  
|Android 应用包（*.apk 文件）|是|  
|“Google Play 上的 Android 应用包”|是|  
|Mac OS X|否|  
|Web 应用程序|只有在部署到 iOS、Android、Windows Phone 和注册的 Windows PC 时|  
|通过 MDM 的 Windows 安装程序|是|  
  
## 基于状态的应用程序  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的应用程序支持基于状态的监视，此功能可让你跟踪用户和设备的上次应用程序部署状态。 这些状态消息显示了有关单个设备的信息。 例如，将应用程序部署到用户集合，那么，你可以在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中查看此部署的符合性状态和部署目的。 可以通过使用 **控制台中的“监视”工作区来监视所有软件的部署**[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 。 软件部署包括软件更新、符合性设置、应用程序、任务序列以及包和程序。 有关详细信息，请参阅[使用 System Center Configuration Manager 监视应用程序](../LocTest/Monitor-applications-with-System-Center-Configuration-Manager.md)。  
  
 应用程序部署由 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]定期重新计算。 例如：  
  
-   最终用户卸载了部署的应用程序。 在下一个评估周期， [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将检测到应用程序不存在并重新安装它。  
  
-   应用程序由于未满足要求而未安装在设备上。 随后将对设备进行更改，现在它即满足要求。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 检测到此更改并安装应用程序。  
  
 可以通过使用“部署的计划重新评估”  客户端设置配置应用程序部署的重新评估时间间隔。 有关详细信息，请参阅[关于 System Center Configuration Manager 中的客户端设置](../LocTest/About-client-settings-in-System-Center-Configuration-Manager.md)。  
  
## 创建应用程序入门  
 如果你想要直接开始创建应用程序，你将在[使用 System Center Configuration Manager 创建和部署应用程序](../LocTest/Create-and-deploy-an-application-with-System-Center-Configuration-Manager.md)主题中找到创建简单的应用程序的演练。  
  
 如果你已熟悉基本知识，想查看所有可用选项有关的更多详细参考信息，可从 [System Center Configuration Manager 应用程序管理技术参考](../LocTest/Application-management-technical-reference-for-System-Center-Configuration-Manager.md)开始。  
  
## 软件中心和应用程序目录  
 在以前版本的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]中，软件中心用于安装和计划软件安装、配置远程控制设置和配置电源管理设置。 用户可以连接到应用程序目录，以便浏览和请求软件、配置某些首选项设置，以及远程擦除其移动设备。  
  
 虽然这些设置在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]中仍然可用，但现已推出软件中心的新版本，它你能够浏览应用程序而无须使用应用程序目录（需要启用了 Silverlight 的 Web 浏览器）。 但是，仍然需要应用程序目录网站点站点系统角色和应用程序目录 Web 服务点站点系统角色，才能在软件中心显示用户可用的应用。  
  
 有关详细信息，请参阅[在 System Center Configuration Manager 中规划和配置应用程序管理](../LocTest/Plan-for-and-configure-application-management-in-System-Center-Configuration-Manager.md)。  
  
## 使用 Configuration Manager 包和程序  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 继续以支持在产品的早期版本中使用的包和程序。 部署以下任何一项时，使用包和程序的部署可能比使用某个应用程序的部署更适用：  
  
-   不在计算机上安装应用程序的脚本，如用于对计算机磁盘驱动器进行碎片整理的脚本  
  
-   不需要持续监视的“一次性”脚本  
  
-   按定期计划运行且不能使用全局评估的脚本  
  
 有关详细信息，请参阅 [System Center Configuration Manager 中的包和程序](../LocTest/Packages-and-programs-in-System-Center-Configuration-Manager.md)。  
  
## 另请参阅  
 [使用 System Center Configuration Manager 部署并管理应用程序](../LocTest/Deploy-and-manage-applications-with-System-Center-Configuration-Manager.md)
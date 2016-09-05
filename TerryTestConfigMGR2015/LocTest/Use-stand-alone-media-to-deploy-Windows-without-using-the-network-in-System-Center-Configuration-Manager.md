---
title: "在 System Center Configuration Manager 中使用独立媒体部署 Windows，而不使用网络"
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
ms.assetid: 58a0d2ae-de76-401f-b854-7a5243949033
caps.latest.revision: 16
caps.handback.revision: 15
---
# 在 System Center Configuration Manager 中使用独立媒体部署 Windows，而不使用网络
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的独立媒体包含在计算机上部署操作系统所需的所有内容。 这包括启动映像、操作系统映像和安装操作系统的任务序列（包括应用程序、驱动程序等）。 独立媒体部署允许在下列情况下部署操作系统：  
  
-   在通过网络复制操作系统映像包或其他大型包并不实际可行的环境中。  
  
-   在无网络连接或具有低带宽网络连接的环境中。  
  
 你可以在以下操作系统部署方案中使用独立媒体：  
  
-   [通过 System Center Configuration Manager，使用新版本的 Windows 刷新现有的计算机](../LocTest/Refresh-an-existing-computer-with-a-new-version-of-Windows-using-System-Center-Configuration-Manager.md)  
  
-   [使用 System Center Configuration Manager 在新计算机（裸机）上安装新版本的 Windows](../LocTest/Install-a-new-version-of-Windows-on-a-new-computer--bare-metal--with-System-Center-Configuration-Manager.md)  
  
-   [使用 System Center Configuration Manager 将 Windows 升级到最新版本](../LocTest/Upgrade-Windows-to-the-latest-version-with-System-Center-Configuration-Manager.md)  
  
 完成其中一个操作系统部署方案中的步骤，然后运行以下部分来准备并创建独立媒体。  
  
## 使用独立媒体时不支持任务序列操作  
 如果你已完成其中一个受支持的操作系统部署方案中的步骤，则会创建要部署或升级操作系统的任务序列并且所有关联的内容都将被分发到分发点。 使用独立媒体时，任务序列中不支持以下操作：  
  
-   任务序列中的“自动应用驱动程序”步骤。 不支持自动应用驱动程序目录的设备驱动程序，但可以选择“应用驱动程序包”步骤以创建一组可用于 Windows 安装程序的指定驱动程序。  
  
-   安装软件更新。  
  
-   在部署操作系统之前安装软件。  
  
-   将用户与目标计算机关联以支持用户设备相关性。  
  
-   通过“安装包”任务安装动态程序包。  
  
-   通过“安装应用程序”任务安装动态应用程序。  
  
> [!NOTE]  
>  如果用于部署操作系统的任务序列包括 [安装包](../LocTest/Task-sequence-steps-in-System-Center-Configuration-Manager.md#BKMK_InstallPackage) 步骤，并且你在管理中心站点创建独立媒体，则可能发生错误。 管理中心站点并没有在执行任务序列期间启用软件分发代理所需的必要客户端配置策略。 在 CreateTsMedia.log 文件中可能会出现以下错误：  
>   
>  `“WMI method SMS_TaskSequencePackage.GetClientConfigPolicies failed (0x80041001)”`  
>   
>  对于包含“安装包”步骤的独立媒体，必须在启用了软件分发代理的主站点上创建独立媒体，或者必须在任务序列中的 [安装 Windows 和 ConfigMgr](../LocTest/Task-sequence-steps-in-System-Center-Configuration-Manager.md#BKMK_SetupWindowsandConfigMgr) 步骤之后和第一个“安装包”步骤之前添加一个 [运行命令行](../LocTest/Task-sequence-steps-in-System-Center-Configuration-Manager.md#BKMK_RunCommandLine) 步骤。 “运行命令行”步骤运行 WMIC 命令，以便在第一个安装包步骤运行之前启用软件分发代理。 可以在“运行命令行”任务序列步骤中使用以下命令：  
>   
>  **命令行：WMIC \/namespace:\\\\root\\ccm\\policy\\machine\\requestedconfig path ccm\_SoftwareDistributionClientConfig CREATE ComponentName\="Enable SWDist", Enabled\="true", LockSettings\="TRUE", PolicySource\="local", PolicyVersion\="1.0", SiteSettingsKey\="1" \/NOINTERACTIVE**  
  
## 配置部署设置  
 当你使用独立媒体来启动操作系统部署过程时，必须配置该部署才能使操作系统对媒体可用。 可以在“部署软件向导”的“部署设置”页面或部署属性的“部署设置”选项卡上配置这一选项。  对于“可用于以下项目”设置，请配置下述内容之一：  
  
-   **Configuration Manager 客户端、媒体和 PXE**  
  
-   **仅媒体和 PXE**  
  
-   **仅媒体和 PXE（隐藏）**  
  
## 创建独立媒体  
 你可以指定独立媒体是 U 盘还是 CD\/DVD 集。 将启动媒体的计算机必须支持选为可启动驱动器的选项。 有关详细信息，请参阅 [使用 System Center Configuration Manager 创建独立媒体](../LocTest/Create-stand-alone-media-with-System-Center-Configuration-Manager.md)。  
  
## 从独立媒体安装操作系统  
 在计算机的可启动驱动器中插入独立媒体，然后再启动它以安装操作系统。  
  
## 请参阅  
 [使用 System Center Configuration Manager 部署企业版操作系统的方法](../LocTest/Methods-to-deploy-enterprise-operating-systems-using-System-Center-Configuration-Manager.md)
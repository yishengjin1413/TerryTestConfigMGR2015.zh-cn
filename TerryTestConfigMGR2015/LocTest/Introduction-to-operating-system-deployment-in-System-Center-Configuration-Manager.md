---
title: "System Center Configuration Manager 中的操作系统部署简介"
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
ms.assetid: d9a1c545-8301-492c-832f-2c108ff93c77
caps.latest.revision: 12
caps.handback.revision: 11
translationtype: Human Translation
---
# System Center Configuration Manager 中的操作系统部署简介
以下部分说明了用于在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 环境中部署操作系统的某些概念。  
  
-   [操作系统部署过程](#BKMK_OSDeploymentProcess)  
  
-   [操作系统部署方案](#BKMK_OSDScenarios)  
  
-   [用于部署操作系统的方法](#BKMK_OSDMethods)  
  
-   [启动映像](#BKMK_BootImages)  
  
-   [操作系统映像](#BKMK_OSImages)  
  
-   [操作系统升级包](#BKMK_OSUpgradePackages)  
  
-   [用于部署操作系统的媒体](#BKMK_OSDMedia)  
  
-   [设备驱动程序](#BKMK_DeviceDrivers)  
  
-   [保存并还原用户状态](#BKMK_OSDUserState)  
  
-   [部署到未知计算机](#BKMK_UnknownComputer)  
  
-   [将用户与计算机关联](#BKMK_UDA)  
  
-   [使用任务序列自动执行步骤](#BKMK_TaskSequences)  
  
##  <a name="BKMK_OSDeploymentProcess"></a> 操作系统部署过程  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 提供了可用于部署操作系统的一些方法。 无论使用哪种部署方法，都必须执行一些操作：  
  
-   标识要开始启动映像或安装操作系统映像（必须部署的）所必需的 Windows 设备驱动程序。  
  
-   确定想要用来启动目标计算机的启动映像。  
  
-   使用任务序列捕获将要部署的操作系统的映像。 或者，你可以使用默认的操作系统映像。  
  
-   将启动映像、操作系统映像包以及任何相关内容分发至分发点。  
  
-   创建任务序列，该序列带有部署启动映像和操作系统映像的步骤。  
  
-   将任务序列部署到计算机集合。  
  
-   监视部署。  
  
##  <a name="BKMK_OSDScenarios"></a> 操作系统部署方案  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中有许多你可以从中选择的操作系统部署方案，具体取决于你的环境和安装操作系统的目的。  例如，你可以使用新版本的 Windows 对现有计算机进行分区和格式化，或将 Windows 升级到最新版本。 为帮助你确定可满足你需要的部署方法，请查看[使用 System Center Configuration Manager 部署企业版操作系统的方案](../LocTest/Scenarios-to-deploy-enterprise-operating-systems-with-System-Center-Configuration-Manager.md)。  你可以从以下操作系统部署方案中进行选择：  
  
-   [使用 System Center Configuration Manager 将 Windows 升级到最新版本](../LocTest/Upgrade-Windows-to-the-latest-version-with-System-Center-Configuration-Manager.md)  
  
-   [通过 System Center Configuration Manager，使用新版本的 Windows 刷新现有的计算机](../LocTest/Refresh-an-existing-computer-with-a-new-version-of-Windows-using-System-Center-Configuration-Manager.md)  
  
-   [使用 System Center Configuration Manager 在新计算机（裸机）上安装新版本的 Windows](../LocTest/Install-a-new-version-of-Windows-on-a-new-computer--bare-metal--with-System-Center-Configuration-Manager.md)  
  
-   [使用 System Center Configuration Manager 替换现有计算机和传输设置](../LocTest/Replace-an-existing-computer-and-transfer-settings-with-System-Center-Configuration-Manager.md)  
  
##  <a name="BKMK_OSDMethods"></a> 用于部署操作系统的方法  
 可以使用一些方法将操作系统部署到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端计算机。  
  
-   **PXE 启动部署**：PXE 启动部署允许客户端计算机通过网络请求部署。 在此部署方法中，操作系统映像包和 Windows PE 启动映像会发送到配置为接受 PXE 启动请求的分发点。 有关详细信息，请参阅[使用 PXE 与 System Center Configuration Manager 一起通过网络部署 Windows](../LocTest/Use-PXE-to-deploy-Windows-over-the-network-with-System-Center-Configuration-Manager.md)。  
  
-   **使操作系统在软件中心中可用**：可以部署操作系统，并使其在软件中心中可用。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端可以从软件中心启动操作系统安装。 有关详细信息，请参阅[使用 System Center Configuration Manager 替换现有计算机和传输设置](../LocTest/Replace-an-existing-computer-and-transfer-settings-with-System-Center-Configuration-Manager.md)。  
  
-   **多播部署**：多播部署通过将数据并行发送到多个客户端，而不是通过单独连接向每个客户端发送数据副本，从而节省网络带宽。 在此部署方法中，操作系统映像包将发送到分发点。 这反过来会在客户端计算机请求部署时部署映像。 有关详细信息，请参阅[使用多播与 System Center Configuration Manager 一起通过网络部署 Windows](../LocTest/Use-multicast-to-deploy-Windows-over-the-network-with-System-Center-Configuration-Manager.md)。  
  
-   **可启动媒体部署**：可启动媒体部署允许在目标计算机启动时部署操作系统。 在目标计算机启动时，它从网络中检索任务序列、操作系统映像包和任何其他必需的内容。 由于媒体上未包括该内容，因此，你无需重新创建媒体就能更新内容。 有关详细信息，请参阅[使用 System Center Configuration Manager 创建可启动媒体](../LocTest/Create-bootable-media-with-System-Center-Configuration-Manager.md)。  
  
-   **独立媒体部署**：独立媒体部署允许在下列情况下部署操作系统：  
  
    -   在通过网络复制操作系统映像包或其他大型包并不实际可行的环境中。  
  
    -   在无网络连接或具有低带宽网络连接的环境中。  
  
     有关详细信息，请参阅[使用 System Center Configuration Manager 创建独立媒体](../LocTest/Create-stand-alone-media-with-System-Center-Configuration-Manager.md)。  
  
-   **预留媒体部署**：预留媒体部署允许将操作系统部署到未完全设置的计算机。 预留媒体是 Windows 映像格式 \(WIM\) 文件，可以由制造商安装在裸机上，也可以安装在未连接到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 环境的企业暂存中心。  
  
     之后在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 环境中，计算机使用媒体提供的启动映像启动，然后连接到站点管理点以执行完成下载过程的可用任务序列。 此部署方法可以减少网络流量，因为启动映像和操作系统映像包已在目标计算机上。 你可以指定要包含在预留媒体中的应用程序、包和驱动程序包。 有关详细信息，请参阅[使用 System Center Configuration Manager 创建预留媒体](../LocTest/Create-prestaged-media-with-System-Center-Configuration-Manager.md)。  
  
##  <a name="BKMK_BootImages"></a> 启动映像  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的一个启动映像是在操作系统部署过程中使用的 Windows PE \(WinPE\) 映像。 启动映像用于在 WinPE 中启动计算机，它是用于准备在目标计算机上安装 Windows 的有限组件和服务的最精简操作系统。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 提供两个启动映像：一个用于支持 x86 平台，另一个用于支持 x64 平台。 这些视为默认启动映像。 你创建并添加到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的启动映像被视为自定义映像。 当你更新 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 时，可自动替换默认启动映像。 有关启动映像的详细信息，请参阅[使用 System Center Configuration Manager 管理启动映像](../LocTest/Manage-boot-images-with-System-Center-Configuration-Manager.md)。  
  
##  <a name="BKMK_OSImages"></a> 操作系统映像  
 Configuration Manager 中的操作系统映像以 Windows 映像 \(WIM\) 文件格式存储，代表在计算机上成功安装和配置操作系统所需的引用文件和文件夹的压缩集合。 对于所有操作系统部署方案，必须选择操作系统映像。 你可以使用默认操作系统映像或从你配置的引用计算机生成操作系统映像。 有关详细信息，请参阅[使用 System Center Configuration Manager 管理操作系统映像](../LocTest/Manage-operating-system-images-with-System-Center-Configuration-Manager.md)。  
  
##  <a name="BKMK_OSUpgradePackages"></a> 操作系统升级包  
 操作系统升级包用于升级操作系统，并且是安装程序启动的操作系统部署。 你从 DVD 或已安装的 ISO 文件将操作系统升级包导入到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]。 有关详细信息，请参阅[使用 System Center Configuration Manager 管理操作系统升级包](../LocTest/Manage-operating-system-upgrade-packages-with-System-Center-Configuration-Manager.md)。  
  
##  <a name="BKMK_OSDMedia"></a> 用于部署操作系统的媒体  
 你可以创建若干种可用于部署操作系统的媒体。 这包括捕获用于捕获操作系统映像的媒体，以及捕获用于部署操作系统的独立、预留和可启动媒体。 通过使用媒体，你可以在没有网络连接或者使用低带宽连接来连接到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点的计算机上部署操作系统。 有关如何使用媒体的详细信息，请参阅[使用 System Center Configuration Manager 创建任务序列媒体](../LocTest/Create-task-sequence-media-with-System-Center-Configuration-Manager.md)。  
  
##  <a name="BKMK_DeviceDrivers"></a> 设备驱动程序  
 你可以在目标计算机上安装设备驱动程序，而不将它们包含在正在部署的操作系统映像中。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 提供一个驱动程序目录，该目录包含对导入 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的所有设备驱动程序的引用。 此驱动程序目录位于“软件库”工作区中并且包含以下两个节点：“驱动程序”和“驱动程序包”。 “驱动程序”节点列出了已导入到驱动程序目录的所有驱动程序。 你可以使用此节点发现关于每个导入的驱动程序的详细信息，更改驱动程序所属的驱动程序包或启动映像，启用或禁用驱动程序，以及执行其他操作。 有关详细信息，请参阅[在 System Center Configuration Manager 中管理驱动程序](../LocTest/Manage-drivers-in-System-Center-Configuration-Manager.md)。  
  
##  <a name="BKMK_OSDUserState"></a> 保存并还原用户状态  
 部署操作系统时，你可以保存目标计算机中的用户状态，部署操作系统，然后在部署操作系统之后还原用户状态。 此过程通常在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端计算机上安装操作系统时使用。  
  
 用户状态信息是使用任务序列捕获和还原的。 捕获用户状态信息后，可以使用下列方法之一存储信息：  
  
-   你可以通过配置状态迁移点以远程存储用户状态数据。 捕获任务序列将数据发送到状态迁移点。 然后，在部署操作系统之后，还原任务序列检索数据并在目标计算机上还原用户状态。  
  
-   你可以以本地方式将用户状态数据存储到特定位置。 在此方案中，捕获任务序列将用户数据复制到目标计算机上的特定位置。 然后，在部署操作系统之后，还原任务序列从该位置检索用户数据。  
  
-   你可以指定可用于将用户数据还原到其原始位置的硬链接。 在此方案中，删除旧操作系统时，用户状态数据会保留在驱动器上。 然后，在部署操作系统之后，还原任务序列使用硬链接将用户状态数据还原到其原始位置。  
  
 有关详细信息，请参阅[在 System Center Configuration Manager 中管理用户状态](../LocTest/Manage-user-state-in-System-Center-Configuration-Manager.md)。  
  
##  <a name="BKMK_UnknownComputer"></a> 部署到未知计算机  
 你可以将操作系统部署到非 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 管理的计算机上。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 数据库中没有这些计算机的记录。 这些计算机称为未知计算机。 未知计算机包括下列各项：  
  
-   未安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端的计算机  
  
-   未导入到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的计算机  
  
-   未由 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 发现的计算机  
  
 有关详细信息，请参阅[在 System Center Configuration Manager 中准备未知计算机部署](../LocTest/Prepare-for-unknown-computer-deployments-in-System-Center-Configuration-Manager.md)。  
  
##  <a name="BKMK_UDA"></a> 将用户与计算机关联  
 部署操作系统时，可以将用户与目标计算机关联，以支持用户设备关联操作。 将用户与目标计算机关联时，管理用户稍后可以对与该用户关联的任何计算机执行操作，如将应用程序部署到特定用户的计算机。 但是，在部署操作系统时，你无法将操作系统部署到特定用户的计算机。 有关详细信息，请参阅[将用户与 System Center Configuration Manager 中的目标计算机关联](../LocTest/Associate-users-with-a-destination-computer-in-System-Center-Configuration-Manager.md)。  
  
##  <a name="BKMK_TaskSequences"></a> 使用任务序列自动执行步骤  
 你可以在你的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 环境中创建任务序列来执行各种任务。 序列的各个步骤中定义了任务序列的操作。 运行任务序列时，系统在命令行级别执行每个步骤的操作，无需用户干预。 可以针对以下情况使用任务序列：  
  
-   [在 System Center Configuration Manager 中创建用于安装操作系统的任务序列](../LocTest/Create-a-task-sequence-to-install-an-operating-system-in-System-Center-Configuration-Manager.md)  
  
-   [使用 System Center Configuration Manager 创建用于非操作系统部署的任务序列](../LocTest/Create-a-task-sequence-for-non-operating-system-deployments-with-System-Center-Configuration-Manager.md)  
  
-   [创建任务序列来捕获 System Center Configuration Manager 中的操作系统](../LocTest/Create-a-task-sequence-to-capture-an-operating-system-in-System-Center-Configuration-Manager.md)  
  
-   [创建任务序列以捕获和还原 System Center Configuration Manager 中的用户状态](../LocTest/Create-a-task-sequence-to-capture-and-restore-user-state-in-System-Center-Configuration-Manager.md)  
  
-   [使用 System Center Configuration Manager 创建自定义任务序列](../LocTest/Create-a-custom-task-sequence-with-System-Center-Configuration-Manager.md)  
  
## 请参阅  
 [使用 System Center Configuration Manager 管理企业操作系统](assetId:///c6b0ff4c-235a-4e4c-99c0-d14d202de478)
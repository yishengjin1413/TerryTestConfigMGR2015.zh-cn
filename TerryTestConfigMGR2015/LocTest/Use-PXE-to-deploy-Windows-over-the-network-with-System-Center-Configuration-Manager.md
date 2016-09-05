---
title: "使用 PXE 与 System Center Configuration Manager 一起通过网络部署 Windows"
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
ms.assetid: da5f8b61-2386-4530-ad54-1a5c51911f07
caps.latest.revision: 19
caps.handback.revision: 16
---
# 使用 PXE 与 System Center Configuration Manager 一起通过网络部署 Windows
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中启动了 PXE 的操作系统部署允许客户端计算机通过网络请求和部署操作系统。 在此操作系统部署方案中，操作系统映像包以及 x86 和 x64 Windows PE 启动映像会发送到配置为接受 PXE 启动请求的分发点。  
  
> [!NOTE]  
>  当创建一个仅针对 x64 BIOS 计算机的操作系统部署时，x64 启动映像和 x86 启动映像都必须在分发点上可用。  
  
 你可以在以下操作系统部署方案中使用启动了 PXE 的操作系统部署：  
  
-   [通过 System Center Configuration Manager，使用新版本的 Windows 刷新现有的计算机](../LocTest/Refresh-an-existing-computer-with-a-new-version-of-Windows-using-System-Center-Configuration-Manager.md)  
  
-   [使用 System Center Configuration Manager 在新计算机（裸机）上安装新版本的 Windows](../LocTest/Install-a-new-version-of-Windows-on-a-new-computer--bare-metal--with-System-Center-Configuration-Manager.md)  
  
 完成其中一个操作系统部署方案中的步骤，然后使用以下部分来准备启动了 PXE 的部署。  
  
##  <a name="BKMK_Configure"></a> 配置至少一个分发点以接受 PXE 请求  
 要将操作系统部署到发出 PXE 启动请求的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端，你必须使用一个或多个配置为响应 PXE 启动请求的分发点。  有关在分发点上启用 PXE 的步骤，请参阅[配置分发点以接受 PXE 请求](../LocTest/Prepare-site-system-roles-for-operating-system-deployments-with-System-Center-Configuration-Manager.md#BKMK_PXEDistributionPoint)。  
  
## 准备 PXE 启用的启动映像  
 若要使用 PXE 来部署操作系统，必须将已启用 PXE 的 x86 和 x64 启动映像分发到一个或多个已启用 PXE 的分发点。 使用信息在启动映像上启用 PXE 并将启动映像分发到分发点：  
  
-   若要在启动映像上启用 PXE，请从启动映像属性中的“数据源”选项卡中，选择“从已启用 PXE 的分发点部署此启动映像”。  
  
-   如果你更改启动映像的属性，请将启动映像重新分发到分发点。 有关详细信息，请参阅 [Distribute content](../LocTest/Manage-content-and-content-infrastructure-for-System-Center-Configuration-Manager.md#bkmk_dist)。  
  
##  <a name="BKMK_PXEExclusionList"></a> 创建 PXE 部署的排除列表  
 当使用 PXE 部署操作系统时，可以在每个分发点上创建排除列表，以忽略排除列表中计算机发出的 PXE 启动请求。 排除列表包含你希望分发点忽略的计算机的 MAC 地址。 这些计算机将不接收 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 用于 PXE 部署的部署任务序列。  
  
 使用以下步骤来创建 PXE 排除列表。  
  
#### 创建排除列表  
  
1.  在针对 PXE 启用的分发点上创建一个文本文件。 例如，将此文本文件命名为 **pxeExceptions.txt**。  
  
2.  使用标准文本编辑器（例如记事本）来添加要由启用 PXE 的分发点忽略的计算机的 MAC 地址。 用冒号分隔 MAC 地址值，每行输入一个地址。 例如：`01:23:45:67:89:ab`  
  
3.  将该文本文件保存在启用 PXE 的分发点站点系统服务器上。 可将该文本文件保存到服务器上的任何位置。  
  
4.  编辑启用 PXE 的分发点的注册表，创建一个 **MACIgnoreListFile** 注册表项，其中包含该文本文件在启用 PXE 的分发点站点系统服务器上的位置的完整路径字符串值。 使用以下注册表路径：  
  
     **HKLM\\Software\\Microsoft\\SMS\\DP**  
  
    > [!WARNING]  
    >  如果不正确地使用注册表编辑器，可能会导致也许需要你重新安装操作系统的严重问题。 Microsoft 不保证能够解决因注册表编辑器使用不当而导致的问题。 使用注册表编辑器的风险由您自己承担。  
  
     进行此注册表更改后，无需重启服务器。  
  
## 配置部署设置  
 若要使用启动了 PXE 的操作系统部署，必须配置该部署以使操作系统对 PXE 启动请求可用。 可以在“部署软件向导”的“部署设置”页面或部署属性的“部署设置”选项卡上配置这一选项。  对于“可用于以下项目”设置，请配置下述内容之一：  
  
-   Configuration Manager 客户端、媒体和 PXE  
  
-   仅媒体和 PXE  
  
-   仅媒体和 PXE（隐藏）  
  
##  <a name="BKMK_Deploy"></a> 部署任务序列  
 将操作系统部署到目标集合。 有关详细信息，请参阅 [部署任务序列](../LocTest/Manage-task-sequences-to-automate-tasks-in-System-Center-Configuration-Manager.md#BKMK_DeployTS)。 当使用 PXE 部署操作系统时，你可以将部署配置为必需或可用。  
  
-   **所需的部署**：所需的部署将使用 PXE，无需任何用户干预。 用户不能绕过 PXE 启动。 但是，如果用户在分发点响应之前取消 PXE 启动，则将不部署操作系统。  
  
-   **可用部署**：可用部署要求用户在目标计算机旁，以便他们能够按 F12 键以继续进行 PXE 启动过程。 如果由于没有用户在场而未按 F12，则计算机将启动到当前操作系统，或者将从下一个可用启动设备启动计算机。  
  
 通过清除分配给 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 集合或计算机的上一个 PXE 部署的状态，你可以重新部署所需的 PXE 部署。 此操作将重置该部署的状态并重新部署最近的所需部署。  
  
> [!IMPORTANT]  
>  PXE 协议不安全。 请确保 PXE 服务器和 PXE 客户端位于物理安全网络上，如在数据中心，以防止未经授权就访问你的站点。  
  
## 请参阅  
 [使用 System Center Configuration Manager 部署企业版操作系统的方法](../LocTest/Methods-to-deploy-enterprise-operating-systems-using-System-Center-Configuration-Manager.md)
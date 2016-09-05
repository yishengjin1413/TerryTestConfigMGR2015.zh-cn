---
title: "System Center Configuration Manager 中的 Endpoint Protection"
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
ms.assetid: 76c90f64-d729-456b-8304-01852cd66fb6
caps.latest.revision: 11
caps.handback.revision: 6
---
# System Center Configuration Manager 中的 Endpoint Protection
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的 Endpoint Protection 让你可以为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 层次结构中的客户端计算机管理反恶意软件策略和 Windows 防火墙安全性。  
  
> [!IMPORTANT]  
>  你必须获得使用 Endpoint Protection 的许可，才能管理 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 层次结构中的客户端。  
  
 将 Endpoint Protection 与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 配合使用时，具有以下优势：  
  
-   为所选的计算机组配置反恶意软件策略和 Windows 防火墙设置  
  
-   使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 软件更新下载最新的反恶意软件定义文件，使客户端计算机保持最新  
  
-   发送电子邮件通知、使用控制台中的监视、查看报表，以在客户端计算机上检测到恶意软件时，通知管理用户  
  
 除 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端外，Endpoint Protection 还会安装其自己的客户端。 Windows Defender 不需要终结点保护管理客户端。 Endpoint Protection 客户端具有以下功能：  
  
-   恶意软件与间谍软件检测和修正  
  
-   Rootkit 检测和修正  
  
-   严重漏洞评估与自动定义和引擎更新  
  
-   通过网络检查系统进行网络漏洞检测  
  
-   与 Microsoft Active Protection Service 集成，以向 Microsoft 报告恶意软件。 加入此服务后，如果在计算机上检测到无法识别的恶意软件，Endpoint Protection 客户端或 Windows Defender 可以从恶意软件保护中心下载最新的定义。  
  
> [!NOTE]  
>  [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端可安装在运行 Hyper\-V 的服务器以及具有受支持操作系统的来宾虚拟机上。 为防止 CPU 使用率过高，[!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 操作配置有内置的随机化延迟，因此保护服务不会同时运行。  
  
 此外，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 让你可以在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中管理 Windows 防火墙设置。  
  
 有关如何配置与管理 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 和 Windows 防火墙的信息，请参阅 [示例方案：使用 System Center Endpoint Protection 来保护计算机在 System Center Configuration Manager 中免受恶意软件侵害](../Topic/Example%20scenario:%20Using%20System%20Center%20Endpoint%20Protection%20to%20protect%20computers%20from%20malware%20in%20System%20Center%20Configuration%20Manager.md)。  
  
## 使用 Endpoint Protection 管理恶意软件  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的 Endpoint Protection 允许你创建包含 Endpoint Protection 客户端配置设置的反恶意软件策略。 然后可以将这些反恶意软件策略部署到客户端计算机，并在“监视”工作区的“[!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 状态”节点中，或通过使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 报表进行监视。  
  
 其他信息：  
  
-   [如何在 System Center Configuration Manager 中为 Endpoint Protection 创建和部署反恶意软件策略](../LocTest/How-to-create-and-deploy-antimalware-policies-for-Endpoint-Protection-in-System-Center-Configuration-Manager.md) \- 使用可以配置的一系列设置创建、部署和监视恶意软件策略  
  
-   [如何在 System Center Configuration Manager 中监视 Endpoint Protection](../LocTest/How-to-monitor-Endpoint-Protection-in-System-Center-Configuration-Manager.md) \- 监视活动报表、受感染的客户端计算机等等。  
  
-   [如何在 System Center Configuration Manager 中为 Endpoint Protection 管理反恶意软件策略和防火墙设置](../LocTest/How-to-manage-antimalware-policies-and-firewall-settings-for-Endpoint-Protection-in-System-Center-Configuration-Manager.md) \- 修正客户端计算机中发现的恶意软件  
  
## 使用 Endpoint Protection 管理 Windows 防火墙  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的 Endpoint Protection 提供对客户端计算机上的 Windows 防火墙的基本管理。 对于每个网络配置文件，可以配置以下设置：  
  
-   启用或禁用 Windows 防火墙。  
  
-   阻止传入连接，包括位于允许程序列表中的程序。  
  
-   Windows 防火墙阻止新程序时通知用户。  
  
> [!NOTE]  
>  Endpoint Protection 仅支持管理 Windows 防火墙。  
  
 有关如何为 Endpoint Protection 创建和部署 Windows 防火墙策略的详细信息，请参阅 [如何在 System Center Configuration Manager 中为 Endpoint Protection 创建和部署 Windows 防火墙策略](../LocTest/How-to-create-and-deploy-Windows-Firewall-policies-for-Endpoint-Protection-in-System-Center-Configuration-Manager.md)。  
  
## Endpoint Protection 工作流  
 使用下面的图表来帮助你了解将在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 层次结构中实现 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 的工作流。  
  
 ![Endpoint Protection Workflow](../LocTest/media/Endpoint-Protection-Workflow.gif "Endpoint)  
  
## 适用于 Mac 计算机和 Linux 服务器的 Endpoint Protection 客户端  
 System Center 2012 包括适用于 Linux 和 Mac 计算机的 Endpoint Protection 客户端。 这些客户端不提供 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]；相反，你必须从 [Microsoft 批量许可服务中心](https://www.microsoft.com/licensing/servicecenter/default.aspx)下载以下产品。  
  
-   适用于 Mac 的 System Center 2012 Endpoint Protection  
  
-   适用于 Linux 的 System Center 2012 Endpoint Protection  
  
> [!IMPORTANT]  
>  你必须是 Microsoft 批量许可客户才能下载适用于 Linux 和 Mac 的 Endpoint Protection 安装文件。  
  
 不能从 Configuration Manager 控制台对这些产品进行管理。 然而，安装文件将提供 System Center Operations Manager 管理包，这让你可以通过使用 Operations Manager 来管理客户端。  
  
 有关如何安装和管理适用于 Linux 和 Mac 计算机的 Endpoint Protection 客户端，请使用这些产品随附的文档，该文档位于“文档”文件夹。
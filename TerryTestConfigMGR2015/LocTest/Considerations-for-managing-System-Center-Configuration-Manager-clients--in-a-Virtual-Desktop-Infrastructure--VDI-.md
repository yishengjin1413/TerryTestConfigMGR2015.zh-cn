---
title: "关于在虚拟桌面基础结构 (VDI) 中管理 System Center Configuration Manager 客户端的注意事项"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-client
ms.tgt_pltfrm: na
ms.topic: get-started-article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: abd45393-d84e-4583-bc80-74bbb3709577
caps.latest.revision: 7
caps.handback.revision: 6
---
# 关于在虚拟桌面基础结构 (VDI) 中管理 System Center Configuration Manager 客户端的注意事项
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 支持在以下虚拟桌面基础结构 \(VDI\) 方案中安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端：  
  
-   **个人虚拟机** – 当你想要确保在会话之间在虚拟机上维护用户数据和设置时，通常使用个人虚拟机。  
  
-   **远程桌面服务会话** – 远程桌面服务使服务器能够承载多个并发客户端会话。 用户可以连接到会话，然后在该服务器上运行应用程序。  
  
-   **共用的虚拟机** – 在会话之间不保留共用的虚拟机。 当关闭会话时，将丢弃所有数据和设置。 当无法使用远程桌面服务时（因为所需的业务应用程序无法在承载客户端会话的 Windows Server 上运行），共用的虚拟机很有用。  
  
 下表列出了关于在虚拟桌面基础结构中管理 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端的考虑事项：  
  
|虚拟机类型|注意事项|  
|-----------|----------|  
|个人虚拟机|[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将个人虚拟机同等地视为物理计算机。 可以在虚拟机映像上预先安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端，或者在设置虚拟机之后部署该客户端。|  
|远程桌面服务|没有为单个远程桌面会话安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端。 而是在远程桌面服务服务器上仅一次性地安装客户端。 在远程桌面服务服务器上可以使用所有 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 功能。|  
|共用的虚拟机|解除授权共用的虚拟机后，你使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 所做的任何更改都会丢失。<br /><br /> [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 功能（如硬件清单、软件清单和软件计数）返回的数据可能与你的需求无关，因为虚拟机可能仅运行很短一段时间。 请考虑从清单任务中排除共用的虚拟机。|  
  
 因为虚拟化支持在相同物理计算机上运行多个 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端，所以对于计划操作（如硬件和软件清点、反恶意软件扫描、软件安装和软件更新扫描），许多客户端操作具有内置的随机化延迟。 对于具有运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端的多个虚拟机的计算机，此延迟有助于分发 CPU 处理以及数据传输。  
  
> [!NOTE]  
>  除了处于维护模式的 Windows Embedded 客户端之外，未在虚拟化环境中运行的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端也使用此随机化延迟。 如果你具有许多部署的客户端，则此行为有助于避免网络带宽高峰，并且可以在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点系统（如管理点和站点服务器）上减少 CPU 处理要求。 延迟间隔因 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 功能而异。  
>   
>  默认情况下，使用以下客户端设置为所需软件更新和所需应用程序部署禁用了随机延迟：“计算机代理”：“禁用截止时间随机性”
---
title: "对 System Center Configuration Manager 的虚拟化环境的支持"
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
ms.assetid: 1098e8c5-9676-4c2b-841b-ec88bd04e495
caps.latest.revision: 6
caps.handback.revision: 5
---
# 对 System Center Configuration Manager 的虚拟化环境的支持
[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 支持在受支持的操作系统上安装客户端和站点系统角色，该操作系统在以下虚拟化环境中作为虚拟机运行。 甚至当虚拟机主机（虚拟化环境）不被支持作为客户端或站点服务器时，这种支持仍然存在。  
  
 **例如**，如果你使用 Microsoft Hyper\-V Server 2012 托管运行 Windows Server 2012 的虚拟机，则你可以在虚拟机 \(Windows Server 2012\) 上安装客户端或站点系统角色，但不是在主机 \(Microsoft Hyper\-V Server 2012\) 上。  
  
|虚拟化环境|  
|-----------|  
|Windows Server 2008 R2|  
|Microsoft Hyper\-V Server 2008 R2|  
|Windows Server 2012|  
|Microsoft Hyper\-V Server 2012|  
|Windows Server 2012 R2|  
  
 你使用的每台虚拟计算机必须满足或超过你将用于物理 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 计算机的相同硬件和软件配置。  
  
 通过使用服务器虚拟化验证计划和其在线的虚拟化计划支持策略向导，你可以验证你的虚拟化环境是否支持 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]。 有关服务器虚拟化验证计划的详细信息，请参阅 [Windows Server 虚拟化验证计划](http://go.microsoft.com/fwlink/p/?LinkId=134672)。  
  
> [!NOTE]  
>  [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不支持在 Mac 上运行的虚拟 PC 或虚拟服务器来宾操作系统。  
  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 无法管理虚拟机，除非虚拟机处于联机状态。 不能更新脱机虚拟机映像，也不能使用主计算机上的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端收集清单。  
  
 未提供虚拟机的特别注意事项。 例如，如果停止并重新启动了虚拟机，但是没有保存应用更新的虚拟机状态，则 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 可能无法确定是否需要将更新重新应用到虚拟机映像。  
  
##  <a name="bkmk_Azure"></a> Microsoft Azure 虚拟机  
 支持在 Microsoft Azure 虚拟机中运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]，正如在物理公司网络中运行内部部署一样。 你可以在以下方案中将 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 与 Microsoft Azure 虚拟机配合使用：  
  
-   **方案 1：**你可以在 Microsoft Azure 虚拟机中运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]，并使用它管理安装在其他 Microsoft Azure 虚拟机上的客户端。  
  
-   **方案 2：**你可以在 Microsoft Azure 虚拟机中运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]，并使用它管理未在 Microsoft Azure 中运行的客户端。  
  
-   **方案 3：**你可以在 Microsoft Azure 虚拟机中运行不同的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点系统角色，同时在物理公司网络（具有用于通信的相应网络连接）中运行其他角色。  
  
 如果网络 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 要求以及支持的配置和硬件要求适用于在你的物理公司网络中安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 内部部署，则这些要求也适用于在 Microsoft Azure 中进行安装。  
  
> [!IMPORTANT]  
>  [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点和在 Azure 虚拟机中运行的客户端与安装内部部署遵循相同的许可证要求。  
  
## 请参阅  
 [System Center Configuration Manager 支持的配置](../LocTest/Supported-configurations-for-System-Center-Configuration-Manager.md)
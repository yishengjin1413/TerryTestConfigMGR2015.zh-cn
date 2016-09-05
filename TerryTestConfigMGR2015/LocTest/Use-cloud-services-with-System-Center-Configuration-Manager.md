---
title: "将云服务用于 System Center Configuration Manager"
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
ms.assetid: 24fca61e-9cdb-447a-ad7a-f4d2e4fd6704
caps.latest.revision: 10
caps.handback.revision: 9
---
# 将云服务用于 System Center Configuration Manager
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 支持多个基于云的选项，这些选项补充你的本地基础结构，还有助于解决以下业务问题，如：  
  
-   管理 BYOD（通过将 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 用于移动设备管理）\)  
  
-   向公司防火墙之外的 Intranet 上的独立客户端或资源提供内容资源（通过使用基于云的分发点）\)  
  
-   当物理硬件不可用或以逻辑方式放置以支持你的需求时，扩大基础结构（通过使用 Microsoft Azure 虚拟机）\)  
  
 尽管不一定必须在部署 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]之前预配云资源，但是它对于在层次结构设计规划进展太快之前理解这些选项十分有益。 使用云资源可让你在解决业务问题时节省金钱和时间，而这一点是本地基础结构不能做到的。  
  
## 可与 Configuration Manager 一起使用的基于云的资源  
 由于每个选项具有不同的要求，更深入地调查每个选项可了解唯一的先决条件、限制和根据使用情况产生额外成本的可能性。  
  
-   有关基于云的分发点的信息，请参阅  
  
-   有关 Windows Azure 的详细信息，请参阅 MSDN 库中的 [Windows Azure](http://go.microsoft.com/fwlink/p/?LinkId=262965) 。  
  
### Microsoft Azure 虚拟机<br />\(用于基于云的基础结构\)  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 支持使用在 Azure 虚拟机中运行的计算机，正如在你的物理公司网络中进行本地运行一样。 你可在以下方案中使用 Azure 虚拟机：  
  
-   **方案 1：** 你可以在虚拟机中运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] ，并使用它管理其他虚拟机上安装的客户端。  
  
-   **方案 2：** 你可以在虚拟机中运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] ，并使用它管理未在 Azure 中运行的客户端。  
  
-   **方案 3：** 你可以在虚拟机中运行不同的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点系统角色，同时在物理公司网络（具有用于通信的相应网络连接）中运行其他角色。  
  
 如果网络、操作系统和硬件要求适用于在你的物理公司网络中安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] ，则相同的这些要求也适用于在 Microsoft Azure 中安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 。  
  
 使用 Azure 虚拟机要求你拥有 Azure 订阅，且费用是根据你使用的虚拟机的数量及其配置，以及基于云的资源的使用而产生的。  
  
 此外，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点和在 Azure 虚拟机中运行的客户端与本地安装遵循相同的许可证要求  
  
### Microsoft Azure 服务（用于基于云的分发点）\)  
 你可以使用 Azure 服务托管 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 分发点，它名为调用的基于云的分发点。  你可以[将基于云的分发点与 System Center Configuration Manager](../LocTest/Use-a-cloud-based-distribution-point-with-System-Center-Configuration-Manager.md)，连同本地分发点和 Azure 虚拟机中部署的分发点一起使用。  
  
 这与使用在其上部署了站点系统角色的 Azure 虚拟机不同。 基于云的分发点：  
  
-   在 Microsoft Azure 中作为一项服务运行，而不是在虚拟机上运行  
  
-   自动扩展以适应客户端的内容请求增加  
  
-   支持 Internet 和 intranet 上的客户端  
  
 使用 Azure 托管分发点要求具有 Azure 订阅，且费用是根据与服务之间传输的数据量产生的。  
  
### Microsoft Intune <br />\(用于移动设备管理\)  
 你可以将 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 订阅与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 集成，以实现通过使用 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 服务对设备进行管理。 此集成：  
  
-   称为混合配置，并扩展 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]（或 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)]，具体取决于你的观点），以支持多种设备。  
  
-   需要 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 连接器站点系统角色。  
  
-   要求你有一个单独的 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 订阅，并且对于将使用 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)]  
  
 尽管 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 使用 Microsoft Azure，但它不要求你单独配置 Azure，也不会产生 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 订阅成本以外的其他成本。  
  
### 附加 Configuration Manager 管理功能  
 某些 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 功能可以连接到基于云的服务，如：  
  
-   Windows Server 更新服务 (WSUS)\)  
  
-   [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 服务云可下载更新 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]  
  
 这些附加功能不需要你具有 Azure 订阅，也不需要在云中配置特定连接、证书或服务。 相反，它们由 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 为你自动管理。  你需要做的就是确保可应用的站点系统和设备能够访问基于 Internet 的 URL。  
  
##  <a name="BKMK_CloudSec"></a> 基于云的服务的安全性  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 使用证书来预配和访问 Microsoft Azure 中的内容，并管理你使用的服务。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 加密你存储在 Azure 中的数据，但除引入 Azure 提供的那些安全或数据控制之外，不会引入的其他安全或数据控制。  
  
 有关详细信息，请参阅关于不同的基于云的资源方案的详细信息。 你还可以查看 Microsoft Azure 安全性的以下主题：  
  
-   [Microsoft Azure：了解 Microsoft Azure 中的安全帐户管理](http://go.microsoft.com/fwlink/p/?LinkId=262968)  
  
-   [Windows Azure Security Overview（Windows Azure 安全性概述）](http://go.microsoft.com/fwlink/p/?LinkId=262970)  
  
-   [Get Past the Security Crossroads in Your Cloud Migration（在云迁移中通过安全性十字路口）](http://go.microsoft.com/fwlink/p/?LinkId=262971)  
  
-   [Azure 中的数据安全性，第 1 部分（共 2 部分）](http://go.microsoft.com/fwlink/p/?LinkId=262974)  
  
## 另请参阅  
 [为 System Center Configuration Manager 准备网络环境](../LocTest/Prepare-your-network-environment-for-System-Center-Configuration-Manager.md)
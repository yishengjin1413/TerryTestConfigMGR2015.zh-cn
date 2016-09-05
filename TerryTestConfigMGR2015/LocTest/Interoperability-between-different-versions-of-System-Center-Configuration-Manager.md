---
title: "System Center Configuration Manager 不同版本之间的互操作性"
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
ms.assetid: 9b0a7859-747f-4495-a2f4-13fd5991f897
caps.latest.revision: 8
caps.handback.revision: 7
---
# System Center Configuration Manager 不同版本之间的互操作性
支持在同一网络上安装和运行多个独立的 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 层次结构。 但是，由于不同的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 层次结构不会在迁移外部交互操作，因此每个层次结构都需要配置以防止相互之间冲突。 此外，你可以进行某些配置来帮助你所管理的资源与正确层次结构中的站点系统交互。  
  
 下列部分提供有关在同一网络上使用不同版本的 Configuration Manager 的信息：  
  
-   [System Center Configuration Manager 和 早期版本之间的互操作性](#BKMK_SupConfigInterop)  
  
-   [Configuration Manager 控制台的互操作性](#BKMK_ConsoleInterop)  
  
-   [混合版本层次结构中的 Configuration Manager 限制](#bkmk_mixed)  
  
##  <a name="BKMK_SupConfigInterop"></a> System Center Configuration Manager 和 早期版本之间的互操作性  
 除非处于从 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 向 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 升级的过程中，或者从 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 的某个版本向更新的版本升级的过程中（使用控制台中更新），不同版本的站点无法在同一层次结构中共存。  
  
 因为你可以将一个 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 站点和层次结构与现有的 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 站点或层次结构并排部署，所以请计划阻止任一版本的客户端尝试加入另一个版本中的站点。 例如，如果两个或更多 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 层次结构具有包含相同网络位置的重叠边界（见[有关重叠边界](../LocTest/Define-site-boundaries-and-boundary-groups-for-System-Center-Configuration-Manager.md#BKMK_BoundaryOverlap)），则最好将每个新客户端分配给特定站点，而不是使用自动站点分配。 有关 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 中自动站点分配的信息，请参阅[如何在 System Center Configuration Manager 中将客户端分配到一个站点](../LocTest/How-to-assign-clients-to-a-site-in-System-Center-Configuration-Manager.md)。  
  
 此外，不支持在承载 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 中的站点系统角色的计算机上安装 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]中的客户端，也不支持在承载 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的站点系统角色的计算机上安装 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)]客户端。  
  
 类似地，以下客户端和虚拟专用网 \(VPN\) 连接不受支持：  
  
-   任何 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 或更早的计算机客户端版本  
  
-   任何 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 或更早版本的设备管理客户端  
  
-   Windows CE Platform Builder 设备管理客户端（任意版本\)  
  
-   System Center Mobile Device Manager VPN 连接  
  
###  <a name="BKMK_SupConfigSiteAssignment"></a> 客户端站点分配注意事项  
 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 客户端只能分配到一个主站点。 当在客户端安装期间使用自动站点分配将客户端分配到站点，多个边界组包括相同的边界，并且边界组有不同的已分配站点时，将无法预测客户端的实际站点分配。  
  
 如果多个 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点和层次结构之间的边界重叠，则可能不会将客户端分配到你所期望的站点，或者根本不能分配到站点。  
  
 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 客户端将在完成站点分配之前检查 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点的版本，如果边界重叠，则无法分配到早期版本。 但是， [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 客户端可能会错误地分配到 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 站点。  
  
 为了防止在两个层次结构有重叠的边界时将客户端意外地分配到错误的站点，请配置 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端安装参数以将客户端分配到特定站点。  
  
##  <a name="bkmk_mixed"></a> 混合版本层次结构中的 Configuration Manager 限制  
 当你处于升级 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 站点的过程中，有时不同的站点会位于不同的版本中。  例如，可能会将管理中心站点升级到新版本，但由于站点维护窗口，需要一段时间以后才能升级一个或多个主站点。  
  
 当单一层次结构中的不同站点使用不同版本时，某些功能不可用。 这可能会影响你在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中管理 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 对象的方式，并影响客户端可用的功能。 通常，无法在站点上或通过运行较低 Service Pack 版本的客户端访问 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的较新版本中的功能。  
  
### 升级 Configuration Manager 的限制  
  
|对象|详细信息|  
|------------|-------------|  
|网络访问帐户|**在从 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 升级到 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 时：**当你使用连接到已更新到 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 的管理中心站点的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台以查看网络访问帐户详细信息时，控制台不显示在运行 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 的主站点进行配置的帐户的详细信息。 主站点升级到与管理中心站点相同的版本后，将可在控制台中看到帐户详细信息。<br /><br /> **在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 版本之间进行升级时：**当你使用连接到已更新到新版本 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 的管理中心站点的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台以查看网络访问帐户详细信息时，控制台不显示在运行旧版本的主站点进行配置的帐户的详细信息。 主站点升级到与管理中心站点相同的版本后，将可在控制台中看到帐户详细信息。|  
|操作系统部署的启动映像|**当从 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 升级到 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 时：**当层次结构的顶层站点升级到 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 时，默认启动映像自动更新到基于 Windows ADK 10 的启动映像。 仅为针对 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 站点上的客户端的部署使用这些启动映像。 有关详细信息，请参阅[在 System Center Configuration Manager 中规划操作系统部署互操作性](../LocTest/Planning-for-operating-system-deployment-interoperability-in-System-Center-Configuration-Manager.md)。<br /><br /> **当在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 版本之间升级时：**只要新版本的 cm6long 未更新正在使用的 Windows ADK 版本，则不会对启动映像造成影响。|  
|新建任务序列步骤|当创建包含 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的某个版本中引入的任何任务序列步骤的任务序列时，你可能会遇到下列问题：<br /><br /> \-\-   当尝试从运行以前版本的 Configuration Manager 站点编辑任务序列时，就会出错。<br /><br /> \-\- 在运行早期版本 Configuration Manager 客户端的计算机上将不运行任务序列。|  
|客户端到下层管理点的通信|对于与某个站点中的管理点通信的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端，如果该站点运行的版本比客户端低，则该客户端只能使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的下层版本所支持的功能。 例如，如果你将内容从最新更新的 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 站点部署到与管理点通信的客户端，而该客户端尚未升级到该版本，则该客户端无法使用最新版本的新功能。|  
  
##  <a name="BKMK_ConsoleInterop"></a> Configuration Manager 控制台的互操作性  
 下表包含关于在具有 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 混合版本的环境中使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台的信息。  
  
|互操作性环境|更多信息|  
|----------------------------------|----------------------|  
|具有 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 和 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]|要管理 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点，控制台及其连接到的站点必须运行相同版本的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]。 例如，你无法使用 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 控制台来管理 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 站点，反之亦然。<br /><br /> 不支持在相同计算机上安装 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 控制台和 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 控制台。|  
|具有 System Center Configuration Manager 的多个版本的环境|[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 不支持在计算机上安装多个 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台。 要使用特定于 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]的不同版本的多个控制台，你必须在单独的计算机上安装不同的控制台。<br /><br /> 在升级层次结构中的站点过程中，你可以将控制台连接到运行更新的版本的站点，并查看关于该层次结构中其他站点的信息。 但是，不建议使用此配置，因为控制台版本和 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点版本之间的差异可能导致数据问题，且某些在最新产品版本中可用的功能在控制台中不可用。|  
  
## 另请参阅  
 [System Center Configuration Manager 的站点和层级结构基础结构技术参考](../LocTest/Site-and-hierarchy-infrastructure-technical-reference-for-System-Center-Configuration-Manager.md)
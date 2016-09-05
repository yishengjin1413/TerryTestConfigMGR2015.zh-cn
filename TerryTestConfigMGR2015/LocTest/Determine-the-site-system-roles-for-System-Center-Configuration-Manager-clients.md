---
title: "为 System Center Configuration Manager 客户端确定站点系统角色"
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
ms.assetid: 984e8d92-7327-4b08-9228-0c955e6ac778
caps.latest.revision: 9
caps.handback.revision: 7
---
# 为 System Center Configuration Manager 客户端确定站点系统角色
使用下列部分来帮助你确定部署 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端所需的站点系统：  
  
-   [确定是否需要管理点](#BKMK_Determine_MP)  
  
-   [确定你是否需要回退状态点](#BKMK_Determine_FSP)  
  
-   [确定是否需要注册点和注册代理点](#BKMK_Determine_EnrollmentPoints)  
  
-   [确定是否需要分发点](#BKMK_Determine_DP)  
  
-   [确定是否需要应用程序目录网站点和应用程序目录 Web 服务点](#BKMK_Determine_ApplicationCatalogPoints)  
  
 有关在层次结构中何处安装这些站点系统角色的详细信息，请参阅[设计 System Center Configuration Manager 的站点层次结构](../LocTest/Design-a-hierarchy-of-sites-for-System-Center-Configuration-Manager.md)。  
  
 有关如何安装和配置所需的站点系统角色的详细信息，请参阅[安装 System Center Configuration Manager 站点](../Topic/Install%20System%20Center%20Configuration%20Manager%20sites.md)。  
  
##  <a name="BKMK_Determine_MP"></a> 确定是否需要管理点  
 默认情况下，所有 Windows 客户端计算机都使用分发点来安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端，并且可以在分发点不可用时回退到管理点。 但是，如果使用 CCMSetup 命令行属性 **\/source:\<Path\>**，则可以通过替代来源在计算机上安装 Windows 客户端。 例如，这可能适合在 Internet 上安装客户端的情况。 另一种情况是想在客户端安装过程中避免在计算机与管理点之间发送网络包，可能是因为防火墙阻止安装方法所需的端口，或者因为你具有低带宽连接。 但是，所有客户端都必须与管理点进行通信，才能分配给站点以及由 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 来管理。  
  
 有关 CCMSetup 命令行属性 **\/source:\<Path\>** 的详细信息，请参阅[关于 System Center Configuration Manager 中的客户端安装属性](../LocTest/About-client-installation-properties-in-System-Center-Configuration-Manager.md)。  
  
 在层次结构中安装多个管理点时，客户端会根据其林成员身份和网络位置自动连接到最合适的管理点。 你无法在辅助站点中安装多个管理点。  
  
 用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 注册的 Mac 计算机客户端和移动设备客户端始终需要用于客户端安装的管理点。 此管理点必须在主站点中，必须配置为支持移动设备，并且必须接受来自 Internet 的客户端连接。 这些客户端无法使用辅助站点中的管理点或者无法连接到其他主站点中的管理点。  
  
##  <a name="BKMK_Determine_FSP"></a> 确定你是否需要回退状态点  
 你可以使用回退状态点监视 Windows 计算机的客户端部署，以及标识因无法与管理点通信而不受管理的这些计算机上的客户端。 Mac 计算机、通过 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 注册的移动设备，以及使用 Exchange Server 连接器管理的移动设备不使用回退状态点。  
  
> [!NOTE]  
>  监视客户端活跃状况和客户端健康状况不需要回退状态点。  
  
 回退状态点始终使用 HTTP 与客户端通信，HTTP 使用未经过身份验证的连接并以明文形式发送数据。 这会使回退状态点易受到攻击，特别是在与基于 Internet 的客户端管理一起使用时。 为了帮助减少攻击面，请在生产环境中始终专门使用一个服务器来运行回退状态点，并且不要在该服务器上安装其他站点系统角色。  
  
 如果以下所有条件都适用，请安装回退状态点：  
  
-   你想将 Windows 计算机中的客户端通信错误发送给站点，即使这些客户端计算机无法与管理点通信也不例外。  
  
-   你想要使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端部署报表，这些报表显示回退状态点发送的数据。  
  
-   此站点系统角色具有专用服务器，并且采取了其他安全措施来帮助保护服务器不受攻击。  
  
-   使用回退状态点的好处大于与未经过身份验证的连接以及通过 HTTP 流量进行的明文传输关联的安全风险。  
  
 如果下列条件适用，请不要安装回退状态点：  
  
-   使用未经过身份验证的连接以及明文传输运行网站的安全风险大于确定客户端通信问题的好处。  
  
##  <a name="BKMK_Determine_RSP"></a> 确定是否需要 Reporting Services 点  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 提供了许多报表，以帮助你在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中监视客户端的安装、分配和管理。 一些客户端部署报表需要将客户端分配到回退状态点。  
  
 虽然部署客户端不需要报表，并且你可以在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中查看某些部署信息，或者可以使用客户端日志文件获取详细信息，但客户端报表可提供重要的信息，以帮助监视客户端部署以及对其进行故障排除。  
  
##  <a name="BKMK_Determine_EnrollmentPoints"></a> 确定是否需要注册点和注册代理点  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 需要注册点和注册代理点以注册移动设备以及注册 Mac 计算机的证书。 如果将使用 Exchange Server 连接器来管理移动设备，如果安装移动设备旧客户端（例如，用于 Windows CE），或者如果独立于 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 在 Mac 计算机上请求和安装客户端证书，则不需要这些站点系统角色。  
  
##  <a name="BKMK_Determine_DP"></a> 确定是否需要分发点  
 虽然在 Windows 计算机上安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端不需要分发点，但是默认情况下，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 使用分发点在 Windows 计算机上安装客户端源文件，但它可以进行回退以从管理点中下载这些文件。 分发点并不用于安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 注册的移动设备客户端，但如果你安装移动设备旧客户端，则会使用分发点。 如果在操作系统部署过程中安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端，则会在分发点中存储和检索操作系统映像包。  
  
 虽然安装大多数 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端可能不需要分发点，但在客户端上安装诸如应用程序和软件更新之类的软件却需要分发点。  
  
##  <a name="BKMK_Determine_ApplicationCatalogPoints"></a> 确定是否需要应用程序目录网站点和应用程序目录 Web 服务点  
 客户端部署不需要应用程序目录网站点和应用程序目录 Web 服务点。 但是，你可能需要在客户端部署过程中安装它们，以便在 Windows 计算机上安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端之后用户可以立即执行以下操作：  
  
-   擦除他们的移动设备。  
  
-   从应用程序目录中搜索并安装应用程序。  
  
-   将应用程序部署到用户和设备（部署目的为“可用”）。  
  
## 请参阅  
 [在 System Center Configuration Manager 中部署客户端的规划注意事项](../LocTest/Planning-considerations-for-deploying-clients-in-System-Center-Configuration-Manager.md)
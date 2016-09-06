---
title: "对 System Center Configuration Manager 中的 Windows 功能和网络的支持"
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
ms.assetid: 0cf4bacb-6b6d-4d4f-8640-b13fe15873de
caps.latest.revision: 8
caps.handback.revision: 7
translationtype: Human Translation
---
# 对 System Center Configuration Manager 中的 Windows 功能和网络的支持
本主题介绍 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 对以下 Windows 功能和网络功能的支持：  
  
-   [BranchCache](#bkmk_branchcache)  
  
-   [工作组中的计算机](#bkmk_Workgroups)  
  
-   [DirectAccess](#bkmk_DA)  
  
-   [重复数据删除](#bkmmk_datadedup)  
  
-   [双引导计算机](#bkmk_dualboot)  
  
-   [Internet 协议版本 6](#bkmk_IPv6)  
  
-   [网络地址转换](#bkmk_NAT)  
  
-   [专用存储技术](#bkmk_storage)  
  
##  <a name="bkmk_branchcache"></a> BranchCache  
 已在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中集成了 Windows BranchCache。 你可以在应用程序的部署类型上、在包和任务序列的部署上配置 BranchCache 设置。  
  
 当满足 BranchCache 的所有要求后，此功能允许远程位置处的客户端从具有当前内容缓存的本地客户端中获取内容。  
  
 例如，当第一台启用 BranchCache 的客户端计算机从配置为 BranchCache 服务器的分发点请求内容时，客户端计算机将下载内容并对其进行缓存。 然后，此内容可供请求此相同内容的相同子网上的客户端使用，这些客户端也会缓存该内容。 这样，相同子网上的后续客户端不必从分发点下载内容，该内容将跨多个客户端进行分发以便将来传输。  
  
 **若要使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 支持 BranchCache：**  
  
-   将 **Windows BranchCache** 功能添加到配置为分发点的站点系统服务器。  
  
    -   服务器上的分发点配置为支持 BranchCache 无需其他配置  
  
    -   你不能向基于云的分发点添加 Windows BranchCache，但基于云的分发点支持针对 Windows BranchCache 配置的客户端下载内容  
  
 **若要使客户端能够使用 BranchCache：**  
  
-   必须针对 BranchCache 分布模式配置可支持 BranchCache 的客户端  
  
-   必须启用用于 BITS 客户端设置的操作系统设置以支持 BranchCache  
  
 **Windows BranchCache 支持以下客户端操作系统：**  
  
|操作系统|支持详细信息|  
|----------|------------|  
|带 SP1 的 Windows 7|默认情况下支持|  
|Windows 8|默认情况下支持|  
|Windows 8.1|默认情况下支持|  
|Windows 10|默认情况下支持|  
|带 SP2 的 Windows Server 2008|**需要 BITS 4.0** \- 你可以使用软件更新或软件分发在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端上安装 BITS 4.0 版本。 有关 BITS 4.0 版本的详细信息，请参阅 [Windows Management Framework](http://go.microsoft.com/fwlink/p/?LinkId=181979)。<br /><br /> 此操作系统中，BranchCache 客户端功能不支持用于从网络运行的软件分发或 SMB 文件传输。 此外，此操作系统不能将 BranchCache 功能用于基于云的分发点。|  
|Windows Server 2008 R2|默认情况下支持|  
|Windows Server 2012|默认情况下支持|  
|Windows Server 2012 R2|默认情况下支持|  
  
 有关 BranchCache 的详细信息，请参阅 Windows Server 文档中的 [BranchCache for Windows](http://go.microsoft.com/fwlink/p/?LinkId=177945)。  
  
##  <a name="bkmk_Workgroups"></a> 工作组中的计算机  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 提供对工作组中的客户端的支持。  
  
-   [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 支持将客户端从工作组移动到域，或者从域移动到工作组。有关详细信息，请参阅 [如何在 System Center Configuration Manager 中部署客户端到 Windows 计算机](../LocTest/How-to-deploy-clients-to-Windows-computers-in-System-Center-Configuration-Manager.md) 主题中的 [如何在工作组计算机上安装 Configuration Manager 客户端](../LocTest/How-to-deploy-clients-to-Windows-computers-in-System-Center-Configuration-Manager.md#BKMK_ClientWorkgroup)  
  
> [!NOTE]  
>  尽管所有工作组中的客户端受支持，但所有站点系统必须是受支持的 Active Directory 域的成员  
  
##  <a name="bkmmk_datadedup"></a> 重复数据删除  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 在以下操作系统上支持将重复数据删除用于分发点：  
  
-   Windows Server 2012  
  
-   Windows Server 2012 R2  
  
> [!IMPORTANT]  
>  托管包源文件的卷不能标记为重复数据删除。 这是因为重复数据删除使用重新分析点，但 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不支持使用有文件存储在重新分析点上的内容源位置。  
  
 有关详细信息，请参阅 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 团队博客上的 [Configuration Manager 分发点和 Windows Server 2012 重复数据删除](http://blogs.technet.com/b/configmgrteam/archive/2014/02/18/configuration-manager-distribution-points-and-windows-server-2012-data-deduplication.aspx)和 Windows Server TechNet 库中的[重复数据删除概述](http://technet.microsoft.com/library/hh831602.aspx)。  
  
##  <a name="bkmk_DA"></a> DirectAccess  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 支持 Windows Server 2008 R2 中的 DirectAccess 功能，以便站点系统服务器和客户端之间的通信。  
  
-   当满足了 DirectAccess 的所有要求后，则通过使用此功能，Internet 上的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端可以与其分配的站点通信，就好像在 Intranet 上一样。  
  
-   对于由服务器启动的操作（如远程控制和客户端请求安装），启动的计算机（如站点服务器）必须运行 IPv6，并且必须在所有介入性网络设备上支持该协议。  
  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 在 DirectAccess 上不支持以下内容：  
  
-   部署操作系统  
  
-   [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点间的通信  
  
-   同一站点中的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点系统服务器间的通信  
  
##  <a name="bkmk_dualboot"></a> 双引导计算机  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不能在单台计算机上管理多个操作系统。 如果必须管理的计算机上存在多个操作系统，则调整用于确保仅在需要管理的操作系统上安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端的发现和安装方法。  
  
##  <a name="bkmk_IPv6"></a> Internet 协议版本 6  
 除 Internet 协议版本 4 \(IPv4\) 之外，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 还支持 Internet 协议版本 6 \(IPv6\)，以下情况例外：  
  
|函数|对 IPv6 支持的例外|  
|--------|------------------|  
|基于云的分发点|支持 Microsoft Azure 和基于云的分发点需要 IPv4。|  
|由 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 和 Microsoft 服务连接器注册的移动设备|支持由 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 和 Microsoft 服务连接器注册的移动设备需要 IPv4。|  
|网络发现|配置 DHCP 服务器以在“网络发现”中搜索时需要 IPv4。|  
|操作系统部署|支持操作系统部署需要 IPv4。|  
|唤醒代理通信|支持客户端唤醒代理数据包需要 IPv4。|  
|Windows CE|在 Windows CE 设备上支持 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端需要 IPv4 。|  
  
##  <a name="bkmk_NAT"></a> 网络地址转换  
 在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中不支持网络地址转换 \(NAT\)，除非站点支持位于 Internet 上的客户端且客户端检测到它连接到 Internet。 有关基于 Internet 的客户端管理的详细信息，请参阅[System Center Configuration Manager 中的客户端管理计划](../LocTest/Plan-for-managing-Internet-based-clients-in-System-Center-Configuration-Manager.md)。  
  
##  <a name="bkmk_storage"></a> 专用存储技术  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 与在安装了 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 组件的操作系统版本的 Windows 硬件兼容列表 \(HCL\) 上经过认证的任何硬件配合使用。 站点服务器角色需要 NTFS 文件系统才能设置目录和文件权限。 因为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 假定它具有逻辑驱动器的完全所有权，因此在单独计算机上运行的站点系统不能共享任何存储技术上的逻辑分区。 但是，每台计算机可以使用共享存储设备的同一物理分区上的单独逻辑分区。  
  
 **支持注意事项：**  
  
-   **存储区域网络**：只要将受支持的基于 Windows 的服务器直接连接至 SAN 托管的卷，就支持存储区域网络 \(SAN\)。  
  
-   **单实例存储**：[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不支持在启用了单实例存储 \(SIS\) 的卷上配置分发点包和签名文件夹。  
  
     此外，在启用了 SIS 的卷上不支持 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端的缓存。  
  
-   **可移动磁盘驱动器**：[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不支持在可移动磁盘驱动器上安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点系统或客户端。  
  
## 请参阅  
 [System Center Configuration Manager 支持的配置](../LocTest/Supported-configurations-for-System-Center-Configuration-Manager.md)
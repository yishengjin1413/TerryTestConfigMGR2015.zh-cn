---
title: "升级支持 System Center Configuration Manager 的本地基础结构"
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
ms.assetid: 8ca970dd-e71c-404f-9435-d36e773a0db2
caps.latest.revision: 7
caps.handback.revision: 6
translationtype: Human Translation
---
# 升级支持 System Center Configuration Manager 的本地基础结构
使用以下信息来帮助你升级运行 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]的基础结构。  
  
-   [升级站点系统的站点操作系统](#BKMK_SupConfigUpgradeSiteSrv)  
  
-   [升级客户端的操作系统](#BKMK_SupConfigUpgradeClient)  
  
-   [升级站点数据库服务器上的 SQL Server](#BKMK_SupConfigUpgradeDBSrv)  
  
##  <a name="BKMK_SupConfigUpgradeSiteSrv"></a> 升级站点系统的站点操作系统  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 在以下情况下，支持就地升级站点服务器的操作系统：  
  
-   只要生成的 Service Pack 级别仍然受 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 支持，就就地升级到更高版本的 Windows Server Service Pack。  
  
-   从 Windows Server 2012 就地升级到 Windows Server 2012 R2。  
  
-   运行版本 1602 或更高版本的 Configuration Manager 站点支持站点服务器的操作系统从 Windows Server 2008 R2 就地升级到 Windows Server 2012 R2。  
  
    > [!WARNING]  
    >  升级到 Windows Server 2012 R2 之前，**必须从服务器中卸载 WSUS 3.2**。  
    >   
    >  有关此关键步骤的信息，请参阅 Windows Server 文档中 [Windows Server 更新服务概述](https://technet.microsoft.com/library/hh852345.aspx)中的“新增和更改的功能”部分。  
  
     若要升级服务器，请使用 Windows Server 2012 R2 升级过程，且在升级后不需要运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点服务器还原。  有关升级过程，请参阅 Windows Server 文档中的 [Windows Server 2012 R2 的升级选项](https://technet.microsoft.com/library/dn303416.aspx)。  
  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不支持以下 Windows Server 升级方案。  
  
-   Windows Server 2008 到 Windows Server 2012 或更高版本。  
  
-   Windows Server 2008 R2 到 Windows Server 2012。  
  
##  <a name="BKMK_SupConfigUpgradeClient"></a> 升级客户端的操作系统  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 在以下情况下，支持就地升级 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端的操作系统：  
  
-   只要生成的 Service Pack 级别仍然受 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 支持，便就地升级到更高版本的 Windows Service Pack。  
  
-   从支持的版本到 Windows 10 的 Windows 就地升级。 有关详细信息，请参阅[使用 System Center Configuration Manager 将 Windows 升级到最新版本](../LocTest/Upgrade-Windows-to-the-latest-version-with-System-Center-Configuration-Manager.md)。  
  
-   Windows 10 的内部版本到内部版本服务升级。  有关详细信息，请参阅[使用 System Center Configuration Manager 将 Windows 作为服务进行管理](../LocTest/Manage-Windows-as-a-service-using-System-Center-Configuration-Manager.md)。  
  
##  <a name="BKMK_SupConfigUpgradeDBSrv"></a> 升级站点数据库服务器上的 SQL Server  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 在站点数据库服务器上支持将 SQL Server 从受支持的 SQL 版本就地升级。 下表提供了有关 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 支持的升级方案的详细信息和每个方案的任何要求。  
  
 有关 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 支持的 SQL Server 版本的详细信息，请参阅[对 System Center Configuration Manager 的 SQL Server 版本的支持](../LocTest/Support-for-SQL-Server-versions-for-System-Center-Configuration-Manager.md)。  
  
 有关 SQL Server 支持升级的 SQL Server 版本的信息，请参阅 TechNet 上的 SQL Server 文档：  
  
-   [升级到 SQL Server 2014](http://technet.microsoft.com/library/ms143393\(v=sql.120\).aspx)  
  
-   [升级到 SQL Server 2012](http://technet.microsoft.com/library/ms143393\(v=sql.110\).aspx)  
  
|升级方案|更多信息|  
|----------------------|----------------------|  
|升级 SQL Server 的 Service Pack 版本|[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 只要生成的 SQL Server Service Pack 级别仍然受 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 支持，就支持将 SQL Server 就地升级到更高版本的 Service Pack。<br /><br /> 当你的层次结构中有多个 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点时，每个站点可以运行不同的 SQL Server 的 Service Pack 版本，并且站点升级用于站点数据库的 SQL Server 的 Service Pack 版本没有顺序限制。|  
|升级到 SQL Server 2012|[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 支持将 SQL Server 就地升级到 SQL Server 2012，但有以下限制：<br /><br /> 当在每个站点托管站点数据库的 SQL Server 版本升级到 SQL Server 2012 时，必须在站点按以下顺序升级 SQL Server：<br /><br /> 1.首先升级管理中心站点上的 SQL Server。<br /><br /> 2.升级辅助站点，然后再升级辅助站点父主站点。<br /><br /> 3.最后升级父主站点。 这包括向管理中心站点报告的子主站点和是层次结构的顶层站点的独立主站点。|  
|升级到 SQL Server 2014|[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]支持将 SQL Server 就地升级到 SQL Server 2014，但有以下限制：<br /><br /> 将在每个站点托管站点数据库的 SQL Server 版本升级到 SQL Server 2014 时，必须在站点按以下顺序升级使用的 SQL Server 版本：<br /><br /> 1.首先升级管理中心站点上的 SQL Server。<br /><br /> 2.升级辅助站点，然后再升级辅助站点父主站点。<br /><br /> 3.最后升级父主站点。 这包括向管理中心站点报告的子主站点和是层次结构的顶层站点的独立主站点。|  
  
### 在站点数据库服务器上升级 SQL Server  
  
1.  停止站点上的所有 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 服务。  
  
2.  将 SQL Server 升级到支持的版本。  
  
3.  重启 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 服务。  
  
> [!NOTE]  
>  在管理中心站点上将使用的 SQL Server 版本从 Standard Edition 更改为 Datacenter 或 Enterprise Edition 时，限制层次结构支持的客户端数量的数据库分区不会更改。
---
title: "配置 System Center Configuration Manager 的站点和层次结构"
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
ms.assetid: 9efb4061-f642-48bd-8332-3357ff5b3118
caps.latest.revision: 15
caps.handback.revision: 15
translationtype: Human Translation
---
# 配置 System Center Configuration Manager 的站点和层次结构
在安装首个 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 站点或将附加站点添加到你的层次结构之后，请使用以下清单确保已考虑会同时影响站点和层次结构的最常见配置。  
  
## 全新站点和附加站点的常见配置清单  
 在大多数部署中，你不需要按任何特定顺序配置以下选项：  
  
-   某些选项相互依赖，例如 Active Directory 林发现、边界和边界组。  
  
-   一些配置有默认值，你可以使用这些默认值而不进行配置更改，至少暂时可以这样做。  
  
-   如边界组和分发点组等附加配置则需要你进行配置，之后才能使用它们。  
  
|操作|详细信息|  
|------------|-------------|  
|配置基于角色的管理|基于角色的管理是指如何分离管理分配，从而控制哪些管理用户可在 Configuration Manager 环境中查看和管理不同对象和数据。<br /><br /> 配置基于角色的管理与层次结构中的所有站点共享。   <br />请参阅[为 System Center Configuration Manager 配置基于角色的管理](../LocTest/Configure-role-based-administration-for-System-Center-Configuration-Manager.md)|  
|将站点数据发布到 Active Directory 域服务 (AD DS)|当你将站点数据发布到 AD DS 时，可便于客户端查找服务并有效地使用站点资源。<br /><br /> 你必须首先[扩展 System Center Configuration Manager 的 Active Directory 架构](../LocTest/Extend-the-Active-Directory-schema-for-System-Center-Configuration-Manager.md)，然后每个站点必须被单独配置为[发布 System Center Configuration Manager 的站点数据](../LocTest/Publish-site-data-for-System-Center-Configuration-Manager.md)。|  
|配置服务连接点|在层次结构的顶层站点上，应计划安装和配置服务连接点。 有关信息，请参阅[关于 System Center Configuration Manager 中的服务连接点](../LocTest/About-the-service-connection-point-in-System-Center-Configuration-Manager.md)。|  
|添加站点系统角色|向单独的站点安装一个或多个附加站点系统角色。  请参阅 [Add site system roles for System Center Configuration Manager](../LocTest/Add-site-system-roles-for-System-Center-Configuration-Manager.md)。|  
|配置站点边界和边界组|指定可定义 Intranet 上网络位置的边界（这些位置可包含要管理的设备），然后配置边界组，以使这些网络位置上的客户端可找到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 服务资源。 请参阅[为 System Center Configuration Manager 定义站点边界和边界组](../LocTest/Define-site-boundaries-and-boundary-groups-for-System-Center-Configuration-Manager.md)|  
|配置分发点组|配置分发点的逻辑组可简化部署的管理。 请参阅[为 System Center Configuration Manager 安装和配置分发点](../LocTest\Install-and-configure-distribution-points-for-System-Center-Configuration-Manager.md)中的[管理分发点组](../LocTest\Install-and-configure-distribution-points-for-System-Center-Configuration-Manager.md#bkmk_manage)。|  
|运行发现|运行发现可查看网络中的资源，其中包括网络基础结构、设备和用户。<br /><br /> 请参阅 [Run discovery for System Center Configuration Manager](../LocTest/Run-discovery-for-System-Center-Configuration-Manager.md)。|  
|为管理基础结构的管理员添加冗余和容量|可以通过安装附加 SMS 提供程序和 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台来扩展容量，以便管理员管理基础结构：<br /><br /> **安装附加 SMS 提供程序** 可提供冗余，以便联系点管理站点和层次结构。 请参阅 [Modify your System Center Configuration Manager infrastructure](../LocTest/Modify-your-System-Center-Configuration-Manager-infrastructure.md#BKMK_ManageSMSprovider) 中的 [Manage the SMS Provider](../LocTest/Modify-your-System-Center-Configuration-Manager-infrastructure.md)<br /><br /> **安装附加 Configuration Manager 控制台** 可同时提供访问其他管理用户的权限。 请参阅[安装 Configuration Manager 控制台](../LocTest\Install-System-Center-Configuration-Manager-consoles.md)|  
|配置站点组件|可以配置每个站点中的站点组件，以修改站点系统角色和站点状态报告的行为。 请参阅 [Site components for System Center Configuration Manager](../LocTest/Site-components-for-System-Center-Configuration-Manager.md)。|  
|创建自定义集合|通过使用发现的关于设备和用户的信息，创建对象的自定义集合以简化未来的管理任务。 请参阅[如何在 System Center Configuration Manager 中创建集合](../LocTest/How-to-create-collections-in-System-Center-Configuration-Manager.md)|  
|配置设置以管理高风险部署|在站点中配置设置，这些设置会在管理用户创建高风险任务序列部署时警告他们。  请参阅 [Settings to manage high-risk deployments for System Center Configuration Manager](../LocTest/Settings-to-manage-high-risk-deployments-for-System-Center-Configuration-Manager.md)。|  
|配置管理点的数据库副本|配置数据库副本，以减少管理点在处理来自客户端的请求时放在站点数据库服务器上的 CPU 负载。 请参阅 [Database replicas for management points for System Center Configuration Manager](../LocTest/Database-replicas-for-management-points-for-System-Center-Configuration-Manager.md)。|  
|配置 SQL Server AlwaysOn 可用性组以承载站点数据库|从版本 1602 开始，可以将可用性组配置为高可用性和灾难恢复解决方案，以用于承载主站点和管理中心站点上的站点数据库。 请参阅[通过 SQL Server AlwaysOn 实现适用于 System Center Configuration Manager 的高可用性站点数据库](../LocTest/SQL-Server-AlwaysOn-for-a-highly-available-site-database-for-System-Center-Configuration-Manager.md)|  
|修改站点之间的复制|请参阅 [System Center Configuration Manager 中的站点间数据传输](../LocTest/Data-transfers-between-sites-in-System-Center-Configuration-Manager.md)以了解有关以下主题：<br /><br /> 在辅助站点之间配置 [File-based replication](../LocTest/Data-transfers-between-sites-in-System-Center-Configuration-Manager.md#bkmk_fileroute)<br /><br /> 配置 [Database replication links](../LocTest/Data-transfers-between-sites-in-System-Center-Configuration-Manager.md#bkmk_Dblinks)<br /><br /> 配置 [Distributed views](../LocTest/Data-transfers-between-sites-in-System-Center-Configuration-Manager.md#bkmk_distviews)|  
  
## 另请参阅  
 [开始使用 System Center Configuration Manager](../LocTest/Start-using-System-Center-Configuration-Manager.md)
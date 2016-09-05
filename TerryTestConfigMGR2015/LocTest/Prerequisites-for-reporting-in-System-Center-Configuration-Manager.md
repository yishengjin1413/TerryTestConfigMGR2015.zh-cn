---
title: "System Center Configuration Manager 中报告的先决条件"
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
ms.assetid: 9cc508a5-5023-4833-b776-ae9a6971138f
caps.latest.revision: 5
caps.handback.revision: 4
---
# System Center Configuration Manager 中报告的先决条件
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的报表有外部依赖关系和产品内的依赖关系。  
  
## Configuration Manager 的外部依赖关系  
 下表列出了报表的外部依赖关系。  
  
|先决条件|更多信息|  
|----------|----------|  
|SQL Server Reporting Services|你必须安装和配置 SQL Server Reporting Services，然后才能在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中使用报表。<br /><br /> 有关在你的环境中规划和部署 Reporting Services 的信息，请参阅 SQL Server 2008 联机丛书中的 [Reporting Services](http://go.microsoft.com/fwlink/p/?LinkId=212032) 部分。|  
|运行 Reporting Services 点的计算机的站点系统角色依赖关系。|[System Center Configuration Manager 支持的配置](../LocTest/Supported-configurations-for-System-Center-Configuration-Manager.md)|  
  
## Configuration Manager 的内部依赖关系  
 下表列出了 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的报表的依赖关系。  
  
|先决条件|更多信息|  
|----------|----------|  
|Reporting Services 点|必须配置 Reporting Services 点站点系统角色，然后才能在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中使用报表。 有关如何安装和配置 Reporting Services 点的详细信息，请参阅[配置 System Center Configuration Manager 中的报表](../LocTest/Configuring-reporting-in-System-Center-Configuration-Manager.md)。|  
  
## Reporting Services 点支持的 SQL Server 版本  
 可以将 Reporting Services 数据库安装在 64 位 SQL Server 安装的默认实例或已命名实例上。 SQL Server 实例可与站点系统服务器共存，或位于远程计算机上。  
  
 下表列出了 Reporting Services 点支持的 SQL Server 版本。  
  
|SQL Server 版本|Reporting Services 点|  
|-------------------|--------------------------|  
|SQL Server 2008 SP2（至少包含累积更新 9）<br /><br /> -   Standard<br />-   企业版<br />-   Datacenter|√|  
|SQL Server 2008 SP3（至少包含累积更新 4）<br /><br /> -   Standard<br />-   企业版<br />-   Datacenter|√|  
|SQL Server 2008 R2 SP1（至少包含累积更新 6）<br /><br /> -   Standard<br />-   企业版<br />-   Datacenter|√|  
|SQL Server 2008 R2 SP2<br /><br /> -   Standard<br />-   企业版<br />-   Datacenter|√|  
|SQL Server Express 2008 R2 SP1（至少包含累积更新 4）|不支持|  
|SQL Server Express 2008 R2 SP2|不支持|  
|SQL Server 2012（至少包含累积更新 2）<br /><br /> -   Standard<br />-   企业版|√|  
|SQL Server 2012 SP1（没有最低累积更新）<br /><br /> -   Standard<br />-   企业版|√|  
|SQL Server 2014<br /><br /> -   Standard<br />-   企业版|√|  
  
## 请参阅  
 [规划 System Center Configuration Manager 中的报告](../LocTest/Planning-for-reporting-in-System-Center-Configuration-Manager.md)
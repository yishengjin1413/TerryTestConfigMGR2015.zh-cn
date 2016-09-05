---
title: "System Center Configuration Manager 的诊断和使用情况数据"
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
ms.assetid: 88ac4e55-d47b-4c94-b9c3-704c6a48b845
caps.latest.revision: 9
caps.handback.revision: 8
---
# System Center Configuration Manager 的诊断和使用情况数据
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 收集有关自身的诊断和使用情况数据，这些数据由 Microsoft 用于改进将来版本的安装体验、质量和安全性。  
  
 诊断和使用情况数据是针对每个 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 层次结构启用的。 它包含在每个主站点和管理中心站点每周运行一次的 SQL Server 查询。 层次结构使用管理中心站点时，主站点中的数据随后会复制到该站点。 在层次结构的顶层站点上，服务连接点在检查更新时提交此信息。 如果服务连接点处于脱机模式下，则将使用服务连接工具传输信息。  
  
> [!NOTE]  
>  [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 仅从站点 SQL 服务器数据库收集数据，而不会直接从客户端或站点服务器收集数据。  
  
 有关详细信息，请参见 [System Center Configuration Manager 隐私声明](http://go.microsoft.com/fwlink/?LinkID=626527)。  
  
 可在以下主题中详细了解 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 的诊断和使用数据：  
  
-   [如何将诊断和使用情况数据用于 System Center Configuration Manager](../LocTest/How-diagnostics-and-usage-data-is-used-for-System-Center-Configuration-Manager.md)  
  
-   [System Center Configuration Manager 的诊断使用情况数据收集的级别](../LocTest/Levels-of-diagnostic-usage-data-collection-for-System-Center-Configuration-Manager.md)  
  
-   [System Center Configuration Manager 如何收集诊断和使用情况数据](../LocTest/How-diagnostics-and-usage-data-is-collected-by-System-Center-Configuration-Manager.md)  
  
-   [如何查看 System Center Configuration Manager 的诊断和使用情况数据](../LocTest/How-to-view-diagnostics-and-usage-data-for-System-Center-Configuration-Manager.md)  
  
-   [System Center Configuration Manager 的客户体验改善计划 \(CEIP\)](../LocTest/Customer-Experience-Improvement-Program--CEIP--for-System-Center-Configuration-Manager.md)  
  
-   [有关 System Center Configuration Manager 的诊断和使用情况数据的常见问题](../LocTest/Frequently-asked-questions-about-diagnostics-and-usage-data-for-System-Center-Configuration-Manager.md)  
  
## 另请参阅  
 [System Center Configuration Manager 的技术参考](../LocTest/Technical-reference-for-System-Center-Configuration-Manager.md)   
 [System Center Configuration Manager 的站点安装技术参考](../LocTest/Site-installation-technical-reference-for-System-Center-Configuration-Manager.md)   
 [关于 System Center Configuration Manager 中的服务连接点](../LocTest/About-the-service-connection-point-in-System-Center-Configuration-Manager.md)
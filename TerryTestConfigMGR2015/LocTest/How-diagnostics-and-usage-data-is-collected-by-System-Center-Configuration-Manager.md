---
title: "System Center Configuration Manager 如何收集诊断和使用情况数据"
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
ms.assetid: becfa825-b19f-448c-ab82-bb929255e4ae
caps.latest.revision: 5
caps.handback.revision: 5
---
# System Center Configuration Manager 如何收集诊断和使用情况数据
若要为 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 收集诊断和使用情况数据，每个主站点每周都会运行 SQL Server 查询。 在多站点层次结构中，数据会复制到管理中心站点。  
  
 在层次机构的顶层站点上，服务连接点站点系统角色在检查更新时提交此信息。 数据的传输方式取决于服务连接点的模式：  
  
-   **在联机模式下：**每周自动从服务连接点向云服务发送一次诊断和使用情况数据。  
  
-   **在脱机模式下：**使用服务连接工具手动传输诊断和使用情况数据。 有关详细信息，请参阅 [Use the Service Connection Tool for System Center Configuration Manager](../LocTest/Use-the-Service-Connection-Tool-for-System-Center-Configuration-Manager.md)。  
  
 有关详细信息，请参阅 [About the service connection point in System Center Configuration Manager](../LocTest/About-the-service-connection-point-in-System-Center-Configuration-Manager.md)。  
  
## 另请参阅  
 [System Center Configuration Manager 的诊断和使用情况数据](../LocTest/Diagnostics-and-usage-data-for-System-Center-Configuration-Manager.md)   
 [System Center Configuration Manager 的诊断使用情况数据收集的级别](../LocTest/Levels-of-diagnostic-usage-data-collection-for-System-Center-Configuration-Manager.md)   
 [如何将诊断和使用情况数据用于 System Center Configuration Manager](../LocTest/How-diagnostics-and-usage-data-is-used-for-System-Center-Configuration-Manager.md)   
 [如何查看 System Center Configuration Manager 的诊断和使用情况数据](../LocTest/How-to-view-diagnostics-and-usage-data-for-System-Center-Configuration-Manager.md)
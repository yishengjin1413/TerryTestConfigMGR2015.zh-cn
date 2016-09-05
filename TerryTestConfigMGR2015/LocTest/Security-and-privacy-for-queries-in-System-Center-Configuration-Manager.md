---
title: "System Center Configuration Manager 中的查询的安全和隐私"
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
ms.assetid: 30080620-20d3-4c38-b8dd-db5516e1acae
caps.latest.revision: 5
caps.handback.revision: 4
---
# System Center Configuration Manager 中的查询的安全和隐私
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的查询使你可以基于指定条件从站点数据库中检索信息。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 会在标准操作过程中收集站点数据库信息。 例如，通过使用从发现或清单收集的信息，可以配置查询来标识满足指定条件的设备。  
  
 有关查询的详细信息，请参阅[System Center Configuration Manager 中的查询简介](../LocTest/Introduction-to-queries-in-System-Center-Configuration-Manager.md)。 有关 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 操作（收集可以使用查询检索的信息）的任何安全最佳方案和隐私信息的详细信息，请参阅 [System Center Configuration Manager 的安全性和隐私](../LocTest/Security-and-privacy-for-System-Center-Configuration-Manager.md)。  
  
## 查询的最佳安全方案  
 可将以下最佳安全方案用于查询。  
  
|最佳安全方案|更多信息|  
|------------|----------|  
|当你导出或导入保存到网络位置的查询时，请保护该位置和网络通道的安全。|限制可访问网络文件夹的人员。<br /><br /> 在网络位置与站点服务器之间使用服务器消息块 \(SMB\) 签名或 Internet 协议安全性 \(IPsec\)，以防止攻击者在查询数据导入之前篡改它。|  
  
## 请参阅  
 [System Center Configuration Manager 中查询的技术参考](../LocTest/Queries-technical-reference-for-System-Center-Configuration-Manager.md)
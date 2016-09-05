---
title: "System Center Configuration Manager 中硬件清单的最佳方案"
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
ms.assetid: daed49d1-060c-4511-9cfe-3890d396ae68
caps.latest.revision: 5
caps.handback.revision: 4
author: barlanmsft
---
# System Center Configuration Manager 中硬件清单的最佳方案
使用下面的最佳方案信息可帮助你在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中使用硬件清单。  
  
## 仅在需要时启用 MIF 文件收集  
 MIF 文件可能包含大量数据，收集这些数据可能对你网站的性能产生负面影响。 仅在需要时启用 MIF 文件收集，并在硬件清单客户端设置中配置“最大自定义 MIF 文件大小 \(KB\)”选项。 有关详细信息，请参阅[如何在 System Center Configuration Manager 中扩展硬件清单](../LocTest/How-to-extend-hardware-inventory-in-System-Center-Configuration-Manager.md)。  
  
## 请参阅  
 [在 System Center Configuration Manager 中规划硬件清单](../LocTest/Planning-for-hardware-inventory-in-System-Center-Configuration-Manager.md)
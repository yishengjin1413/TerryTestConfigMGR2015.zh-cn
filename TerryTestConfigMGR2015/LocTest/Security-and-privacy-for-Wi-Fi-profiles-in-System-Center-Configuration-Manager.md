---
title: "System Center Configuration Manager 中 Wi-Fi 配置文件的安全和隐私"
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
ms.assetid: ef3ab519-9cf7-47fc-8831-d400e0e96df8
caps.latest.revision: 4
caps.handback.revision: 3
---
# System Center Configuration Manager 中 Wi-Fi 配置文件的安全和隐私
本主题包含 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中 Wi\-Fi 配置文件的安全和隐私信息。  
  
##  <a name="BKMK_Security_RemoteConnections"></a> Wi\-Fi 配置文件的最佳安全方案  
 在针对设备管理 Wi\-Fi 配置文件时，请使用下列最佳安全方案。  
  
|最佳安全方案|更多信息|  
|------------|----------|  
|请尽可能选择 Wi\-Fi 基础结构和客户端操作系统可支持的最安全选项。|Wi\-Fi 配置文件提供了一种简便的方法来集中分发和管理你的设备已支持的 Wi\-Fi 设置。[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 不会添加 Wi\-Fi 功能。<br /><br /> 确定、实施和遵循已为你的设备和 Wi\-Fi 基础结构推荐的任何最佳安全方案。|  
  
## Wi\-Fi 配置的隐私信息  
 你可以使用 Wi\-Fi 配置文件来配置客户端设备以连接到 Wi\-Fi 服务器，然后评估那些设备在应用了配置文件后是否变为符合。 管理点会将符合性信息发送到站点服务器，该信息存储在站点数据库中。 设备在将信息发送到管理点时会对其进行加密，但信息不会以加密格式存储在站点数据库中。 数据库将保留该信息，直到站点维护任务“删除过期的配置管理数据”将其删除为止。 默认删除间隔是 90 天，但你可以更改它。 符合性信息不会被发送到 Microsoft。  
  
 默认情况下，设备不评估 Wi\-Fi 配置文件。 此外，你必须配置 VPN 配置文件，然后将它们部署到用户。  
  
 在配置 Wi\-Fi 配置文件之前，请考虑你的隐私要求。  
  
## 请参阅  
 [System Center Configuration Manager 中的 Wi\-Fi 配置文件](../LocTest/Wi-Fi-Profiles-in-System-Center-Configuration-Manager.md)
---
title: "System Center Configuration Manager 中 VPN 配置文件的安全和隐私"
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
ms.assetid: dc78c1a4-d34e-4c7c-9abe-72c5adf073e5
caps.latest.revision: 5
caps.handback.revision: 5
translationtype: Human Translation
---
# System Center Configuration Manager 中 VPN 配置文件的安全和隐私
本主题包含 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的 VPN 配置文件的安全和隐私信息。  
  
##  <a name="BKMK_Security_RemoteConnections"></a> VPN 配置文件的最佳安全方案  
 在为设备管理 VPN 配置文件时，请使用下列最佳安全方案。  
  
|最佳安全方案|更多信息|  
|------------|----------|  
|请尽可能选择 VPN 基础结构和客户端操作系统可支持的最安全选项。|VPN 配置文件提供了一种便利的方法来集中分发和管理设备已支持的 VPN 设置。[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 不会添加 VPN 功能。<br /><br /> 确定、实施和遵循已为你的设备和 VPN 基础结构推荐的任何最佳安全方案。|  
  
## VPN 配置文件的隐私信息  
 你可以使用 VPN 配置文件来配置客户端设备以连接到 VPN 服务器，并评估那些设备在应用了配置文件后是否变为符合。 管理点会将符合性信息会发送到站点服务器，并存储在站点数据库中。 设备在将信息发送到管理点时会对其进行加密，但信息不会以加密格式存储在站点数据库中。 信息将保留在数据库中，直到每 90 天站点维护任务“删除过期的配置管理数据”将其删除。 可以配置删除间隔。 符合性信息不会被发送到 Microsoft。  
  
 默认情况下，设备不评估 VPN 配置文件。 此外，你必须配置 VPN 配置文件，然后将它们部署到用户。  
  
 在配置 VPN 配置文件之前，请考虑隐私要求。  
  
## 请参阅  
 [System Center Configuration Manager 中的 VPN 配置文件](../LocTest/VPN-profiles-in-System-Center-Configuration-Manager.md)
---
title: "System Center Configuration Manager 中 Wi-Fi 配置文件的先决条件"
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
ms.assetid: d2dacb2d-ab3b-42a2-8dc8-94da31f993c2
caps.latest.revision: 5
caps.handback.revision: 5
---
# System Center Configuration Manager 中 Wi-Fi 配置文件的先决条件
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的 Wi-Fi 配置文件只在产品内有依赖关系。  
  
 你必须具有下列安全权限才能管理公司资源访问设置，例如证书配置文件、Wi-Fi 配置文件和 VPN 配置文件：  
  
-   若要查看和管理 Wi-Fi 配置文件的警报和报表：需要对“警报” 对象的“创建” 、“删除” 、“修改” 、“修改报表” 、“读取”  和“运行报表”  权限。  
  
-   若要创建和管理证书配置文件：需要“证书配置文件” 对象的“创作策略” 、“修改报表” 、“读取”  和“运行报表”  权限。  
  
-   若要管理 Wi-Fi、证书和 VPN 配置文件部署：需要对“集合” 对象的“部署配置策略” 、“修改客户端状态警报” 、“读取”  和“读取资源”  。  
  
-   若要管理所有配置策略：需要对“配置策略” 对象的“创建” 、“删除” 、“修改” 、“读取”  和“设置安全作用域”  权限。  
  
-   若要运行与 Wi-Fi 配置文件相关的查询：需要对“查询”  对象的“读取”  权限。  
  
-   若要在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 控制台中查看 Wi-Fi 配置文件信息：需要对“站点”  对象的“读取”  权限。  
  
-   若要查看 Wi-Fi 配置文件的状态消息：需要对“状态消息”  对象的“读取”  权限。  
  
-   若要创建和修改受信任的 CA 证书配置文件：需要对“受信任的 CA 证书配置文件” 对象的“创作策略” 、“修改报表” 、“读取”  和“运行报表”  权限。  
  
-   若要创建和管理 VPN 配置文件：需要对“VPN 配置文件” 对象的“创作策略” 、“修改报表” 、“读取”  和“运行报表”  权限。  
  
-   若要创建和管理 Wi-Fi 配置文件：需要对“Wi-Fi 配置文件” 对象的“创作策略” 、“修改报表” 、“读取”  和“运行报表”  权限。  
  
 “公司资源访问管理器”  安全角色包括在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]中管理 Wi-Fi 配置文件所需的这些权限。 有关详细信息，请参阅 [Configure security in System Center Configuration Manager](../LocTest/Configure-security-in-System-Center-Configuration-Manager.md)。
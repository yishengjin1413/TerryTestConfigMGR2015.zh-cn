---
title: "为 System Center Configuration Manager 配置防火墙、端口和域"
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
ms.assetid: d6993bba-f6bd-4639-adbf-efc1c638b2f3
caps.latest.revision: 15
caps.handback.revision: 15
---
# 为 System Center Configuration Manager 配置防火墙、端口和域
若要准备网络以支持 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]，则计划配置基础结构（如防火墙）以传递 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 使用的通信。  
  
|注意事项|详细信息|  
|----------|----------|  
|不同的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 功能使用的**端口和协议**。 某些端口是必需的，而其他的**域和服务**则可以自定义。|大多数 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 通信使用通用端口，比如用于 HTTP 通信的端口 80 或用于 HTTPS 通信的端口 443。但是，[某些站点系统角色支持使用自定义网站](https://technet.microsoft.com/library/mt426625.aspx) 和自定义端口。<br /><br />**在部署 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]** 之前，确定你打算使用的端口，并相应地配置防火墙。<br /><br />**以后，如果你需要在安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 后更改端口**，请不要忘记更新设备上的防火墙和网络，同时从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 内更改端口的配置。<br /><br />有关详细信息，请参阅 [如何在 System Center Configuration Manager 中配置客户端通信端口](../LocTest/How-to-configure-client-communication-ports-in-System-Center-Configuration-Manager.md) 和 [System Center Configuration Manager 中使用的端口](../LocTest/Ports-used-in-System-Center-Configuration-Manager.md)。|  
|站点服务器和客户端可能需要访问的**域和服务**。|[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 功能可以要求站点服务器和客户端有权访问 Internet 上的特定服务和域，如 Windowsudpate.microsoft.com 或 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 服务。<br /><br /> 如果将使用 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 管理移动设备，那么还必须配置 Intune 要求的对 [端口和域的访问权限。](https://technet.microsoft.com/dn646950.aspx)|  
|用于站点系统服务器和用于客户端通信的**代理服务器**。 你可以对不同的站点系统服务器和客户端指定单独的代理服务器。|因为这些配置是在安装站点系统角色或客户端时所做的，因此只需注意代理服务器配置，以供将来配置站点系统角色和客户端时参考。<br /><br /> 如果不能确定你的部署是否将需要使用代理服务器，请查看 [System Center Configuration Manager 中的代理服务器支持](../LocTest/Proxy-server-support-in-System-Center-Configuration-Manager.md) 以了解可以使用代理服务器的站点系统角色和客户端操作的相关信息。|  
  
## 请参阅  
 [为 System Center Configuration Manager 准备网络环境](../LocTest/Prepare-your-network-environment-for-System-Center-Configuration-Manager.md)
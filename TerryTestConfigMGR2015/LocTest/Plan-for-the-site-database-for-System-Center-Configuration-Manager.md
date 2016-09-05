---
title: "为 System Center Configuration Manager 规划站点数据库"
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
ms.assetid: 104fb4cc-6e83-40a3-8e6b-ac909fb9ec7d
caps.latest.revision: 5
caps.handback.revision: 3
translationtype: Human Translation
---
# 为 System Center Configuration Manager 规划站点数据库
站点数据库服务器是一台计算机，该计算机运行用于存储 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点信息的 Microsoft SQL Server 受支持版本。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 层次结构中的每个站点都包含站点数据库以及分配了站点数据库服务器角色的服务器。  
  
-   对于管理中心站点和主站点，你可以在站点服务器上安装 SQL Server，或者可以在不是站点服务器的计算机上安装 SQL Server  
  
-   对于辅助站点，你可以使用 SQL Server Express（而不是完整安装的 SQL Server）；但是，数据库服务器必须在辅助站点服务器上运行  
  
 如果使用远程数据库服务器计算机，请确保干预网络连接是高可用的高带宽网络连接。 这是因为站点服务器和某些站点系统角色必须不断地与承载站点数据库的 SQL Server 通信。  
  
 **如果选择远程数据库服务器位置，请考虑下列事项：**  
  
-   与数据库服务器的通信所需的带宽量取决于多个不同站点和客户端配置的组合；因此无法充分地预测所需的实际带宽。  
  
-   运行 SMS 提供程序以及连接到站点数据库的每台计算机都会增加网络带宽需求。  
  
-   运行 SQL Server 的计算机必须位于与站点服务器和运行 SMS 提供程序的所有计算机具有双向信任的域中。  
  
-   当站点数据库与站点服务器并存时，你无法为站点数据库服务器使用群集 SQL Server。  
  
 通常，站点系统服务器仅支持单一 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点中的站点系统角色；不过，你可以使用运行 SQL Server 的群集或非群集服务器上的不同 SQL Server 实例来承载不同 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点中的数据库。 为了支持不同站点中的数据库，你必须将 SQL Server 的每个实例配置为使用唯一端口进行通信。  
  
 **以下 SQL Server 配置可以用于承载站点数据库：**  
  
-   SQL Server 的默认实例  
  
-   运行 SQL Server 的单台计算机上的命名实例  
  
-   SQL Server 的群集实例上的命名实例  
  
 **站点数据库的先决条件：**  
  
-   要承载站点数据库，SQL Server 必须满足 [对 System Center Configuration Manager 的 SQL Server 版本的支持](../LocTest/Support-for-SQL-Server-versions-for-System-Center-Configuration-Manager.md)中详述的要求。  
  
## 请参阅  
 [设计 System Center Configuration Manager 的站点层次结构](../LocTest/Design-a-hierarchy-of-sites-for-System-Center-Configuration-Manager.md)
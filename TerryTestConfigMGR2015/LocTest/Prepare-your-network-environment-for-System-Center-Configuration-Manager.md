---
title: "为 System Center Configuration Manager 准备网络环境"
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
ms.assetid: e86e9bfc-c994-4d84-bed1-a02153b8b859
caps.latest.revision: 14
caps.handback.revision: 12
translationtype: Human Translation
---
# 为 System Center Configuration Manager 准备网络环境
成功安装和使用 Configuration Manager 之前，你必须配置网络、Windows 基础结构和支持技术以支持 Configuration Manager。 这可以包括：  
  
-   [扩展 Active Directory 架构](https://technet.microsoft.com/library/mt345589.aspx)，以便站点可以发布有关其配置和功能的信息，客户端就可以在这些信息中找到它。 如果不扩展此架构，你可能需要配置解决方法，以帮助客户端找到可用的服务和资源。  
  
-   [配置网络基础结构](https://technet.microsoft.com/library/mt427452.aspx)（如防火墙和端口）以使站点、站点系统服务器和客户端能够跨网络进行通信。  
  
-   通过安装 Windows 功能、Windows 角色和配置 IIS[准备 Windows Server 以支持 System Center Configuration Manager ](../LocTest/Prepare-Windows-Servers-to-support-System-Center-Configuration-Manager.md)。 并非所有站点系统都具有相同的先决条件或配置要求，但一些可能会要求你在对其进行配置后重新启动服务器 – 因此请提前计划来减少之后部署的时间。  
  
-   为要求 IIS 且接受来自客户端通信的站点系统角色[配置自定义网站](https://technet.microsoft.com/library/mt426625.aspx)。  
  
-   为与部署集成    [准备云服务](http://technet.microsoft.com/library/mt449632.aspx)（如 Microsoft Azure 和 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)]）。  
  
-   [对 System Center Configuration Manager 站点数据库使用非默认的 SQL Server 配置](../Topic/Use%20non-default%20SQL%20Server%20configurations%20for%20the%20System%20Center%20Configuration%20Manager%20site%20database.md)如 SQL 群集和另一个数据库文件位置。  
  
-   [System Center Configuration Manager 的 PKI 证书要求](../LocTest/PKI-certificate-requirements-for-System-Center-Configuration-Manager.md)  
  
-   [System Center Configuration Manager 的 PKI 证书的分步部署示例：Windows Server 2008 证书颁发机构](../Topic/Step-by-step%20example%20deployment%20of%20the%20PKI%20certificates%20for%20System%20Center%20Configuration%20Manager:%20Windows%20Server%202008%20Certification%20Authority.md)  
  
## 请参阅  
 [为 System Center Configuration Manager 做准备](../LocTest/Get-ready-for-System-Center-Configuration-Manager.md)
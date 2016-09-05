---
title: "System Center Configuration Manager 站点系统服务器支持的操作系统"
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
ms.assetid: 17905b4c-3895-4ad4-a69c-5e0d0fc5a8c3
caps.latest.revision: 44
caps.handback.revision: 44
---
# System Center Configuration Manager 站点系统服务器支持的操作系统

  本文详细介绍了可用于托管 [!INCLUDE[cm6long_md](../LocTest/includes/cm6long_md.md)] 站点或站点系统角色的 Windows 版本。 
  
 
 将本主题中的信息和以下文章中的信息一起使用：
-   [用于 Configuration Manager 的推荐硬件](../LocTest/Recommended-hardware-for-System-Center-Configuration-Manager.md)
-   [用于 Configuration Manager 的站点和站点系统先决条件](Site%20and%20site%20system%20prerequisites%20for%20System%20Center%20Configuration%20Manager.md)
-   [用于 Configuration Manager 的大小和扩展数量](Size%20and%20scale%20numbers%20for%20System%20Center%20Configuration%20Manager.md)
 

  
## Windows Server 2012 R2 (x64) - 标准版、数据中心版  
 **站点服务器：**  
  
-   管理中心站点  
  
-   主站点  
  
-   辅助站点  
  
 **站点系统服务器：**  
  
-   应用程序目录 Web 服务点  
  
-   应用程序目录网站点  
  
-   资产智能同步点  
  
-   证书注册点  
  
-   分发点  
  
     分发点支持多种不同的配置，每个具有不同的要求，并且在某些情况下不仅支持服务器上的安装，还支持客户端操作系统上的安装。 有关分发点可用选项的详细信息，请参阅[为 System Center Configuration Manager 管理内容和内容基础结构](../LocTest/Manage-content-and-content-infrastructure-for-System-Center-Configuration-Manager.md)。  
  
-   Endpoint Protection 点  
  
-   注册点  
  
-   注册代理点  
  
-   回退状态点  
  
-   Reporting Services 点  
  
-   服务连接点  
  
-   站点数据库服务器  
  
     只读域控制器 (RODC) 上不支持站点数据库服务器。 有关详细信息，请参阅 Microsoft 知识库中的 [You may encounter problems when installing SQL Server on a domain controller（在域控制器上安装 SQL Server 时可能会遇到问题）](http://go.microsoft.com/fwlink/p/?LinkId=264856) 。 此外，任何域控制器上都不支持辅助站点服务器。  
  
-   SMS_Provider  
  
-   软件更新点  
  
-   状态迁移点  
  
## Windows Server 2012 (x64) - 标准版、数据中心版  
 **站点服务器：**  
  
-   管理中心站点  
  
-   主站点  
  
-   辅助站点  
  
 **站点系统服务器：**  
  
-   应用程序目录 Web 服务点  
  
-   应用程序目录网站点  
  
-   资产智能同步点  
  
-   证书注册点  
  
-   分发点  
  
     分发点支持多种不同的配置，每个具有不同的要求，并且在某些情况下不仅支持服务器上的安装，还支持客户端操作系统上的安装。 有关分发点可用选项的详细信息，请参阅[为 System Center Configuration Manager 管理内容和内容基础结构](../LocTest/Manage-content-and-content-infrastructure-for-System-Center-Configuration-Manager.md)。  
  
-   Endpoint Protection 点  
  
-   注册点  
  
-   注册代理点  
  
-   回退状态点  
  
-   Reporting Services 点  
  
-   服务连接点  
  
-   站点数据库服务器  
  
     只读域控制器 (RODC) 上不支持站点数据库服务器。 有关详细信息，请参阅 Microsoft 知识库中的 [You may encounter problems when installing SQL Server on a domain controller（在域控制器上安装 SQL Server 时可能会遇到问题）](http://go.microsoft.com/fwlink/p/?LinkId=264856) 。 此外，任何域控制器上都不支持辅助站点服务器。  
  
-   SMS_Provider  
  
-   软件更新点  
  
-   状态迁移点  
  
## 带 SP1 的 Windows Server 2008 R2 (x64) – 标准版、企业版、数据中心版  
 根据 [Microsoft 支持生命周期](https://support.microsoft.com/lifecycle)提供的详细信息，Windows Server 2008 R2 现处于外延支持，不再处于主流支持。 有关将来对这些操作系统作为具有 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的站点系统服务器的支持的详细信息，请参阅 [System Center Configuration Manager 的已删除和已弃用的功能](../LocTest/Removed-and-deprecated-features-for-System-Center-Configuration-Manager.md)。  
  
 **站点服务器：**  
  
-   管理中心站点  
  
-   主站点  
  
-   辅助站点  
  
 **站点系统服务器：**  
  
-   应用程序目录 Web 服务点  
  
-   应用程序目录网站点  
  
-   资产智能同步点  
  
-   证书注册点  
  
-   分发点  
  
     分发点支持多种不同的配置，每个具有不同的要求，并且在某些情况下不仅支持服务器上的安装，还支持客户端操作系统上的安装。 有关分发点可用选项的详细信息，请参阅[为 System Center Configuration Manager 管理内容和内容基础结构](../LocTest/Manage-content-and-content-infrastructure-for-System-Center-Configuration-Manager.md)。  
  
-   Endpoint Protection 点  
  
-   注册点  
  
-   注册代理点  
  
-   回退状态点  
  
-   Reporting Services 点  
  
-   服务连接点  
  
-   站点数据库服务器  
  
     只读域控制器 (RODC) 上不支持站点数据库服务器。 有关详细信息，请参阅 Microsoft 知识库中的 [You may encounter problems when installing SQL Server on a domain controller（在域控制器上安装 SQL Server 时可能会遇到问题）](http://go.microsoft.com/fwlink/p/?LinkId=264856) 。 此外，任何域控制器上都不支持辅助站点服务器。  
  
-   SMS_Provider  
  
-   软件更新点  
  
-   状态迁移点  
  
## Windows Server 2008 SP2 (x86, x64) - 标准版、企业版、数据中心版  
 根据 [Microsoft 支持生命周期](https://support.microsoft.com/lifecycle)提供的详细信息，Windows Server 2008 现处于外延支持，不再处于主流支持。 有关将来对这些操作系统作为具有 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的站点系统服务器的支持的详细信息，请参阅 [System Center Configuration Manager 的已删除和已弃用的功能](../LocTest/Removed-and-deprecated-features-for-System-Center-Configuration-Manager.md)。  
  
 **站点服务器：**  
  
-   管理中心站点  
  
-   主站点  
  
-   辅助站点  
  
 **站点系统服务器：**  
  
-   应用程序目录 Web 服务点  
  
-   应用程序目录网站点  
  
-   资产智能同步点  
  
-   证书注册点  
  
-   分发点  
  
    -   此操作系统上的分发点不支持多播。  
  
    -   此操作系统上的分发点受 PXE 支持，但它们不支持 EFI 模式下客户端计算机的网络启动。 支持具有 BIOS 或具有旧模式下的 EFI 启动的客户端计算机。  
  
    -   分发点支持多种不同的配置，每个具有不同的要求，并且在某些情况下不仅支持服务器上的安装，还支持客户端操作系统上的安装。 有关分发点可用选项的详细信息，请参阅[为 System Center Configuration Manager 管理内容和内容基础结构](../LocTest/Manage-content-and-content-infrastructure-for-System-Center-Configuration-Manager.md)。  
  
-   Endpoint Protection 点  
  
-   注册点  
  
-   注册代理点  
  
-   回退状态点  
  
-   Reporting Services 点  
  
-   服务连接点  
  
-   站点数据库服务器  
  
     只读域控制器 (RODC) 上不支持站点数据库服务器。 有关详细信息，请参阅 Microsoft 知识库中的 [You may encounter problems when installing SQL Server on a domain controller（在域控制器上安装 SQL Server 时可能会遇到问题）](http://go.microsoft.com/fwlink/p/?LinkId=264856) 。 此外，任何域控制器上都不支持辅助站点服务器。  
  
-   SMS_Provider  
  
-   软件更新点  
  
-   状态迁移点  
  
## Windows 10（x86、x64）– 专业版、企业版  
 **站点系统服务器：**  
  
-   分发点  
  
    -   此操作系统上的分发点不受 PXE 支持。  
  
    -   此操作系统版本上的分发点不支持多播。  
  
    -   分发点支持多种不同的配置，每个具有不同的要求，并且在某些情况下不仅支持服务器上的安装，还支持客户端操作系统上的安装。 有关分发点可用选项的详细信息，请参阅[为 System Center Configuration Manager 管理内容和内容基础结构](../LocTest/Manage-content-and-content-infrastructure-for-System-Center-Configuration-Manager.md)。  
  
## Windows 8.1（x86、x64）– 专业版、企业版  
 **站点系统服务器：**  
  
-   分发点  
  
    -   此操作系统上的分发点不受 PXE 支持。  
  
    -   此操作系统版本上的分发点不支持多播。  
  
    -   分发点支持多种不同的配置，每个具有不同的要求，并且在某些情况下不仅支持服务器上的安装，还支持客户端操作系统上的安装。 有关分发点可用选项的详细信息，请参阅[为 System Center Configuration Manager 管理内容和内容基础结构](../LocTest/Manage-content-and-content-infrastructure-for-System-Center-Configuration-Manager.md)。  
  
## Windows 8（x86、 x64）– 专业版，企业分发点  
 **站点系统服务器：**  
  
-   分发点  
  
    -   此操作系统上的分发点不受 PXE 支持。  
  
    -   此操作系统版本上的分发点不支持多播。  
  
    -   分发点支持多种不同的配置，每个具有不同的要求，并且在某些情况下不仅支持服务器上的安装，还支持客户端操作系统上的安装。 有关分发点可用选项的详细信息，请参阅[为 System Center Configuration Manager 管理内容和内容基础结构](../LocTest/Manage-content-and-content-infrastructure-for-System-Center-Configuration-Manager.md)。  
  
## 带 SP1 的 Windows 7（x86、x64）– 专业版、企业版、旗舰版  
 **站点系统服务器：**  
  
-   分发点  
  
    -   此操作系统上的分发点不受 PXE 支持。  
  
    -   此操作系统版本上的分发点不支持多播。  
  
    -   分发点支持多种不同的配置，每个具有不同的要求，并且在某些情况下不仅支持服务器上的安装，还支持客户端操作系统上的安装。 有关分发点可用选项的详细信息，请参阅[为 System Center Configuration Manager 管理内容和内容基础结构](../LocTest/Manage-content-and-content-infrastructure-for-System-Center-Configuration-Manager.md)。  
  
## Windows Server 2012 的 Server Core 安装  
 除了上述操作系统之外，支持将 Windows Server 2012 的 Server Core 安装用作具有以下限制的分发点：  
  
-   仅支持 x64  
  
-   此操作系统上的分发点不支持 PXE 或多播  
  
## Windows Server 2012 R2 的 Server Core 安装  
 除了上述操作系统之外，支持将 Windows Server 2012 R2 的 Server Core 安装用作具有以下限制的分发点：  
  
-   仅支持 x64  
  
-   此操作系统上的分发点不支持 PXE 或多播  
  


  


  
## 另请参阅  
 [System Center Configuration Manager 支持的配置](../LocTest/Supported-configurations-for-System-Center-Configuration-Manager.md)
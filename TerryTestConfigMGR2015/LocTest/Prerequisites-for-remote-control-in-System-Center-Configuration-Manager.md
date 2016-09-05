---
title: "在 System Center Configuration Manager 中远程控制的先决条件"
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
ms.assetid: c1b2057e-b74f-43fa-a293-763a8f866d3d
caps.latest.revision: 6
caps.handback.revision: 3
author: barlanmsft
translationtype: Human Translation
---
# 在 System Center Configuration Manager 中远程控制的先决条件
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中远程控制拥有外部依赖关系和产品中的依赖关系。  
  
## Configuration Manager 的外部依赖关系  
  
|依赖关系|更多信息|  
|----------|----------|  
|计算机视屏卡驱动程序|为获得最优的远程控制性能，请确保客户端计算机上已安装了最新的视屏驱动程序。|  
  
 运行 Windows Embedded、Windows Embedded for Point of Service \(POS\) 以及 Windows Fundamentals for Legacy PC 的设备不支持远程控制查看器，但它们却支持远程控制客户端。  
  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 远程控制不能用于远程管理运行 Systems Management Server 2003 或 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 2007 的客户端计算机。  
  
> [!NOTE]  
>  不需要 Windows 服务作为远程控制的外部依赖关系。  
  
### 支持远程控制查看器的操作系统  
 以下列表提供有关支持远程控制查看器的操作系统的信息。 有关支持的客户端操作系统的详细信息，请参阅 [System Center Configuration Manager 支持的配置](../LocTest/Supported-configurations-for-System-Center-Configuration-Manager.md)。  
  
|操作系统|查看器支持|更多信息|  
|----------|-----------|----------|  
|Windows XP（32 位）|是|若要在此操作系统上运行远程控制查看器，必须先从 Microsoft 下载中心下载并安装[远程桌面连接 \(RDC\) 客户端更新 7.0 \(KB969084\)](http://go.microsoft.com/fwlink/?LinkId=232483)。|  
|Windows XP（64 位）|否|无更多信息。|  
|Windows Vista（32 位）|是|若要在此操作系统上运行远程控制查看器，必须先从 Microsoft 下载中心下载并安装[远程桌面连接 \(RDC\) 客户端更新 7.0 \(KB969084\)](http://go.microsoft.com/fwlink/?LinkId=232483)。|  
|Windows Vista（64 位）|是|若要在此操作系统上运行远程控制查看器，必须先从 Microsoft 下载中心下载并安装[远程桌面连接 \(RDC\) 客户端更新 7.0 \(KB969084\)](http://go.microsoft.com/fwlink/?LinkId=232483)。|  
|Windows 7（32 位）|是|无更多信息。|  
|Windows 7（64 位）|是|无更多信息。|  
|Windows Server 2003（32 位）|否|无更多信息。|  
|Windows Server 2003（64 位）|否|无更多信息。|  
|Windows Server 2008（32 位）|否|无更多信息。|  
|Windows Server 2008（64 位）|否|无更多信息。|  
|Windows Server 2008 R2（64 位）|是|无更多信息。|  
  
## Configuration Manager 依赖关系  
  
|依赖关系|更多信息|  
|----------|----------|  
|必须为客户端启用远程控制|默认情况下，当你安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 时，不启用远程控制。 有关如何启用和配置远程控制的详细信息，请参阅 [配置 System Center Configuration Manager 中的远程控制](../LocTest/Configuring-remote-control-in-System-Center-Configuration-Manager.md)。|  
|Reporting Services 点|在远程控制的报表前，必须先安装 Reporting Services 点站点系统角色。 有关详细信息，请参阅[System Center Configuration Manager 中的报表](../LocTest/Reporting-in-System-Center-Configuration-Manager.md)。|  
|管理远程控制的安全权限|必须具有以下安全权限才能使用远程控制：<br /><br /> -   若要访问集合资源并且从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中启动远程控制会话：“控制 AMT”、“读取”、“读取资源”以及“集合”对象的“远程控制”权限。<br /><br /> “远程工具操作人员”安全角色包括这些在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中管理远程控制需要的权限。<br /><br /> 有关详细信息，请参阅 [为 System Center Configuration Manager 配置基于角色的管理](../LocTest/Configure-role-based-administration-for-System-Center-Configuration-Manager.md)。<br /><br /> 此外，还必须通过使用“远程工具”客户端设置中的“远程控制和远程协助允许的查看者”选项将你想授予使用远程控制和远程协助权限的用户添加到远程控制允许的查看列表当中。|  
  
## 请参阅  
 [System Center Configuration Manager 中远程控制的技术参考](../LocTest/Remote-control-technical-reference-for-System-Center-Configuration-Manager.md)
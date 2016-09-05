---
title: "System Center Configuration Manager 中的资产智能先决条件"
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
ms.assetid: 23ab4f94-7bfe-436e-8a6a-029409a2730c
caps.latest.revision: 10
caps.handback.revision: 6
author: barlanmsft
translationtype: Human Translation
---
# System Center Configuration Manager 中的资产智能先决条件
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的资产智能具有外部依赖关系和产品内部的依赖关系。  
  
## Configuration Manager 的外部依赖关系  
 下表提供 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 外部的资产智能依赖关系。  
  
|依赖关系|更多信息|  
|----------|----------|  
|成功登录事件审核先决条件|四个资产智能报表显示从客户端计算机上的 Windows 安全事件日志收集的信息。 如果安全事件日志未配置为记录所有成功登录事件，则即使启用了适当的硬件清单报表类，这些报表也不包含任何数据。<br /><br /> 下列资产智能报表依赖于收集的 Windows 安全事件日志信息：<br /><br /> -   硬件 03A \- 计算机主要用户<br />-   硬件 03B \- 特定主控制台用户的计算机<br />-   硬件 04A \- 共享\(多个用户\)计算机<br />-   硬件 05A \- 特定计算机上的控制台用户<br /><br /> 要使硬件清单客户端代理能够列出支持这些报表所需的信息，必须先在客户端上将 Windows 安全事件日志设置修改为记录所有成功登录事件，并启用 **SMS\_SystemConsoleUser** 硬件清单报表类。 有关将安全事件日志设置修改为记录所有成功登录事件的详细信息，请参阅[启用成功登录事件的审核](../LocTest/Configuring-Asset-Intelligence-in-System-Center-Configuration-Manager.md#BKMK_EnableSuccessLogonEvents)。 **Note:**  **SMS\_SystemConsoleUser** 硬件清单报表类在安全事件日志中仅保留前 90 天的成功登录事件数据，而不考虑日志的长度。 如果安全事件日志包含少于 90 天的数据，则读取整个日志。|  
  
## Configuration Manager 的内部依赖关系  
 下表提供 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 内部的资产智能依赖关系。  
  
|依赖关系|更多信息|  
|----------|----------|  
|客户端代理先决条件|资产智能报表依赖于通过客户端硬件和软件清单报表获取的客户端信息。 要获取所有资产智能报表所需的信息，必须启用下列客户端代理：<br /><br /> -   硬件清单客户端代理<br />-   软件计数客户端代理|  
|硬件清单客户端代理依赖关系|要收集某些资产智能报表所需的清单数据，必须启用硬件清单客户端代理。 此外，还必须在主站点服务器计算机上启用资产智能报表所依赖于的一些硬件清单报表类。<br /><br /> 有关启用硬件清单客户端代理的信息，请参阅[如何在 System Center Configuration Manager 中扩展硬件清单](../LocTest/How-to-extend-hardware-inventory-in-System-Center-Configuration-Manager.md)。|  
|软件计数客户端代理依赖关系|若干资产智能软件报表均依赖于软件计数客户端代理提供数据。 有关启用软件计数客户端代理的信息，请参阅[在 System Center Configuration Manager 中使用软件计数监视应用使用情况](../LocTest/Monitor-app-usage-with-software-metering-in-System-Center-Configuration-Manager.md)。<br /><br /> 下列资产智能报表依赖于软件计数客户端代理提供数据：<br /><br /> -   软件 07A \- 按计算机数列出的最近使用过的可执行文件<br />-   软件 07B \- 最近使用过指定的可执行文件的计算机<br />-   软件 07C \- 特定计算机上最近使用的可执行文件<br />-   软件 08A \- 按用户数列出的最近使用过的可执行文件<br />-   软件 08B \- 最近使用过指定的可执行文件的用户<br />-   软件 08C \- 指定用户最近使用过的可执行文件|  
|资产智能硬件清单报表类先决条件|[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的资产智能报表依赖于特定硬件清单报表类。 在硬件清单报表类已启用并且客户端基于这些类报告了硬件清单之前，关联资产智能报表不包含任何数据。 可以启用以下硬件清单报表类以支持资产智能报表要求：<br /><br /> -   SMS\_SystemConsoleUsage<sup>1</sup><br />-   SMS\_SystemConsoleUser<sup>1</sup><br />-   SMS\_InstalledSoftware<br />-   SMS\_AutoStartSoftware<br />-   SMS\_BrowserHelperObject<br />-   Win32\_USBDevice<br />-   SMS\_InstalledExecutable<br />-   SMS\_SoftwareShortcut<br />-   SoftwareLicensingService<br />-   SoftwareLicensingProduct<br />-   SMS\_SoftwareTag<br /><br /> <sup>1</sup> 默认情况下，**SMS\_SystemConsoleUsage** 和 **SMS\_SystemConsoleUser** 资产智能硬件清单报表类处于启用状态。<br /><br /> 可以在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台的“资产和符合性”工作区中，在单击“资产智能”节点时编辑资产智能硬件清单报表类。 有关详细信息，请参阅[启用资产智能硬件清单报表类](../LocTest/Configuring-Asset-Intelligence-in-System-Center-Configuration-Manager.md#BKMK_EnableAssetIntelligence)主题中的[在 System Center Configuration Manager 中配置资产智能](../LocTest/Configuring-Asset-Intelligence-in-System-Center-Configuration-Manager.md)部分。|  
|Reporting Services 点|必须先安装 Reporting Services 点站点系统角色才能显示软件更新报表。 有关创建 Reporting Services 点的详细信息，请参阅[在 Configuration Manager 中配置报表](http://go.microsoft.com/fwlink/p/?LinkId=232661)。|  
  
## 请参阅  
 [System Center Configuration Manager 中的资产智能](../LocTest/Asset-Intelligence-in-System-Center-Configuration-Manager.md)
---
title: "在 System Center Configuration Manager 中使用软件计数监视应用使用情况"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-app
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: b1fdaee2-2816-4447-94cd-609f6948f215
caps.latest.revision: 8
caps.handback.revision: 5
author: barlanmsft
---
# 在 System Center Configuration Manager 中使用软件计数监视应用使用情况
使用 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的软件计数监视和收集 Windows PC 上的软件使用数据。  
  
 若要收集此使用数据，需配置软件计数规则或使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 收集的清单来自动生成这些规则。 客户端评估这些规则，并收集计数数据以发送到站点。 当未连接到站点时，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端继续收集使用数据并在重新建立连接时发送此信息。  
  
 从客户端收集使用数据之后，可以使用不同的方式来查看数据，包括使用集合、查询和报告。 此数据与来自软件清单的数据组合使用可以协助您的组织确定下列事项：  
  
-   特定应用有多少个副本部署到你的组织中的 PC 上。 在这些 PC 中，你可以确定有多少用户实际运行此应用。  
  
-   在与应用供应商续订许可协议时，需要购买多少特定的应用许可证。  
  
-   是否有用户仍在运行特定的应用。 如果未使用该应用，你可将其停用。  
  
-   一天中最常使用某个应用的时间。  
  
> [!IMPORTANT]  
>  软件计数用于监视文件名以“.exe”结尾的 Windows 桌面应用。 软件计数不监视现代 Windows 应用（例如 Windows 8 曾使用的应用）。  
  
 本主题包含有关如何使用软件计数来解决业务问题的示例方案。 有关所有可以使用的选项的详细信息，请参阅[System Center Configuration Manager 中的软件计数](../LocTest/Software-metering-in-System-Center-Configuration-Manager.md)。  
  
## 使用软件计数的示例方案  
 在本部分中，可以创建一个示例软件计数规则，它可以帮助解决下列业务要求：  
  
-   确定公司中有多少特定应用的副本。  
  
-   发现任何未使用的应用副本  
  
-   确定哪些用户定期使用特定应用  
  
 Woodgrove Bank 部署了 Microsoft Office 2010 作为其标准的办公生产力套件。 但是，若要支持旧应用程序，有些计算机必须继续运行 Microsoft Office Word 2003。 IT 部门要减少支持和授权成本，如果不再使用旧应用程序，则需要删除这些 Word 2003 副本。 技术支持还需要识别哪些用户使用旧应用程序。  
  
 John 是 Woodgrove Bank 的 IT 系统经理，他使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的软件计数来实现这些业务目标。 他执行下表中的操作：  
  
|过程|参考|  
|--------|--------|  
|John 检查软件计数的先决条件，并确认 Reporting Services 点安装且正常运行。|[软件计数的先决条件](../LocTest/Software-metering-in-System-Center-Configuration-Manager.md#BKMK_Pre)|  
|John 配置软件计数的默认客户端设置：<br /><br /> -   John 启用软件计数，并且使用每七天一次的默认数据收集计划。<br />-   他通过配置软件清单客户端设置“列出这些文件类型的清单”，来配置软件清单以列出具有 .exe 扩展名的清单。<br />-   他添加了一条名为“woodgrove.exe”的新软件计数规则，用于监视银行的旧应用程序。|[配置软件计数](../LocTest/Software-metering-in-System-Center-Configuration-Manager.md#BKMK_Config)<br /><br /> [创建软件计数规则](../LocTest/Software-metering-in-System-Center-Configuration-Manager.md#BKMK_Create)|  
|John 等待七天后，客户端计算机开始报告“woodgrove.exe”可执行文件的使用数据。||  
|John 使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 报表“所有计数软件程序的安装基础”来查看哪些计算机加载了应用程序“woodgrove.exe”。|[监视软件计数](../LocTest/Software-metering-in-System-Center-Configuration-Manager.md#BKMK_Monitor)|  
|六个月后，他使用报表“已安装计数程序，但在指定的日期后尚未运行此程序的计算机”，指定软件计数规则以及六个月以前的一个日期。 此报表识别了在过去六个月内未运行该程序的 120 台计算机。|[监视软件计数](../LocTest/Software-metering-in-System-Center-Configuration-Manager.md#BKMK_Monitor)|  
|John 进行进一步检查，以确认标识的计算机上不再需要旧应用程序。 然后他从这些计算机中卸载旧应用程序和 Word 2003 副本。<br /><br /> John 运行该报表“已运行特定计数的软件程序的用户”来为技术支持提供继续使用旧应用程序的用户的列表。|无更多信息。|  
|John 继续每周检查软件计数报表，并在必要时采取修正措施。|[监视软件计数](../LocTest/Software-metering-in-System-Center-Configuration-Manager.md#BKMK_Monitor)|  
  
 进行这一系列操作的结果就是，通过删除不再需要的应用程序，减少了 IT 支持与授权成本。 此外，技术支持人员现在获得了他们想要的运行旧应用程序的用户的列表。  
  
## 请参阅  
 [使用 System Center Configuration Manager 监视应用程序](../LocTest/Monitor-applications-with-System-Center-Configuration-Manager.md)
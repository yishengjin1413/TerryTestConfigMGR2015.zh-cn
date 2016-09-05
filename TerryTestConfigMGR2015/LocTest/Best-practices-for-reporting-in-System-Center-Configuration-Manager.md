---
title: "System Center Configuration Manager 中报告的最佳做法"
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
ms.assetid: 64f9d931-33f1-456f-a4e4-0ec077465bd0
caps.latest.revision: 4
caps.handback.revision: 4
---
# System Center Configuration Manager 中报告的最佳做法
下列最佳方案适用于 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的报表：  
  
## 为了获得最佳性能，请将 Reporting Services 点安装在远程站点系统服务器上  
 尽管你可以将 Reporting Services 点安装在站点服务器或远程站点系统上，但如果将 Reporting Services 点安装在远程站点系统服务器上，性能将得到提升。  
  
## 优化 SQL Server Reporting Services 查询  
 通常，任何报表延迟都是由于运行查询和检索结果所花费的时间导致的。 如果你在使用 Microsoft SQL Server，则诸如查询分析器和事件探查器等工具可帮助你优化查询。  
  
## 将报表订阅处理安排在标准办公时间之外运行  
 请尽可能将报表订阅处理安排在正常标准办公时间之外进行，以最大程度地减少 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点数据库服务器上的 CPU 处理。 这种方案还可改善不可预测报表请求的可用性。  
  
## 请参阅  
 [规划 System Center Configuration Manager 中的报告](../LocTest/Planning-for-reporting-in-System-Center-Configuration-Manager.md)
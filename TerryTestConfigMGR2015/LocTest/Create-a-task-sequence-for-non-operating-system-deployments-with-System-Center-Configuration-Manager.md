---
title: "使用 System Center Configuration Manager 创建用于非操作系统部署的任务序列"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-osd
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 92aaec8a-8751-442a-b64b-62ab05b5bf50
caps.latest.revision: 6
caps.handback.revision: 5
translationtype: Human Translation
---
# 使用 System Center Configuration Manager 创建用于非操作系统部署的任务序列
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的任务序列用于自动执行你环境中的各种任务。 这些任务经过测试主要设计用于部署操作系统。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 具有许多其他功能，这些功能将是以下这些方案采用的主要技术：[应用程序安装](http://technet.microsoft.com/library/mt627959\(TechNet.10\).aspx)、[软件更新安装](http://technet.microsoft.com/library/mt634340\(TechNet.10\).aspx)、[设置配置](http://technet.microsoft.com/library/mt629310\(TechNet.10\).aspx)或自定义自动化。 此外，你也可以考虑诸如 [Orchestrator](https://technet.microsoft.com/library/hh237242.aspx) 和 [Service Management Automation](https://technet.microsoft.com/library/dn469260.aspx) 等其他 Microsoft System Center 自动化技术。  
  
 任务序列的强大功能在于其灵活性以及如何使用它们配置客户端设置、分发软件、更新驱动程序、编辑用户状态并执行独立于操作系统部署的其他任务。 你可以创建自定义任务序列以添加任意数量的任务。 虽然支持将自定义任务序列用于非操作系统部署的这种基本使用，但还没有方法可以测试所有可能的配置并且当你开发更为复杂的任务序列时，遇到问题的可能性也会增加。  
  
 以下步骤可用于非操作系统部署自定义任务序列。  
  
-   [检查准备情况](../LocTest/Task-sequence-steps-in-System-Center-Configuration-Manager.md#BKMK_CheckReadiness)  
  
-   [连接到网络文件夹](../LocTest/Task-sequence-steps-in-System-Center-Configuration-Manager.md#BKMK_ConnectToNetworkFolder)  
  
-   [下载包内容](../LocTest/Task-sequence-steps-in-System-Center-Configuration-Manager.md#BKMK_DownloadPackageContent)  
  
-   [安装应用程序](../LocTest/Task-sequence-steps-in-System-Center-Configuration-Manager.md#BKMK_InstallApplication)  
  
-   [安装包](../LocTest/Task-sequence-steps-in-System-Center-Configuration-Manager.md#BKMK_InstallPackage)  
  
-   [安装软件更新](../LocTest/Task-sequence-steps-in-System-Center-Configuration-Manager.md#BKMK_InstallSoftwareUpdates)  
  
-   [重启计算机](../LocTest/Task-sequence-steps-in-System-Center-Configuration-Manager.md#BKMK_RestartComputer)  
  
-   [运行命令行](../LocTest/Task-sequence-steps-in-System-Center-Configuration-Manager.md#BKMK_RunCommandLine)  
  
-   [运行 PowerShell 脚本](../LocTest/Task-sequence-steps-in-System-Center-Configuration-Manager.md#BKMK_RunPowerShellScript)  
  
-   [设置动态变量](../LocTest/Task-sequence-steps-in-System-Center-Configuration-Manager.md#BKMK_SetDynamicVariables)  
  
-   [设置任务序列变量](../LocTest/Task-sequence-steps-in-System-Center-Configuration-Manager.md#BKMK_SetTaskSequenceVariable)  
  
## 请参阅  
 [使用 System Center Configuration Manager 创建自定义任务序列](../LocTest/Create-a-custom-task-sequence-with-System-Center-Configuration-Manager.md)
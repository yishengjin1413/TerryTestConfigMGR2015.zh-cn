---
title: "如何在 System Center Configuration Manager 中创建 App-V 虚拟环境"
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
ms.assetid: b6b86078-fcc4-46cf-87d6-4b52b914b712
caps.latest.revision: 6
caps.handback.revision: 5
author: barlanmsft
---
# 如何在 System Center Configuration Manager 中创建 App-V 虚拟环境
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的 Microsoft Application Virtualization \(App\-V\) 虚拟环境能让所部署的虚拟应用程序在客户端计算机上共享相同的文件系统和注册表。 这意味着这些应用程序可以互相共享数据（这与标准的虚拟应用程序不同）。 在安装应用程序时，或者在客户端接下来评估已安装的应用程序时，会在客户端计算机上创建或修改虚拟环境。 可以对这些应用程序进行排序，以便在多个应用程序尝试修改一个文件系统或注册表值时，排在最前面的应用程序优先进行修改。  
  
> [!IMPORTANT]  
>  不要依靠 App\-V 虚拟环境来提供安全保护（例如抵御恶意软件）。  
  
 使用下列过程在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中创建 App\-V 虚拟环境。  
  
### 创建 App\-V 虚拟环境  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“软件库”。  
  
2.  在“软件库”工作区中，展开“应用程序管理”，然后单击“App\-V 虚拟环境”。  
  
3.  在“主页”选项卡的“创建”组中，单击“创建虚拟环境”。  
  
4.  在“创建虚拟环境”对话框中，指定下列信息：  
  
    -   **名称** \- 指定虚拟环境的唯一名称（最多 128 个字符）。  
  
    -   **描述** \- 根据需要指定虚拟环境的描述。  
  
5.  单击“添加”以将新的部署类型添加到虚拟环境中。 必须添加至少一种部署类型。  
  
6.  在“添加应用程序”对话框中，指定最长为 128 个字符的“组名”，此名称将用于指代你添加到虚拟环境中的那一组应用程序。  
  
7.  单击“添加”，选择你要添加到组中的 App\-V 5 应用程序和部署类型，然后单击“确定”。  
  
8.  在“添加应用程序”对话框中，可以单击“升序”或“降序”，以指定在多个应用程序尝试修改同一个虚拟环境中的文件系统或注册表设置时哪个应用程序将优先进行修改。  
  
9. 单击“确定”以返回到“创建虚拟环境”对话框。  
  
10. 在完成添加组的操作后，单击“确定”以创建虚拟环境。 新的虚拟环境显示在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台的“App\-V 虚拟环境”节点中。 可以使用“App\-V 虚拟环境状态”报告来监视虚拟环境的状态。  
  
    > [!NOTE]  
    >  在安装应用程序时，或者在客户端接下来评估已安装的应用程序时，会在客户端计算机上添加或修改虚拟环境。  
  
## 请参阅  
 [System Center Configuration Manager 中应用程序管理的技术参考](../LocTest/Application-management-technical-reference-for-System-Center-Configuration-Manager.md)
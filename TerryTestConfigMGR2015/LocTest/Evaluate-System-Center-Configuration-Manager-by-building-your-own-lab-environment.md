---
title: "通过构建你自己的实验室环境来评估 System Center Configuration Manager"
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
ms.assetid: 01b30260-f03a-4851-a549-d1b76e8cfc69
caps.latest.revision: 25
caps.handback.revision: 24
author: barlanmsft
translationtype: Human Translation
---
# 通过构建你自己的实验室环境来评估 System Center Configuration Manager
了解如何创建实验室环境来评估 System Center Configuration Manager 在组织中的使用。  
  
## 通过构建你自己的实验室环境来评估 System Center Configuration Manager  
 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 是一种功能全面的强大工具，用于管理用户、设备和软件。 我们建议你在完整部署之前完成 [!INCLUDE[cmshortname](../LocTest/includes/cmshortname_md.md)] 的全面评估，以便能够将概念性理解和实际练习相结合。  
  
 本指南主要由管理员用于评估企业环境中 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的使用。  
  
-   正在寻找用于完全管理 PC、服务器和移动设备的解决方案的管理员  
  
-   既要求本地设备管理的安全性、又要求基于云的设备管理的灵活性的高安全性行业中的管理员  
  
-   希望能够扩大本地服务器体系结构的管理员  
  
### 此实验室能做什么  
 创建此环境的主要目的是提供着手使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 所需的常规知识，并通过操作增强你对 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的理解。 通过引导你快速组装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的当前版本来实现这一目标，将使用两台服务器：  
  
-   一台用于托管 Active Directory、域控制器和 DNS 服务器  
  
-   另一台用于托管 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 以及所有关联的 SQL Server 组件。  
  
-   在 Hyper\-V 内安装客户端计算机。 实验室本身也可以作为完全虚拟化的系统在一台服务器上运行。  
  
### 此实验室不能做什么  
 此实验室将不逐一演示 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 方案，且不适合立即迁移到活动环境中。  
  
 构建此实验室，你将获得一个用于工作的功能性环境。 但是，此环境将不针对系统性能、硬盘空间管理、SQL Server 存储等进行优化。  
  
###  <a name="BKMK_EvalRec"></a> 开始构建实验室前推荐阅读的内容  
 [System Center Configuration Manager 文档](../LocTest/Documentation-for-System-Center-Configuration-Manager.md)中提供了大量内容。 以下包含了此库中的精选主题，建议所有从事实验工作的管理员在开始这些练习之前阅读这些主题。  
  
-   在 [System Center Configuration Manager 简介](../LocTest/Introduction-to-System-Center-Configuration-Manager.md)中，可以了解 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台、最终用户门户和示例方案的核心概念  
  
-   在 [System Center Configuration Manager 的特性和功能](../LocTest/Features-and-capabilities-of-System-Center-Configuration-Manager.md)中，可以了解 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的主要管理功能  
  
-   通过 [System Center Configuration Manager 基础知识](../LocTest/Fundamentals-of-System-Center-Configuration-Manager.md)，可以巩固理解  
  
-   在 [System Center Configuration Manager 的基于角色的管理基础](../LocTest/Fundamentals-of-role-based-administration-for-System-Center-Configuration-Manager.md)中，可以了解安全角色的重要性  
  
-   理解这些[内容管理的概念](../LocTest/Fundamental-concepts-for-content-management-in-System-Center-Configuration-Manager.md#bkmk_Concepts)，可以让你认识与内容管理相关的特定概念  
  
-   [了解客户端如何查找 System Center Configuration Manager 的站点资源和服务](../LocTest/Understand-how-clients-find-site-resources-and-services-for-System-Center-Configuration-Manager.md)，可以成功支持部署中的所有日常操作  
  
## 请参阅  
 [设置你的 System Center Configuration Manager 实验室](../LocTest/Set-up-your-System-Center-Configuration-Manager-lab.md)
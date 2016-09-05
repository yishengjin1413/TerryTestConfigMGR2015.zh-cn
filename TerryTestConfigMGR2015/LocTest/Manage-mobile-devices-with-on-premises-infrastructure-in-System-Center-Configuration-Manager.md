---
title: "在 System Center Configuration Manager 中使用本地基础结构管理移动设备"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-client
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 497c05c7-fe9f-4b88-983b-1c5b3d59308e
caps.latest.revision: 8
caps.handback.revision: 3
---
# 在 System Center Configuration Manager 中使用本地基础结构管理移动设备
[!INCLUDE[onprem_first](../LocTest/includes/onprem_first_md.md)] 是一个设备管理解决方案，它在使用企业的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 基础结构管理和维护设备时，（基于开放移动联盟设备管理或 OMA DM 标准）需要依赖设备操作系统的内置管理功能。 这不同于 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)]，后者还依赖于内置的 OMA DM 功能，但所有管理功能都通过云服务提供。[!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 也不同于基于客户端的管理解决方案（过去由 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 提供），因为它依赖类似于企业的基础结构而不是使用其管理的计算机和设备上独立安装的客户端软件。  
  
 下表列出了 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 与传统基于客户端管理相比的优缺点：  
  
|优点|缺点|  
|--------|--------|  
|**简化了基础结构** \- 需要的站点系统角色更少。<br /><br /> **更易于维护** \- 由于管理功能是内置于设备操作系统的，因此当向 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 系统引入新的管理功能时将不再需要新版本的客户端软件。<br /><br /> **本地** \- 所有管理和数据均保留在本地。|**客户端管理功能更少** \- 没有业务流程、软件计数、第三方集成、任务序列或软件中心支持。<br /><br /> **设备支持有限** \- 当前 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 仅支持运行 Windows 10 和 Windows 10 移动版的设备。|  
  
 以下主题提供的信息可用于 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 规划、准备和注册设备：  
  
-   [在 System Center Configuration Manager 中规划本地移动设备管理](../LocTest/Plan-for-On-premises-Mobile-Device-Management-in-System-Center-Configuration-Manager.md)  
  
     了解在 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 中设置 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 基础结构和规划设备注册时需要考虑的事项。  
  
-   [用于 System Center Configuration Manager 中本地移动设备管理的准备步骤](../LocTest/Preparation-steps-for-On-premises-Mobile-Device-Management-in-System-Center-Configuration-Manager.md)  
  
     了解如何通过设置 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 订阅、设置证书、安装站点系统角色和设置设备注册为 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 准备 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 系统。  
  
-   [在 System Center Configuration Manager 中为本地移动设备管理注册设备](../LocTest/Enroll-devices-for-On-premises-Mobile-Device-Management-in-System-Center-Configuration-Manager.md)  
  
     了解如何进行注册、用户如何注册其自己的设备，以及如何使用注册包批量注册设备。  
  
## 请参阅  
 [使用 System Center Configuration Manager 管理计算机和设备](../LocTest/Manage-computers-and-devices-with-System-Center-Configuration-Manager.md)
---
title: "System Center Configuration Manager 中软件更新的最佳方案"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-sum
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 6d20389a-9de2-4a64-bced-9fc4fa519174
caps.latest.revision: 6
caps.handback.revision: 5
---
# System Center Configuration Manager 中软件更新的最佳方案
本主题包括 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中软件更新的最佳方案。 此信息分类为初始安装和当前操作的最佳方案。  
  
## 安装最佳方案  
 在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中安装软件更新时，请使用下列最佳方案。  
  
### 为软件更新点使用共享 WSUS 数据库  
 在主站点上安装多个软件更新点时，请为同一 Active Directory 林中的每个软件更新点使用同一 WSUS 数据库。 通过共享同一数据库，你可以明显减轻在客户端切换到新软件更新点时可能产生的客户端和网络性能影响。 当客户端切换到与旧软件更新点共享数据库的新软件更新点时，仍会进行增量扫描，但此扫描相对于在 WSUS 服务器有自己的数据库的情况下所进行的扫描要小很多。  
  
> [!IMPORTANT]  
>  为软件更新点使用共享的 WSUS 数据库时，还必须共享本地 WSUS 内容文件夹。  
  
 有关软件更新点切换的详细信息，请参阅[Software update point switching](../LocTest/Plan-for-software-updates-in-System-Center-Configuration-Manager.md#BKMK_SUPSwitching)主题中的[在 System Center Configuration Manager 中规划软件更新](../LocTest/Plan-for-software-updates-in-System-Center-Configuration-Manager.md)部分。  
  
### 当 Configuration Manager 和 WSUS 使用同一 SQL Server 时，请将其中的一个配置为使用命名实例，并将另一个配置为使用 SQL Server 的默认实例  
 当 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 和 WSUS 数据库使用同一 SQL Server 并共享 SQL Server 的同一实例时，你将无法轻松确定两个应用程序之间的资源使用情况。 如果为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 和 WSUS 使用不同的 SQL Server 实例，将可以更轻松地解决和诊断每个应用程序可能发生的资源使用问题。  
  
### 为 WSUS 安装指定“本地存储更新”设置  
 当安装 WSUS 3.0 时，选择“本地存储更新”设置。 如果选择此设置，则会在同步过程中下载与软件更新关联的许可条款，并存储在 WSUS 服务器的本地硬盘驱动器上。 如果未选择此设置，则客户端计算机可能无法扫描具有许可条款的软件更新的软件更新符合性。 当你安装软件更新点时，WSUS Synchronization Manager 默认情况下将每隔 60 分钟验证一次是否启用了此设置。  
  
## 操作最佳方案  
 在使用软件更新时，请使用下列最佳方案：  
  
### 将单个软件更新部署中的软件更新数限制为 1000  
 你必须为每个软件更新部署将软件更新数限制为 1000。 在创建自动部署规则时，请验证你指定的条件不会产生超过 1000 个软件更新。 在手动部署软件更新时，请不要选择超过 1000 个更新进行部署。  
  
### 在自动部署规则每次为“周二补丁日”和一般部署运行时创建一个新软件更新组  
 软件更新部署的软件更新数限制为 1000 个。 在创建自动部署规则时，将指定是使用现有更新组还是在规则每次运行时创建新更新组。 如果在自动部署规则中指定的条件产生多个软件更新，并且规则定期运行，请指定在规则每次运行时创建新的软件更新组。 这将防止部署超过每个部署 1000 个软件更新的限制。  
  
### 为 Endpoint Protection 定义更新的自动部署规则使用现有软件更新组  
 如果经常使用自动部署规则来部署 Endpoint Protection 定义更新，请始终使用现有软件更新组。 否则，可能会在一段时间内创建数百个软件更新组。 通常，定义更新发布者会将定义更新设置为在被四个较新的更新取代时过期。 因此，自动部署规则创建的软件更新组最多只能包含发布者的 4 个定义更新：1 个活动更新和 3 个被取代的更新。  
  
## 请参阅  
 [在 System Center Configuration Manager 中规划软件更新](../LocTest/Plan-for-software-updates-in-System-Center-Configuration-Manager.md)
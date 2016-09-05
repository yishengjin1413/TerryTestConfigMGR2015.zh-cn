---
title: "使用 System Center Configuration Manager 创建 Windows Embedded 应用程序"
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
ms.assetid: 16acfd63-0c40-424c-82f4-8c63f7f1c30b
caps.latest.revision: 7
caps.handback.revision: 6
author: barlanmsft
---
# 使用 System Center Configuration Manager 创建 Windows Embedded 应用程序
除了创建应用程序的其他 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 要求和过程，你还必须在创建和部署适用于 Windows Embedded 设备的应用程序时考虑以下注意事项。  
  
## 一般注意事项  
  
-   将应用程序部署到启用了写入筛选器的 Windows Embedded 设备时，你可以指定是否在部署过程中对设备禁用写入筛选器，然后在部署后重启设备。 如果未禁用写入筛选器，则软件会部署到临时覆盖区，并且重启设备后将不再安装软件，除非另一部署强制保留更改。  
  
-   将应用程序部署到 Windows Embedded 设备时，确保设备是配置了维护时段的集合的成员。 这样，你可以管理禁用和启用写入筛选器的时间，以及设备重启的时间。  
  
-   控制写入筛选器行为的用户体验设置是一个名为“在截止时间或在维护时段内提交更改\(需要重启\)”的复选框。  
  
## 部署应用程序提示  
  
### 为启用了写入筛选器的 Windows Embedded 设备使用必需的应用程序（而不是可用应用程序）  
 由于用户无法从启用了写入筛选器的 Windows Embedded 设备中通过软件中心安装应用程序，因此请在部署应用程序时始终以对这些设备必需为部署目标，而不是对这些设备可用。 通常这不会有问题，因为运行 Windows Embedded 操作系统的计算机通常运行必须为多个用户采用相同方式运行的单一应用程序。 正因为如此，IT 部门会严密管理和锁定这些设备。 必需的应用程序非常适合于这种情况。 但是，如果在启用了写入筛选器的情况下用户确实在嵌入式设备上运行多个应用程序，请将以下限制告知这些用户：  
  
-   用户无法通过软件中心安装所需的软件。  
  
-   用户无法在软件中心的“选项”选项卡上更改其工作时间。  
  
-   用户无法推迟必需应用程序的安装。  
  
 此外，如果 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]为软件安装和更新提交更改，低权限用户将无法在维护期间登录。 在此期间，用户将看到一条消息，告知他们设备由于正在维护而不可用。  
  
### 如果应用程序要求用户接受许可条款，请不要将应用程序部署到启用了写入筛选器的 Windows Embedded 设备  
 在禁用了写入筛选器以便 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 能够在嵌入式设备上安装软件时，低权限用户将无法登录到设备。 如果安装要求用户接受许可条款，这将无法进行，并且安装将失败。 如果安装需要用户交互，请确保不要将软件部署到 Windows Embedded 设备。 你可以使用“适用平台”列表来筛选这些操作系统。  
  
## 请参阅  
 [使用 System Center Configuration Manager 创建和部署应用程序](../LocTest/Create-and-deploy-an-application-with-System-Center-Configuration-Manager.md)
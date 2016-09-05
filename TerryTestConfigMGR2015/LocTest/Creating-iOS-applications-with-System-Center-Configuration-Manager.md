---
title: "使用 System Center Configuration Manager 创建 iOS 应用程序"
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
ms.assetid: d5420109-6538-4430-9ca6-db352ee84c2e
caps.latest.revision: 10
caps.handback.revision: 5
author: barlanmsft
translationtype: Human Translation
---
# 使用 System Center Configuration Manager 创建 iOS 应用程序
除了创建应用程序的其他 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 要求和过程，还必须在创建和部署适用于 iOS 设备的应用程序时考虑以下注意事项。  
  
## 一般注意事项  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 支持部署以下应用类型：  
  
|设备类型|受支持的文件|  
|----------|------------|  
|iOS|\*.ipa **Note:**  在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中，不需要在导入 iOS 应用时指定属性列表 \(.plist\) 文件。|  
  
 支持以下部署操作：  
  
|设备类型|支持的操作|  
|----------|-----------|  
|iOS 和 Mac OS X（当向 Intune 注册时）|可用、必需的（但用户必须同意安装）、卸载|  
  
> [!IMPORTANT]  
>  目前，最终用户无法从 iOS 的 Microsoft Intune 公司门户应用程序中安装公司应用程序。 这是由于 iOS 应用商店中发布的应用受到限制（请参阅应用商店查看准则，第 2 部分）。 用户可通过浏览到 Intune Web 门户 \(portal.manage.microsoft.com\) 在其设备上安装企业应用（包括托管的应用商店应用和业务线应用包）。 有关由 Intune 公司门户应用启用的移动管理功能的详细信息，请参阅 [Microsoft Intune 中的移动设备管理功能](https://technet.microsoft.com/library/dn600287.aspx)。  
  
## 请参阅  
 [使用 System Center Configuration Manager 部署并管理应用程序](../LocTest/Deploy-and-manage-applications-with-System-Center-Configuration-Manager.md)
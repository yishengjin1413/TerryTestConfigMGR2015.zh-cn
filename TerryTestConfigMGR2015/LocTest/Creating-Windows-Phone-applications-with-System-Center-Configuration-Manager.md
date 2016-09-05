---
title: "使用 System Center Configuration Manager 创建 Windows Phone 应用程序"
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
ms.assetid: 866113ff-efd0-40d2-ac3a-2edd49732a24
caps.latest.revision: 10
caps.handback.revision: 7
author: barlanmsft
translationtype: Human Translation
---
# 使用 System Center Configuration Manager 创建 Windows Phone 应用程序
除了创建应用程序的其他 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 要求和过程外，在创建和部署适用于 Windows Phone 设备的应用程序时还必须考虑以下注意事项。  
  
## 一般注意事项  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 支持部署以下应用类型：  
  
|设备类型|受支持的文件|  
|----------|------------|  
|Windows Phone 8|\*.xap|  
|Windows Phone 8.1|\*.xap、\*.appx、\*.appxbundle|  
  
 支持以下部署操作：  
  
|设备类型|支持的操作|  
|----------|-----------|  
|Windows Phone 8 和 Windows Phone 8.1|可用、要求、卸载|  
  
## 使用取代来部署最新 Windows Phone 公司门户应用的步骤  
 下表提供了创建和部署最新 Windows Phone 8 公司门户应用的步骤、详细信息和更多信息。  
  
|步骤|更多信息|  
|--------|----------|  
|**步骤 1：**获取最新的公司门户应用。|下载 [Windows Phone 8 公司门户应用](http://go.microsoft.com/fwlink/?LinkId=268440)。|  
|**步骤 2：**使用 Symantec 证书对公司门户应用进行签名。|有关如何对公司门户应用进行签名的信息，请参见 [使用 System Center Configuration Manager 和 Microsoft Intune 设置 Windows Phone 和 Windows 10 移动混合设备管理](../LocTest/Set-up-Windows-Phone-and-Windows-10-Mobile-hybrid-device-management-with-System-Center-Configuration-Manager-and-Microsoft-Intune.md)。|  
|**步骤 3：**使用公司门户应用的最新版本创建新的应用程序，并指定取代关系。|有关详细信息，请参阅 [如何使用 System Center Configuration Manager 创建应用程序](../LocTest/How-to-create-applications-with-System-Center-Configuration-Manager.md) 和 [如何在 System Center Configuration Manager 中修订和取代应用程序](../LocTest/How-to-revise-and-supersede-applications-in-System-Center-Configuration-Manager.md)。|  
|**步骤 4：**将该应用程序添加到 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 订阅向导。|添加 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 订阅向导的应用程序 Windows Phone 8 页面。 有关详细信息，请参阅 [使用 System Center Configuration Manager 和 Microsoft Intune 设置 Windows Phone 和 Windows 10 移动混合设备管理](../LocTest/Set-up-Windows-Phone-and-Windows-10-Mobile-hybrid-device-management-with-System-Center-Configuration-Manager-and-Microsoft-Intune.md)。|  
|**步骤 5：**删除向 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 订阅向导添加公司门户应用时自动创建的部署。|[!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 订阅已创建了此应用的自动部署，因为此部署将不支持取代。|  
|**步骤 6：**在“部署软件向导”的“部署设置”页面创建新应用程序部署，并检查“自动升级此应用程序的任何取代版本”。|使用取代功能以及用取代关系创建的应用程序来创建新部署。|  
|**步骤 7（可选）：**默认情况下，7 天后将在设备上安装取代应用。 为了更快地将公司门户应用部署到以前注册的设备，你可以将“计划部署的重新评估”设置更改为较低的值。 **Important:**  将此值设置为低于默认值的值可能会对网络和客户端计算机性能有负面影响。|有关详细信息，请参阅 [使用 System Center Configuration Manager 部署并管理应用程序](../LocTest/Deploy-and-manage-applications-with-System-Center-Configuration-Manager.md)。|  
  
## 请参阅  
 [使用 System Center Configuration Manager 部署并管理应用程序](../LocTest/Deploy-and-manage-applications-with-System-Center-Configuration-Manager.md)
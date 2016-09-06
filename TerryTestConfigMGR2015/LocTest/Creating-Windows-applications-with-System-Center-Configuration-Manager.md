---
title: "使用 System Center Configuration Manager 创建 Windows 应用程序"
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
ms.assetid: 9181c84e-d74f-44ea-9bb9-f7805eb465fc
caps.latest.revision: 8
caps.handback.revision: 7
author: barlanmsft
translationtype: Human Translation
---
# 使用 System Center Configuration Manager 创建 Windows 应用程序
除了创建应用程序的其他 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 要求和过程外，在创建和部署适用于 Windows 设备的应用程序时还必须考虑以下注意事项。  
  
## 一般注意事项  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 支持部署以下应用类型：  
  
|设备类型|受支持的文件|  
|----------|------------|  
|Windows RT 和 Windows RT 8.1|\*.appx、\*.appxbundle|  
|注册为移动设备的 Windows 8.1 和更高版本|\*.appx、\*.appxbundle|  
  
 支持以下部署操作：  
  
|设备类型|支持的操作|  
|----------|-----------|  
|Windows 8.1 及更高版本|可用、要求。 卸载|  
|Windows RT|可用、要求、卸载|  
  
## 对通用 Windows 平台 \(UWP\) 应用的支持  
 Windows 10 设备安装业务线应用时无需旁加载密钥。 但是，注册表项 **HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\Appx\\AllowAllTrustedApps** 必须将值设置为“1”才能启用旁加载。  
  
 如果未配置此注册表项，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 在你第一次向设备部署应用时会自动将此值设置为“1”。 如果将此值设置为“0”，则 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将无法自动更改此值，业务线应用部署将失败。  
  
 通用 Windows 平台业务线应用必须使用代码签名证书签名，并且该证书应在应用部署到的每个设备上受信任。 你可以使用内部 PKI 基础结构中的证书，也可以使用设备上安装的第三方公共根证书中的证书。  
  
 在 Windows 10 移动版设备上，可以使用非 Symantec 代码签名证书对通用 **.appx** 应用签名。 对于 **.xap** 应用以及要在 Windows 10 移动版设备上安装且针对 Windows Phone 8.1 生成的 **.appx** 包，必须使用 Symantec 代码签名证书。  
  
## 将 Windows Installer 应用部署到已注册的 Windows 10 PC  
 **通过 MDM 的 Windows Installer \(\*.msi\)** 安装程序类型让你可以创建基于 Windows Installer 的应用并将其部署到运行 Windows 10 的已注册 PC 上。  
  
 使用此安装程序类型时，需要考虑下列注意事项：  
  
-   只能上载扩展名为 .msi 的单个文件。  
  
-   该文件的产品代码和产品版本将用于应用检测。  
  
-   将使用该应用的默认重启行为。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不控制此功能。  
  
-   将为单个用户安装每个用户 MSI 包。  
  
-   将为设备上的所有用户安装每个计算机 MSI 包。  
  
-   当每个版本的 MSI 产品代码相同时，支持应用更新。  
  
## 请参阅  
 [使用 System Center Configuration Manager 部署并管理应用程序](../LocTest/Deploy-and-manage-applications-with-System-Center-Configuration-Manager.md)
---
title: "使用 Configuration Manager 中的应用配置策略配置应用"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 74d5d776-e37d-45de-bdba-43541b03d12c
caps.latest.revision: 10
caps.handback.revision: 2
translationtype: Human Translation
---
# 使用 Configuration Manager 中的应用配置策略配置应用
使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的移动应用配置策略提供用户在运行应用时可能需要的设置。 例如，应用可能要求用户指定：  
  
-   自定义端口号  
  
-   语言设置  
  
-   安全设置  
  
-   公司徽标之类的品牌设置  
  
 如果用户输入的这些设置不正确，可能会加重支持人员的负担并降低新应用的采用率。  
  
 通过让你在运行应用之前将策略中的这些设置部署给用户，应用配置策略可消除此类问题。 随后这些设置会自动提供，用户无需执行任何操作。  
  
 无需直接向用户和设备部署这些策略， 而是在部署应用程序时，将该策略与部署类型关联。 只要应用检测到策略设置（通常在其首次运行时），即会使用它们。  
  
> [!TIP]  
>  应用配置策略目前仅在运行 iOS 7.1 及更高版本的设备上可用，并支持下列应用安装程序类型：  
>   
>  -   **iOS 应用包（\*.ipa 文件）**  
>   
>  有关应用安装类型的详细信息，请参阅 [System Center Configuration Manager 中的应用程序管理入门](../LocTest/Get-started-with-application-management-in-System-Center-Configuration-Manager.md)。  
  
## 配置应用配置策略  
 在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“软件库”。  
  
## 将应用配置策略与 Configuration Manager 应用程序关联  
  
## 请参阅  
 [使用 System Center Configuration Manager 管理和保护应用](../LocTest/Manage-and-protect-apps-with-System-Center-Configuration-Manager.md)
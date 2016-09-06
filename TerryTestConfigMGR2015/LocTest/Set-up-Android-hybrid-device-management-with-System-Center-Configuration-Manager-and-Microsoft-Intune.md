---
title: "Set up Android hybrid device management with System Center Configuration Manager and Microsoft Intune"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-hybrid
ms.tgt_pltfrm: na
ms.topic: get-started-article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: c517fe34-0130-465b-a020-bdb555878778
caps.latest.revision: 9
caps.handback.revision: 9
translationtype: Human Translation
---
# Set up Android hybrid device management with System Center Configuration Manager and Microsoft Intune
对于 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]，用户可以从 Google Play 中下载 Android 公司门户应用，以便他们可以注册 Android（包括 Samsung KNOX）设备。 利用 Android 公司门户应用，你可以管理符合性设置、擦除或删除 Android 设备、部署应用以及收集软件和硬件清单。 如果 Android 设备上未安装 Android 公司门户应用，则你不会拥有所有的管理功能，如清单和符合性设置，但是你仍然可以将应用部署到 Android 设备。  
  
## 使用 Configuration Manager 和 Intune 准备管理 Android 移动设备  
 以下步骤可让 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 管理 Android 设备。  
  
#### 若要启用 Android 注册  
  
1.  **先决条件** - 在可设置任何平台的注册之前，完成[使用 System Center Configuration Manager 和 Microsoft Intune 的混合移动设备管理 (MDM)](../LocTest/Hybrid-mobile-device-management--MDM--with-System-Center-Configuration-Manager-and-Microsoft-Intune.md) 中的先决条件和过程。  
  
2.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中的“管理”工作区中，转到“云服务” > “Microsoft Intune 订阅”。  
  
3.  在“主页”选项卡上的“订阅”组中，单击“配置平台” > “Android”。  
  
4.  在“Microsoft Intune 订阅属性”  对话框中，选择“Android”  选项卡并单击选择“启用 Android 注册”  复选框。  
  
 设置完成后，需要让用户知道如何注册其设备。 请参阅[用户需要了解的有关设备注册的内容](https://technet.microsoft.com/library/dn948527.aspx)。 此信息适用于 Microsoft Intune 和 Configuration Manager 托管的移动设备。
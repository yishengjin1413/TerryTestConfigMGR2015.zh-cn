---
title: "Set up Windows hybrid device management with System Center Configuration Manager and Microsoft Intune"
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
ms.assetid: dc1f70f5-64ab-42ab-aa91-d3858803e12f
caps.latest.revision: 9
caps.handback.revision: 9
translationtype: Human Translation
---
# Set up Windows hybrid device management with System Center Configuration Manager and Microsoft Intune
可以结合 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 使用  [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 来管理台式机、笔记本电脑和其他将 Windows 作为移动设备运行的设备。 在管理作为移动设备的 Windows 设备之前，必须启用针对这些操作系统的移动设备注册。  
  
## 设置 Windows 设备注册  
 若要启用 Windows 移动设备管理，需要启用操作系统的管理。  
  
### 创建 DNS 别名以进行设备注册  
 通过在设备注册期间自动填充服务器名称，DNS 别名（CNAME 记录类型）可让用户更轻松地注册其设备。 若要创建 DNS 别名（CNAME 记录类型），必须在公司的 DNS 记录中配置 CNAME，将发送给公司域名中的 URL 的请求重定向到 Microsoft 的云服务服务器。  例如，贵公司的域为 contoso.com，则应在 DNS 中创建将 EnterpriseEnrollment.contoso.com 重定向到 EnterpriseEnrollment-s.manage.microsoft.com 的 CNAME。  
  
|类型|主机名|指向|  
|----------|---------------|---------------|  
|CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com|  
|CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|  
  
### 启用 Windows 设备的注册  
 若要支持注册 Windows 计算机作为移动设备进行管理，请完成以下步骤。  
  
##### 若要启用 Windows 设备的注册  
  
1.  **先决条件** - 在可设置任何平台的注册之前，必须先完成[使用 System Center Configuration Manager 和 Microsoft Intune 的混合移动设备管理 (MDM)](../LocTest/Hybrid-mobile-device-management--MDM--with-System-Center-Configuration-Manager-and-Microsoft-Intune.md) 中的先决条件和过程。  
  
2.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中的“管理”工作区中，转到“云服务” > “Microsoft Intune 订阅”。  
  
    > [!WARNING]  
    >  如果其他 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 对话框处于打开状态，请在继续执行此过程之前将其关闭。  
  
3.  在“主页”  选项卡上，单击“配置平台” ，然后单击“Windows” 。  
  
4.  在“常规”  选项卡上，选择“启用 Windows 注册” 。  
  
 设置完成后，需要让用户知道如何注册其设备。 请参阅[用户需要了解的有关设备注册的内容](https://technet.microsoft.com/library/dn948527.aspx)。 此信息适用于 Microsoft Intune 和 Configuration Manager 托管的移动设备。
---
title: "在 System Center Configuration Manager 中为本地移动设备管理设置 Microsoft Intune 订阅"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-client
ms.tgt_pltfrm: na
ms.topic: get-started-article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 1e42b1c1-3d58-481f-8647-5c7ae640c5f5
caps.latest.revision: 8
caps.handback.revision: 7
---
# 在 System Center Configuration Manager 中为本地移动设备管理设置 Microsoft Intune 订阅
[!INCLUDE[onprem_first](../LocTest/includes/onprem_first_md.md)] 需要 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 订阅，以便跟踪授权。[!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 服务不能用于管理设备或存储管理信息。 对于 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)]，由 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 基础结构来处理所有设备管理。  
  
> [!IMPORTANT]  
>  [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不支持同时使用 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 和本地 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 基础结构作为管理机构。 因此，当设置 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 订阅以用于本地管理时，你实际上禁用了 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 管理。  
  
 设置 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 服务以使用 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 涉及以下高级步骤：  
  
-   [注册 Microsoft Intune](#bkmk_signup)  
  
-   [将 Intune 订阅添加到 Configuration Manager](#bkmk_addSub)  
  
-   [为本地移动设备管理配置 Intune 订阅](#bkmk_configure)  
  
> [!TIP]  
>  我们建议先设置 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 的 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 订阅，然后再安装所需的站点系统角色，以最小化新安装站点系统角色开始正常运行所需的时间。  
  
##  <a name="bkmk_signup"></a> 注册 Microsoft Intune  
 需要 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 来让 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 正常工作。 只需针对试用或付费订阅进行[注册](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/)，然后转到下一步，将订阅添加到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]。  
  
##  <a name="bkmk_addSub"></a> 将 Intune 订阅添加到 Configuration Manager  
 若要将订阅添加到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]，请遵循通过 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 为移动设备管理添加订阅的相同基本步骤进行添加。 阅读以下有关特定差异的说明，然后使用 [使用 System Center Configuration Manager 和 Microsoft Intune 的混合移动设备管理 \(MDM\)](../LocTest/Hybrid-mobile-device-management--MDM--with-System-Center-Configuration-Manager-and-Microsoft-Intune.md) 中 [To create the Microsoft Intune subscription](../LocTest/Hybrid-mobile-device-management--MDM--with-System-Center-Configuration-Manager-and-Microsoft-Intune.md#bkmk_subscription) 内的指示。  
  
> [!NOTE]  
>  添加 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 订阅时，请记住以下内容：  
>   
>  -   添加 Microsoft Intune 订阅向导中指定的集合不用于 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 用户权限委派。 仅用于通过 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 实现的移动设备管理。 但是，需要指定一个继续执行向导所需的集合。  
> -   对于 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)]，会忽略向导中指定的站点代码设置。 使用的站点代码是你在某个注册配置文件中指定的代码，该文件授予用户注册设备的权限。  
> -   请勿启用多重身份验证。 这在 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 中不受支持。  
  
##  <a name="bkmk_configure"></a> 为本地移动设备管理配置 Intune 订阅  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，右键单击 **Microsoft Intune 订阅**，然后单击**属性**。  
  
2.  在“本地移动设备管理”框中，单击“仅管理本地设备”旁边的复选框，然后单击“确定”。  
  
    > [!NOTE]  
    >  通过单击此复选框，将会配置 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 订阅以保留所有本地管理信息且不将数据复制到云中。  
  
3.  如果打算管理 Windows 10 移动设备，请右键单击“Microsoft Intune 订阅”，单击“配置平台”，然后单击“Windows Phone”。  
  
4.  单击“Windows Phone 8.1 和 Windows 10 移动版”旁边的复选框，然后单击“确定”。  
  
5.  如果打算管理 Windows 10 桌面计算机，请右键单击“Microsoft Intune 订阅”，单击“配置平台”，然后单击“启用Windows 注册”。  
  
6.  单击“启用 Windows 注册”旁边的复选框，然后单击“确定”。  
  
## 请参阅  
 [用于 System Center Configuration Manager 中本地移动设备管理的准备步骤](../LocTest/Preparation-steps-for-On-premises-Mobile-Device-Management-in-System-Center-Configuration-Manager.md)
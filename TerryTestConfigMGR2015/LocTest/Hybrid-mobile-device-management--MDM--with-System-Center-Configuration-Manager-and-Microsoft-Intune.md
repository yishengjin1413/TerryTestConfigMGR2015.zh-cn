---
title: "Hybrid mobile device management (MDM) with System Center Configuration Manager and Microsoft Intune"
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
ms.assetid: bb95154b-f63e-4491-896e-41d732c802f8
caps.latest.revision: 34
caps.handback.revision: 34
translationtype: Human Translation
---
# Hybrid mobile device management (MDM) with System Center Configuration Manager and Microsoft Intune
本演练向你表明如何配置 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 以通过 Internet 使用 Microsoft Intune 联机服务来管理 iOS、Android（包括 Samsung KNOX）、Windows Phone 和 Windows 设备。 尽管你使用 Intune 服务，但管理任务是通过使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中的服务连接点系统角色完成的。  
  
 你可以将 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 配置允许用户以安全的管理方式访问其设备上的公司资源。 通过使用设备管理，你可以保护公司数据，同时允许用户注册其个人移动设备或公司拥有的移动设备，并向用户提供公司数据访问权限。 将 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 与 Intune 配合使用时，你在设备上具有以下管理功能：  
  
-   停用和擦除设备  
  
-   配置密码、安全性、漫游、加密和无线通信等符合性设置  
  
-   将业务线应用部署到设备  
  
-   将应用部署到连接到 Windows 应用商店、Windows Phone 应用商店、应用商店或 Google Play 的设备  
  
-   收集硬件清单  
  
-   使用内置报表收集软件清单  
  
 若要阅读有关哪些新功能可用于混合 MDM 的信息，请参阅[使用 System Center Configuration Manager 和 Microsoft Intune 的混合移动设备管理中的新增功能](../LocTest/What-s-new-in-hybrid-mobile-device-management-with-System-Center-Configuration-Manager-and-Microsoft-Intune.md)。  
  
 本文档假设你正在使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 管理计算机，并且对使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 扩展 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 控制台来管理移动设备感兴趣。 若要了解 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 和混合移动设备管理之间的差异，请参阅[在 Microsoft Intune 独立版和使用 System Center Configuration Manager 的混合移动设备管理之间选择](../LocTest/Choose-between-Microsoft-Intune-standalone-and-hybrid-mobile-device-management-with-System-Center-Configuration-Manager.md)。  
  
 使用 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 扩展 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 后，可授予用户权限，以供注册其个人设备或注册和管理公司拥有的设备。 还可以使用 Configuration Manager 通过 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 管理公司拥有的设备。 请参阅[使用 Configuration Manager 注册公司拥有的设备以用于混合部署](../LocTest/Enroll-company-owned-devices-for-hybrid-deployments-with-Configuration-Manager.md)。  
  
 使用下列部分来帮助你管理移动设备。  
  
##  <a name="bkmk_preq"></a> 先决条件  
 使用以下信息来确定管理移动设备的先决条件。  
  
###  <a name="BKMK_ADmin"></a> Configuration Manager 的外部依赖关系  
 如有必要，请执行以下步骤以满足 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 外部的任何依赖关系：  
  
1.  确保你具有公开注册的域名且每位用户具有可由 Intune 验证的公共域 UPN。 GoDaddy 或 Symantec 是提供域名的公司的典型例子。  
  
     在同步 Active Directory 用户帐户之前，必须验证用户帐户是否具有公共域 UPN。 有关详细信息，请参阅 Active Directory 文档库中的 [添加用户主体名称后缀](http://go.microsoft.com/fwlink/?LinkID=271122) 。  
  
     可以创建 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 自定义报表，以使用下列 SQL 查询来验证所发现的用户的 UPN 是否与 Intune 帐户门户一致：  
  
    ```  
    SELECT UserPrincipalName,   
    COUNT(*) AS NumOfOccurances FROM (SELECT RIGHT(User_Principal_Name0,   
    LEN(User_Principal_Name0)-PATINDEX('%@%',   
    User_Principal_Name0)) AS UserPrincipalName FROM CM_EC1.dbo.v_R_User)   
    AS sub GROUP BY UserPrincipalName  
    ```  
  
2.  可选但强烈推荐：部署并配置 Active Directory 联合身份验证服务 (AD FS)。  
  
     在设置单一登录时，用户可以使用其公司凭据登录，以访问 [!INCLUDE[wit_nextref](../LocTest/includes/wit_nextref_md.md)]中的服务。  
  
     有关详细信息，请参阅下列主题：  
  
    -   [为单一登录做准备](http://go.microsoft.com/fwlink/?LinkID=271124)  
  
    -   [规划和部署 AD FS 2.0 以用于单一登录](http://go.microsoft.com/fwlink/?LinkID=271125)  
  
3.  部署并配置目录同步。  
  
     目录同步可让你利用同步的用户帐户来填充 [!INCLUDE[wit_nextref](../LocTest/includes/wit_nextref_md.md)] 。 同步的用户帐户和安全组被添加到 [!INCLUDE[wit_nextref](../LocTest/includes/wit_nextref_md.md)]中。 未能启用目录同步是在使用 Microsoft Intune 设置 Configuration Manager MDM 时，设备无法注册的一个常见原因。  
  
     有关详细信息，请参阅 Active Directory 文档库中的 [目录集成](http://go.microsoft.com/fwlink/?LinkID=271120) 。  
  
4.  可选但不建议：如果没有使用 Active Directory 联合身份验证服务，则重置用户的 Microsoft Online 密码。  
  
     如果没有使用 AD FS，则必须为每个用户设置 Microsoft Online 密码。  
  
##  <a name="bkmk_witsub"></a> 配置 Microsoft Intune 订阅  
 Intune 订阅可使你为 Intune 服务指定配置设置。 这包括指定可以注册其设备的用户，以及定义要管理移动设备平台。 创建了订阅后，你可以随后安装服务连接点站点系统角色，该角色使你能够连接到 Intune 服务。 此站点系统角色会将设置和应用程序推送到 Intune 服务。 Intune 订阅执行以下任务：  
  
-   检索服务连接点连接到 Intune 服务所需的证书  
  
-   定义使用户能够注册移动设备的用户集合。  
  
-   定义和配置要支持的移动平台。  
  
> [!IMPORTANT]  
>  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中为Microsoft Intune 创建订阅会将你站点的服务连接点置于“联机模式”下。 请参阅[关于 System Center Configuration Manager 中的服务连接点](../LocTest/About-the-service-connection-point-in-System-Center-Configuration-Manager.md)。  
  
###  <a name="bkmk_subscription"></a> 创建 Microsoft Intune 订阅  
  
1.  如果尚未注册，请在 [Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=271123) 处注册 Microsoft Intune 帐户。  
  
     请参阅  [Microsoft Intune 入门](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune)了解相关指导。  
  
2.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“管理” 。  
  
3.  在“管理”  工作区中，展开“云服务” ，并单击“Microsoft Intune 订阅” 。 在“主页”  选项卡上，单击“添加 Microsoft Intune 订阅” 。  
  
4.  在“创建 Microsoft Intune 订阅向导”的“介绍”  页上，查看文本并单击“下一步” 。  
  
5.  在“订阅”  页上，单击“登录”  并使用你的工作或学校帐户登录。 在“设置移动设备管理机构”  对话框中，选中相应复选框，以便只能通过 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 来管理移动设备。 要继续进行订阅，你必须选择此选项。  
  
    > [!IMPORTANT]  
    >  选择 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 作为管理机构后，将来你无法将管理机构更改为 Microsoft Intune。  
  
6.  单击隐私链接以查看它们，然后单击“下一步” 。  
  
7.  在“常规”  页上，指定以下选项，然后单击“下一步” 。  
  
    -   **集合**：指定一个用户集合，其中包含将注册其移动设备的用户。  
  
        > [!NOTE]  
        >  如果从集合中删除某个用户，则将继续管理该用户的设备最多 24 小时，直至从用户数据库中删除用户记录为止。  
  
    -   **公司名称**：指定你的公司名称。  
  
    -   “指向公司隐私文档的 URL”：如果将公司隐私信息发布到可从 Internet 中访问的链接，请提供该链接以便用户可从公司门户中访问它，例如 http://www.contoso.com/CP_privacy.html。 隐私信息可阐明用户与你的公司分享了什么信息。  
  
    -   **公司门户的配色方案**：（可选）更改公司门户的默认颜色（蓝色）。  
  
    -   **Configuration Manager 站点代码**：指定主站点的站点代码以管理移动设备。  
  
        > [!NOTE]  
        >  更改站点代码仅影响新注册，不影响现有注册设备。  
  
    -   指定“设备注册限制” 。 每个授权用户可以注册最多 5 台设备。 如果用户尝试注册多于指定数量的设备，将会收到错误消息。  
  
8.  在“公司联系人信息”  页上，指定显示在公司门户中的公司联系人信息，然后单击“下一步” 。  
  
9. 在“公司徽标”  页上，选择是否要在公司门户中显示徽标，然后单击“下一步” 。  
  
10. 完成向导。  
  
 移动设备的 Intune 管理配置完成后，就可以创建“条款和条件” 。 使用条款和条件向用户说明他们注册设备时会发生的情况。 在注册设备之前，用户必须接受相应的条款和条件。 请参阅 [System Center Configuration Manager 中的条款和条件](../LocTest/Terms-and-Conditions-in-System-Center-Configuration-Manager.md)。  
  
##  <a name="bkmk_WITconn"></a> 服务连接点站点系统角色  
 服务连接点将设置和软件部署信息发送到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] ，并从移动设备中检索状态和清单消息。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 服务充当与移动设备通信的网关并存储设置。  
  
> [!NOTE]  
>  服务连接点系统角色只能安装在管理中心站点或独立主站点上。 服务连接点必须具有 Internet 访问权限。  
  
###  <a name="bkm_connector"></a> 若要配置服务连接点角色  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“管理” 。  
  
2.  在“管理”  工作区中，展开“站点配置” ，然后单击“服务器和站点系统角色” 。  
  
3.  使用关联的步骤将“服务连接点”  角色添加到新的或现有的站点系统服务器：  
  
    -   新站点系统服务器：在“主页”  选项卡上的“创建”  组中，单击“创建站点系统服务器”  以启动创建站点系统服务器向导。  
  
    -   现有站点系统服务器：单击你要在其上安装服务连接点角色的服务器。 然后，在“主页”  选项卡上的“服务器”  组中，单击“添加站点系统角色”  以启动添加站点系统角色向导。  
  
4.  在“系统角色选择”  页面上，选择“服务连接点” ，然后单击“下一步” 。  
  
5.  完成向导。  
  
### 服务连接点如何通过 Microsoft Intune 服务进行身份验证？  
 服务连接点通过与基于云的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 服务建立连接扩展 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] ，从而可通过 Internet 管理移动设备。 服务连接点按照以下方式通过 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 服务进行身份验证：  
  
1.  在 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 控制台中创建 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 订阅时，通过连接到 Azure Active Directory 对 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 管理员进行身份验证，Azure Active Directory 将重定向到相应的 ADFS 服务器，提示输入用户名和密码。 然后， [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 向租户颁发证书。  
  
2.  步骤 1 中的证书安装在服务连接点站点角色上，用于对与 Microsoft Intune 服务的所有进一步通信进行身份验证和授权。  
  
## 启用移动设备注册  
 在可以注册设备之前，必须建立管理解决方案和托管的移动设备之间的信任关系。 这种关系是特定于平台的。因此，如果你想要管理-比如 iOS 设备，必须使用 Apple Push Notification 服务 (APNs) 证书通过 Apple 的服务器启用注册。  以下主题说明任何为每套设备启用 MDM：  
  
-   [Set up iOS hybrid device management with System Center Configuration Manager and Microsoft Intune](../LocTest/Set-up-iOS-hybrid-device-management-with-System-Center-Configuration-Manager-and-Microsoft-Intune.md)  
  
-   [Set up Android hybrid device management with System Center Configuration Manager and Microsoft Intune](../LocTest/Set-up-Android-hybrid-device-management-with-System-Center-Configuration-Manager-and-Microsoft-Intune.md)  
  
-   [Set up Windows Phone and Windows 10 Mobile hybrid device management with System Center Configuration Manager and Microsoft Intune](../LocTest/Set-up-Windows-Phone-and-Windows-10-Mobile-hybrid-device-management-with-System-Center-Configuration-Manager-and-Microsoft-Intune.md)  
  
-   [Set up Windows hybrid device management with System Center Configuration Manager and Microsoft Intune](../LocTest/Set-up-Windows-hybrid-device-management-with-System-Center-Configuration-Manager-and-Microsoft-Intune.md)  
  
### 验证移动设备管理配置  
 可以通过检查以下日志文件来验证某些设备管理组件：  
  
-   检查 Cloudusersync.log 以验证用户帐户是否已成功同步。  
  
-   检查 Sitecomp.log 以验证是否已成功创建服务连接点。  
  
## 管理与 Configuration Manager 关联的 Intune 订阅  
 如果将 Microsoft Intune（试用订阅或付费订阅）添加到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]，随后需要切换到不同的 Intune 订阅，则必须先从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中同时删除 **Microsoft Intune 订阅**和**服务连接点**，然后才能添加新订阅。  
  
#### 如何从 Configuration Manager 中删除 Intune 订阅  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“管理” 。  
  
2.  在“管理”工作区中，展开“概述”，转到“云服务”，然后单击“Microsoft Intune 订阅”。  
  
3.  右键单击“Microsoft Intune 订阅”，然后单击“删除”。 “Microsoft Intune订阅”。  
  
    > [!IMPORTANT]  
    >  所有内容（包括为 Intune 评估订阅配置的用户注册、策略和应用部署）都会丢失。  
  
4.  在“管理”工作区中，展开“概述”，转到“站点配置”，然后选择“服务器和站点系统角色”。  
  
5.  选择承载“服务连接点”角色的服务器。  
  
6.  在“站点系统角色”列表中，选择“服务连接点”，然后在功能区中单击“删除角色”。 确认要删除角色。 服务连接点会删除。  
  
7.  现在可以创建新服务连接点、将新 Intune 订阅添加到 Configuration Manager 以及将 Configuration Manager 设置为 MDM 机构。  
  
## 另请参阅  
 [使用 System Center Configuration Manager 管理计算机和设备](../LocTest/Manage-computers-and-devices-with-System-Center-Configuration-Manager.md)
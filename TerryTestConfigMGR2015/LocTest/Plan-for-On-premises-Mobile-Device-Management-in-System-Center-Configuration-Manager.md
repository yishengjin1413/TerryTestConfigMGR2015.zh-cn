---
title: "在 System Center Configuration Manager 中规划本地移动设备管理"
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
ms.assetid: 02979fb8-ea7e-4ec6-b7e0-ecbfda73e52d
caps.latest.revision: 9
caps.handback.revision: 9
translationtype: Human Translation
---
# 在 System Center Configuration Manager 中规划本地移动设备管理
在准备用于处理 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)]基础结构之前，请考虑以下要求：  
  
-   [支持的设备](#bkmk_devices)  
  
-   [使用 Microsoft Intune 订阅](#bkmk_intune)  
  
-   [所需站点系统角色](#bkmk_roles)  
  
-   [所需受信任的通信](#bkmk_trustedComs)  
  
-   [注册注意事项](#bkmk_enrollment)  
  
##  <a name="bkmk_devices"></a> 支持的设备  
 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 允许你使用内置于设备操作系统的管理功能来管理移动设备。  该管理功能基于开放移动联盟 (OMA) 设备管理 (DM) 标准，许多设备平台都使用此标准来允许对设备进行管理。  我们将它们称为“新式设备”  （在文档和 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台用户界面中），以将它们与其他需要 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端来进行管理的设备区别开来。  
  
 [!INCLUDE[onprem_devices](../LocTest/includes/onprem_devices_md.md)]   
##  <a name="bkmk_intune"></a> 使用 Microsoft Intune 订阅  
 若要开始使用 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)]，你需要 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 订阅。 仅跟踪设备授权时需要订阅，订阅不用于管理或储存设备的管理信息。 所有管理均由你组织的企业使用本地 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 基础结构来进行。  
  
> [!IMPORTANT]  
>  [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不支持同时使用 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 和本地 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 基础结构作为管理机构。 因此，当设置 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 订阅以用于本地管理时，你实际上禁用了 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 管理。  
  
 如果你的站点拥有具 Internet 连接性的设备，可使用 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 服务通知设备检查设备管理点是否有策略更新。 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 的这种用法仅限用于对面向 Internet 设备进行通知。 无 Internet 连接（且不能由 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)]连接）的设备依靠配置的轮询间隔来签入站点系统角色，从而实现管理功能。  
  
> [!TIP]  
>  我们建议先设置 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] ，然后再设置所需的站点系统角色，以最小化站点系统角色开始正常运行所需的时间。  
  
 有关如何设置 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 订阅的信息，请参阅[在 System Center Configuration Manager 中为本地移动设备管理设置 Microsoft Intune 订阅](../LocTest/Set-up-a-Microsoft-Intune-subscription-for-On-premises-Mobile-Device-Management-in-System-Center-Configuration-Manager.md)。  
  
##  <a name="bkmk_roles"></a> 所需站点系统角色  
 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 需要以下站点系统角色中至少一个：  
  
-   **注册代理点** ，用于支持注册请求。  
  
-   **注册点** ，用于支持设备注册。  
  
-   **设备管理点** ，用于策略传递。 此站点系统角色是管理点角色的变体，后者已配置为允许移动设备管理。  
  
-   **分发点** ，用于内容传递。  
  
-   **服务连接点** ，用于连接到 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 以通知位于防火墙外的设备。  
  
 这些站点系统角色可以安装在单个站点系统服务器上，或者根据组织的需要分别运行在不同的服务器上。 用于 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 的每个站点系统服务器都必须配置为 HTTPS 终结点，以便与受信任的设备通信。 有关详细信息，请参阅 [所需受信任的通信](#bkmk_trustedComs)。  
  
 有关规划站点系统角色的详细信息，请参阅 [Plan for site system servers and site system roles for System Center Configuration Manager](../LocTest/Plan-for-site-system-servers-and-site-system-roles-for-System-Center-Configuration-Manager.md)。  
  
 有关如何添加所需站点系统角色的详细信息，请参阅 [Install site system roles for On-premises Mobile Device Management in System Center Configuration Manager](../LocTest/Install-site-system-roles-for-On-premises-Mobile-Device-Management-in-System-Center-Configuration-Manager.md)。  
  
##  <a name="bkmk_trustedComs"></a> 所需受信任的通信  
 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 要求启用站点系统角色以进行 HTTPS 通信。 根据需要，你可以使用企业的证书颁发机构 (CA) 在服务器和设备之间建立受信任的连接，或者使用公开发布的 CA 作为受信任的颁发机构。  无论哪种方式，你都需要在托管所需站点系统角色的站点系统服务器上用 IIS 配置 Web 服务器证书，并且需要在要连接到那些服务器的设备上安装该 CA 的根证书。  
  
 如果你使用企业的 CA 建立受信任的通信，则需要执行下列任务：  
  
-   在 CA 上创建和颁发 Web 服务器证书模板。  
  
-   为托管所需站点系统角色的每个站点系统服务器请求一个 Web 服务器证书。  
  
-   在站点系统服务器上配置 IIS 以使用所需的 Web 服务器证书。  
  
 对于已加入企业 Active Directory 域的设备，企业 CA 的根证书在受信任连接的设备上已经可用。 这意味着使用站点系统服务器的 HTTPS 连接将自动信任已加入域的设备（如台式计算机）。 但是，未加入域的设备（通常为移动设备）将不安装所需根证书。 将需要在这些设备上手动安装根证书，才能与支持 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)]的站点系统服务器成功通信。  
  
 你必须导出所颁发 CA 的根证书供各设备使用。 要获取根证书文件，你可以使用 CA 导出它，或者采用更简单的方法，即使用由 CA 颁发的 Web 服务器证书提取根目录并创建根证书文件。   然后，必须将根证书传递到设备。  传递方法示例包括  
  
-   文件系统  
  
-   电子邮件附件  
  
-   内存卡  
  
-   受限设备  
  
-   云存储（例如 OneDrive）  
  
-   近场通信 (NFC) 连接  
  
-   条形码扫描程序  
  
-   现成体验 (OOBE) 预配包  
  
 有关详细信息，请参阅 [Set up certificates for trusted communications for On-premises Mobile Device Management in System Center Configuration Manager](../LocTest/Set-up-certificates-for-trusted-communications-for-On-premises-Mobile-Device-Management-in-System-Center-Configuration-Manager.md)。  
  
##  <a name="bkmk_enrollment"></a> 注册注意事项  
 若要为 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)]启用设备注册，必须授予用户注册权限，且其设备必须能够与托管所需站点系统角色站点系统服务器实现受信任的通信。  
  
 可以通过在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端设置中设置注册配置文件，来授予用户注册权限。 你可以使用默认客户端设置将注册配置文件推送到所有已发现的用户；或者在自定义客户端设置中设置注册配置文件，并将设置推送到一个或多个用户集合。  
  
 授予用户注册权限后，用户即可注册其自己的设备。 要进行注册，用户的设备必须具有颁发托管站点系统角色的站点系统服务器上所用 Web 服务器证书的证书颁发机构 (CA) 的根证书。  
  
 除用户启动的注册外，你还可以设置一个允许在没有用户干预的情况下注册设备的批量注册包。 可在最初配置此注册包以供使用之前，或在设备完成其 OOBE 流程之后将此注册包传递到设备。  
  
 有关如何设置和注册设备的详细信息，请参阅  
  
-   [为 System Center Configuration Manager 中的本地移动设备管理设置设备注册](../LocTest/Set-up-device-enrollment-for-On-premises-Mobile-Device-Management-in-System-Center-Configuration-Manager.md)  
  
-   [在 System Center Configuration Manager 中为本地移动设备管理注册设备](../LocTest/Enroll-devices-for-On-premises-Mobile-Device-Management-in-System-Center-Configuration-Manager.md)  
  
## 另请参阅  
 [在 System Center Configuration Manager 中使用本地基础结构管理移动设备](../LocTest/Manage-mobile-devices-with-on-premises-infrastructure-in-System-Center-Configuration-Manager.md)
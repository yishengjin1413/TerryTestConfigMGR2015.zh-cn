---
title: "关于 System Center Configuration Manager 中的服务连接点"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-other
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: bc2282d5-0571-465b-9528-a555855eaacd
caps.latest.revision: 19
caps.handback.revision: 18
translationtype: Human Translation
---
# 关于 System Center Configuration Manager 中的服务连接点
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 服务连接点是一个站点系统角色，为层次结构提供几个重要的功能。 配置服务连接点之前，需了解和规划其使用范围，这会影响你配置此站点系统角色的方式：  
  
-   “使用 Microsoft Intune 管理移动设备” – 此角色替换此前版本的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]使用的Windows Intune 连接器，并可通过 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 订阅详细信息进行配置。 请参阅[使用 System Center Configuration Manager 和 Microsoft Intune 的混合移动设备管理 (MDM)](../LocTest/Hybrid-mobile-device-management--MDM--with-System-Center-Configuration-Manager-and-Microsoft-Intune.md)  
  
-   **使用本地 MDM 管理移动设备** – 此角色为你所管理的未连接 Internet 的本地设备提供支持。 请参阅[在 System Center Configuration Manager 中使用本地基础结构管理移动设备](../LocTest/Manage-mobile-devices-with-on-premises-infrastructure-in-System-Center-Configuration-Manager.md)  
  
-   **从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 基础结构上传使用情况数据** – 你可以控制上传信息的量和详细级别。 上载的数据帮助我们：  
  
    -   主动识别和排除问题  
  
    -   改进我们的产品和服务  
  
    -   标识适用于所使用的 Configuration Manager 版本的 Configuration Manager 更新  
  
     请参阅 [Usage data levels and settings](../LocTest/Reference-for-System-Center-Configuration-Manager-Setup.md#bkmk_usage)。  
  
-   **下载适用于你的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 基础结构的更新** - 基于你所上传的使用情况数据，仅适用于你的基础结构的相关更新可用。  
  
 **每个层次结构支持此角色的单一实例：**  
  
-   此站点系统角色只能安装在层次结构的顶层站点（管理中心站点或独立主站点上）。  
  
-   如果将独立主站点扩展到更大的层次结构中，必须从主站点中卸载此角色，然后可将其安装在管理中心站点上。  
  
##  <a name="bkmk_modes"></a> 操作模式  
 服务连接点支持两种操作模式：  
  
-   在“联机模式” 下，服务连接点每 24 小时自动检查更新并下载可用于当前基础结构和产品版本的新更新，使其在 Configuration Manager 控制台中可用  
  
-   在**脱机模式**下，服务连接点不会连接到 Microsoft 云服务，必须手动[使用 System Center Configuration Manager 的服务连接工具](../LocTest/Use-the-Service-Connection-Tool-for-System-Center-Configuration-Manager.md)导入可用更新  
  
 安装了服务连接点之后在联机或脱机模式之间进行更改时，随后必须首先重新启动 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] SMS_Executive 服务的 SMS_DMP_DOWNLOADER 线程，此更改才会生效。  为此，请使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 服务管理器仅重新启动 SMS_Execctuive 服务的 SMS_DMP_DOWNLOADER 线程。  还可以为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 重新启动 SMS_Executive 服务（这会重新启动大多数站点组件），或等待诸如站点备份这类计划任务（它会停止，然后在以后为你重新启动 SMS_Executive）。  
  
 若要使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 服务管理器，请在控制台中导航到“监视” > “系统状态” > “组件状态”，单击“启动”，然后选择“Configuration Manager 服务管理器”。  在服务管理器中：  
  
-   在导航窗格中，依次展开站点和“组件”，然后选择要重新启动的组件。  
  
-   在细节窗格中，右键单击该组件，然后选择“查询”。  
  
-   确认该组件的状态之后，再次右键单击该组件，选择“停止”。  
  
-   再次**查询**该组件，以确认它已停止，然后再次右键单击该组件，并选择“启动”。  
  
> [!IMPORTANT]  
>  当你将  [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 订阅添加到服务连接点时，它会自动将站点系统角色设置为联机状态。 使用 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 订阅进行配置时，服务连接点不支持脱机模式。  
  
 **当角色安装在远离站点服务器的计算机上：**  
  
-   必须配置一个站点系统服务器，用于托管具有站点系统安装账户的角色  
  
-   站点服务器上的分发管理器使用该站点系统安装帐户来传输服务连接点的更新。  
  
##  <a name="bkmk_urls"></a> Internet 访问要求  
 若要启用操作，托管服务连接点的计算机以及该计算机与 Internet 之间的任何防火墙必须通过**端口 TCP 443** 与以下 Internet 位置进行通信。 服务连接点也支持使用 Web 代理（具有或不具有身份验证皆可）来访问这些位置。  
  
 **更新和服务**  
  
-   *.akamaiedge.net  
  
-   *.manage.microsoft.com 

-   go.microsoft.com 
  
-   blob.core.windows.net  
  
-   download.microsoft.com  
  
-   sccmconnected-a01.cloudapp.net  
  
 **Microsoft Intune**  
  
-   *manage.microsoft.com  
  
 **Windows 10 维护服务**  
  
-   download.microsoft.com  
  
-   https://go.microsoft.com/fwlink/?LinkID=619849  
  
## 另请参阅  
 [System Center Configuration Manager 的站点和层级结构基础结构技术参考](../LocTest/Site-and-hierarchy-infrastructure-technical-reference-for-System-Center-Configuration-Manager.md)
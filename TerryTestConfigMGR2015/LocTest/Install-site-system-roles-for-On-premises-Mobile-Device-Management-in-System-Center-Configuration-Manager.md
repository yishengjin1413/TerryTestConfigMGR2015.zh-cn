---
title: "在 System Center Configuration Manager 中为本地移动设备管理安装站点系统角色"
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
ms.assetid: c3cf9f64-c2b9-4ace-9527-2aba6d4eef04
caps.latest.revision: 9
caps.handback.revision: 8
---
# 在 System Center Configuration Manager 中为本地移动设备管理安装站点系统角色
[!INCLUDE[onprem_first](../LocTest/includes/onprem_first_md.md)] 在你的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点基础结构中要求以下站点系统角色：  
  
-   注册点  
  
-   注册代理点  
  
-   分发点  
  
-   设备管理点  
  
-   服务连接点  
  
 如果你的组织使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端软件管理大多数 PC 和设备，那么向其添加 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 时，你可能已将大多数站点系统角色安装为现有基础结构的一部分。 如果不是这样，请参阅 [添加 System Center Configuration Manager 的站点系统角色](../LocTest/Add-site-system-roles-for-System-Center-Configuration-Manager.md)，了解有关如何将其添加到网站的完整信息。  
  
> [!NOTE]  
>  如果你以设备管理点站点系统角色使用数据库副本，那么新注册的设备最初无法连接到设备管理点，直到数据库副本与之同步。 此连接失败的原因是数据库副本没有建立成功连接所需的新注册设备的信息。 副本每 5 分钟同步一次，因此设备在注册之后的最初 5 分钟将无法连接（通常尝试 2 次连接），在此之后设备将成功连接。  
  
 无论使用现有站点系统角色还是添加新角色，你都必须将其配置用于管理新式设备。 按照下列步骤配置的分发点和设备管理点，使它们对 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 正常工作：  
  
> [!NOTE]  
>  [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的当前分支仅支持从设备到 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 的分发点和设备管理点的 Intranet 连接。 但是，如果你还管理着 Mac OS X 计算机，则这些客户端将需要通过 Internet 连接到这些站点系统角色。 在这种情况下，配置分发点和设备管理点的属性时应改用“允许 Intranet 和 Internet 连接”设置。  
  
### 若要配置站点系统角色以管理新式设备：  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“管理”\>“概述”\>“站点配置”\>“服务器和站点系统角色”。  
  
2.  选择具有想要配置的分发点或设备管理点的站点系统服务器，打开“站点系统”的属性并确保它指定了 FQDN。 单击"**确定**"。  
  
3.  打开分发点站点系统角色的属性。 在“常规”选项卡上，确保选中了“HTTPS”并选择“仅允许 Intranet 连接”。  
  
     如果你还通过 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端单独管理着 Mac 计算机，请改用“允许 Intranet 和 Internet 连接”。  
  
    > [!NOTE]  
    >  为 Intranet 连接配置的分发点需要为其配置站点边界。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的当前分支仅支持 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 的 IPv4 范围边界。 有关配置站点边界的详细信息，请参阅 [为 System Center Configuration Manager 定义站点边界和边界组](../LocTest/Define-site-boundaries-and-boundary-groups-for-System-Center-Configuration-Manager.md)。  
  
4.  单击“允许移动设备连接到此分发点”旁边的复选框，然后单击“确定”。  
  
5.  打开管理点站点系统角色的属性。 在“常规”选项卡上，确保选中了“HTTPS”，并选择“仅允许 Intranet 连接”。  
  
     如果你还通过 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端单独管理着 Mac 计算机，请改用“允许 Intranet 和 Internet 连接”。  
  
6.  单击“允许移动设备和 Mac 计算机使用此管理点”旁的复选框。 单击"**确定**"。  
  
     这会将该管理点有效地变为设备管理点。  
  
 添加站点系统角色并将其配置用于管理新式设备后，需要将承载该角色的服务器配置为受信任终结点，以便注册托管设备并与之通信。 有关详细信息，请参阅[为 System Center Configuration Manager 中的本地移动设备管理的受信任通信设置证书](../LocTest/Set-up-certificates-for-trusted-communications-for-On-premises-Mobile-Device-Management-in-System-Center-Configuration-Manager.md)。  
  
## 请参阅  
 [用于 System Center Configuration Manager 中本地移动设备管理的准备步骤](../LocTest/Preparation-steps-for-On-premises-Mobile-Device-Management-in-System-Center-Configuration-Manager.md)
---
title: "在 System Center Configuration Manager 中使用远程连接配置文件"
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
ms.assetid: eea36ac7-b261-45da-b448-0358c9e74386
caps.latest.revision: 7
caps.handback.revision: 7
---
# 在 System Center Configuration Manager 中使用远程连接配置文件
使用 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 远程连接配置文件，允许用户在未连接到域时或者其个人计算机通过 Internet 连接时以远程方式连接到工作计算机。  
  
 用户可以从以下设备类型连接到其工作电脑：  
  
-   运行 Microsoft Windows 的计算机  
  
-   运行 iOS 的设备  
  
-   运行 Android 的设备  
  
 利用远程连接配置文件，你可以将远程桌面连接设置部署到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 层次结构中的用户。 用户随后可使用公司门户，利用公司门户提供的远程桌面连接设置通过远程桌面访问他们的任何主要工作计算机。  
  
 如果你希望用户使用公司门户连接到其工作电脑，则需要 Microsoft Intune。 如果你未使用 Intune，用户仍然能够使用远程连接配置文件中的信息，通过 VPN 连接使用远程桌面连接到其工作电脑。  
  
> [!IMPORTANT]  
>  当你使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台指定远程连接配置文件设置时，这些设置将存储在客户端计算机的本地策略中。 这些设置可能会替代另一个应用程序配置的远程桌面设置。 此外，如果你使用 Windows 组策略配置远程桌面设置，则组策略中指定的设置将会替代使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]配置的设置。  
  
 在安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]时，将创建“远程电脑连接” 新安全组。 当部署远程连接配置文件（其中包括你向其中部署配置文件的计算机的主要用户）时，将填充此组。 尽管本地管理员可向此组中添加用户名，但在下次评估已部署远程连接配置文件的符合性时，会将这些用户从组中删除。  
  
 如果你向此组中手动添加用户，用户可以启动远程连接，但不会在公司门户中发布连接信息。  
  
 如果你从组中手动删除 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]已添加的用户， [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将通过在下次评估远程连接配置文件的符合性时重新添加该用户来自动修正此更改。  
  
> [!IMPORTANT]  
>  如果用户和设备之间的用户设备相关性发生更改（例如，用户连接到的计算机不再是用户的主要设备）， [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将禁用远程连接配置文件和 Windows 防火墙设置以防止连接到该计算机。  
  
## 先决条件  
  
### 外部依赖关系  
  
|依赖关系|更多信息|  
|----------------|----------------------|  
|远程桌面网关服务器。|如果要允许用户从公司域的外部在 Internet 上连接，你必须安装和配置远程桌面网关服务器。<br /><br /> 如果远程桌面或终端服务设置由另一个应用程序或组策略设置管理，远程连接配置文件可能无法正常工作。 当你通过 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台部署远程连接配置文件时，其设置将存储在客户端计算机的本地策略中。 这些设置可能会替代另一个应用程序配置的远程桌面设置。 此外，如果你使用组策略设置来配置远程桌面设置，则组策略设置中指定的设置将会替代 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]配置的设置。<br /><br /> 有关如何安装和配置远程桌面网关服务器的详细信息，请参阅 Windows Server 文档。|  
|如果客户端计算机运行基于主机的防火墙，该防火墙必须启用 Mstsc.exe 程序。|在配置远程连接配置文件时，你必须启用“对 Windows 域和专用网络上的连接允许 Windows 防火墙例外”  设置。 启用了此设置后， [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将自动配置 Windows 防火墙以启用 Mstsc.exe 程序。 但是，如果客户端计算机运行其他基于主机的防火墙，你必须手动配置此防火墙依赖关系。<br /><br /> 用于配置 Windows 防火墙的组策略设置可能会覆盖在 Configuration Manager 中设置的配置。 如果使用组策略来配置 Windows 防火墙，请确保组策略设置不会阻止 Mstsc.exe 程序。|  
  
### Configuration Manager 依赖关系  
  
|依赖关系|更多信息|  
|----------------|----------------------|  
|[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 连接到 Microsoft Intune（称为混合配置）。|有关将 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 连接到 Microsoft Intune 的详细信息，请参阅使用 Configuration Manager 和 Microsoft Intune 管理移动设备。|  
|为了使用户连接到公司网络上的工作计算机，该计算机必须是用户的主设备。|有关用户设备相关性的详细信息，请参阅[在 System Center Configuration Manager 中将用户和设备同用户设备相关性相链接](../LocTest/Link-users-and-devices-with-user-device-affinity-in-System-Center-Configuration-Manager.md)。|  
|必须授予特定的安全权限来管理远程连接配置文件。|“符合性设置管理员”  安全角色包括管理远程连接配置文件所需的权限。 有关详细信息，请参阅 <br />[为 System Center Configuration Manager 配置基于角色的管理](../LocTest/Configure-role-based-administration-for-System-Center-Configuration-Manager.md)。|  
  
## 远程连接配置文件的安全和隐私注意事项  
  
### 安全注意事项  
  
|最佳安全方案|更多信息|  
|----------------------------|----------------------|  
|手动指定用户设备相关性，而不是允许用户确定其主设备。 此外，不要启用基于使用情况的配置。|由于你必须启用“允许工作计算机的所有主要用户进行远程连接”  然后才能部署远程连接配置文件，因此请始终手动指定用户设备相关性。 不考虑从用户或从极可信赖的设备中收集的信息。 如果部署远程连接配置文件，并且受信任的管理用户未指定用户设备相关性，则未授权用户可能会收到提升的权限，然后能够远程连接到计算机。<br /><br /> 如果确实启用基于使用情况的配置，则会通过未受 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 保护的状态消息收集此信息。 为了帮助减轻此威胁，请在客户端计算机和管理点之间使用服务器消息块 (SMB) 签名或 Internet 协议安全性 (IPsec)。|  
|限制站点服务器计算机上的本地管理员权限。|在站点服务器上具有本地管理权限的用户可向 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 自动创建和维护的“远程 PC 连接”安全组中手动添加成员。 由于添加到此组的成员会接收远程桌面权限，因此这可能会导致权限提升。|  
  
### 隐私注意事项  
  
-   如果用户从公司门户中发起与工作计算机的连接，则会下载一个扩展名为 .rdp 或 .wsrdp 的文件，其中包含发起“远程桌面”会话所需的设备名称和远程桌面网关服务器名称。 文件扩展名取决于设备的操作系统。 例如，Windows 7 和 Windows 8 操作系统使用 .rdp 文件，Windows 8.1 使用 .wsrdp 文件。  
  
-   用户可选择打开或保存 .rdp 文件。 如果用户选择打开 .rdp 文件，则文件可能存储在 Web 浏览器缓存中，具体情况视为浏览器配置的保留设置而定。 如果用户选择保存文件，则不会将文件存储在浏览器缓存中。 系统会保存文件，直至用户将其手动删除为止。  
  
-   会自动下载并以本地方式保存 .wsrdp 文件。 用户下次运行“远程桌面”会话时，会覆盖此文件。  
  
-   在配置远程连接配置文件之前，请考虑隐私要求。  
  
## 后续步骤  
 接下来，你很可能会想要开始创建和部署远程连接配置文件。  
  
 有关可使用的所有设置的帮助，请参阅[如何在 System Center Configuration Manager 中创建远程连接配置文件](../LocTest/How-to-create-remote-connection-profiles-in-System-Center-Configuration-Manager.md)。  
  
## 另请参阅  
 [使用 System Center Configuration Manager 确保设备的合规性](../LocTest/Ensure-device-compliance-with-System-Center-Configuration-Manager.md)
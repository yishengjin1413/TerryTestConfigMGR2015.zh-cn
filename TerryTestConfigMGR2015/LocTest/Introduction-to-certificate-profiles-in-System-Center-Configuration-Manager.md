---
title: "System Center Configuration Manager 中的证书配置文件简介"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-other
ms.tgt_pltfrm: na
ms.topic: get-started-article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 41dcc259-f147-4420-bff2-b65bdf8cff77
caps.latest.revision: 7
caps.handback.revision: 7
---
# System Center Configuration Manager 中的证书配置文件简介
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的证书配置文件使用 Active Directory 证书服务和网络设备注册服务角色设置被管理的设备的身份验证证书，使用户能够无缝地访问公司资源。 例如，可以创建和部署证书配置文件来为用户提供必要的证书，从而启动 VPN 和无线连接。  
  
 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的证书配置文件提供以下管理功能：  
  
-   通过企业证书颁发机构 (CA) 为运行 iOS、Windows 8.1、Windows RT 8.1、Windows 10 桌面和移动版以及 Android 的设备注册和续订证书。这些证书随后可用于 Wi-Fi 和 VPN 连接。  
  
-   部署受信任的根 CA 证书和中间 CA 证书，以在需要服务器身份验证时针对 VPN 和 Wi-Fi 连接在设备上配置一个信任链。  
  
-   监视并报告已安装的证书。  
  
 证书配置文件可自动配置用户设备，以便能够访问诸如 Wi-Fi 网络和 VPN 服务器等公司资源，而不必手动安装证书或使用带外进程。 证书配置文件还有助于保持公司资源的安全，因为你可使用受企业公钥基础结构 (PKI) 支持的更安全的设置。 例如，你可以要求对所有 Wi-fi 和 VPN 连接进行服务器身份验证，因为你已经在托管设备上设置了所需证书。  
  
 **例如：** 所有员工都必须能够连接到多个公司位置的 Wi-fi 热点。 为了实现这一点，你可以部署建立 Wi-Fi 连接所需的证书，并同时部署 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的 Wi-Fi 配置文件，这些配置文件引用要使用的正确证书，使 Wi-Fi 连接对于用户而言是无缝进行的。  
  
 **例如：** 你有 PKI 并且想迁移到更灵活、更安全的证书设置方法，可使用户在不影响安全性的情况下从个人设备访问公司资源。 为了实现这一点，你可以将证书配置文件配置为包含对于特定设备平台受支持的设置和协议。 随后设备可从面向 Internet 的注册服务器自动请求这些证书。 然后，可以配置 VPN 配置文件以使用这些证书，以便设备能够访问公司资源。  
  
## 证书配置文件的类型  
 你可以在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]中创建两种类型的证书配置文件：  
  
-   “可信 CA 证书” - 允许部署受信任的根 CA 或中间 CA 证书，以便在设备必须验证服务器时形成证书信任链。  
  
-   “简单证书注册协议 (SCEP) 设置” - 允许通过在运行 Windows Server 2012 R2 的服务器上使用 SCEP 协议和网络设备注册服务，为设备或用户请求一个证书。  
  
    > [!NOTE]  
    >  你必须创建“受信任的 CA 证书”  类型的证书配置文件，然后才能创建“简单证书注册协议 (SCEP) 设置” 类型的证书配置文件。  
  
## 要求和支持的平台  
 若要部署使用“简单证书注册协议”的证书配置文件，你必须在管理中心站点或主站点中的站点系统服务器上安装证书注册点。 你还必须在运行 Windows Server 2012 R2（包含 Active Directory 证书服务角色和有效的网络设备注册服务）的服务器上安装网络设备注册服务策略模块，即 Configuration Manager 策略模块，在需要证书的设备中可以访问该模块。 对于通过 [!INCLUDE[wit_firstref](../LocTest/includes/wit_firstref_md.md)]注册的设备，则要求网络设备注册服务可从 Internet 中访问，例如，位于外围子网（也称为 DMZ）中。  
  
 有关网络设备注册服务如何支持策略模块以便 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 可以部署证书的详细信息，请参阅 [Using a Policy Module with the Network Device Enrollment Service（将策略模块与网络设备注册服务配合使用）](http://go.microsoft.com/fwlink/p/?LinkId=328657)。  
  
 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 支持将证书部署到不同的证书存储，具体情况视要求以及设备类型和操作系统而定。 支持下列设备和操作系统：  
  
-   Windows RT 8.1  
  
-   Windows 8.1  
  
-   Windows Phone 8.1  
  
-   Windows 10 桌面和移动版  
  
-   iOS  
  
-   Android  
  
    > [!NOTE]  
    >  有关在运行 Android 的设备上安装证书时最终用户必须执行的操作的信息，请参阅[如何在 System Center Configuration Manager 中的 Android 设备上安装证书](../LocTest/How-to-install-certificates-on-Android-devices-in-System-Center-Configuration-Manager.md)。  
  
> [!IMPORTANT]  
>  要将配置文件部署到 Android、iOS、Windows Phone 和注册的 Windows 8.1 或更高版本设备，必须将这些设备注册到 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)]中。 有关如何注册设备的信息，请参阅 [使用 Microsoft Intune 管理移动设备](https://technet.microsoft.com/en-us/library/dn646962.aspx)。  
  
 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 的一个典型方案是在连接使用 EAP-TLS、EAP-TTLS 和 PEAP 身份验证协议以及 IKEv2、L2TP/IPsec 和 Cisco IPsec VPN 隧道协议时安装受信任的根 CA 证书以验证 Wi-Fi 和 VPN 服务器。  
  
 你必须确保在设备上安装企业根 CA 证书，然后设备才能使用 SCEP 证书配置文件请求证书。  
  
 你可以在 SCEP 证书配置文件中指定各种设置，以便针对不同的环境或连接要求请求自定义证书。 “创建证书配置文件向导”  包含两个注册参数页面。 首先，“SCEP 注册” 包含有关注册请求以及在何处安装证书的设置。 其次，“证书属性” 本身描述了请求的证书。  
  
## 部署证书模板  
 在部署证书配置文件时，配置文件内的证书文件安装在客户端设备上。 还将部署任何 SCEP 参数，并且将在客户端设备上处理 SCEP 请求。 你可以将证书配置文件部署到用户集合或设备集合，并为每个证书指定目标存储。 适用性规则确定证书是否可安装在设备上。 将证书配置文件部署到用户集合时，用户设备相关性确定用户的哪台设备将安装证书。 将包含用户证书的证书配置文件部署到设备集合时，默认情况下证书将安装在用户的每台主设备上。 你可以在“创建证书配置文件向导”  的“SCEP 注册” 页上修改此行为，以将证书安装在用户的任何设备上。 此外，如果设备是工作组计算机，则不会将用户证书部署到这些设备。  
  
## 监视证书配置文件  
 你可以通过 **控制台中“监视”****工作区中的“部署”**[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 节点监视证书配置文件部署。  
  
 你还可以使用下列 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 报表之一来监视证书配置文件：  
  
-   **证书注册点所颁发的证书的历史记录**  
  
-   **证书注册点所注册的证书的按证书颁发状态列出的资产的列表**  
  
-   **证书接近到期日期的资产的列表**  
  
## 自动吊销证书  
 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 在以下情况下会自动吊销使用证书配置文件部署的用户和计算机证书：  
  
-   从 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 管理中停用了设备。  
  
-   有选择地擦除了设备。  
  
-   从 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 层次结构中阻止了设备。  
  
 为了吊销证书，站点服务器会将吊销命令发送至证书颁发机构。 吊销原因是“停止操作” 。  
  
## 另请参阅  
 [System Center Configuration Manager 中的证书配置文件](../LocTest/Certificate-profiles-in-System-Center-Configuration-Manager.md)
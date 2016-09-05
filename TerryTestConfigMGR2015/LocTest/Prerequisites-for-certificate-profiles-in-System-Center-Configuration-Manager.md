---
title: "System Center Configuration Manager 中证书配置文件先决条件"
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
ms.assetid: 0317fd02-3721-4634-b18b-7c976a4e92bf
caps.latest.revision: 9
caps.handback.revision: 9
translationtype: Human Translation
---
# System Center Configuration Manager 中证书配置文件先决条件
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的证书配置文件有外部依赖关系和产品中的依赖关系。  
  
## Configuration Manager 的外部依赖关系  
  
|依赖关系|更多信息|  
|----------------|----------------------|  
|运行 Active Directory 证书服务 (AD CS) 的企业证书颁发机构 (CA)。<br /><br /> 若要吊销证书，层次结构顶部站点服务器的计算机帐户需要有针对 Configuration Manager 中证书配置文件所使用的各证书模板的 *颁发和管理证书* 权限。 或者，对证书管理器授予权限，使其可授予对该 CA 所使用的所有证书模板的权限。<br /><br /> 支持证书请求的管理程序审批。 但是，必须针对证书使用者的“在请求中提供”  配置用于颁发证书的证书模板，以便 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 可自动提供此值。|有关 Active Directory 证书服务的详细信息，请参阅 Windows Server 文档。<br /><br /> 对于 Windows Server 2012： [Active Directory 证书服务概述](http://go.microsoft.com/fwlink/p/?LinkId=286744)<br /><br /> 对于 Windows Server 2008： [Windows Server 2008 中的 Active Directory 证书服务](http://go.microsoft.com/fwlink/p/?LinkId=115018)|  
|Active Directory 证书服务的网络设备注册服务角色服务（在 Windows Server 2012 R2 上运行）。<br /><br /> 此外：<br /><br /> 对于客户端与网络设备注册服务之间的通信，不支持除 TCP 443（用于 HTTPS）或 TCP 80（用于 HTTP）外的端口号。<br /><br /> 运行网络设备注册服务的服务器与颁发 CA 必须位于不同的服务器上。|[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 与 Windows Server 2012 R2 中的网络设备注册服务通信以生成并验证简单证书注册协议 (SCEP) 请求。<br /><br /> 如果将向通过 Internet 连接的用户或设备（例如通过 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)]管理的移动设备）颁发证书，则那些设备必须可从 Internet 中访问运行网络设备注册服务的服务器。 例如，将服务器安装在外围网络（也称为 DMZ、隔离区和外围子网）中。<br /><br /> 如果运行网络设备注册服务的服务器和颁发 CA 之间有防火墙，则必须配置该防火墙以允许两个服务器之间的通信流量 (DCOM)。 此防火墙要求也适用于运行 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 站点服务器的服务器以及颁发 CA，以便 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 可以吊销证书。<br /><br /> 如果网络设备注册服务配置为需要 SSL（一种最佳安全方案），请确保连接设备可访问证书吊销列表 (CRL) 以验证服务器证书。<br /><br /> 有关 Windows Server 2012 R2 中的网络设备注册服务的详细信息，请参阅 [Using a Policy Module with the Network Device Enrollment Service（将策略模块与网络设备注册服务配合使用）](http://go.microsoft.com/fwlink/p/?LinkId=328657)。|  
|如果颁发 CA 运行 Windows Server 2008 R2，则服务器对于 SCEP 续订请求需要一个修补程序。|如果颁发 CA 计算机上尚未安装此修补程序，请安装该修补程序。 有关详细信息，请参阅 Microsoft 知识库文章 [2483564：Renewal request for an SCEP certificate fails in Windows Server 2008 R2 if the certificate is managed by using NDES（如果使用 NDES 管理证书，则 SCEP 证书续订请求将在 Windows Server 2008 R2 中失败）](http://go.microsoft.com/fwlink/?LinkId=311945) 。|  
|PKI 客户端身份验证证书和导出的根 CA 证书。|此证书向 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]验证运行网络设备注册服务的服务器。<br /><br /> 有关详细信息，请参阅 [System Center Configuration Manager 的 PKI 证书要求](../LocTest/PKI-certificate-requirements-for-System-Center-Configuration-Manager.md)。|  
|支持的设备操作系统。|你可以将证书配置文件部署到运行 iOS、Windows 8.1、Windows RT 8.1、Windows 10 和 Android 操作系统的设备。|  
  
## Configuration Manager 依赖关系  
  
|依赖关系|更多信息|  
|----------------|----------------------|  
|证书注册点站点系统角色|你必须安装证书注册点站点系统角色，然后才能使用证书配置文件。 此角色与 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 数据库、 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 站点服务器和 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 策略模块通信。<br /><br /> 有关此站点系统角色的系统要求以及在层次结构中的何处安装此角色的详细信息，请参阅 [System Center Configuration Manager 支持的配置](../LocTest/Supported-configurations-for-System-Center-Configuration-Manager.md)主题中的**站点系统要求**部分。<br /><br /> 请注意，证书注册点不能安装在运行网络设备注册服务的同一服务器上。|  
|[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 策略模块|若要部署证书配置文件，你必须安装 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 策略模块。 你可以在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 安装媒体上找到此策略模块。|  
|发现数据|证书使用者和使用者可选名称的值由 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 提供并从通过发现收集的信息中检索：<br /><br /> 关于用户证书：Active Directory 用户发现<br /><br /> 关于计算机证书：Active Directory 系统发现和网络发现|  
|用于管理证书配置文件的特定安全权限|你必须具有下列安全权限才能管理公司资源访问设置，例如证书配置文件、Wi-Fi 配置文件和 VPN 配置文件：<br /><br /> 若要查看和管理证书配置文件的警报和报表：需要对“警报” 对象的“创建” 、“删除” 、“修改” 、“修改报表” 、“读取”  和“运行报表”  权限。<br /><br /> 若要创建和管理证书配置文件：需要“证书配置文件” 对象的“创作策略” 、“修改报表”  、“读取”  和“运行报表”  权限。<br /><br /> 若要管理 Wi-Fi、证书和 VPN 配置文件部署：需要对“集合” 对象的“部署配置策略” 、“修改客户端状态警报” 、“读取”  和“读取资源”  。<br /><br /> 若要管理所有配置策略：需要对“配置策略” 对象的“创建” 、“删除” 、“修改”  、“读取”  和“设置安全作用域”  权限。<br /><br /> 若要运行与证书配置文件相关的查询：需要对“查询”  对象的“读取”  权限。<br /><br /> 若要在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 控制台中查看证书配置文件信息：需要对“站点”  对象的“读取”  权限。<br /><br /> 若要查看证书配置文件的状态消息：需要对“状态消息”  对象的“读取”  权限。<br /><br /> 若要创建和修改受信任的 CA 证书配置文件：需要对“受信任的 CA 证书配置文件” 对象的“创作策略” 、“修改报表”  、“读取”  和“运行报表”  权限。<br /><br /> 若要创建和管理 VPN 配置文件：需要对“VPN 配置文件” 对象的“创作策略” 、“修改报表”  、“读取”  和“运行报表”  权限。<br /><br /> 若要创建和管理 Wi-Fi 配置文件：需要对“Wi-Fi 配置文件” 对象的“创作策略” 、“修改报表”  、“读取”  和“运行报表”  权限。<br /><br /> “公司资源访问管理器”  安全角色包括在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]中管理证书配置文件所需的这些权限。 有关详细信息，请参阅 **Configure role-based administration** 主题中的 [Configure security in System Center Configuration Manager](../LocTest/Configure-security-in-System-Center-Configuration-Manager.md) 部分。|  
  
## 另请参阅  
 [在 System Center Configuration Manager 中规划证书配置文件](../LocTest/Planning-for-certificate-profiles-in-System-Center-Configuration-Manager.md)
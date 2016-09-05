---
title: "System Center Configuration Manager 中内容管理的安全和隐私"
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
ms.assetid: 5f38b726-dc00-433a-ba05-5b7dbb0d8e99
caps.latest.revision: 8
caps.handback.revision: 8
---
# System Center Configuration Manager 中内容管理的安全和隐私
本主题包含 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]中的客户端管理的安全和隐私信息。 请结合以下主题阅读本主题：  
  
-   [System Center Configuration Manager 中应用程序管理的安全和隐私](../LocTest/Security-and-privacy-for-application-management-in-System-Center-Configuration-Manager.md)  
  
-   [System Center Configuration Manager 中软件更新的安全和隐私](../LocTest/Security-and-privacy-for-software-updates-in-System-Center-Configuration-Manager.md)  
  
-   [System Center Configuration Manager 中的操作系统部署的安全和隐私](../LocTest/Security-and-privacy-for-operating-system-deployment-in-System-Center-Configuration-Manager.md)  
  
##  <a name="BKMK_Security_ContentManagement"></a> 内容管理的最佳安全方案  
 为内容管理使用以下最佳安全方案：  
  
 **对于 Intranet 上的分发点，请考虑使用 HTTPS 和 HTTP 的优缺点** - 在大多数情况下，相对于包含加密但未经授权的 HTTPS，使用授权的 HTTP 和包访问帐户具有更高的安全性。 但是，如果内容中有你希望在传输过程加密的敏感数据，请使用 HTTPS。  
  
-   **如果为分发点使用 HTTPS**，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不会使用包访问帐户来授予内容访问权限，但在通过网络传输内容时会对内容进行加密。  
  
-   **如果为分发点使用 HTTP**，可以使用包访问帐户来进行授权，但在通过网络传输内容时不会对内容进行加密。  
  
 **如果为分发点使用 PKI 客户端身份验证证书（而不是自签名证书），请使用强密码保护证书文件 (.pfx)。如果在网络上存储文件，将文件导入到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]** 时，请确保网络通道的安全性 - 当你需要密码来导入客户端身份验证证书（用于分发点与管理点通信）时，这可帮助保护证书免受攻击者的攻击。 在网络位置和站点服务器之间使用 SMB 签名或 IPsec 以防止攻击者篡改证书文件。  
  
 **从站点服务器删除分发点角色** - 默认情况下，分发点和站点服务器安装在同一服务器上。 客户端不必与站点服务器直接通信，因此，为了减少攻击面，请将分发点角色分配给其他站点系统，并将其从站点服务器中删除。  
  
 **保护包访问级别的内容** - 分发点共享允许所有用户读取访问。 要限制可访问内容的用户，请在为 HTTP 配置了分发点时使用包访问帐户。 这一点不适用于基于云的分发点，这些分发点不支持包访问帐户。 有关包访问帐户的详细信息，请参阅[管理帐户以访问内容](Manage%20accounts%20to%20access%20content%20in%20System%20Center%20Configuration%20Manager.md)。
 
  
 **如果 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 在你添加分发点站点系统角色时安装 IIS，请在分发点安装完成时删除 HTTP 重定向以及 IIS 管理脚本和工具** - 分发点不需要 HTTP 重定向和 IIS 管理脚本和工具。 为了减少攻击面，请为 Web 服务器 (IIS) 角色删除这些角色服务。  有关分发点的 Web 服务器 (IIS) 角色服务的详细信息，请参阅 [System Center Configuration Manager 站点和客户端支持的操作系统](../Topic/Supported%20operating%20systems%20for%20sites%20and%20clients%20for%20System%20Center%20Configuration%20Manager.md)。  
  
 **创建包时，请设置包访问权限** - 由于只有在重新分发包时，对包文件上的访问帐户所做的更改才会生效，因此请在第一次创建包时小心设置包访问权限。 当包很大或分发到许多分发点时，以及当用于内容分发的网络带宽容量有限时，这一点尤其重要。  
  
 **实施访问控制来保护包含预留内容的媒体** - 预留内容已压缩但未加密。 攻击者可读取和修改随后下载到设备的文件。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端将拒绝被篡改的内容，但仍将进行下载。  
  
 **仅通过使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 提供的 ExtractContent 命令行工具 (ExtractContent.exe) 导入预留内容，并确保其经过 Microsoft 签名** - 若要避免篡改和特权提升，请仅使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 提供的已授权命令行工具。  
  
 **保护站点服务器和包源位置之间的信道** - 创建应用程序和包时，在站点服务器和包源位置之间使用 IPsec 或 SMB 签名。 这可帮助防止攻击者篡改源文件。  
  
 **如果在安装了任何分发点角色之后更改站点配置选项以使用自定义网站（而不是默认网站），请删除默认虚拟目录** - 从使用默认网站更改为使用自定义网站时，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不会删除虚拟目录。 删除 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 最初在默认网站下创建的虚拟目录：  
  
-   SMS_DP_SMSPKG$  
  
-   SMS_DP_SMSSIG$  
  
-   NOCERT_SMS_DP_SMSPKG$  
  
-   NOCERT_SMS_DP_SMSSIG$  
  
 **针对基于云的分发点，保护订阅的详细信息和证书** - 当使用基于云的分发点时，需保护高价值项目（包括 Azure 订阅的用户名和密码、Azure 管理证书和基于云的分发点服务证书）。 安全地存储证书，如果在配置基于云的分发点时通过网络浏览到这些证书，请在站点系统服务器和源位置之间使用 IPsec 或 SMB 签名。  
  
 **对于基于云的分发点：关于服务持续性，请监视证书的到期日期** -   
                [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不会向你发出警告。 你必须独立于 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 监视过期日期，并确保在到期日期之前续订然后导入新证书。 如果从外部证书颁发机构 (CA) 购买 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 基于云的分发点服务证书，这一点特别重要，因为你可能需要额外的时间来获取续订的证书。  
  
 如果任一证书过期，则“云服务管理器”  将生成状态消息 ID **9425** ， **CloudMgr.log** 文件将包含一个通过过期日期和登录 UTC 指示证书 **is in expired state**的条目。  
  
## 内容管理的安全注意事项  
在规划内容管理时，请考虑以下内容：  
  
-   客户端不会在下载内容之前对其进行验证  
  
     [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端只有在将内容下载到其客户端缓存后才会验证内容上的哈希。 如果攻击者篡改要下载的文件列表或篡改内容本身，则下载过程可能会占用客户端的大量网络带宽，并随后会在遇到无效哈希时丢弃内容。  
  
-   当你使用基于云的分发点时，会将内容自动限制为仅供你的企业访问，并且你无法将其进一步限制为仅供所选用户或组访问。  
  
-   当你使用基于云的分发点时，客户端通过管理点进行验证，然后使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 令牌来访问基于云的分发点。 该令牌的有效时间为 8 小时，因此，如果你因为客户端不再受信任而将其阻止，则在此令牌的有效期过期之前，客户端可继续从基于云的分发点下载内容。 此时，管理点将不会为该客户端发出其他令牌，因为该客户端已被阻止。  
  
     为避免被阻止的客户端在这 8 小时内下载内容，你可从 **控制台“管理”****工作区中“云”****节点的“层次结构配置”**[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 停止云服务。  
  
##  <a name="BKMK_Privacy_ContentManagement"></a> 内容管理的隐私信息  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不会在内容文件中包括任何用户数据（尽管管理用户可能会选择这样做）。  
  
 在配置内容管理之前，请考虑隐私要求。  
    
## 另请参阅  
 [System Center Configuration Manager 中内容管理的基本概念](../LocTest/Fundamental-concepts-for-content-management-in-System-Center-Configuration-Manager.md)   
 [System Center Configuration Manager 的安全性和隐私](../LocTest/Security-and-privacy-for-System-Center-Configuration-Manager.md)
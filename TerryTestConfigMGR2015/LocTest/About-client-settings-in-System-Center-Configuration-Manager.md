---
title: "关于 System Center Configuration Manager 中的客户端设置"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-client
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: f7560876-8084-4570-aeab-7fd44f4ba737
caps.latest.revision: 15
caps.handback.revision: 7
translationtype: Human Translation
---
# 关于 System Center Configuration Manager 中的客户端设置
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的所有客户端设置都在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台内“管理”工作区的“客户端设置”节点中进行管理。 系统随 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 一起提供了一组默认设置。 如果修改默认的客户端设置，则这些设置将应用于层次结构中的所有客户端。 你也可以配置自定义客户端设置，当将这些设置分配给集合时，它们将替代默认客户端设置。 有关如何配置客户端设置的信息，请参阅 [如何在 System Center Configuration Manager 中配置客户端设置](../LocTest/How-to-configure-client-settings-in-System-Center-Configuration-Manager.md)。  
  
 许多客户端设置具有自解释性。 使用下列部分获取有关在配置之前可能需要一些信息的客户端设置的详细信息。  
  
 设备的客户端设置：  
  
-   [后台智能传输](#BKMK_BITS)  
  
-   [客户端策略](#BKMK_ClientPolicyDeviceSettings)  
  
-   [符合性设置](#BKMK_Compliance)  
  
-   [计算机代理](#BKMK_ComputerAgentDeviceSettings)  
  
-   [计算机重新启动](#BKMK_ComputerRestartDeviceSettings)  
  
-   [Endpoint Protection](#BKMK_EndpointProtectionDeviceSettings)  
  
-   [硬件清单](#BKMK_HardwareInventoryDeviceSettings)  
  
-   [按流量计费的 Internet 连接](#BKMK_MeteredInternetConnetionsSettings)  
  
-   [电源管理](#BKMK_PowMgmtDeviceSettings)  
  
-   [远程工具](#BKMK_RemoteToolsDeviceSettings)  
  
-   [软件部署](#BKMK_SoftwareDeploymentDeviceSettings)  
  
-   [软件清单](#BKMK_SoftInventoryDeviceSettings)  
  
-   [软件更新](#BKMK_SoftwareUpdatesDeviceSetting)  
  
-   [用户和设备相关性](#BKMK_UserDeviceAffinityDeviceSettings)  
  
 用户的客户端设置：  
  
-   [移动设备](#BKMK_MobileDevicesUserSettings)  
  
-   [注册](#BKMK_EnrollmentUserSettings)  
  
-   [用户和设备相关性](#BKMK_UserDeviceAffinityUserSettings)  
  
##  <a name="BKMK_ClientSettingsDevices"></a> 设备的客户端设置  
 使用下列部分获取有关客户端设备设置的信息。  
  
###  <a name="BKMK_BITS"></a> 后台智能传输  
  
|设置名|更多信息|  
|---------|----------|  
|**限制 BITS 后台传输的最大网络带宽**|如果将此选项配置为“True”或“是”，则 BITS 带宽限制将由 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端使用。|  
|**限制时段开始时间**|用本地时间指定 BITS 限制时段将开始的开始时间。|  
|**限制时段结束时间**|用本地时间指定 BITS 限制时段将结束的结束时间。 如果此值与“限制时段开始时间”相同，则始终启用 BITS 限制。|  
|**限制时段期间的最大传输速率\(Kbps\)**|指定 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端在指定的 BITS 限制时段内可以使用的最大传输速率 \(Kbps\)。|  
|**允许 BITS 在限制时段外下载**|选择此选项以允许 BITS 在限制时段外下载。 此选项允许 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端在指定的时段之外使用单独的 BITS 设置。|  
|**限制时段外的最大传输速率\(Kbps\)**|指定 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端在指定的 BITS 限制时段外将使用的最大传输速率 \(Kbps\)。 只有选择允许在指定的时段之外使用 BITS 限制时才可以配置此选项。|  
  
###  <a name="BKMK_ClientPolicyDeviceSettings"></a> 客户端策略  
  
|设置名|更多信息|  
|---------|----------|  
|**客户端策略轮询间隔\(分钟\)**|指定以下 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端下载客户端策略的频率：<br /><br /> -   Windows 计算机（例如，台式机、服务器、便携计算机）<br />-   [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 注册的移动设备<br />-   Mac 计算机<br />-   运行 Linux 或 UNIX 的计算机|  
|**在客户端上启用用户策略轮询**|将此设置配置为“True”或“是”并且 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 发现了用户，则计算机上的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端将接收以登录的用户为目标的应用程序和程序。 有关如何发现用户的详细信息，请参阅[运行 System Center Configuration Manager 发现](../LocTest/Run-discovery-for-System-Center-Configuration-Manager.md)中的[为计算机、用户或组配置 Active Directory 发现](../LocTest/Run-discovery-for-System-Center-Configuration-Manager.md#BKMK_ConfigADDiscGeneral)。<br /><br /> 由于应用程序目录从站点服务器接收可供用户使用的软件的列表，因此不必将此设置配置为“真”或“是”，用户便可以从应用程序目录中查看和请求应用程序。 但是，如果此设置为“假”或“否”，则在用户使用应用程序目录时以下各项将不工作：<br /><br /> -   用户无法安装他们在应用程序目录中看到的应用程序。<br />-   用户将看不到有关他们的应用程序批准请求的通知。 相反，他们必须刷新应用程序目录并检查审批状态。<br />-   用户将不会收到发布到应用程序目录的应用程序的修订和更新。 但是，他们会在应用程序目录中看到对应用程序所做更改的信息。<br />-   如果在客户端应用程序目录中安装应用程序后删除应用程序部署，则客户端最多会对是否安装了应用程序的情况继续检查 2 天。<br /><br /> 此外，如果此设置为“假”或“否”，则用户将不会收到为用户部署的所需应用程序，也不会收到用户策略中包含的任何其他管理操作。<br /><br /> 如果用户的计算机在 Intranet 和 Internet 上，则此设置适用于用户；如果你也想对 Internet 启用用户策略，则必须将此设置配置为“真”或“是”。|  
|**启用来自 Internet 客户端的用户策略请求**|如果为基于 Internet 的客户端管理配置客户端和站点，并且将此选项配置为“真”或“是”且以下两个条件都适用，则当用户的计算机在 Internet 上时，用户将收到用户策略：<br /><br /> -   “在客户端上启用用户策略轮询”客户端设置配置为“真”或“在客户端上启用用户策略”配置为“是”。<br />-   基于 Internet 的管理点可通过使用 Windows 身份验证（Kerberos 或 NTLM）成功地对用户进行验证。<br /><br /> 如果将此选项保留为“假”或“否”，或者任何一个条件失败，则 Internet 上的计算机将仅收到计算机策略。 在此情况下，用户仍然能够查看、请求和安装基于 Internet 的应用程序目录中的应用程序。 如果此设置为“假”或“否”，但“在客户端上启用用户策略轮询”配置为“真”或“在客户端上启用用户策略”配置为“是”，则在计算机连接到 Intranet 之前，用户将不会收到用户策略。<br /><br /> 有关在 Internet 上管理客户端的详细信息，请参阅[System Center Configuration Manager 中终结点之间的通信](../LocTest/Communications-between-endpoints-in-System-Center-Configuration-Manager.md)中的[来自 Internet 或不受信任林的客户端通信的注意事项](../LocTest/Communications-between-endpoints-in-System-Center-Configuration-Manager.md#BKMK_clientspan)。 **Note:**  来自用户的应用程序批准请求不需要用户策略或用户身份验证。|  
  
###  <a name="BKMK_Compliance"></a> 符合性设置  
  
|设置名|更多信息|  
|---------|----------|  
|**计划符合性评估**|单击“计划”以创建将在用户部署配置基线时向用户显示的默认计划。 可以在“部署配置基线”对话框中为每个基线配置此值。|  
|**启用用户数据和配置文件**|如果想要向层次结构中的 Windows 8 计算机部署用户数据和配置文件配置项目，请选择“是”。<br /><br /> 有关用户数据和配置文件的详细信息，请参阅 [如何在 System Center Configuration Manager 中创建用户数据和配置文件的配置项目](../LocTest/How-to-create-user-data-and-profiles-configuration-items-in-System-Center-Configuration-Manager.md)。|  
  
###  <a name="BKMK_ComputerAgentDeviceSettings"></a> 计算机代理  
  
|设置名|更多信息|  
|---------|----------|  
|**默认应用程序目录网站点**|[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 使用此设置将用户连接到软件中心中的应用程序目录。 你可以通过 NetBIOS 名称或 FQDN 指定承载应用程序目录网站点的服务器、指定自动检测，或者指定自定义部署的 URL。 在大多数情况下，自动检测是最佳选择，因为它具有下列优点：<br /><br /> -   如果客户端的站点包含应用程序目录网站点，则从客户端站点中向客户端自动提供应用程序目录网站点。<br />-   防御未授权服务器，因为 Intranet 上被配置为使用 HTTPS 的应用程序目录网站点优先于未被配置为使用 HTTPS 的应用程序目录网站点。<br />-   对基于 Intranet 和 Internet 的客户端管理配置客户端后，如果客户端在 Internet 上，则会为它们提供基于 Internet 的应用程序目录网站点；如果客户端在 Intranet 上，则会为它们提供基于 Intranet 的应用程序目录网站点。<br /><br /> 自动检测不保证将为客户端提供与其最接近的应用程序目录网站点。 由于以下原因，你可能决定不使用“自动检测”：<br /><br /> -   你想要为客户端手动配置最接近的服务器，或者确保客户端不跨慢速网络连接连接到服务器。<br />-   你想要控制哪些客户端连接到哪台服务器。 这可能是出于测试、性能或商业原因。<br />-   你不想等待 25 个小时之久，或者不想为客户端网络更改配置其他应用程序目录网站点。<br /><br /> 如果指定应用程序目录网站点而不是使用自动检测，请指定 NetBIOS 名称而不是 Intranet FQDN，以帮助减少在用户连接到 Intranet 上的应用程序目录时提示用户输入凭据的可能性。 要使用 NetBIOS 名称，必须应用下列条件：<br /><br /> -   在应用程序目录网站点属性中指定 NetBIOS 名称。<br />-   使用与应用程序目录网站点在同一域中的 WINS 或所有客户端。<br />-   针对 HTTP 客户端连接或 HTTPS 客户端连接配置了应用程序目录网站点，并且 Web 服务器证书包含 NetBIOS 名称。<br /><br /> 通常，当 URL 包含 FQDN 时会提示用户输入凭据，但当 URL 为 NetBIOS 名称时不会。 当用户从 Internet 进行连接时，应该始终提示用户，因为此连接必须使用 Internet FQDN。 如果当用户在 Internet 上时提示用户输入凭据，请确保运行应用程序目录网站点的服务器可以连接到用户帐户的域控制器，以便可以使用 Kerberos 对用户进行身份验证。 **Note:**  自动检测的工作原理： 客户端向管理点提出服务位置请求。 如果存在与客户端在同一站点中的应用程序目录网站点，则会将此服务器作为应用程序目录服务器提供给客户端使用。 如果站点中有多个可用的应用程序目录网站点，则启用 HTTPS 的服务器优先于未启用 HTTPS 的服务器。 在进行此筛选之后，会为所有客户端提供服务器之一以用作应用程序目录；[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不在多个服务器之间进行负载平衡。 如果客户端的站点不包含应用程序目录网站点，则管理点会不确定地从层次结构中返回应用程序目录网站点。 当客户端在 Intranet 上时，如果为所选的应用程序目录网站点配置了应用程序目录 URL 的 NetBIOS 名称，则会为客户端提供此 NetBIOS 名称，而不是 Intranet FQDN。 当检测到客户端在 Internet 时，仅向客户端提供 Internet FQDN。 每 25 个小时或者每当客户端检测到网络更改时，客户端便会提出此服务位置请求。 例如，客户端从 Intranet 移动到 Internet，并且客户端可以查找基于 Internet 的管理点，则基于 Internet 的管理点会将基于 Internet 的应用程序目录网站点服务器提供给客户端。|  
|**向 Internet Explorer 受信任的站点区域添加默认应用程序目录网站**|如果将此选项配置为“真”或“是”，则当前默认应用程序目录网站 URL 会自动添加到客户端上 Internet Explorer 的受信任的站点区域中。<br /><br /> 此设置确保不启用 Internet Explorer 的“保护模式”设置。 如果启用“保护模式”，则 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端可能无法安装应用程序目录中的应用程序。 默认情况下，受信任的站点区域还支持应用程序目录用户登录，这需要 Windows 身份验证。<br /><br /> 如果将此选项保留为“False”，则 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端可能无法从应用程序目录安装应用程序，除非在客户端使用的应用程序目录 URL 的另一个区域中配置这些 Internet Explorer 设置。 **Note:**  每当 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将默认的应用程序目录添加到受信任的站点区域中时，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 会删除 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 在添加新条目之前添加的以前的默认应用程序目录 URL。 如果已在安全区域之一中指定了 URL，则 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 无法添加此 URL。 在此情况下，你必须从其他区域中删除此 URL，或者手动配置所需的 Internet Explorer 设置。|  
|**允许 Silverlight 应用程序在提升的信任模式下运行**|如果用户运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端并使用应用程序目录，则必须将此设置配置为“是”。<br /><br /> 如果更改此设置，则当用户下次加载其浏览器或刷新其当前打开的浏览器窗口时，更改将生效。<br /><br /> 有关此设置的详细信息，请参阅[System Center Configuration Manager 中应用程序管理的安全和隐私](../LocTest/Security-and-privacy-for-application-management-in-System-Center-Configuration-Manager.md)中的[Microsoft Silverlight 5 的证书，以及应用程序目录所需的提升的信任模式](../LocTest/Security-and-privacy-for-application-management-in-System-Center-Configuration-Manager.md#BKMK_CertificatesSilverlight5)。|  
|**软件中心中显示的组织名称**|键入用户在软件中心中看到的名称。 此品牌信息有助于用户将此应用程序识别为受信任的源。|  
|**使用新的软件中心**|如果启用，则这些客户端设置所针对的所有客户端计算机都将使用新的软件中心，以显示以前只在依赖于 Silverlight 的应用程序目录中可访问的用户可用的应用。<br /><br /> 但是，仍然需要应用程序目录网站点站点系统角色和应用程序目录 Web 服务点站点系统角色来让用户可用的应用显示在软件中心。<br /><br /> 有关详细信息，请参阅 [规划和配置 System Center Configuration Manager 中的应用程序管理](../LocTest/Plan-for-and-configure-application-management-in-System-Center-Configuration-Manager.md)。|  
|**安装权限**|**Warning:**  此设置适用于应用程序目录和软件中心。 当用户使用公司门户时，此设置不起作用。 <br /><br /> 配置用户启动软件、软件更新和任务序列安装的方式：<br /><br /> -   **所有用户**：使用除“来宾”之外的任何权限登录到客户端计算机的用户可以启动软件、软件更新和任务序列的安装。<br />-   **仅限管理员**：登录到客户端计算机的用户必须是本地管理员组的成员才能启动软件、软件更新和任务序列的安装。<br />-   **仅限管理员和主要用户**：登录到客户端计算机的用户必须是本地管理员组的成员或计算机的主要用户才能启动软件、软件更新和任务序列的安装。<br />-   **无用户**：登录到客户端计算机的用户无法启动软件、软件更新和任务序列的安装。 计算机的所需部署始终在截止时间安装，用户无法从应用程序目录或软件中心启动软件安装。|  
|**重新启动时挂起 Bitlocker PIN 项**|如果在计算机上配置了 BitLocker PIN 条目，则在软件安装之后重启计算机时，此选项可以略过输入 PIN 的要求。<br /><br /> -   **始终**：[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 在安装了需要重启的软件并且启动了计算机重启之后，它会临时挂起 BitLocker 提出的在下次计算机重启时输入 PIN 的要求。 此设置仅适用于 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 启动的计算机重启，当用户重启计算机时，它不会挂起输入 BitLocker PIN 的要求。 在 Windows 启动后恢复 BitLocker PIN 输入要求。<br />-   **从不**：[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 在安装了需要重启的软件之后，它不会挂起 BitLocker 提出的在下次计算机重启时输入 PIN 的要求。 在此情况下，直到用户输入 PIN 来完成标准启动过程并加载 Windows，才能完成软件安装。|  
|**其他用于管理应用程序部署和软件更新的软件**|只有在下列条件之一成立时才启用此选项：<br /><br /> -   你使用需要启用此设置供应商解决方案。<br />-   你使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 软件开发工具包 \(SDK\) 来管理客户端代理通知以及应用程序和软件更新的安装。 **Warning:**  如果在任一条件都不适用时选择此选项，则将不在客户端上安装软件更新和所需的应用程序。 此设置不阻止用户安装应用程序目录中的应用程序，或者不阻止在客户端计算机上安装包和程序以及任务序列。|  
|**PowerShell 执行策略**|配置 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端运行 Windows PowerShell 脚本的方式。 这些脚本经常用于检测配置项目中的符合性设置，但也可以在开发过程中作为标准脚本发送。<br /><br /> -   **绕过**：[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端在客户端计算机上绕过 Windows PowerShell 配置，以便未签名的脚本可以运行。<br />-   “受限”：[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端在客户端计算机上使用当前的 Windows PowerShell 配置，以便确定未签名的脚本是否可以运行。<br />-   **已全部签名**：只有当受信任的发布者对脚本进行了签名，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端才能运行这些脚本。 系统将应用此限制，而与客户端计算机上的当前 Windows PowerShell 配置无关。<br /><br /> 此选项至少需要 Windows PowerShell 版本 2.0，并且默认值为“已全部签名”。 **Tip:**  如果由于此客户端设置的缘故而无法运行未签名的脚本，则 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 会用以下方法报告此错误： <ul><li>错误 ID“0X87D00327”和“脚本未签名”的说明作为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台的“监视”工作区中的部署状态错误。</li><li>错误代码“0X87D00327”及描述“脚本未签名”，或“0X87D00320”及描述“尚未安装脚本宿主”（报表中的错误类型为“发现错误”，如“资产配置基线中配置项目的错误详细信息”）。</li><li>**Script is not signed \(Error: 87D00327; Source: CCM\)** 文件中的消息 **DcmWmiProvider.log**。</li></ul>|  
|**禁用截止时间随机化**|此设置确定在达到截止时间时客户端是否使用长达两个小时的激活延迟来安装所需的软件更新。 默认情况下，激活延迟处于禁用状态。<br /><br /> 对于虚拟桌面基础结构 \(VDI\) 情况，此延迟可有助于为具有运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端的多个虚拟机的计算机分发 CPU 处理以及数据传输。 即使不使用 VDI，如果许多客户端同时安装相同的更新，那么这也可能会在站点服务器上负面增加 CPU 使用率，减慢分发点的速度，以及大大减小可用网络带宽。<br /><br /> 如果在达到配置的截止时间时必需毫不延迟地安装所需的软件更新，请对此设置选择“是”。|  
  
###  <a name="BKMK_ComputerRestartDeviceSettings"></a> 计算机重新启动  
 如果指定这些计算机重启设置，请确保重启临时通知间隔的值与最终倒计时间隔的值的持续时间比应用于计算机的最短维护时段还短。  
  
 有关维护时段的详细信息，请参阅[如何在 Configuration Manager 中使用维护时段](../LocTest/How-to-use-maintenance-windows-in-System-Center-Configuration-Manager.md)。  
  
###  <a name="BKMK_EndpointProtectionDeviceSettings"></a> Endpoint Protection  
  
|设置名|更多信息|  
|---------|----------|  
|**在客户端计算机上管理 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端**|如果想要在你的层次结构中的计算机上管理现有的 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端，请选择“True”或“是”。<br /><br /> 如果已经安装了 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端并且想要使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 来管理它，请选择此选项。<br /><br /> 此外，如果想要创建脚本来卸载现有反恶意软件解决方案、安装 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端以及使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 应用程序或包和程序来部署此脚本，请选择此选项。|  
|**在客户端计算机上安装 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端**|选择“True”或“是”，以在尚未安装该客户端的客户端计算机上安装和启用 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端。 **Note:**  如果已经安装了 Endpoint Protection 客户端，则选择“假”或“否”将不卸载 Endpoint Protection 客户端。 若要卸载 Endpoint Protection 客户端，请将“在客户端计算机上管理 Endpoint Protection 客户端”客户端设置设为“假”或“否”，然后部署包和程序以卸载 Endpoint Protection 客户端。|  
|**安装 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 之前，自动删除以前安装的反恶意软件**|选择“真”或“是”以卸载现有反恶意软件。 **Note:**  [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 试图仅卸载下列反恶意软件： <ul><li>Symantec AntiVirus Corporate Edition 版本10</li><li>Symantec Endpoint Protection 版本 11</li><li>Symantec Endpoint Protection Small Business Edition 版本 12</li><li>McAfee VirusScan Enterprise 版本 8</li><li>Trend Micro OfficeScan</li><li>Microsoft Forefront Codename Stirling Beta 2</li><li>Microsoft Forefront Codename Stirling Beta 3</li><li>Microsoft Forefront Client Security 版本 1</li><li>Microsoft Security Essentials 版本 1</li><li>Microsoft Security Essentials 2010</li><li>Microsoft Forefront Endpoint Protection 2010</li><li>Microsoft Security Center Online 版本 1</li></ul> <br /><br /> 如果尝试在计算机上安装 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端，并且不支持卸载现有恶意软件解决方案，则 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端安装将失败。 在这种情况下，可以使用应用程序管理来卸载现有反恶意软件解决方案，安装 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端，然后使用“在客户端计算机上管理 Endpoint Protection 客户端”客户端设置，以使 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 管理新安装的 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端。|  
|**对于带有写入筛选器的 Windows Embedded 设备，提交 Endpoint Protection 客户端安装\(需要重新启动\)**|选择“是”以对 Windows Embedded 设备禁用写入筛选器并重启该设备。 这会在设备上执行安装。<br /><br /> 如果指定“否”，则在临时覆盖区上安装客户端，重启设备时会清除此临时覆盖区。 在此情况下不会提交 Endpoint Protection 客户端，直到另一个安装对设备执行更改为止。 此为默认设置。|  
|**在安装 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端后，禁止任何要求的计算机重启**|如果在安装 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端后需要，请选择“True”或“是”，以禁止计算机重启。 **Important:**  如果 Endpoint Protection 客户端需要计算机重启，并且将此设置配置为“假”，则将进行重启，而与已经配置的任何维护时段无关。|  
|**允许用户将要求的重新启动推迟一段时间，以完成 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 安装（小时）**|如果在安装 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端后需要计算机重启，请指定用户可以延迟计算机重启的小时数。 此选项只有“安装 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端后禁止任何要求的计算机重启”选项设置为“False”时才可以进行配置。|  
|**禁用替代源\(例如 Windows 更新、Microsoft Windows Server Update Services 或 UNC 共享\)来更新客户端计算机的初始定义**|如果希望 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 仅在客户端计算机上安装初始定义更新，请选择“True”或“是”。 此设置可有助于在初次安装定义更新期间避免不必要的网络连接以及减小网络带宽。|  
  
###  <a name="BKMK_HardwareInventoryDeviceSettings"></a> 硬件清单  
  
|设置名|更多信息|  
|---------|----------|  
|**最大自定义 MIF 文件大小\(KB\)**|指定将在硬件清单周期过程中从客户端收集的每个自定义管理信息格式 \(MIF\) 文件所允许的最大大小，以千字节 \(KB\) 为单位。 如果任何 MIF 文件超过此大小，则 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 硬件清单将不处理这些文件。 你可以指定介于 1 和 5000 KB 之间的大小。 默认情况下，此值设置为 250 KB。 此设置不影响常规硬件清单数据文件的大小。 **Note:**  此设置仅在默认客户端设置中可用。|  
|**硬件清单类**|在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中，你可以扩展从客户端中收集的硬件信息，而不用手动编辑 sms\_def.mof 文件。 如果想要扩展 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 硬件清单，请单击“设置类”。 有关详细信息，请参阅 [如何在 System Center Configuration Manager 中扩展硬件清单](../LocTest/How-to-configure-hardware-inventory-in-System-Center-Configuration-Manager.md)。|  
|**收集 MIF 文件**|使用此设置指定是否在硬件清单期间从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端中收集管理信息格式 \(MIF\) 文件。<br /><br /> 为了按照硬件清单收集 MIF 文件，此文件必须位于客户端计算机上的正确位置中。 默认情况下，这些文件的位置应该如下所示：<br /><br /> -   IDMIF 文件应位于 Windows\\System32\\CCM\\Inventory\\Idmif 文件夹中。<br />-   NOIDMIF 文件应位于 Windows\\System32\\CCM\\Inventory\\Noidmif 文件夹中。 **Note:**  此设置仅在默认客户端设置中可用。|  
  
###  <a name="BKMK_MeteredInternetConnetionsSettings"></a> 按流量计费的 Internet 连接  
 你可以管理 Windows 8 客户端计算机在使用按流量计费的 Internet 连接时如何与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点通信。 Internet 提供商有时根据你在按流量计费的 Internet 连接上发送和接收的数据量计费。  
  
> [!NOTE]  
>  在以下情况下，配置的客户端设置不适用于 Windows 8 客户端计算机：  
>   
>  -   计算机采用漫游数据连接：[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端不会执行需要将数据传输到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点的任何操作。  
> -   Windows 网络连接属性被配置为不按流量计费：[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端的行为方式好像是不按流量计费的 Internet 连接，因此会将数据传输至 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点。  
  
|设置名|更多信息|  
|---------|----------|  
|**客户端通过按流量计费的 Internet 连接进行的通信**|从下拉列表中，针对 Windows 8 客户端计算机选择以下选项之一：<br /><br /> <ul><li>**允许**：除非客户端设备正在使用漫游数据连接，否则允许通过按流量计费的 Internet 连接进行所有客户端通信。</li><li>**限制**：只允许通过按流量计费的 Internet 连接进行以下客户端通信：<br /><br /> <ul><li>客户端策略检索</li><li>将发送到站点的客户端状态消息</li><li>通过使用应用程序目录提出的软件安装请求</li><li>所需部署（达到安装截止时间后）</li></ul> **Important:**      如果用户从软件中心或应用程序目录中启动软件安装，则始终允许这些项，与按流量计费的 Internet 连接设置无关。 <br /><br />     如果达到按流量计费的 Internet 连接的数据传输限制，则客户端不再尝试与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点通信。</li><li>**阻止**：[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端采用按流量计费的 Internet 连接时不尝试与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点通信。 此为默认值。</li></ul>|  
  
###  <a name="BKMK_PowMgmtDeviceSettings"></a> 电源管理  
  
|设置名称|更多信息|  
|----------|----------|  
|**允许用户从电源管理中排除其设备**|从下拉列表中，选择“真”或“是”，以允许软件中心的用户从任何配置的电源管理设置中排除其计算机。|  
|**启用唤醒代理**|指定“是”以在为单播包配置站点 LAN 唤醒设置后对其进行补充。<br /><br /> 有关唤醒代理的详细信息，请参阅[Planning How to Wake Up Clients in System Center Configuration Manager](../Topic/Planning%20How%20to%20Wake%20Up%20Clients%20in%20System%20Center%20Configuration%20Manager.md)。 **Warning:**  在未首先了解唤醒代理的工作原理以及在测试环境中对其进行评估之前，请不要在生产网络中启用唤醒代理。|  
|**唤醒代理端口号\(UDP\)**|保留管理器计算机用于向睡眠中计算机发送唤醒包的端口号的默认值，或者将此数字更改为你选择的值。<br /><br /> 如果你配置“针对唤醒代理的 Windows 防火墙例外”选项，则会为运行 Windows 防火墙的客户端自动配置在此处指定的端口号。 如果客户端运行另一个防火墙，则你必须手动将其配置为允许为此设置指定的 UDP 端口号。|  
|**LAN 唤醒端口号\(UDP\)**|保留默认值 9，除非在站点的“属性”的“端口”选项卡中更改了 LAN 唤醒 \(UDP\) 端口号。 **Important:**  此数字必须与站点“属性”中的数字匹配。 如果在一个位置更改此数字，则不会在其他位置自动更新此数字。|  
  
###  <a name="BKMK_RemoteToolsDeviceSettings"></a> 远程工具  
  
|设置名称|更多信息|  
|----------|----------|  
|**在客户端上启用远程控制**<br /><br /> **防火墙例外配置文件**|选择是否为接收这些客户端设置的所有客户端计算机启用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 远程控制。 单击“配置”以启用远程控制，并根据需要将防火墙设置配置为允许远程控制在客户端计算机上工作。 **Important:**  如果未配置防火墙设置，则远程控制可能无法正常工作。 **Note:**  默认情况下，禁用了远程控制。|  
|**用户可以在软件中心内更改策略或通知设置**|选择用户是否可以从软件中心中更改远程控制选项。|  
|**允许远程控制无人参与的计算机**|选择管理员是否可以使用远程控制来访问注销或锁定的客户端计算机。 禁用此设置后，只能远程控制登录和解锁的计算机。|  
|**提示用户提供远程控制权限**|选择客户端计算机是否将显示一条消息，以在允许远程控制会话之前请求提供用户的权限。|  
|**将远程控制权限授予本地管理员组**|选择服务器上启动远程控制连接的本地管理员是否可以与客户端计算机建立远程控制会话。|  
|**允许的访问级别**|指定将允许的远程控制访问级别。 可以选择：<br /><br /> -   完全控制<br />-   仅查看<br />-   无|  
|**允许的查看者**|单击“设置查看者”打开“配置客户端设置”对话框，并指定可以与客户端计算机建立远程控制会话的 Windows 用户的名称。|  
|**在任务栏上显示会话通知图标**|选择此选项以在客户端计算机的任务栏上显示一个图标，来指明远程控制会话处于活动状态。|  
|**显示会话连接栏**|选择此选项以在客户端计算机上显示高可见性会话连接栏，来指明远程控制会话处于活动状态。|  
|**在客户端上播放声音**|选择此选项以当远程控制会话在客户端计算机上处于活动状态时用声音指明。 你可以在会话连接或断开时播放声音，或者可以在会话过程中重复播放声音。|  
|**管理未经请求的远程协助设置**|选择此选项以允许 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 管理未经请求的远程协助会话。<br /><br /> 未经请求的远程协助会话是指其中的客户端计算机用户不请求协助以启动会话的那些会话。|  
|**管理经请求的远程协助设置**|选择此选项以允许 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 管理经请求的远程协助会话。<br /><br /> 经请求的远程协助会话是指其中的客户端计算机用户向管理员发送远程协助请求的会话。|  
|**远程协助访问级别**|选择访问级别以分配给在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中启动的远程协助会话。 **Note:**  客户端计算机用户必须始终允许发生远程帮助会话。|  
|**管理远程桌面设置**|选择此选项以允许 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 管理计算机的远程桌面会话。|  
|**允许获得许可的查看者使用远程桌面连接进行连接**|选择此选项以允许将允许的查看者列表中指定的用户添加到客户端计算机上的远程桌面本地用户组中。|  
|**在运行 Windows Vista 和更高版本的操作系统的计算机上要求网络级别身份验证**|如果想要使用网络级别身份验证与运行 Windows Vista 或更高版本的客户端计算机建立远程桌面连接，请选择此更加安全的选项。 网络级别身份验证最初需要较少的远程计算机资源，因为它在建立远程桌面连接之前完成用户身份验证。 此方法更加安全，因为它可以帮助保护计算机不受恶意用户或软件的攻击，并且可减小拒绝服务攻击风险。|  
  
###  <a name="BKMK_SoftwareDeploymentDeviceSettings"></a> 软件部署  
  
|设置名|更多信息|  
|---------|----------|  
|**计划部署的重新评估**|配置 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 为所有部署重新评估要求规则的时间计划。 默认值为每 7 天一次。 **Important:**  建议不要将此值更改为低于默认值的值，因为这可能会对网络和客户端计算机性能有负面影响。 <br /><br /> 还可以通过从控制面板中的“Configuration Manager”的“操作”选项卡选择“应用程序部署评估周期”操作，从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端计算机初始化此操作。|  
  
###  <a name="BKMK_SoftInventoryDeviceSettings"></a> 软件清单  
  
|设置名|更多信息|  
|---------|----------|  
|**清单报告详细信息**|指定要列出清单的文件信息的级别。 你可以仅列出关于文件的详细信息清单、列出关于与文件关联的产品的详细信息清单，或者列出关于文件的所有信息清单。|  
|**列出这些文件类型的清单**|如果想要指定要列出清单的文件类型，请单击“设置类型”，然后在“配置客户端设置”对话框中配置以下各项： **Note:**  如果对计算机应用了多个自定义客户端设置，则将合并每个设置返回的清单。 <br /><br /> -   单击“新建”图标以将新文件类型添加到清单中，然后在“清单文件属性”对话框中指定以下信息：<br />-   **名称** \- 提供要列出清单的文件的名称。 你可以使用“\*”字符来表示任何文本字符串，使用“?”字符来表示任何单一字符。 例如，如果想要列出扩展名为 .doc 的所有文件的清单，请指定文件名 **\*.doc**。<br />-   “位置”– 单击“设置”，打开“路径属性”对话框。 你可以配置软件清单以在所有客户端硬盘中搜索指定的文件，搜索指定的路径（例如 **C:\\Folder**）或指定的变量（例如 *%windir%*），并且也可以搜索指定路径下面的所有子文件夹。<br />-   **排除加密文件和压缩文件** – 如果选择此选项，则将不列出压缩或加密的任何文件的清单。<br />-   **排除 Windows 文件夹中的文件** – 如果选择此选项，则将不列出 Windows 文件夹及其子文件夹中的任何文件的清单。<br />-   单击“确定”以关闭“清单文件属性”对话框。<br />-   添加想要列出清单的所有文件，然后单击“确定”以关闭“配置客户端设置”对话框。|  
|**收集文件**|如果想从客户端计算机中收集文件，请单击“设置文件”，然后配置以下各项： **Note:**  如果对计算机应用了多个自定义客户端设置，则将合并每个设置返回的清单。 <br /><br /> -   在“配置客户端设置”对话框中，单击新建图标以添加要收集的文件。<br />-   在“收集的文件属性”对话框中，提供以下信息：<br />-   **名称** \- 提供要收集的文件的名称。 你可以使用“\*”字符来表示任何文本字符串，使用“?”字符来表示任何单一字符。<br />-   “位置”– 单击“设置”，打开“路径属性”对话框。 你可以配置软件清单以在所有客户端硬盘中搜索要收集的文件，搜索指定的路径（例如 **C:\\Folder**）或指定的变量（例如 *%windir%*），并且也可以搜索指定路径下面的所有子文件夹。<br />-   **排除加密文件和压缩文件** – 如果选择此选项，则将不收集压缩或加密的任何文件。<br />-   “文件的总大小超过 \(KB\) 时停止文件收集”– 指定文件大小（以 KB 为单位），之后将不再收集“名称”下指定的文件。 **Note:**      站点服务器收集五个最近更改的收集文件版本，并将它们存储在 *\<ConfigMgr 安装目录\>***\\Inboxes\\Sinv.box\\Filecol** 目录中。 如果自上次软件清单收集以来文件未更改，则不会再收集该文件。     软件清单不收集超过 20 MB 的文件。     “配置客户端设置”对话框中的“所有收集的文件的最大大小\(KB\)”值显示所有收集的文件的最大大小。 达到该大小后，将停止文件收集。 已收集的任何文件都会被保留并发送到站点服务器。 **Important:**      如果将软件清单配置为收集许多大文件，则这可能会对网络和站点服务器的性能有负面影响。 <br />     有关如何查看收集的文件的信息，请参阅 [如何使用资源浏览器来查看 System Center Configuration Manager 中的软件清单](../LocTest/How-to-use-Resource-Explorer-to-view-software-inventory-in-System-Center-Configuration-Manager.md)。<br />-   单击“确定”以关闭“收集的文件属性”对话框。<br />-   添加想要收集的所有文件，然后单击“确定”以关闭“配置客户端设置”对话框。|  
|**设置名称**|在列出软件清单过程中，会从安装在站点客户端上的文件的标题信息中检索制造商名称和产品名称。 因为这些名称在文件标题信息中并不始终是标准化名称，所以当你在资源浏览器中查看软件清单信息或运行查询时，有时可能会显示相同制造商或产品名称的不同版本。 如果想要标准化这些显示名称，请单击“设置名称”，然后在“配置客户端设置”对话框中配置以下各项：<br /><br /> -   **名称类型**：软件清单收集关于制造商和产品的信息。 从下拉列表中，选择是要为“制造商”还是“产品”配置显示名称。<br />-   **显示名称**：指定想要用来替代“清单名称”列表中的名称的显示名称。 可以单击“新建”图标以指定新的显示名称。<br />-   清单名称：\- 单击“新建”图标以添加一个新清单名称，该名称将在软件清单中被“显示名称”列表中所选择的名称替代。 你可以添加将替换的多个名称。|  
  
###  <a name="BKMK_SoftwareUpdatesDeviceSetting"></a> 软件更新  
  
|设置名|更多信息|  
|---------|----------|  
|**在客户端上启用软件更新**|使用此设置在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端上启用软件更新。 如果清除此设置，则 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 会从客户端中删除现有的部署策略。 当重新启用此设置时，客户端会下载当前部署策略。 **Important:**  如果清除此设置，则依赖于软件更新设备设置的 NAP 和符合性设置策略将不再有用。|  
|**软件更新扫描计划**|使用此设置指定客户端启动软件更新符合性评估扫描的频率。 此符合性评估扫描确定客户端上的软件更新的状态（例如必需或者已安装）。 有关符合性评估的详细信息，请参阅[软件更新符合性评估](../LocTest/Introduction-to-software-updates-in-System-Center-Configuration-Manager.md#BKMK_SUMCompliance)。<br /><br /> 默认情况下，会使用简单的计划，而且符合性扫描每 7 天启动一次。 可以选择创建自定义计划以指定确切的开始日期和时间，选择是使用 UTC 还是使用本地时间，以及为一周中的特定日配置重复间隔。 **Note:**  如果指定小于 1 天的间隔，则 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将自动默认为 1 天。 **Warning:**  客户端计算机上的实际开始时间是开始时间加上随机的一段时间（最多为 2 小时）。 这可以防止客户端计算机同时启动扫描和连接到活动软件更新点服务器上的 Windows Server Update Services \(WSUS\)。|  
|**计划部署重新评估**|使用此设置可配置软件更新客户端代理重新评估 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端计算机上的软件更新安装状态的频率。 如果在客户端计算机上无法再找到以前安装的软件更新，但仍然需要它们，则会重新安装这些软件更新。 应根据公司的软件更新符合性策略、用户是否能够卸载软件更新等因素来调整部署重新评估计划，而且在这样做时还应考虑到每个部署重新评估周期都会导致一些网络和客户端计算机 CPU 活动。 默认情况下，会使用简单的计划，而且部署重新评估扫描每 7 天启动一次。 **Note:**  如果指定小于 1 天的间隔，则 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将自动默认为 1 天。|  
|**在达到任何软件更新部署截止时间时，安装所有截止时间在指定时间段内的其他软件更新部署**|使用此设置可安装截止时间在指定时间段内的所需部署中的所有软件更新。 在达到所需的某个软件更新部署的截止时间时，会在客户端上启动该部署中的软件更新的安装过程。 此设置确定是否也启动在所需的其他部署（它们的截止时间被配置为在指定的时间段内）中定义的软件更新的安装过程。<br /><br /> 使用此设置可加快所需的软件更新的软件更新安装速度，从而可能可以提高安全性、减少显示的通知数和减少客户端计算机上的系统重新启动次数。 默认情况下不启用此设置。|  
|**在此时间段内截止的所有挂起的部署在一定时间内也将进行安装。**|使用此设置可指定前一个设置的时间段。 可以输入介于 1 到 23 个小时和介于 1 到 365 天的值。 默认情况下，此设置将配置为 7 天。|  
  
###  <a name="BKMK_UserDeviceAffinityDeviceSettings"></a> 用户和设备相关性  
  
|设置名|更多信息|  
|---------|----------|  
|**用户设备相关性使用情况阈值\(分钟\)**|指定在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 创建用户设备相关性映射之前的分钟数。|  
|**用户设备相关性使用情况阈值\(天\)**|指定基于使用情况的相关性阈值的测量天数。 **Note:**  例如，如果将“用户设备相关性使用情况阈值\(分钟\)”指定为“60”分钟，并将“用户设备相关性使用情况阈值\(天\)”指定为“5”天，那么，用户必须在 5 天的期间内使用设备 60 分钟，才能自动创建用户设备相关性。|  
|**利用使用情况数据自动配置用户设备相关性**|选择“True”或“是”，启用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 以基于收集的使用情况信息自动创建用户设备相关性。|  
  
##  <a name="BKMK_ClientSettingsUsers"></a> 用户的客户端设置  
 使用下列部分来了解有关客户端上的用户设置的信息。  
  
###  <a name="BKMK_MobileDevicesUserSettings"></a> 移动设备  
  
|设置名|更多信息|  
|---------|----------|  
|**移动设备注册配置文件**|在可以配置此设置之前，必须首先将移动设备用户设置“允许用户注册移动设备”设置为“真”。 然后，可以单击“设置配置文件”，以指定注册配置文件（包含有关要在注册过程中使用的证书模板的信息）、包含注册点和注册代理点的站点以及将在注册后管理设备的站点。 **Important:**  在配置此选项之前，请确保你配置了要用于移动设备注册的证书模板。|  
  
###  <a name="BKMK_EnrollmentUserSettings"></a> 注册  
  
|设置名|更多信息|  
|---------|----------|  
|**移动设备注册配置文件**|在可以配置此设置之前，必须首先将注册用户设置“允许用户注册移动设备和 Mac 计算机”设置为“是”。 然后，可以单击“设置配置文件”，以指定注册配置文件（包含有关要在注册过程中使用的证书模板的信息）、包含注册点和注册代理点的站点以及将在注册后管理设备的站点。 **Important:**  在配置此选项之前，请确保你配置了要用于移动设备注册或用于 Mac 客户端证书注册的证书模板。|  
  
###  <a name="BKMK_UserDeviceAffinityUserSettings"></a> 用户和设备相关性  
  
|设置名|更多信息|  
|---------|----------|  
|**允许用户定义其主要设备**|指定是否允许用户通过“应用程序目录”和“我的设备”选项卡标识他们自己的主要设备。|  
  
## 请参阅  
 [System Center Configuration Manager 中客户端管理的技术参考](../LocTest/Client-management-technical-reference-for-System-Center-Configuration-Manager.md)
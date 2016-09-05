---
title: "在 System Center Configuration Manager 中配置证书配置文件"
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
ms.assetid: 29ae59b7-2695-4a0f-a9ff-4f29222f28b3
caps.latest.revision: 7
caps.handback.revision: 7
---
# 在 System Center Configuration Manager 中配置证书配置文件
你必须执行本主题描述的配置步骤，然后才能使用 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 在设备上以及为用户注册证书。  
  
## 在 Configuration Manager 中配置证书注册的步骤  
 使用下表来了解有关如何在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]中配置证书注册的步骤、详情及更多信息。 在开始之前，请检查 [System Center Configuration Manager 中证书配置文件先决条件](../LocTest/Prerequisites-for-certificate-profiles-in-System-Center-Configuration-Manager.md)中列出的所有先决条件。  
  
 完成这些步骤并验证了安装后，你可以配置和部署证书配置文件。 有关详细信息，请参阅[如何在 System Center Configuration Manager 中创建证书配置文件](../LocTest/How-to-create-certificate-profiles-in-System-Center-Configuration-Manager.md)。  
  
|步骤|详细信息|更多信息|  
|-----------|-------------|----------------------|  
|**步骤 1：** 安装和配置网络设备注册服务及依赖关系|Active Directory 证书服务 (AD CS) 的网络设备注册服务角色服务必须在 Windows Server 2012 R2 操作系统上运行。<br /><br /> **重要说明：**必须完成一些其他配置步骤，然后才能将网络设备注册服务与 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 配合使用。|请参阅本主题中的 [步骤 1：安装和配置网络设备注册服务及依赖关系](#BKMK_Step1) 。|  
|**步骤 2：** 安装和配置证书注册点|你至少必须安装一个证书注册点。 此注册点可以在管理中心站点或主站点中。|请参阅本主题中的 [步骤 2：安装和配置证书注册点](#BKMK_Step2) 。|  
|**逐步 3：** 安装 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 策略模块|在运行网络设备注册服务的服务器上安装策略模块。|请参阅本主题中的 [步骤 3：安装 Configuration Manager 策略模块](#BKMK_Step3) 。|  
  
## 在 Configuration Manager 中配置证书注册的补充过程  
 如果上表中的步骤需要执行补充过程，请使用以下信息。  
  
###  <a name="BKMK_Step1"></a> 步骤 1：安装和配置网络设备注册服务及依赖关系  
 你必须安装和配置用于 Active Directory 证书服务 (AD CS) 的网络设备注册服务角色服务、更改有关证书模板的安全权限、部署公钥基础结构 (PKI) 客户端身份验证证书、编辑注册表以增加 Internet Information Services (IIS) 默认 URL 大小限制。 必要时还必须配置证书颁发机构 (CA) 以允许自定义有效期。  
  
> [!IMPORTANT]  
>  在配置 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 以使用网络设备注册服务之前，请验证网络设备注册服务安装和配置。 如果这些依赖关系未正常工作，那么使用 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]诊断证书注册将有困难。  
  
##### 安装和配置网络设备注册服务及依赖关系  
  
1.  在运行 Windows Server 2012 R2 的服务器上，安装和配置用于 Active Directory 证书服务服务器角色的网络设备注册服务角色服务。 有关详细信息，请参阅 TechNet 上 Active Directory 证书服务库中的 [Network Device Enrollment Service Guidance（网络设备注册服务指导）](http://go.microsoft.com/fwlink/p/?LinkId=309016) 。  
  
2.  检查并在必要时修改网络设备注册服务所使用的证书模板的安全权限：  
  
    -   对于运行 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 控制台的帐户：“读取”  权限。  
  
         此权限是必需的，以便在你运行“创建证书配置文件向导”时能够浏览以选择要在创建 SCEP 设置配置文件时使用的证书模板。 选择证书模板意味着随后会为你自动填充向导中的某些设置，因此可以减少你要配置的内容，并降低选择与网络设备注册服务所使用的证书模板不兼容的设置所带来的风险。  
  
    -   对于网络设备注册服务应用程序池使用的 SCEP 服务帐户：“读取”  和“注册”  权限。  
  
         此项要求并不特定于 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] ，但却是配置网络设备注册服务过程的一部分。 有关详细信息，请参阅 TechNet 上 Active Directory 证书服务库中的 [Network Device Enrollment Service Guidance（网络设备注册服务指导）](http://go.microsoft.com/fwlink/p/?LinkId=309016) 。  
  
    > [!TIP]  
    >  若要确定网络设备注册服务所使用的证书模板，请在运行网络设备注册服务的服务器上查看下列注册表项：HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP。  
  
    > [!NOTE]  
    >  有一些将适合于大多数环境的默认安全权限。 但是，你可以使用备用安全配置。 有关详细信息，请参阅[为 System Center Configuration Manager 中证书配置文件规划证书模板权限](../LocTest/Planning-for-certificate-template-permissions-for-certificate-profiles-in-System-Center-Configuration-Manager.md)。  
  
3.  将支持客户端身份验证的 PKI 证书部署到此服务器。 你可能已在计算机上安装了可以使用的合适证书，或者可能必须（或希望）明确为此目的部署证书。 有关此证书的要求的详细信息，请参阅 [System Center Configuration Manager 的 PKI 证书要求](../LocTest/PKI-certificate-requirements-for-System-Center-Configuration-Manager.md)主题中[服务器的 PKI 证书](../LocTest/PKI-certificate-requirements-for-System-Center-Configuration-Manager.md#BKMK_PKIcertificates_for_servers)部分中的“将 Configuration Manager 策略模块与网络设备注册服务角色服务一起运行的服务器”的详细信息。  
  
    > [!TIP]  
    >  如果在部署此证书时需要帮助，你可以使用 [System Center Configuration Manager 的 PKI 证书的部署分步示例：Windows Server 2008 证书颁发机构](../Topic/Step-by-step%20example%20deployment%20of%20the%20PKI%20certificates%20for%20System%20Center%20Configuration%20Manager:%20Windows%20Server%202008%20Certification%20Authority.md)主题中[为分发点部署客户端证书](../Topic/Step-by-step%20example%20deployment%20of%20the%20PKI%20certificates%20for%20System%20Center%20Configuration%20Manager:%20Windows%20Server%202008%20Certification%20Authority.md#BKMK_clientdistributionpoint2008_cm2012)的说明，因为证书要求相同，但有一处例外：  
    >   
    >  -   不要在证书模板属性的“请求处理”  选项卡上选择“允许导出私钥”  复选框。  
    >   
    >  你不必随私钥一起导出此证书，因为你在配置 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 策略模板时将能浏览到本地计算机存储并选择此证书。  
  
4.  找到客户端身份验证证书链接到的根证书。 然后将此根 CA 证书导出到证书 (.cer) 文件。 将此文件保存到你在稍后安装和配置证书注册点站点系统服务器时可安全访问的安全位置。  
  
5.  在同一服务器上，使用注册表编辑器，通过设置 HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\HTTP\Parameters 中的下列注册表项 DWORD 值来增加 IIS 默认 URL 大小限制：  
  
    -   将“MaxFieldLength”  项设置为“65534” 。  
  
    -   将“MaxRequestBytes”  项设置为“16777216” 。  
  
     有关详细信息，请参阅 Microsoft 知识库中的文章 [820129：用于 Windows 的 Http.sys 注册表设置](http://go.microsoft.com/fwlink/?LinkId=309013) 。  
  
6.  在同一服务器上的 Internet Information Services (IIS) 管理器中，修改 /certsrv/mscep 应用程序的请求筛选设置，然后重启服务器。 在“编辑请求筛选设置”  对话框中，“请求限制”  设置应如下所示：  
  
    -   **允许的最大内容长度(字节)**： **30000000**  
  
    -   **最大 URL 长度(字节)**： **65534**  
  
    -   **最大查询字符串(字节)**： **65534**  
  
     有关这些设置以及如何配置这些设置的详细信息，请参阅 IIS 参考库中的 [Requests Limits（请求限制）](http://go.microsoft.com/fwlink/?LinkId=309014) 。  
  
7.  如果希望能够请求有效期比所使用的证书模板短的证书：对于企业 CA，默认情况下会禁用此配置。 若要对企业 CA 启用此选项，请使用 certutil 命令行工具，然后通过使用下列命令停止并重启证书服务：  
  
    1.  **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**  
  
    2.  **net stop certsvc**  
  
    3.  **net start certsvc**  
  
     有关详细信息，请参阅 TechNet 上 PKI 技术库中的 [Certificate Services Tools and Settings（证书服务工具和设置）](http://go.microsoft.com/fwlink/p/?LinkId=309015) 。  
  
8.  使用下列链接作为示例，验证网络设备注册服务是否工作： **https://server.contoso.com/certsrv/mscep/mscep.dll**。 你应会看到内置的网络设备注册服务网页。 此网页说明服务是什么，并且说明了网络设备使用该 URL 来提交证书请求。  
  
 既然配置了网络设备注册服务和依赖关系，即可安装和配置证书注册点。  
  
###  <a name="BKMK_Step2"></a> 步骤 2：安装和配置证书注册点  
 你必须至少在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 层次结构中安装和配置一个证书注册点，并且可以在管理中心站点或主站点中安装此站点系统角色。  
  
> [!IMPORTANT]  
>  在安装证书注册点之前，请参阅 **站点系统要求** 主题中的 [Supported configurations for System Center Configuration Manager](../LocTest/Supported-configurations-for-System-Center-Configuration-Manager.md) 部分，了解证书注册点的操作系统要求和依赖关系。  
  
##### 安装和配置证书注册点  
  
1.  在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 控制台中，单击“管理” 。  
  
2.  在“管理”  工作区中，展开“站点配置” ，单击“服务器和站点系统角色” ，然后选择要用于证书注册点的服务器。  
  
3.  在“主页”  选项卡上的“服务器”  组中，单击“添加站点系统角色” 。  
  
4.  在“常规”  页上，指定站点系统的常规设置，然后单击“下一步” 。  
  
5.  在“代理”  页上，单击“下一步” 。 证书注册点不使用 Internet 代理设置。  
  
6.  在“系统角色选择”  页上，从可用角色列表中选择“证书注册点”  ，然后单击“下一步” 。  
  
7.  在“证书注册点”  页上，接受或更改默认设置，然后单击“添加” 。  
  
8.  在“添加 URL 和根 CA 证书”  对话框中，指定下列各项，然后单击“确定” ：  
  
    1.  **网络设备注册服务的 URL**：采用以下格式指定 URL：https://*<server_FQDN>*/certsrv/mscep/mscep.dll。 例如，如果运行网络设备注册服务的服务器的 FQDN 为 server1.contoso.com，请键入 **https://server1.contoso.com/certsrv/mscep/mscep.dll**。  
  
    2.  **根 CA 证书**：浏览到并选择你在 **步骤 1：安装和配置网络设备注册服务及依赖关系**中创建和保存的 .cer 证书文件。 此根 CA 证书允许证书注册点验证 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 策略模块将使用的客户端身份验证证书。  
  
    > [!NOTE]  
    >  如果使用多个运行网络设备注册服务的服务器，请单击“添加”  指定其他服务器的详细信息。  
  
9. 单击“下一步”  并完成向导。  
  
10. 等待几分钟让安装完成，然后使用下列任何方法验证证书注册点是否已成功安装：  
  
    -   在“监视”  工作区中，展开“系统状态” ，单击“组件状态” ，并从“SMS_CERTIFICATE_REGISTRATION_POINT”  组件中查找状态消息。  
  
    -   在站点系统服务器上，使用 <ConfigMgr Installation Path\>\Logs\crpsetup.log 文件和 <ConfigMgr Installation Path\>\Logs\crpmsi.log 文件。 成功的安装将返回退出代码 0。  
  
    -   使用浏览器验证是否能连接到证书注册点的 URL — 例如，https://server1.contoso.com/CMCertificateRegistration。 你应会看到应用程序名称的“服务器错误”  页，包含 HTTP 404 描述。  
  
11. 找到证书注册点在主站点服务器计算机上的下列文件夹中自动创建的根 CA 的已导出证书文件：<ConfigMgr Installation Path\>\inboxes\certmgr.box。 将此文件保存到你稍后在运行网络设备注册服务的服务器上安装 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 策略模块时可安全访问的安全位置。  
  
    > [!TIP]  
    >  此证书不会立即出现在此文件夹中。 在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 将文件复制到此位置之前，你可能需要等待一会（例如，半个小时）。  
  
 既然已安装和配置了证书注册点，你即可为网络设备注册服务安装 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 策略模块。  
  
###  <a name="BKMK_Step3"></a> 步骤 3：安装 Configuration Manager 策略模块  
 你必须在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 步骤 2：安装和配置证书注册点 **中指定的每台服务器上安装和配置** 策略模块，将其作为证书注册点属性中的“网络设备注册服务的 URL”  。  
  
##### 安装策略模块  
  
1.  在运行网络设备注册服务的服务器上，以域管理员身份登录，并将下列文件从 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 安装媒体上的 <ConfigMgrInstallationMedia\>\SMSSETUP\POLICYMODULE\X64 文件夹复制到临时文件夹：  
  
    -   PolicyModule.msi  
  
    -   PolicyModuleSetup.exe  
  
     此外，如果安装媒体上有 LanguagePack 文件夹，请复制此文件夹及其内容。  
  
2.  从临时文件夹中，运行 PolicyModuleSetup.exe 以启动 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 策略模块安装向导。  
  
3.  在向导的初始页上，单击“下一步” ，接受许可条款，然后单击“下一步” 。  
  
4.  在“安装文件夹”  页上，接受策略模块的默认安装文件夹或指定其他文件夹，然后单击“下一步” 。  
  
5.  在“证书注册点”  页上，使用站点系统服务器的 FQDN 以及证书注册点属性中指定的虚拟应用程序名称来指定证书注册点的 URL。 默认虚拟应用程序名称为 CMCertificateRegistration。 例如，如果站点系统服务器的 FQDN 为 server1.contoso.com，并且你使用默认虚拟应用程序名称，请指定 **https://server1.contoso.com/CMCertificateRegistration**。  
  
6.  接受默认端口“443”  ，或指定证书注册点正在使用的其他端口号，然后单击“下一步” 。  
  
7.  在“策略模块的客户端证书” 页上，浏览到并指定你在 **步骤 1：安装和配置网络设备注册服务及依赖关系**中部署的客户端身份验证证书，然后单击“下一步” 。  
  
8.  在“证书注册点证书”  页上，单击“浏览”  选择你在 **步骤 2：安装和配置证书注册点**结尾找到并保存的已导出根 CA 证书文件。  
  
    > [!NOTE]  
    >  如果之前未保存此证书文件，则该文件位于站点服务器计算机上的 <ConfigMgr Installation Path\>\inboxes\certmgr.box 中。  
  
9. 单击“下一步”  并完成向导。  
  
 既然已完成了配置步骤来安装网络设备注册服务及依赖关系、证书注册点以及 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 策略模块，你即可通过创建和部署证书配置文件将证书部署到用户和设备。 有关如何创建证书配置文件的详细信息，请参阅[如何在 System Center Configuration Manager 中创建证书配置文件](../LocTest/How-to-create-certificate-profiles-in-System-Center-Configuration-Manager.md)。  
  
 如果想要卸载 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 策略模块，请使用控制面板中的“程序和功能”  。  
  
## 另请参阅  
 [System Center Configuration Manager 中的证书配置文件](../LocTest/Certificate-profiles-in-System-Center-Configuration-Manager.md)
---
title: "Set up certificates for trusted communications for On-premises Mobile Device Management in System Center Configuration Manager"
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
ms.assetid: 2a7d7170-1933-40e9-96d6-74a6eb7278e2
caps.latest.revision: 27
caps.handback.revision: 27
translationtype: Human Translation
---
# Set up certificates for trusted communications for On-premises Mobile Device Management in System Center Configuration Manager
[!INCLUDE[onprem_first](../LocTest/includes/onprem_first_md.md)] 需要为与托管设备之间的受信任通信设置注册点、注册代理点、分发点、设备管理点站点系统角色。 托管一个或多个这些角色的任何站点系统服务器必须具有绑定到该系统上的 Web 服务器的唯一 PKI 证书。 根与服务器上的证书的根相同的证书大多也存储在托管设备上，以与它们建立受信任通信。  
  
 对于已加入域的设备，Active Directory 证书服务会自动在所有设备上安装所需要的具有受信任根的证书。 对于未加入域的设备，必须通过一些其他手段获取具有受信任根的有效证书。 如果使用站点 CA 作为受信任根（与 Active Directory 用于已加入域的设备相同的根），注册点和注册代理点的站点系统服务器必须具有绑定到它们的 CA 颁发的证书。  
  
 要托管的每个设备也需要安装具有相同根的证书，以便支持与站点系统角色之间的受信任通信。 对于批量注册的设备，可以将证书包含在用户首次启动设备时被添加到设备的注册包中以对证书进行注册。 对于用户注册的设备，则需要通过电子邮件，Web 下载或某些其他方法来添加证书。  
  
 作为未加入域的设备的替代方法，可以使用已知公共 CA（如 Verisign 或 GoDaddy）的根来颁发服务器证书，这样可以避免必须手动在设备上安装证书，因为大多数设备本机信任与特定服务器之间的连接，这类服务器使用的根与公共 CA 使用的根相同。 这个替代方法对于用户注册的设备非常有用，因为在该设备中不能通过每台设备上的站点 CA 安装受信任的证书。  
  
> [!IMPORTANT]  
>  有多种方法可以为设备和 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 站点系统服务器之间的受信任通信设置证书。 本文中提供的信息作为实现此操作的其中一种方法的示例给出。 此方法要求在安装有 Active Directory 证书服务角色和证书颁发机构及证书颁发机构 Web 注册角色的站点中运行服务器。 请参阅 [Active Directory 证书服务](http://go.microsoft.com/fwlink/p/?LinkId=115018)了解有关此 Windows Server 角色的详细信息和指南。  
  
 若要设置 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 需要的 SSL 通信的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点，请执行以下高级步骤：  
  
-   [配置 CRL 发布的证书颁发机构 (CA)](#bkmk_configCa)  
  
-   [在 CA 上创建 Web 服务器证书模板](#bkmk_certTempl)  
  
-   [为每个站点系统角色请求 Web 服务器证书](#bkmk_requestCert)  
  
-   [将证书绑定到 Web 服务器](#bkmk_bindCert)  
  
-   [导出根与 Web 服务器证书的根相同的证书](#bkmk_exportCert)  
  
##  <a name="bkmk_configCa"></a> 配置 CRL 发布的证书颁发机构 (CA)  
 默认情况下，证书颁发机构 (CA) 使用基于 LDAP 的证书吊销列表 (CRL)，此列表允许已加入域的设备的连接。 必须将基于 HTTP 的 CRL 添加到 CA，以使具有从 CA 颁发的证书的未加入域设备受信任。 托管 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点系统角色的服务器和为 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 注册的设备之间的 SSL 通信需要这些证书。  
  
 按照以下步骤配置 CA，以自动发布用于颁发证书的 CRL 信息，证书允许已加入域和未加入域的设备的受信任连接。  
  
1.  在运行站点的证书颁发机构的服务器上，单击“开始” > “管理工具” > “证书颁发机构”。  
  
2.  在证书颁发机构控制台中，右键单击“CertificateAuthority”，然后单击“属性”。  
  
3.  在“CertificateAuthority”属性中，单击“扩展”选项卡，确保将“选择扩展”设置为“CRL 分发点 (CDP)”  
  
4.  选择 **http://<ServerDNSName\>/CertEnroll/<CAName\><CRLNameSuffix\><DeltaCRLAllowed\>.crl**。 下面有三个选项：  
  
    -   **包含在 CRL 中。 客户端使用此选项来查找增量 CRL 位置。**  
  
    -   **包含在已颁发证书的 CDP 扩展中。**  
  
    -   **包含在已颁发 CRL 的 IDP 扩展中。**  
  
5.  单击“退出模块”选项卡，再单击“属性...”，然后选择“允许将证书发布到文件系统”。  
  
6.  系统通知 Active Directory 证书服务必须重启时，单击“确定”。  
  
7.  右键单击“吊销证书”，单击“所有任务”，然后单击“发布”。  
  
8.  在“发布 CRL”对话框中，选择“仅增量 CRL”，然后单击“确定”。  
  
##  <a name="bkmk_certTempl"></a> 在 CA 上创建 Web 服务器证书模板  
 在 CA 上发布新的 CRL 后，下一步是创建 Web 服务器证书模板。 为托管注册点、注册代理点、分发点和设备管理点站点系统角色的服务器颁发证书需要此模板。 这些服务器将是站点系统角色和已注册设备之间受信任通信的 SSL 终结点。    请按照以下步骤来创建证书模板：  
  
1.  创建一个名为 **ConfigMgr MDM 服务器**的安全组，该组包含运行站点系统的服务器，而站点系统需要与已注册设备之间的受信任通信。  
  
2.  在证书颁发机构控制台中，右键单击“证书模板”，然后单击“管理”以加载证书模板控制台。  
  
3.  在结果窗格中，右键单击在“模板显示名称”  列中显示“Web 服务器” 的条目，然后单击“复制模板” 。  
  
4.  在“复制模板”  对话框中，确保已选择“Windows 2003 Server，Enterprise Edition”  ，然后单击“确定” 。  
  
    > [!IMPORTANT]  
    >  不要选择“Windows 2008 Server，Enterprise Edition” 。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不支持使用 HTTPS 的受信任通信的 Windows Server 2008 证书模板。  
  
    > [!NOTE]  
    >  如果使用的 CA 位于 Windows Server 2012，单击“复制模板”时系统不会提示证书模板版本。 请改为在模板属性的“兼容性”  选项卡上指定这一点，如下所示：  
    >   
    >  **证书颁发机构**： **Windows Server 2003**  
    >   
    >  **证书接收者**： **Windows XP/Server 2003**  
  
5.  在“常规”选项卡上的“新模板的属性”对话框中，输入模板名称以生成将在 Configuration Manager 站点系统上使用的 Web 证书，例如 **ConfigMgr MDM Web 服务器**。  
  
6.  单击“使用者名称”选项卡，选择“用 Active Directory 中的信息生成”，并为使用者名称格式指定 **DNS 名称**。 如果选择了“用户主体名称 (UPN)”，则清除另一个使用者名称的复选框。  
  
7.  单击“安全”  选项卡，并从安全组“域管理员”  和“企业管理员”  中删除“注册” 权限。  
  
8.  单击“添加”，在文本框中输入 **ConfigMgr MDM 服务器**，然后单击“确定”。  
  
9. 为此组选择“注册”  权限，并且不要清除“读取”  权限。  
  
10. 单击“确定”，然后关闭证书模板控制台。  
  
11. 在证书颁发机构控制台中，右键单击“证书模板” ，单击“新建” ，然后单击“要颁发的证书模板” 。  
  
12. 在“启用证书模板”对话框中，选择刚创建的新模板 **ConfigMgr MDM Web 服务器**，然后单击“确定”。  
  
##  <a name="bkmk_requestCert"></a> 为每个站点系统角色请求 Web 服务器证书  
 为 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 注册的设备必须信任托管注册点、注册代理点、分发点和设备管理点的 SSL 终结点。  下列步骤说明如何对 IIS 请求 Web 服务器证书。 对于托管其中一个 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 所需的站点系统角色的每个服务器（SSL 终结点），都必须执行此操作。  
  
1.  在主站点服务器上，使用管理员权限打开命令提示符，键入 **MMC** 并按 **Enter**。  
  
2.  在 MMC 中，单击“文件” > “添加/删除管理单元”。  
  
3.  在证书管理单元中，选择“证书”，单击“添加”，选择“计算机帐户”，单击“下一步”，单击“完成”，然后单击“确定”，以退出“添加或删除管理单元”窗口。  
  
4.  右键单击“个人”，然后单击“所有任务” > “请求新证书”。  
  
5.  在证书注册向导中，单击“下一步”，选择“Active Directory 注册策略”并单击“下一步”。  
  
6.  选择 Web 服务器证书旁的复选框（“ConfigMgr MDM Web 服务器”），然后单击“注册”。  
  
7.  证书注册完成之后，单击“完成”。  
  
 因为每个服务器都需要唯一的 Web 服务器证书，所以你需要对托管其中一个 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 所需的站点系统角色的每个服务器重复此过程。  如果一个服务器托管了所有站点系统角色，则只需要请求一个 Web 服务器证书。  
  
##  <a name="bkmk_bindCert"></a> 将证书绑定到 Web 服务器  
 现在需要将新证书绑定到托管 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 所需的站点系统角色的每个站点系统服务器的 Web 服务器。 对于托管注册点和注册代理点站点系统角色的每个服务器，请执行以下步骤。 如果一个服务器托管了所有的站点系统角色，则只需要执行一次以下步骤。 对于分发点和设备管理点站点系统角色则无需执行此任务，因为它们在注册过程中会自动获得所需的证书。  
  
1.  在托管注册点、注册代理点、分发点或设备管理点的服务器上，单击“开始” > “管理工具” > “IIS 管理器”。  
  
2.  在“连接”下，导航到并右键单击“默认网站”，然后单击“编辑绑定...”。  
  
3.  在站点绑定对话框中，单击“https”，然后单击“编辑...”。  
  
4.  在“编辑站点绑定”对话框中，选择刚为 **SSL 证书**注册的证书，单击“确定”，然后单击“关闭”。  
  
5.  在 IIS 管理器控制台的“连接”下，选择 Web 服务器，然后在右侧的操作面板中，单击“重新启动”。  
  
##  <a name="bkmk_exportCert"></a> 导出根与 Web 服务器证书的根相同的证书  
 Active Directory 证书服务通常会在所有已加入域的设备上从 CA 安装所需证书。 但是未加入域的设备如果没有来自根 CA 的证书，则不能与站点系统角色通信。 若要获取设备与站点系统角色通信所需的证书，可以从绑定到 Web 服务器的证书中导出证书。  
  
 请按照下列步骤导出 Web 服务器的证书的根证书。  
  
1.  在 IIS 管理器中，单击“默认网站”，然后在右侧的操作面板中单击“绑定...”  
  
2.  在站点绑定对话框中，单击“https”，然后单击“编辑...”。  
  
3.  请确保选中 Web 服务器证书，然后单击“查看...”。  
  
4.  在 Web 服务器证书的属性中，单击“证书路径”，单击证书路径顶部的根，然后单击“查看证书”。  
  
5.  在根证书的属性中，单击“详细信息”，然后单击“复制到文件...”。  
  
6.  在证书导出向导中，单击“下一步”。  
  
7.  确保选中“DER 编码的二进制 X.509 (.CER)”格式，并单击“下一步”。  
  
8.  关于文件名，单击“浏览...”，选择要保存证书文件的位置，命名该文件，然后单击“保存”。  
  
     要注册的设备需要访问此文件以导入根证书，所以建议选择大部分计算机和设备能够访问的常见位置，或者也可以现将其保存到一个便捷的位置（例如 C 驱动器），稍后再将其移动到常见位置。  
  
     单击“下一步” 。  
  
9. 检查设置，然后单击“完成”。  
  
## 另请参阅  
 [用于 System Center Configuration Manager 中本地移动设备管理的准备步骤](../LocTest/Preparation-steps-for-On-premises-Mobile-Device-Management-in-System-Center-Configuration-Manager.md)
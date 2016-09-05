---
title: "如何在 System Center Configuration Manager 中向本地移动设备管理批量注册设备"
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
ms.assetid: b36f5e4a-2b57-4d18-83f6-197081ac2a0a
caps.latest.revision: 13
caps.handback.revision: 9
translationtype: Human Translation
---
# 如何在 System Center Configuration Manager 中向本地移动设备管理批量注册设备
相较于要求用户输入其凭据以注册设备的用户注册，[!INCLUDE[onprem_first](../LocTest/includes/onprem_first_md.md)] 中的批量注册是自动化程度更高的注册设备的方式。  批量注册使用注册程序包在注册过程中对设备进行身份验证。 包（.ppkg 文件）中包含证书配置文件和可选的 Wi\-Fi 配置文件（设备需要 intranet 连接以支持注册时选择）。  
  
 [!INCLUDE[onprem_devices](../LocTest/includes/onprem_devices_md.md)] 以下任务说明如何为 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 批量注册计算机和设备：  
  
-   [创建一份证书配置文件](#bkmk_createCert)  
  
-   [创建 Wi-fi 配置文件](#CreateWifi)  
  
-   [创建注册配置文件](#bkmk_createEnroll)  
  
-   [创建一个注册程序包 (ppkg) 文件](#bkmk_createPpkg)  
  
-   [使用程序包批量注册设备](#bkmk_getPpkg)  
  
-   [验证设备的注册](#bkmk_verifyEnroll)  
  
##  <a name="bkmk_createCert"></a> 创建一份证书配置文件  
 注册程序包的主要组件是一个证书配置文件，用于自动将受信任的根证书设置到正在注册的设备。  设备和 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 所需的站点系统角色之间进行受信任的通信需要此根证书。 如果没有根证书，在该设备和承载注册点、注册代理点、分发点和设备管理点站点系统角色的服务器之间的 HTTPS 连接中，该设备将不受信任。  
  
 作为准备系统以用于 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 这一操作的一部分，要导出可用于注册程序包的证书配置文件的根证书。 有关如何获得受信任的根证书的说明，请参阅 [导出根与 Web 服务器证书的根相同的证书](../LocTest/Set-up-certificates-for-trusted-communications-for-On-premises-Mobile-Device-Management-in-System-Center-Configuration-Manager.md#bkmk_exportCert)。  
  
 使用导出的根证书创建一个证书配置文件。 有关说明，请参阅 [如何在 System Center Configuration Manager 中创建证书配置文件](../LocTest/How-to-create-certificate-profiles-in-System-Center-Configuration-Manager.md)。  
  
##  <a name="CreateWifi"></a> 创建 Wi\-fi 配置文件  
 用于批量注册的包的另一个组件是 Wi\-Fi 配置文件。 在配置了网络设置之前，某些设备可能不具有支持注册所需的网络连接。 在注册程序包中包含一个 Wi\-Fi 配置文件可为设备提供一种建立网络连接的方式。  
  
 若要在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中创建 Wi\-Fi 配置文件，请遵循 [如何在 System Center Configuration Manager 中创建 Wi\-Fi 配置文件](../LocTest/How-to-create-Wi-Fi-profiles-in-System-Center-Configuration-Manager.md) 中的说明。  
  
> [!IMPORTANT]  
>  [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的当前分支只支持 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 的下列 Wi\-Fi 安全性配置：  
>   
>  安全类型：“WPA2 企业”或“WPA2 个人”  
>   
>  加密类型：“AES”或“TKIP”  
>   
>  EAP 类型：“智能卡或其他证书”或“PEAP”  
  
##  <a name="bkmk_createEnroll"></a> 创建注册配置文件  
 注册配置文件允许你指定设备注册时所需的设置，包括将受信任的根证书动态设置到设备的证书配置文件和在需要时将配置网络设置的 Wi\-Fi 配置文件。  
  
 创建注册配置文件之前，请确保你具有证书配置文件并创建了 Wi\-Fi 配置文件（如果需要）。 有关详细信息，请参阅 [创建一份证书配置文件](#bkmk_createCert) 和 [创建 Wi-fi 配置文件](#CreateWifi)。  
  
#### 创建注册配置文件：  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”\>“概述”\>“企业拥有的所有设备”\>“Windows”\>“注册配置文件”。  
  
2.  右键单击“注册配置文件”，然后单击“创建配置文件”。  
  
3.  在“创建注册配置文件”向导中，输入配置文件的名称，请确保针对“管理机构”勾选了“本地”，然后单击“下一步”。  
  
4.  选择站点代码，然后单击“下一步”。  
  
5.  选择“仅 Intranet”，选择设备将用于启动注册过程的注册代理点，然后单击“下一步”。  
  
6.  选择包含受信任的根证书的证书配置文件（即在 [创建一份证书配置文件](#bkmk_createCert) 中创建的配置文件），然后单击“下一步”。  
  
7.  选择包含设备连接到 intranet 所必需的网络设置的 WiFi 配置文件（即在 [创建 Wi-fi 配置文件](#CreateWifi) 中创建的配置文件），然后单击“下一步”。  
  
    > [!NOTE]  
    >  如果你不打算将 Wi\-Fi 配置文件用于注册程序包，则跳过此步骤。  
  
8.  确认注册配置文件的设置，然后	单击“下一步”。 单击“关闭”以退出向导。  
  
##  <a name="bkmk_createPpkg"></a> 创建一个注册程序包 \(ppkg\) 文件  
 注册程序包是用于为 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 批量注册设备的文件。  此文件必须使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 创建。 你可以使用 Windows 映像和配置设计器 \(ICD\) 创建类似类型的程序包，但只有在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中创建的程序包可用于为 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 完成整个设备注册过程。 使用 Windows ICD 创建的包只提供注册所需的用户主体名称 \(UPN\)，而不执行实际的注册过程。  
  
 创建注册程序包的过程需要适用于 Windows 10 的 Windows 评估和部署工具包 \(ADK\)。  请确保你已在运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台的服务器上安装了版本号为 1511 的 Windows ADK。 更多详细信息，请参阅[下载适用于 Windows 10 的工具包和工具](https://msdn.microsoft.com/windows/hardware/dn913721.aspx)中的 ADK 部分。  
  
> [!TIP]  
>  如果你从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中删除了注册程序包，则无法将其用于设备注册。 作为一种用于管理不再需要用于批量注册设备的包的方式，你可以将其删除。  
  
#### 创建一个注册程序包 \(ppkg\) 文件：  
  
1.  右键单击刚创建的配置文件（在 [创建注册配置文件](#bkmk_createEnroll) 中，单击“导出”。  
  
2.  单击“浏览”，找到要保存 .ppkg 文件的位置，为包输入一个名称，然后单击“保存”。  
  
3.  如果你想通过密码来保护包，请单击“加密包”旁边的复选框，然后单击“导出”，然后等待约 10 秒钟，导出即可完成。  
  
    > [!NOTE]  
    >  如果加密了该程序包，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 会提供一条包含解密密码的消息。 请确保保存了密码信息，因为你将需要它在设备上设置包。  
  
4.  单击"**确定**"。  
  
##  <a name="bkmk_getPpkg"></a> 使用程序包批量注册设备  
 在通过全新体验 \(OOBE\) 过程对设备进行设置之前和之后，可以使用程序包注册设备。   还可将注册程序包包含为原始设备制造商 \(OEM\) 设置包的一部分。  
  
 包必须以物理方式传递给要将其用于批量注册的设备。 你可以以各种方式将注册程序包传递给设备，具体取决于你的需要，其中包括以下方式：  
  
-   从文件系统复制  
  
-   附加到电子邮件  
  
-   跨近场通信 \(NFC\) 连接进行复制  
  
-   从内存卡复制  
  
-   扫描条形码  
  
-   从受限设备复制  
  
-   包含在 OEM 设置包中  
  
#### 批量注册设备：  
  
1.  在要注册的设备上，找到注册程序包（使用文件资源管理器），然后双击 .ppkg 文件。  
  
2.  在“用户帐户控制”消息中，单击“是”。  
  
3.  在询问该程序包是否来自你信任的源的对话框中，	单击“是，将其添加”。  
  
     注册过程启动，且需要约 5 分钟完成启动。  
  
4.  打开“设置”。  
  
5.  单击“帐户”\>“工作单位访问”。 注册成功后，会在“CompanyApps”下看到一个账户。  
  
6.  单击该帐户，然后单击“同步”，从而使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 启动管理。  
  
##  <a name="bkmk_verifyEnroll"></a> 验证设备的注册  
 你可以在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台验证设备是否已成功注册。  
  
-   启动 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台  
  
-   单击“资产和符合性”\>“概述”\>“设备”。 列表中将显示已注册的设备。  
  
## 请参阅  
 [在 System Center Configuration Manager 中为本地移动设备管理注册设备](../LocTest/Enroll-devices-for-On-premises-Mobile-Device-Management-in-System-Center-Configuration-Manager.md)
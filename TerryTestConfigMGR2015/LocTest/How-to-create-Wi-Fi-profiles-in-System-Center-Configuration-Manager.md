---
title: "如何在 System Center Configuration Manager 中创建 Wi-Fi 配置文件"
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
ms.assetid: 321b19b2-a093-4b8f-995f-41f74b886eb5
caps.latest.revision: 13
caps.handback.revision: 13
---
# 如何在 System Center Configuration Manager 中创建 Wi-Fi 配置文件
在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中创建 Wi-Fi 配置文件以将无线网络设置部署到机构中的设备。 通过部署这些设置，你可以最大程度地减少最终用户连接到无线网络所需执行的工作。  
  
## 创建 Wi-Fi 配置文件的步骤  
 使用下列必需的步骤，通过“创建 Wi-Fi 配置文件向导” 来创建 Wi-Fi 配置文件。  
  
-   [步骤 1：启动“创建 Wi-Fi 配置文件向导”](#BKMK_Step1)  
  
-   [步骤 2：提供有关 Wi-Fi 配置文件的一般信息](#BKMK_Step2)  
  
-   [步骤 3：提供有关无线网络的信息](#BKMK_Step3)  
  
-   [步骤 4：配置 Wi-Fi 配置文件的安全性](#BKMK_Step4)  
  
-   [步骤 5：配置 Wi-Fi 配置文件的高级设置](#BKMK_Step5)  
  
-   [步骤 6：配置 Wi-Fi 配置文件的代理设置](#BKMK_Step6)  
  
-   [步骤 7：为 Wi-Fi 配置文件配置支持的平台](#BKMK_Step7)  
  
-   [步骤 8：完成向导](#BKMK_Step8)  
  
##  <a name="BKMK_Step1"></a> 步骤 1：启动“创建 Wi-Fi 配置文件向导”  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性” 。  
  
2.  在“资产和符合性”  工作区中，展开“符合性设置” ，展开“公司资源访问” ，然后单击“Wi-Fi 配置文件” 。  
  
3.  在“主页”  选项卡上的“创建”  组中，单击“创建 Wi-Fi 配置文件” 。  
  
##  <a name="BKMK_Step2"></a> 步骤 2：提供有关 Wi-Fi 配置文件的一般信息  
  
1.  在“创建 Wi-Fi 配置文件向导”的“常规”页中，为 Wi-Fi 配置文件输入唯一名称和说明。 最多可以使用 256 个字符。  
  
2.  如果想要使用另一个 Wi-fi 配置文件中的设置，请选择“从文件中导入现有的 Wi-fi 配置文件项”。  
  
    > [!IMPORTANT]  
    >  确保导入的 Wi-fi 配置文件包含 Wi-fi 配置文件的有效 XML。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不会验证配置文件。  
  
3.  在  
                            **报表的不符合性严重程度**：指定在客户端设备上发现 Wi-Fi 配置文件不符合（例如，如果配置文件安装失败）时报告的严重性级别。 可用的严重性级别如下：  
  
    -   **无**：对于 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 报表，不符合此符合性规则的计算机不报告故障严重性。  
  
    -   **信息**：对于 **报表，不符合此符合性规则的计算机将报告故障严重性“信息”**[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 。  
  
    -   **警告**：对于 **报表，不符合此符合性规则的计算机将报告故障严重性“警告”**[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 。  
  
    -   **严重**：对于 **报表，不符合此符合性规则的计算机将报告故障严重性“严重”**[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 。  
  
    -   **事件严重**：对于 **报表，不符合此符合性规则的计算机将报告故障严重性“严重”**[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 。 应用程序事件日志中也会以 Windows 事件的形式记录此严重性级别。  
  
##  <a name="BKMK_Step3"></a> 步骤 3：提供有关无线网络的信息  
  
1.  在“创建 Wi-Fi 配置文件向导”的“Wi-Fi 配置文件”  页上，最多使用 32 个字符指定无线 Internet 连接的描述性名称。 设备会将此名称显示为网络名称。  
  
    > [!IMPORTANT]  
    >  [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不支持在网络名称中使用单引号 (**‘**) 或逗号 (**,**) 字符。  
  
2.  在“SSID” 中，指定你希望设备能够连接到的无线网络的名称 (SSID)。 最多可以使用 32 个字符。 SSID 名称区分大小写，因此请务必完全按照配置输入。  
  
3.  如果你想要允许设备在范围内时自动重新连接到该无线网络，请选择“当此网络处于范围内则自动连接” 。  
  
4.  如果你想要允许设备在连接此网络时继续扫描其他无线网络，则选择“在连接到此网络时查找其他无线网络”  
                            **连接到此网络时查找其他无线网络**：  
  
5.  如果你想要允许设备在网络列表中未显示某网络时连接到该网络（因其处于隐藏状态且未广播其名称），请选择“在网络未广播其名称 (SSID) 时连接” ，  
  
##  <a name="BKMK_Step4"></a> 步骤 4：配置 Wi-Fi 配置文件的安全性  
  
> [!IMPORTANT]  
>  如果你正在为 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)]创建 Wi-Fi 配置文件， [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的当前分支仅支持以下 Wi-Fi 安全性配置：  
>   
>  安全类型：“WPA2 企业”  或“WPA2 个人”   
> 加密类型：“AES”  或“TKIP”   
> EAP 类型：“智能卡或其他证书”  或“PEAP”   
  
1.  在“创建 Wi-Fi 配置文件向导”的“安全性配置”  页上，选择无线网络使用的安全协议；如果该网络无安全保护，则选择“无身份验证(开放式)”  。  
  
     仅限 Android 设备：不支持安全类型“WPA – 个人” 、“WPA2 – 个人”  和“WEP”  。  
  
2.  选择无线网络使用的加密方法。  
  
3.  选择用于向无线网络进行验证的 EAP 类型。  
  
     仅限 Windows Phone 设备：不支持 EAP 类型“LEAP”  和“EAP-FAST”  。  
  
4.  单击“配置”  ，为所选的 EAP 类型指定属性。 对于某些所选的 EAP 类型，此选项可能不可用。  
  
    > [!IMPORTANT]  
    >  单击“配置” 时，打开的对话框是 Windows 对话框。 因此，你必须确保运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台的计算机的操作系统支持配置所选的 EAP 类型。  
    >   
    >  对于 iOS 设备，如果你选择非 EAP 方法用于身份验证，那么无论你选择何种方法，都将使用 MS-CHAP v2 进行连接。  
  
5.  如果你想要存储用户凭据，以便用户无需在每次登录时输入凭据，请选择“在每次登录时记住用户凭据” 。  
  
### 仅适用于 iOS 设备：  
 配置 Wi-Fi 连接所需的任何证书的信息。 必须配置客户端证书以及受信任的服务器证书名称或根证书，如下所示：  
  
-   **受信任的服务器证书名称**：如果设备连接到的服务器使用服务器身份验证证书来识别服务器并帮助保护信道的安全，请在该证书的使用者名称或使用者可选名称中输入一个或多个名称。 名称通常为服务器完全限制的域名。 例如，服务器证书在证书使用者中具有公用名 srv1.contoso.com，则输入“srv1.contoso.com” 。 如果服务器证书具有多个在使用者可选名称中指定的名称，请输入每个名称，以分号分隔。  
  
    > [!TIP]  
    >  如果将使用你为 iOS 设备 EAP 或客户端身份验证选择的客户端证书来向远程身份验证拨入用户服务 (RADIUS) 服务器（例如正在运行网络策略服务器的服务器）进行验证，则你必须将使用者可选名称设置为用户主体名称。  
  
-   “选择用于服务器验证的根证书”：如果设备连接到的服务器使用设备不信任的服务器身份验证证书，请选择包含服务器证书的根证书的证书配置文件，以在设备上创建证书信任链。  
  
-   **选择用于客户端身份验证的客户端证书**：如果服务器或网络设备需要客户端证书来验证连接设备，请选择包含客户端身份验证证书的证书配置文件。  
  
> [!NOTE]  
>  必须首先以证书配置文件的形式配置和部署根证书和客户端证书，然后你才能选择这些证书。 有关证书配置文件的详细信息，请参阅 [System Center Configuration Manager 中的证书配置文件](../LocTest/Certificate-profiles-in-System-Center-Configuration-Manager.md)。  
  
##  <a name="BKMK_Step5"></a> 步骤 5：配置 Wi-Fi 配置文件的高级设置  
 在“创建 Wi-Fi 配置文件向导”的“高级设置”  页上，指定 Wi-Fi 配置文件的高级设置，例如身份验证模式、单一登录选项以及联邦信息处理标准符合性。 有关这些选项的详细信息，请参阅 Windows 文档。  
  
> [!NOTE]  
>  高级设置可能不可用或可能会有所不同，具体情况视你在向导的“安全性配置”  页上所选的选项而定。  
  
##  <a name="BKMK_Step6"></a> 步骤 6：配置 Wi-Fi 配置文件的代理设置  
  
1.  在“创建 Wi-Fi 配置文件向导”的“代理设置”  页上，如果无线网络使用代理服务器，请选择“配置此 Wi-Fi 配置文件的代理设置”  复选框。  
  
2.  指定有关代理服务器及其设置的详细信息。 有关详细信息，请参阅 Windows Server 文档。  
  
##  <a name="BKMK_Step7"></a> 步骤 7：为 Wi-Fi 配置文件配置支持的平台  
 在“创建 Wi-Fi 配置文件向导”的“支持的平台”  页上，选择将在其中安装 Wi-Fi 配置文件的操作系统。 或者单击“全选”  以将 Wi-Fi 配置文件安装到所有可用的操作系统。  
  
##  <a name="BKMK_Step8"></a> 步骤 8：完成向导  
 在向导的“摘要”  页上，查看向导将执行的操作，然后完成向导。 新的 Wi-Fi 配置文件将显示在“资产和符合性”  工作区的“Wi-Fi 配置文件”  节点中。  
  
 有关如何部署 Wi-Fi 配置文件的信息，请参阅[如何在 System Center Configuration Manager 中部署 Wi-Fi 配置文件](../LocTest/How-to-deploy-Wi-Fi-profiles-in-System-Center-Configuration-Manager.md)。  
  
## 另请参阅  
 [System Center Configuration Manager 中 Wi-Fi 配置文件的操作和维护](../LocTest/Operations-and-maintenance-for-Wi-Fi-Profiles-in-System-Center-Configuration-Manager.md)
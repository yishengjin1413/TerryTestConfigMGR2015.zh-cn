---
title: "如何在 System Center Configuration Manager 中创建 Exchange ActiveSync 电子邮件配置文件"
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
ms.assetid: 15f0fd50-e196-44e5-b435-234d7ff6a5cd
caps.latest.revision: 4
caps.handback.revision: 3
translationtype: Human Translation
---
# 如何在 System Center Configuration Manager 中创建 Exchange ActiveSync 电子邮件配置文件
在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中创建电子邮件配置文件以将电子邮件设置部署到公司中的用户。 通过部署这些设置，你可以减少对于使用 Exchange ActiveSync 的设备连接到公司网络上的公司电子邮件所需的最终用户工作。  
  
## 创建 Exchange ActiveSync 电子邮件配置文件的步骤  
 通过使用“创建 Exchange ActiveSync 电子邮件配置文件向导”，使用以下所需步骤创建电子邮件配置文件。  
  
|步骤|详细信息|更多信息|  
|--------|----------|----------|  
|**步骤 1：**启动“创建 Exchange ActiveSync 电子邮件配置文件向导”。|在“资产和符合性”工作区的“符合性设置”节点中启动向导。|请参阅本主题中的 [步骤 1：启动“创建 Exchange ActiveSync 电子邮件配置文件向导”。](#BKMK_Step1) 部分。|  
|**步骤 2：**提供有关 Exchange ActiveSync 电子邮件配置文件的一般信息。|提供 Exchange ActiveSync 电子邮件配置文件的名称和描述。|请参阅本主题中的 [步骤 2：提供有关 Exchange ActiveSync 电子邮件配置文件的一般信息。](#BKMK_Step2) 部分。|  
|**步骤 3：**配置 Exchange ActiveSync 电子邮件配置文件的 Exchange ActiveSync 设置。|配置设备将用于连接到 Exchange ActiveSync 的设置，例如主机名和电子邮件帐户详情。|请参阅本主题中的 [步骤 3：配置 Exchange ActiveSync 电子邮件配置文件的 Exchange ActiveSync 设置。](#BKMK_Step3) 部分。|  
|**步骤 4：**配置 Exchange ActiveSync 电子邮件配置文件的同步设置。|配置同步设置，如电子邮件同步天数和将同步的内容类型。|请参阅本主题中的 [步骤 4：配置 Exchange ActiveSync 电子邮件配置文件的同步设置。](#BKMK_Step4) 部分。|  
|**步骤 5：**指定 Exchange ActiveSync 电子邮件配置文件受支持的平台。|受支持的平台是你将在其中安装 Exchange ActiveSync 电子邮件配置文件的操作系统。|请参阅本主题中的 [步骤 5：指定 Exchange ActiveSync 电子邮件配置文件受支持的平台。](#BKMK_Step5) 部分。|  
|**步骤 6：**完成向导。|完成向导以创建新的 Exchange ActiveSync 电子邮件配置文件。|请参阅本主题中的 [步骤 6：完成向导。](#BKMK_Step6) 部分。|  
  
## 创建新的 Exchange ActiveSync 电子邮件配置文件的补充步骤  
 如果上表中的步骤需要执行补充过程，请使用以下信息。  
  
###  <a name="BKMK_Step1"></a> 步骤 1：启动“创建 Exchange ActiveSync 电子邮件配置文件向导”。  
 使用此步骤启动“创建 Exchange ActiveSync 电子邮件配置文件向导”。  
  
##### 要启动“创建 Exchange ActiveSync 电子邮件配置文件向导”  
  
1.  在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 控制台中，单击“资产和符合性”。  
  
2.  在“资产和符合性”工作区中，展开“符合性设置”，展开“公司资源访问”，然后单击“电子邮件配置文件”。  
  
3.  在“主页”选项卡上的“创建”组中，单击“创建 Exchange ActiveSync 配置文件”。  
  
###  <a name="BKMK_Step2"></a> 步骤 2：提供有关 Exchange ActiveSync 电子邮件配置文件的一般信息。  
 使用此步骤提供有关 Exchange ActiveSync 电子邮件配置文件的一般信息。  
  
##### 要提供有关 Exchange ActiveSync 电子邮件配置文件的一般信息  
  
1.  在“创建 Exchange ActiveSync 电子邮件配置文件向导”的“常规”页上，指定以下信息：  
  
    -   **名称：**输入 Exchange ActiveSync 电子邮件配置文件的唯一名称。 最多可以使用 256 个字符。  
  
    -   **描述：**提供对 Exchange ActiveSync 电子邮件配置文件进行概述的描述，以及可帮助在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 控制台中识别该配置文件的其他相关信息。 最多可以使用 256 个字符。  
  
###  <a name="BKMK_Step3"></a> 步骤 3：配置 Exchange ActiveSync 电子邮件配置文件的 Exchange ActiveSync 设置。  
 使用此步骤来配置 Exchange ActiveSync 电子邮件配置文件的 Exchange ActiveSync 设置。  
  
##### 要配置 Exchange ActiveSync 电子邮件配置文件的 Exchange ActiveSync 设置  
  
1.  在“创建 Exchange ActiveSync 电子邮件配置文件向导”的“Exchange ActiveSync”页上，指定以下信息：  
  
    -   **Exchange ActiveSync 主机：**指定托管 Exchange ActiveSync 服务的公司 Exchange Server 的主机名。  
  
    -   **帐户名称：**指定电子邮件帐户的显示名，因为它将在用户的设备上显示。  
  
    -   **帐户用户名：**选择电子邮件帐户用户名在客户端设备上的配置方式。 你可以从下拉列表中选择下列选项之一：  
  
        -   **用户主体名称** \- 使用完整的用户主体名登录 Exchange。  
  
        -   **sAMAccountName** 使用  
  
        -   **主 SMTP 地址** \- 使用用户主 SMTP 地址登录 Exchange。  
  
    -   **电子邮件地址：**选择每个客户端设备上的用户的电子邮件地址的生成方式。 你可以从下拉列表中选择下列选项之一：  
  
        -   **主 SMTP 地址** \- 使用用户主 SMTP 地址登录 Exchange。  
  
        -   **用户主体名称** \- 使用完整的用户主体名称作为电子邮件地址。  
  
    -   **帐户域：**你可以选择以下选项之一：  
  
        -   **从 Active Directory 获得**  
  
        -   **自定义**  
  
         仅当“sAMAccountName”在“帐户用户名”下拉列表中选中时，此字段适用。  
  
    -   **身份验证方法：**选择将用于对 Exchange ActiveSync 进行身份验证的以下身份验证方法之一：  
  
        -   **证书** \- 身份证书将用于 Exchange ActiveSync 连接的身份验证。  
  
        -   **用户名和密码** \- 设备用户必须提供密码以连接到 Exchange ActiveSync（用户名配置为电子邮件配置文件的一部分）。  
  
    -   **标识证书：**单击“选择”，然后选择用于标识的证书。  
  
        > [!NOTE]  
        >  你必须首先将身份证书配置为简单证书注册协议 \(SCEP\) 证书配置文件，才能选择身份证书。 有关证书配置文件的详细信息，请参阅 [System Center Configuration Manager 中的证书配置文件](../LocTest/Certificate-profiles-in-System-Center-Configuration-Manager.md)。  
  
         此选项只有在选择了“身份验证方法”下的“证书”才可用。  
  
    -   **使用 S\/MIME** \- 使用 S\/MIME 加密发送传出电子邮件。 此选项仅适用于 iOS 设备。  
  
    -   **加密证书：**单击“选择”，然后选择用于加密的证书。 此选项仅适用于 iOS 设备。  
  
        > [!NOTE]  
        >  你必须首先将加密证书配置为简单证书注册协议 \(SCEP\) 证书配置文件，才能选择加密证书。 有关证书配置文件的详细信息，请参阅 [System Center Configuration Manager 中的证书配置文件](../LocTest/Certificate-profiles-in-System-Center-Configuration-Manager.md)。  
  
         仅当你选中“使用 S\/MIME”时，此选项才可用。  
  
    -   **签名证书：**单击“选择”，然后选择用于签名的证书。 此选项仅适用于 iOS 设备。  
  
        > [!NOTE]  
        >  你必须首先将签名证书配置为简单证书注册协议 \(SCEP\) 证书配置文件，才能选择签名证书。 有关证书配置文件的详细信息，请参阅 [System Center Configuration Manager 中的证书配置文件](../LocTest/Certificate-profiles-in-System-Center-Configuration-Manager.md)。  
  
         仅当你选中“使用 S\/MIME”时，此选项才可用。  
  
###  <a name="BKMK_Step4"></a> 步骤 4：配置 Exchange ActiveSync 电子邮件配置文件的同步设置。  
 使用此步骤提供有关 Exchange ActiveSync 电子邮件配置文件的一般信息。  
  
##### 要配置 Exchange ActiveSync 电子邮件配置文件的同步设置  
  
1.  在“创建 Exchange ActiveSync 电子邮件配置文件向导”的“配置同步设置”页上，指定以下信息：  
  
    -   **计划：**选择设备同步 Exchange Server 的数据所依据的计划。 此选项仅适用于 Windows Phone 设备。 选择：  
  
        -   **未配置** \- 未执行同步计划。 这允许用户配置其自己的同步计划。  
  
        -   **消息到达时** \- 电子邮件和日历项等数据将在其到达时自动同步。  
  
        -   **15 分钟** \- 电子邮件和日历项等数据每隔 15 分钟自动同步。  
  
        -   **30 分钟** \- 电子邮件和日历项等数据每隔 30 分钟自动同步。  
  
        -   **60 分钟** \- 电子邮件和日历项等数据每隔 60 分钟自动同步。  
  
        -   **手动** \- 必须由设备用户手动启动同步。  
  
    -   **要同步的电子邮件天数：**从下拉列表中，选择你要同步的电子邮件的天数。 选择下列值之一：  
  
        -   **未配置** \- 不会执行该设置。 这允许用户配置下载到其设备的电子邮件数量。  
  
        -   **无限制** \- 同步所有可用的电子邮件。  
  
        -   **1 天**  
  
        -   **3 天**  
  
        -   **1 周**  
  
        -   **2 周**  
  
        -   **1 个月**  
  
    -   **允许将消息移动到其他电子邮件帐户** \- 通过选择此选项，用户可在其设备上已配置的不同帐户间移动电子邮件消息。 此选项仅适用于 iOS 设备。  
  
    -   **允许从第三方应用程序发送电子邮件** \- 通过选择此选项，用户可从某些非默认的第三方电子邮件应用程序发送电子邮件。 此选项仅适用于 iOS 设备。  
  
    -   **同步最近使用的电子邮件地址** \- 选择此选项可同步设备上最近使用的电子邮件地址的列表。 此选项仅适用于 iOS 设备。  
  
    -   **使用 SSL** \- 选择此选项可在发送电子邮件、接收电子邮件以及与 Exchange Server 通信时使用安全套接字层 \(SSL\) 通信。  
  
    -   **要同步的内容类型：**选择要同步到设备的内容类型。 此选项仅适用于 Windows Phone 设备。 选择：  
  
        -   **Email**  
  
        -   **联系人**  
  
        -   **日历**  
  
        -   **任务**  
  
###  <a name="BKMK_Step5"></a> 步骤 5：指定 Exchange ActiveSync 电子邮件配置文件受支持的平台。  
 使用以下程序指定 Exchange ActiveSync 电子邮件配置文件受支持的平台。  
  
 受支持的平台是将在其上安装 Exchange ActiveSync 电子邮件配置文件的操作系统。  
  
##### 要指定 Exchange ActiveSync 电子邮件配置文件受支持的平台  
  
1.  在“创建 Exchange ActiveSync 电子邮件配置文件向导”的“受支持的平台”页上，选择将安装电子邮件配置文件的操作系统，或单击“全部选择”以在所有可用的操作系统上安装电子邮件配置文件。  
  
###  <a name="BKMK_Step6"></a> 步骤 6：完成向导。  
 在向导的“摘要”页上，查看要执行的操作，然后完成向导。 新的 Exchange ActiveSync 电子邮件配置文件将显示在“资产和符合性”工作区的“电子邮件配置文件”节点中。  
  
 有关如何部署 Exchange ActiveSync 电子邮件配置文件的信息，请参阅[如何在 System Center Configuration Manager 中部署电子邮件配置文件](../LocTest/How-to-deploy-email-profiles-in-System-Center-Configuration-Manager.md)。  
  
## 请参阅  
 [System Center Configuration Manager 中电子邮件配置文件的操作和维护](../LocTest/Operations-and-maintenance-for-email-profiles-in-System-Center-Configuration-Manager.md)
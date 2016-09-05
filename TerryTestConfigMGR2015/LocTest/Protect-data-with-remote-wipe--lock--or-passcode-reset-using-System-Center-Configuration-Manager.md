---
title: "使用 System Center Configuration Manager 的远程擦除、远程锁定或密码重置功能帮助保护数据"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-hybrid
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 770da7bd-02dd-474a-9604-93ff1ea0c1e4
caps.latest.revision: 18
caps.handback.revision: 10
translationtype: Human Translation
---
# 使用 System Center Configuration Manager 的远程擦除、远程锁定或密码重置功能帮助保护数据
[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 提供选择性擦除、完全擦除、远程锁定以及密码重置功能。 移动设备可以存储敏感的公司数据并提供对许多公司资源的访问。 为了保护设备，你可以发出以下命令：  
  
-   用于将设备还原为其出厂默认设置的完全擦除命令。  
  
-   只删除公司数据的选择性擦除命令。  
  
-   用于帮助保护设备安全的远程锁定可能会丢失。  
  
-   重置设备密码。  
  
##  <a name="BKMK_Wipe"></a> 擦除  
 如果需要保护遗失设备的安全或者停用正在使用的设备，你可以向设备发出擦除命令。  
  
 向设备发出“完全擦除”命令以将设备还原为其出厂默认值。 这将删除所有公司及用户数据和设置。  可以在 Windows Phone、iOS、Android 和 Windows 10 上执行完全擦除。  
  
 向设备发出“选择性擦除”命令以仅删除公司数据。 下表按平台描述了将删除什么数据，以及在选择性擦除之后对设备上保留的数据的影响。  
  
|注销设备时删除的内容|Windows 10|Windows 8.1 和 Windows RT 8.1|Windows RT|Windows Phone 8 和 Windows Phone 8.1|iOS|Android|Samsung KNOX|  
|----------------|----------------|----------------------------------|----------------|-----------------------------------------|---------|-------------|------------------|  
|通过使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 和 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 安装的公司应用及关联数据。|将卸载应用并删除旁加载密钥。 使用 Windows 选择性擦除的应用将吊销加密密钥，并且数据将不再可访问。|将卸载应用并删除旁加载密钥。 使用 Windows 选择性擦除的应用将吊销加密密钥，并且数据将不再可访问。|将删除旁加载密钥，但应用保持安装状态。|卸载应用。 删除公司应用数据。|卸载应用。 删除公司应用数据。|保留已安装的应用和数据。|卸载应用。|  
|VPN 和 Wi\-Fi 配置文件|删除。|删除。|不适用。|从 Windows Phone 8.1 中删除。|删除。|删除。|删除。|  
|证书|删除并吊销。|删除并吊销。|不适用。|从 Windows Phone 8.1 中删除。|删除并吊销。|吊销。|吊销。|  
|设置|删除要求。|删除要求。|删除要求。|删除以下设置（仅 Windows Phone 8.1）：<br /><br /> -   需要密码才可解锁移动设备<br />-   允许简单密码<br />-   最短密码长度<br />-   所需的密码类型<br />-   密码过期（天数）<br />-   记住密码历史记录<br />-   擦除设备前允许的重复登录失败次数<br />-   需要提供密码之前处于非活动状态的分钟数<br />-   所需密码类型 \- 最小字符集数<br />-   允许照相机<br />-   需要对移动设备加密<br />-   允许可移动存储<br />-   允许 Web 浏览器<br />-   允许应用程序商店<br />-   允许屏幕捕获<br />-   允许地理位置<br />-   允许 Microsoft 帐户<br />-   允许复制和粘贴<br />-   允许 Wi\-Fi tethering<br />-   允许自动连接到免费 Wi\-Fi 热点<br />-   允许 Wi\-Fi 热点报告<br />-   允许恢复出厂设置<br />-   允许蓝牙<br />-   允许 NFC<br />-   允许 Wi\-Fi|删除，以下各项除外：<br /><br /> -   允许语音漫游<br />-   允许数据漫游<br />-   允许漫游时自动同步|删除要求。|删除要求。|  
|管理代理|不适用。 管理代理是内置的。|不适用。 管理代理是内置的。|不适用。 管理代理是内置的。|不适用。 管理代理是内置的。|删除管理配置文件。|撤销设备管理员权限。|撤销设备管理员权限。|  
|电子邮件配置文件|删除启用了 EFS 的电子邮件，包括 Windows 电子邮件的邮件应用以及附件。|删除启用了 EFS 的电子邮件，包括 Windows 电子邮件的邮件应用以及附件。|不适用。|删除（仅 Windows Phone 8.1）|对于由 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 设置的电子邮件配置文件，将删除电子邮件帐户和电子邮件。|不适用。|对于由 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 设置的电子邮件配置文件，将删除电子邮件帐户和电子邮件。|  
  
#### 从 Configuration Manager 控制台启动远程擦除  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”并选择“设备”。 或者，可以单击“设备集合”并选择一个集合。  
  
2.  选择需停用\/擦除的设备。  
  
3.  单击“设备组”中的“远程设备操作”，然后选择“停用\/擦除”。  
  
### 擦除启用了加密文件系统 \(EFS\) 的内容  
 Windows 8.1 和 Windows RT 8.1 支持选择性擦除 EFS 加密内容。 下列各项适用于启用 EFS 的内容的选择性擦除：  
  
-   仅选择性擦除使用同一 Internet 域作为 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 帐户通过 EFS 保护的应用和数据。 有关详细信息，请参阅[设备数据管理的 Windows 选择性擦除](http://technet.microsoft.com/library/dn486874.aspx)。  
  
-   如果对与 EFS 关联的域进行了任何更改，则更改可能要花费长达 48 小时，之后才能对使用新域的应用和数据进行选择性擦除。  
  
-   向 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)] 注册的每个域均为将擦除的域。  
  
 EFS 选择性擦除当前支持下列数据和应用：  
  
-   Windows 相关邮件应用程序  
  
-   工作文件夹  
  
-   使用 EFS 加密的文件和文件夹。 有关详细信息，请参阅[加密文件系统的最佳方案](http://support.microsoft.com/kb/223316)。  
  
### 选择性擦除的最佳方案  
  
-   向 iOS 和 Windows Phone 8.1 设备提供电子邮件配置文件，以便成功擦除电子邮件。  
  
-   确保通过移动设备应用管理分发了应用，以便成功擦除应用。  
  
-   对于 iOS，将设置“允许备份到 iCloud”配置为“不允许”，以使用户无法使用 iCloud 还原内容。  
  
-   如果帐户已停用一年，那么 Intune 将停用该帐户，并将执行选择性擦除。  
  
##  <a name="BKMK_Reset"></a> 密码重置  
 如果用户忘记密码，则你可以删除设备中的密码，或者在设备上强制使用新的临时密码，从而帮助用户解决问题。 下表列出了在不同的移动平台上是如何重置密码的。  
  
|平台|密码重置|  
|--------|----------|  
|iOS|支持以便清除设备中的密码。 不创建新的临时密码。|  
|Android|支持并且创建临时密码。|  
|Windows 10|此时不受支持。|  
|Windows Phone 8 和 Windows Phone 8.1|支持|  
|Windows RT 8.1 和 Windows RT|不支持|  
|Windows 8.1|不支持|  
  
#### 在 Configuration Manager 中远程重置移动设备上的密码  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”并选择“设备”。 或者，可以单击“设备集合”并选择一个集合。  
  
2.  选择要重置密码的一台或多台设备。  
  
3.  单击“设备组”中的“远程设备操作”，然后选择“密码重置”。  
  
#### 显示密码重置状态  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”并选择“设备”。 或者，可以单击“设备集合”并选择一个集合。  
  
2.  选择要显示密码重置状态的一台或多台设备。  
  
3.  单击“设备组”中的“远程设备操作”，然后选择“显示密码状态”。  
  
##  <a name="BKMK_Lock"></a> 远程锁定  
 如果用户丢失其设备，你可以远程锁定该设备。 下表列出了是如何在不同的移动平台上进行远程锁定的。  
  
|平台|远程锁定|  
|--------|----------|  
|iOS|支持|  
|Android|支持|  
|Windows 10|此时不受支持。|  
|Windows Phone 8 和 Windows Phone 8.1|支持|  
|Windows RT 8.1 和 Windows RT|如果设备的当前用户是注册设备的相同用户，则支持。|  
|Windows 8.1|如果设备的当前用户是注册设备的相同用户，则支持。|  
  
#### 通过 Configuration Manager 控制台远程锁定移动设备  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”并选择“设备”。 或者，可以单击“设备集合”并选择一个集合。  
  
2.  选择要锁定的一台或多台设备。  
  
3.  单击“设备组”中的“远程设备操作”，然后选择“远程锁定”。  
  
#### 显示远程锁定状态  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”并选择“设备”。 或者，可以单击“设备集合”并选择一个集合。  
  
2.  选择要显示远程锁定状态的设备。  
  
3.  单击“设备组”中的“远程设备操作”，然后选择“显示远程锁定状态”。  
  
## 请参阅  
 [设备数据管理的 Windows 选择性擦除](http://technet.microsoft.com/library/dn486874.aspx)   
 [使用 System Center Configuration Manager 和 Microsoft Intune 的混合移动设备管理 \(MDM\)](../LocTest/Hybrid-mobile-device-management--MDM--with-System-Center-Configuration-Manager-and-Microsoft-Intune.md)
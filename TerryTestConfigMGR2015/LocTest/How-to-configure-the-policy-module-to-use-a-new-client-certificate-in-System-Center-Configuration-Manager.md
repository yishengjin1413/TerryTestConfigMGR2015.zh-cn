---
title: "如何配置策略模块以在 System Center Configuration Manager 中使用新客户端证书"
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
ms.assetid: 4f27b819-f43a-4dc8-847a-a81d8c880e5d
caps.latest.revision: 4
caps.handback.revision: 3
translationtype: Human Translation
---
# 如何配置策略模块以在 System Center Configuration Manager 中使用新客户端证书
将 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 策略模块与网络设备注册服务角色服务一起运行的服务器使用客户端证书向 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的证书注册点站点系统服务器验证策略模块。 通常，客户端身份验证证书的有效期为一年。 在证书过期之前，请续订证书，针对新证书更新注册表，然后重启运行网络设备注册服务的 Web 服务器。  
  
> [!NOTE]  
>  如果证书已过期，**“错误\(”未能发送 http 请求 \<thumbprint\>。错误 12037”，**将显示在运行网络设备注册服务的服务器上的 NDESPlugin.log 文件中。在错误消息中，*\<thumbprint\>* 将替换为已过期证书的证书指纹。  
  
 续订证书：  
  
-   如果你手动请求了此客户端证书，请手动请求新证书。 如果需要帮助部署此证书，可以使用 [System Center Configuration Manager 的 PKI 证书的分步部署示例：Windows Server 2008 证书颁发机构](../Topic/Step-by-step%20example%20deployment%20of%20the%20PKI%20certificates%20for%20System%20Center%20Configuration%20Manager:%20Windows%20Server%202008%20Certification%20Authority.md) 主题中的 [为分发点导出客户端证书](../Topic/Step-by-step%20example%20deployment%20of%20the%20PKI%20certificates%20for%20System%20Center%20Configuration%20Manager:%20Windows%20Server%202008%20Certification%20Authority.md#BKMK_exportclientdistributionpoint22008) 说明，但有一个例外：请不要选择证书模板属性中“请求处理”选项卡上的“允许导出私钥”复选框。  
  
-   如果通过使用组策略注册自动部署了此客户端证书，则默认配置是在原始证书过期之前自动请求新证书。  
  
 将新证书部署在运行网络设备注册服务和 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 策略模块的服务器上后，使用下列过程来配置服务器以使用新证书。  
  
### 配置策略模块以使用新客户端证书  
  
1.  在运行网络设备注册服务和 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 策略模块的服务器上，打开注册表编辑器，并使用下列注册表项将旧证书指纹替换为新证书指纹：HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Cryptography\\MSCEP\\Modules\\NDESPolicy\\NDESCertThumbprint。  
  
    > [!TIP]  
    >  若要为新证书标识指纹，请使用证书管理单元在计算机存储中找到证书。 然后，右键单击该证书，单击“属性”，单击“查看证书”，单击“详细信息”选项卡，然后向下滚动并选择“指纹”。 你随后将看到并能够复制作为此证书的证书指纹的十六进制字符的字符串。  
  
2.  使用下列方法之一重启 Web 服务器服务：  
  
    1.  从 Internet Information Services \(IIS\) 管理器中：浏览到树中的 Web 服务器节点。 在“操作”窗格中，单击“重启”。  
  
    2.  在命令行中，键入 **iisreset \/restart** 并按 ENTER。  
  
     有关详细信息，请参阅 TechNet 上 Windows Server 库中的 [Start or Stop the Web Server \(IIS 8\)（启动或停止 Web 服务器 \(IIS 8\)）](http://go.microsoft.com/fwlink/p/?LinkId=320507)。  
  
 可通过在运行网络设备注册服务的服务器上的 NDESPlugin.log file 文件中检查下列条目来确认策略模块正在使用新的证书：**INFO\("NDES thumbprint is \<thumbprint\>.", wszBuffer\);**  
  
## 请参阅  
 [System Center Configuration Manager 中证书配置文件的技术参考](../LocTest/Certificate-profiles-technical-reference-for-System-Center-Configuration-Manager.md)
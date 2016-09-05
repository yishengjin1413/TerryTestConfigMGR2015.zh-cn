---
title: "用户如何在 System Center Configuration Manager 中向本地移动设备管理注册设备"
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
ms.assetid: 59004b34-b64f-4d77-898c-07bf3dc75430
caps.latest.revision: 9
caps.handback.revision: 6
translationtype: Human Translation
---
# 用户如何在 System Center Configuration Manager 中向本地移动设备管理注册设备
借助 [!INCLUDE[onprem_first](../LocTest/includes/onprem_first_md.md)]，如果用户已获得注册权限（通过更新客户端设置的方式）并且其设备已安装所需的根证书以便与承载所需站点系统角色的服务器进行可信通信，则他们可以注册设备。 有关如何设置注册的详细信息，请参阅 [为 System Center Configuration Manager 中的本地移动设备管理设置设备注册](../LocTest/Set-up-device-enrollment-for-On-premises-Mobile-Device-Management-in-System-Center-Configuration-Manager.md)。  
  
 [!INCLUDE[onprem_devices](../LocTest/includes/onprem_devices_md.md)] 以下任务说明了如何注册和验证 [!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 的计算机和设备的注册。  
  
-   [注册 Windows 10 计算机](#bkmk_enrollDesk)  
  
-   [注册 Windows 10 移动版设备](#bkmk_enrollMob)  
  
-   [验证设备注册](#bkmk_verify)  
  
##  <a name="bkmk_enrollDesk"></a> 注册 Windows 10 计算机  
  
1.  在 Windows 10 计算机上，转到“设置”。  
  
2.  单击“帐户”，然后单击“工作单位访问”。  
  
3.  在“工作单位访问”下的“连接到工作单位或学校”中，单击“连接”，输入工作电子邮件地址，然后单击“继续”。  
  
4.  输入注册服务器（承载注册点站点系统角色的服务器）的 FQDN，然后单击“继续”。  
  
5.  在“连接到服务”中，输入你的工作电子邮件密码，然后单击“登录”。  
  
6.  单击“跳过”以记住登录信息，不久过后将连接设备。  
  
##  <a name="bkmk_enrollMob"></a> 注册 Windows 10 移动版设备  
  
1.  在 Windows 10 移动版设备上，转到“设置”。  
  
2.  单击“帐户”，然后单击“工作单位访问”。  
  
3.  单击“连接”。  
  
4.  输入你的工作电子邮件地址以及承载注册代理点站点系统角色的服务器的 FQDN。 单击“连接”。  
  
5.  在下一个屏幕上，输入你的工作电子邮件地址和密码，然后单击“登录”。 不久过后，设备将完成注册。 单击“Done”（完成）。  
  
##  <a name="bkmk_verify"></a> 验证设备注册  
 你可以在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台验证设备是否已成功注册。  
  
1.  启动 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台  
  
2.  单击“资产和符合性”\>“概述”\>“设备”。 列表中将显示已注册的设备。  
  
## 请参阅  
 [在 System Center Configuration Manager 中为本地移动设备管理注册设备](../LocTest/Enroll-devices-for-On-premises-Mobile-Device-Management-in-System-Center-Configuration-Manager.md)
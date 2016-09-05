---
title: "如何确定 WSUS System Center Configuration Manager 中 WSUS 使用的端口设置"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-sum
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: fb5a042f-5c66-424e-8b42-810d971e95ff
caps.latest.revision: 6
caps.handback.revision: 5
---
# 如何确定 WSUS System Center Configuration Manager 中 WSUS 使用的端口设置
在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中安装和配置软件更新点时，必须指定 Microsoft Windows Server Update Services \(WSUS\) 服务器使用的端口设置。  使用下列过程来确定 WSUS 使用的端口设置。  
  
### 在 IIS 中确定所用的端口设置  
  
1.  在 WSUS 服务器上，打开 Internet Information Services \(IIS\) 管理器。  
  
2.  展开“网站”，右键单击 WSUS 服务器的网站，再单击“编辑绑定”。 在“网站绑定”对话框中，HTTP 和 HTTPS 端口值显示在“端口”列中。  
  
## 请参阅  
 [在 System Center Configuration Manager 中配置软件更新](../LocTest/Configure-software-updates-in-System-Center-Configuration-Manager.md)
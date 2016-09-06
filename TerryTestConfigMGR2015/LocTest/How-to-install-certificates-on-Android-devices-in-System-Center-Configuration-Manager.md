---
title: "如何在 System Center Configuration Manager 中的 Android 设备上安装证书"
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
ms.assetid: 4036f3d7-6658-4118-9bd0-6c1a3b276f56
caps.latest.revision: 4
caps.handback.revision: 3
translationtype: Human Translation
---
# 如何在 System Center Configuration Manager 中的 Android 设备上安装证书
在 Android 设备上安装证书时，最终用户必须执行许多操作才能接受和安装证书。 对你的最终用户进行关于他们可能需要执行的操作方面的培训很重要，因为如果用户未执行正确的操作，那么将不会正确安装证书。  
  
 以下过程详细描述了最终用户为接受和安装证书而必须在 Android 设备上执行的操作。  
  
## 证书安装  
  
#### 在 Android 设备上安装证书  
  
1.  用户在 Android 设备上收到一条名为“公司门户”的通知。 单击通知以开始。  
  
2.  在“提取自:\<certificate name\>”框中，用户需要输入密码以提取证书。 用户必须单击“确定”，而不用输入密码。  
  
3.  在“证书名称”框中，系统将显示证书名称，用户必须单击“确定”以继续。  
  
    > [!IMPORTANT]  
    >  用户不能编辑此框中的证书名称，否则证书将不起作用。  
  
4.  在“选择证书”框中，用户必须单击“允许”以允许公司门户使用证书。  
  
    > [!NOTE]  
    >  用户不能单击“安装”按钮，该按钮允许你从存储设备中选择其他证书。  
  
## 请参阅  
 [System Center Configuration Manager 中证书配置文件的技术参考](../LocTest/Certificate-profiles-technical-reference-for-System-Center-Configuration-Manager.md)
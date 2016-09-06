---
title: "如何在 System Center Configuration Manager 中对软件更新启用 CRL 检查"
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
ms.assetid: 7b6e680a-ab8f-4144-bce3-bc36618b256c
caps.latest.revision: 5
caps.handback.revision: 4
translationtype: Human Translation
---
# 如何在 System Center Configuration Manager 中对软件更新启用 CRL 检查
默认情况下，在验证 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 软件更新上的签名时不会检查证书吊销列表 \(CRL\)。 如果在每次使用证书时都检查 CRL，则能更好地抵御因使用已吊销的证书而造成的安全威胁，但这样做会使连接出现延迟，并在执行 CRL 检查的计算机上引发额外的处理操作。  
  
 如果使用，则必须在处理软件更新的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台上启用 CRL 检查。  
  
### 启用 CRL 检查  
  
-   在执行 CRL 检查的计算机上，通过命令提示符从产品 DVD 中运行以下命令：**\\SMSSETUP\\BIN\\X64\\**\<*language*\>**\\UpdDwnldCfg.exe\/checkrevocation**。  
  
     例如，对于英语（美国），你将运行 **\\SMSSETUP\\BIN\\X64\\00000409\\UpdDwnldCfg.exe \/checkrevocation**  
  
## 请参阅  
 [在 System Center Configuration Manager 中配置软件更新](../LocTest/Configure-software-updates-in-System-Center-Configuration-Manager.md)
---
title: "使用更新注册工具将修补程序导入 System Center Configuration Manager"
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
ms.assetid: 8cc13635-85d6-4b07-a3ec-c42188bc5c74
caps.latest.revision: 8
caps.handback.revision: 7
translationtype: Human Translation
---
# 使用更新注册工具将修补程序导入 System Center Configuration Manager
Configuration Manager 的某些更新无法从 Microsoft 云服务获取，只能在带外获取。 用于解决特定问题的受限版本修补程序是一个示例。   
必须安装带外版本，并且更新或修补程序文件名以扩展名 **update.exe** 结尾时，需使用“更新注册工具”手动将更新导入 Configuration Manager 控制台。 该工具使你可以提取更新包并将它传输到站点服务器，然后向 Configuration Manager 控制台注册更新。  
  
 如果修补程序文件有 **.exe** 文件扩展名（不是 **update.exe**，请参阅[使用修补程序安装程序来安装 System Center Configuration Manager 的更新](../LocTest/Use-the-Hotfix-Installer-to-install-updates-for-System-Center-Configuration-Manager.md)  
  
> [!NOTE]  
>  本主题提供有关如何安装更新 System Center Configuration Manager 的修补程序的常规指导。 有关特定修补程序或更新的详细信息，请参阅 Microsoft 支持上该更新的相应知识库 \(KB\) 文章。  
  
 **使用更新注册工具的先决条件：**  
  
-   只有以 **.update.exe** 扩展名结尾的带外更新才能使用此工具安装  
  
-   该工具自包含有直接从 Microsoft 获取的各个更新  
  
-   该工具不依赖于服务连接点的模式  
  
-   该工具必须在承载服务连接点的计算机上运行  
  
-   运行该工具的计算机（服务连接点计算机）必须安装 .NET Framework 4.52  
  
-   用于运行该工具的帐户必须在承载服务连接点的计算机上具有“本地管理员”权限（工具在此计算机上运行）\)  
  
-   用于运行该工具的帐户必须对承载服务连接点的计算机上的以下文件夹具有“写入”权限：**\<ConfigMgr Installation directory\>\\EasySetupPayload\\offline**  
  
### 使用更新注册工具  
  
1.  在承载服务连接点的计算机上：  
  
    -   使用管理特权打开命令提示符，然后将目录更改为包含 **\<Product\>\-\<product version\>\-\<KB article ID\>\-ConfigMgr.Update.exe** 的位置  
  
2.  运行以下命令以启动更新注册工具：  
  
    -   **\<Product\>\-\<product version\>\-\<KB article ID\>\-ConfigMgr.Update.exe**  
  
     修补程序进行注册之后，它会在 24 小时内在控制台中显示为新的更新。  可以使用以下各项之一来加快该过程：  
  
    -   对于版本 1511：在 Configuration Manager 控制台中，导航到“管理”\>“云服务”\>“更新和服务”，然后选择“立即启动更新发现过程”。  这会在注册过程完成时立即开始导入修补程序，从而使它在控制台中可用。  
  
    -   对于版本 1602 及更高版本：在 Configuration Manager 控制台中，导航到“管理”\>“云服务”\>“更新和服务”，然后单击“检查更新”  
  
     更新注册工具会将其操作记录到本地计算机上的 .log 文件。 该日志文件与修补程序 .exe 文件同名，并且会写入到 **%SystemRoot%\/Temp** 文件夹中。  
  
     注册更新之后，可以关闭更新注册工具。  
  
3.  打开 Configuration Manager 控制台并导航到“管理”\>“云服务”\>“更新和服务”。 现在即可安装之前导入的修补程序。 有关安装更新的信息，请参阅[安装 System Center Configuration Manager 在控制台的更新](../LocTest/Install-in-console-updates-for-System-Center-Configuration-Manager.md)  
  
## 另请参阅  
 [System Center Configuration Manager 的更新](../LocTest/Updates-for-System-Center-Configuration-Manager.md)   
 [使用修补程序安装程序来安装 System Center Configuration Manager 的更新](../LocTest/Use-the-Hotfix-Installer-to-install-updates-for-System-Center-Configuration-Manager.md)
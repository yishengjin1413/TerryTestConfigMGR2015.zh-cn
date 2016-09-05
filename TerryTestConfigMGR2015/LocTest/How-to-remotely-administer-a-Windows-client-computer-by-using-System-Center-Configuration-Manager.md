---
title: "如何使用 System Center Configuration Manager 远程管理 Windows 客户端计算机"
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
ms.assetid: 3c9648c4-645e-4e47-ae10-2da817b8c83b
caps.latest.revision: 5
caps.handback.revision: 4
author: barlanmsft
---
# 如何使用 System Center Configuration Manager 远程管理 Windows 客户端计算机
使用以下过程来远程管理 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的计算机。  
  
 在开始使用远程控制之前，请确保已经查看了以下主题的信息：  
  
-   [在 System Center Configuration Manager 中规划远程控制](../LocTest/Planning-for-remote-control-in-System-Center-Configuration-Manager.md)  
  
-   [配置 System Center Configuration Manager 中的远程控制](../LocTest/Configuring-remote-control-in-System-Center-Configuration-Manager.md)  
  
 你可以使用以下三种方法之一来启动 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 远程控制查看器：  
  
-   使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台。  
  
-   在 Windows 命令提示符处。  
  
-   在运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台的计算机上的 Windows“启动”菜单中（从“Microsoft System Center 2012”程序组）。  
  
### 若要从 Configuration Manager 控制台中远程管理客户端计算机  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”。  
  
2.  在“资产和符合性”工作区中，单击“设备”或“设备集合”。  
  
3.  选择要远程管理的计算机，然后在“主页”选项卡上的“设备”组中，单击“启动”，然后单击“远程控制”。  
  
    > [!IMPORTANT]  
    >  如果将“提示用户进行远程控制”客户端设置权限设置为“真”，直至远程计算机上的用户同意远程控制提示后才会启动连接。 有关详细信息，请参阅 [配置 System Center Configuration Manager 中的远程控制](../LocTest/Configuring-remote-control-in-System-Center-Configuration-Manager.md)。  
  
4.  “Configuration Manager 远程控制”窗口打开后，就可以远程管理客户端计算机了。 使用下列选项来配置连接。  
  
    > [!NOTE]  
    >  如果连接的计算机有多台监视器，那么远程控制窗口中会显示所有这些监视器的显示内容。  
  
    -   **文件\-连接** – 连接到另一台计算机。 远程控制会话处于活动状态时，此选项不可用。  
  
    -   **文件\-断开** – 断开活动远程控制会话的连接，但不会关闭“Configuration Manager 远程控制”窗口。  
  
    -   **文件\-退出** – 断开活动远程控制会话的连接，并关闭“Configuration Manager 远程控制”窗口。  
  
        > [!NOTE]  
        >  当断开远程控制会话的连接时，将删除正在查看的计算机上 Windows 剪贴板的内容。  
  
    -   **视图\-全屏** – 最大化显示“Configuration Manager 远程控制”窗口以填满所有可用的显示空间。  
  
        > [!NOTE]  
        >  要退出全屏显示模式，请按 Ctrl \+ Alt \+ Break。  
  
    -   **视图\-调整为适合页面** – 缩放远程计算机的显示尺寸以适合“Configuration Manager 远程控制”窗口的大小。  
  
    -   **视图\-状态栏** – 切换“Configuration Manager 远程控制”窗口状态栏显示。  
  
    -   **操作\-发送 Ctrl \+ Alt \+ Del 键** – 向远程计算机发送 Ctrl \+ Alt \+ Del 键组合。  
  
    -   **操作\-启用剪贴板共享** – 允许你从\/向远程计算机复制和粘贴项目。 如果更改此值，必须重新启动远程控制会话，更改才会生效。  
  
        > [!NOTE]  
        >  如果不希望在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中启用剪贴板共享，请在运行控制台的计算机上将注册表项“HKEY\_CURRENT\_USER\\Software\\Microsoft\\ConfigMgr10\\Remote Control\\Clipboard Sharing”的值设置为“0”。  
  
    -   **操作\-锁定远程键盘和鼠标** – 锁定远程键盘和鼠标以阻止用户操作远程计算机。  
  
    -   **帮助\-关于远程控制** – 显示有关远程控制查看器当前版本的信息。  
  
5.  远程计算机上的用户在单击 Windows 通知区域中的[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]“远程控制”图标或远程控制会话栏上的图标时可以查看有关远程控制会话的详细信息。  
  
6.  当不再需要远程控制会话时，请使用前面介绍的方法之一来结束远程控制会话。  
  
### 若要从 Windows 命令行中启动远程控制查看器  
  
-   在 Windows 命令提示符处键入 *\<Configuration Manager Installation Folder\>***\\AdminConsole\\Bin\\x64\\CmRcViewer.exe**  
  
    > [!NOTE]  
    >  CmRcViewer.exe 支持以下命令行选项：  
    >   
    >  -   *\<Address\>* – 指定要连接的客户端计算机的 NetBIOS 名称、完全限定域名 \(FQDN\) 或 IP 地址。  
    > -   *\<Site Server Name\>* – 指定想要向其发送与远程控制会话相关的状态消息的 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 站点服务器的名称。  
    > -   **\/?** – 显示远程控制查看器的命令行选项。  
    >   
    >  **示例：CmRcViewer.exe** *\<Address\>* *\<\\\\Site Server Name\>*  
  
## 请参阅  
 [System Center Configuration Manager 中远程控制的操作和维护](../LocTest/Operations-and-maintenance-for-remote-control-in-System-Center-Configuration-Manager.md)
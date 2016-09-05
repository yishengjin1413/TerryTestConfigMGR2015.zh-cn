---
title: "通过 Configuration Manager 的绕过激活锁定帮助保护 iOS 设备"
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
ms.assetid: c2e53d99-f19d-4a24-b422-9f54813aa2e2
caps.latest.revision: 14
caps.handback.revision: 13
---
# 通过 Configuration Manager 的绕过激活锁定帮助保护 iOS 设备
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 可以帮助你管理 iOS 激活锁定，这是适用于 iOS 7.1 及更高版本设备的“查找我的 iPhone”应用的功能。 当设备上使用了“查到我的 iPhone”应用时，激活锁定自动启用。 启用后，任何人都必须先输入用户的 Apple ID 和密码，然后才能执行以下操作：  
  
-   关闭“查找我的 iPhone”  
  
-   擦除设备  
  
-   重新激活设备  
  
> [!IMPORTANT]  
>  **[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] Technical Preview 中当前已知的绕过激活锁定问题**  
>   
>  -   因一个有关解密绕过激活锁定代码的问题，在“绕过激活锁定”对话框中显示的检索代码将不起作用。 如果单击“刷新代码”，可能会看到一条请求了新代码的消息，但此过程将无法完成。  
>   
>      由于此问题，你当前无法看到哪些设备正在使用激活锁定。  
> -   当你擦除 Android 设备时，你会看到一个询问你是否要绕过激活锁定的对话框。 由于 Android 设备不使用此功能，你可以放心地忽略此消息。  
  
## 激活锁定对你有何影响  
 尽管激活锁定可帮助保护 iOS 设备的安全，并可提高在设备丢失和被盗时的找回几率，但对于 IT 管理员来说，此功能仍然带来了许多挑战。 例如：  
  
-   你的其中一个用户在设备上设置了激活锁定。 该用户之后离开了公司并返回使用其设备。 如果不提供用户的 Apple ID 和密码，则不能重新激活该设备。  
  
-   你需要报告启用了激活锁定的所有设备。  
  
-   更新你组织中的设备分配情况时，如果你希望将某些设备分配给另一个部门， 你只能重新分配未启用激活锁定的设备。  
  
 为了帮助解决这些问题，Apple 在 iOS 7.1 中引入了绕过激活锁定。 借助此功能，你无需用户的 Apple ID 和密码即可删除监管设备中的激活锁定。 监管设备可以生成设备特定的绕过激活锁定代码，该代码存储在 Apple 的激活服务器上。  
  
> [!TIP]  
>  在 iOS 设备的监管模式下，你可以使用 Apple 配置器工具来锁定设备，以将设备的功能限制为完成特定的业务目的。 监管模式通常仅适用于公司拥有的设备。  
  
## Configuration Manager 如何帮助你管理激活锁定  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 可以请求运行 iOS 7.1 和更高版本的已监管设备和非监管设备的激活锁定状态。 对于监管设备而言，Intune 可以检索绕过激活锁定代码并直接将代码发布到设备。 如果已擦除了设备，你可以直接使用该代码作为用户名并使用一个空密码来访问设备。  
  
 **此功能的业务优势有：**  
  
-   用户能够获得“查到我的 iPhone”应用所具有的安全优势  
  
-   你可以让用户在知道如下事实的情况下进行工作：当需要重新调整设备的用途时，你可以停用或解锁设备  
  
## 如何从 Configuration Manager 控制台使用绕过激活锁定  
  
> [!IMPORTANT]  
>  绕过设备上的激活锁定后，如果“查到我的 iPhone”应用处于打开状态，它将自动应用新的激活锁定。 因此，“你应实际拥有该设备，才能执行此过程”。  
  
-   在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”。  
  
-   在“资产和符合性”工作区中，单击“设备”。  
  
-   选择处于监管模式且你要绕过其激活锁定的已注册设备，然后在“主页” 选项卡上，单击“远程设备操作”\>“绕过激活锁定”。  
  
-   “绕过激活锁定”对话框中将显示所选设备的绕过激活锁定代码。 单击“发送绕过命令”以继续。  
  
-   在“确认绕过激活锁定”对话框中阅读警告消息，在准备好继续操作后单击“是”。  
  
 你可以从“绕过激活锁定”对话框中检查解除锁定请求的状态。  
  
## 请参阅  
 [使用 System Center Configuration Manager 和 Microsoft Intune 的混合移动设备管理 \(MDM\)](../LocTest/Hybrid-mobile-device-management--MDM--with-System-Center-Configuration-Manager-and-Microsoft-Intune.md)
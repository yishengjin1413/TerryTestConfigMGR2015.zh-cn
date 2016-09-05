---
title: "使用 Configuration Manager 管理通过批量采购计划购买的应用"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-app
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: b5e7cead-e257-405b-a2aa-b0130e48dc40
caps.latest.revision: 23
caps.handback.revision: 5
---
# 使用 Configuration Manager 管理通过批量采购计划购买的应用
一些应用商店使你能够为你想在公司中运行的应用购买多个许可证。 这有助于降低跟踪多个已购买应用副本的管理成本。  
  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 可通过从应用商店中导入许可证信息以及跟踪你已使用的许可证的数量来帮助你管理通过这样的程序所购买的应用。  
  
## 管理批量采购的适用于 iOS 设备的应用程序  
 你通过 Apple 批量采购计划 \(VPP\) 购买多个 iOS 应用许可证。 这涉及到从 Apple 网站上设置一个 Apple VPP 帐户并将 Apple VPP 令牌上载到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]。  然后你可以将你的批量采购信息与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 共享并追踪你的批量采购应用使用。  
  
### 开始之前  
 在开始之前，你需要从 Apple 中获取 VPP 令牌并将其上载到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]。  
  
> [!IMPORTANT]  
>  -   每个组织只可以有一个 VPP 帐户和令牌。  
> -   一旦你将 Apple VPP 帐户和 Intune 相关联，随后将不能关联不同的帐户。 出于此原因，有超过一个人拥有你所使用的帐户的详细信息是非常重要的。  
> -   如果你以前在你现有的 Apple VPP 帐户中使用过不同产品的 VPP 令牌，必须使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 生成一个新的以供使用。  
> -   每个令牌的有效期为一年。  
> -   默认情况下，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 每天与 Apple VPP 服务同步两次，以确保你的许可证与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 同步。 但是，你可以在任何时候启动手动同步。  
  
##### 步骤 1 \- 获取并上载 Apple VPP 令牌  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“管理”。  
  
2.  在“管理”工作区中，展开“云服务”，并单击“Microsoft Intune 订阅”。  
  
3.  从列表中选择要你的 Intune 订阅，然后在“主页”选项卡上的“属性”组中，单击“属性”。  
  
4.  在“Microsoft Intune 订阅属性”对话框中的“Apple iOS 批量采购计划”选项卡上，单击“Apple VPP 帐户”链接，如果你还没有注册的话，请注册为企业或教育机构批量采购计划。 一旦注册完成，下载你的帐户的 Apple VPP 令牌。  
  
5.  输入或粘贴 VPP 令牌名和你的 Apple ID，然后单击“应用”。  
  
6.  在警告对话框中，单击该复选框以指示你已了解你此后不能更改为不同的 VPP 帐户，然后单击“是”。  
  
 在“Microsoft Intune 订阅属性”对话框中的“Apple iOS 批量采购计划”选项卡上，你现在可以查看有关 Apple VPP 令牌的信息，包括它上一次更新的时间，何时将过期，以及上一次同步的时间。  
  
 你可以随时通过单击“同步”将 Apple 保存的数据与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 同步。  
  
 如果你希望在你的 VPP 令牌快要过期时得到通知，启用“VPP 令牌过期前显示警报”，然后选择你希望在过期前多少天收到提醒。 然后 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将在你指定的时间生成警报。  
  
### 步骤 2 \- 部署批量采购的应用  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“软件库”。  
  
2.  在“软件库”工作区中，展开“应用程序管理”，然后单击“应用程序”。  
  
3.  在“主页”选项卡上的“创建”组中，单击“创建应用程序”。  
  
4.  在“创建应用程序向导”的“常规”页上，选择“自动检测安装文件中有关此应用程序的信息”。  
  
5.  在“类型”下拉列表中，选择“来自应用商店的 iOS 应用包”，然后单击“浏览”。  
  
6.  在“iOS 浏览器应用包”对话框中，单击“iOS VPP”选项卡。 显示批量采购的 iOS 应用列表。 选择你想要使用的应用，然后单击“确定”以返回到创建应用程序向导的“常规”页。 指向应用的 URL 将填充到“位置”字段中。  
  
7.  完成创建应用程序向导 有关如何创建 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 应用程序的完整详细信息，请参阅[如何使用 System Center Configuration Manager 创建应用程序](../LocTest/How-to-create-applications-with-System-Center-Configuration-Manager.md)。  
  
8.  按照通常方法部署应用程序。 有关部署应用程序的帮助，请参阅[如何使用 System Center Configuration Manager 部署应用程序](../LocTest/How-to-deploy-applications-with-System-Center-Configuration-Manager.md)。  
  
 在部署应用时，安装该应用的每个用户使用一个许可证。  
  
 若要回收许可证，必须将部署操作为“卸载”。 应用卸载后，将回收许可证。  
  
### 步骤 3 \- 监视 iOS VPP 应用  
 你可以监视所有通过使用“具有许可证计数的所有 iOS 批量采购计划应用程序的”报表购买的 VPP 应用的许可证使用情况。  
  
 此报表显示每个应用程序名称，以及你购买的许可证总数、可用许可证数量以及更多内容。  
  
 有关运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 报表的帮助，请参阅[System Center Configuration Manager 中的报表](../LocTest/Reporting-in-System-Center-Configuration-Manager.md)。  
  
## 请参阅  
 [使用 System Center Configuration Manager 管理和保护应用](../LocTest/Manage-and-protect-apps-with-System-Center-Configuration-Manager.md)
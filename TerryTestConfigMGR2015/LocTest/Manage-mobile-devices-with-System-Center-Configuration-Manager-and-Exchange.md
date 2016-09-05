---
title: "使用 System Center Configuration Manager 和 Exchange 管理移动设备"
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
ms.assetid: aba688d9-fd5b-4c42-8cb4-f7e1b161ef50
caps.latest.revision: 8
caps.handback.revision: 7
---
# 使用 System Center Configuration Manager 和 Exchange 管理移动设备
当你希望使用 Microsoft Exchange ActiveSync 协议管理连接到 Exchange Server（本地或联机）的移动设备，并且无法使用 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 注册这些设备时，请使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的 Exchange Server 连接器。 你可从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台配置 Exchange 移动设备管理功能，例如远程设备擦除和针对多个 Exchange 服务器的设置控制。  
  
 ![configmgr&#45;with&#45;exchange](../LocTest/media/configmgr-with-exchange.png "configmgr\-with\-exchange")  
  
 在使用 Exchange Server 连接器管理移动设备时，此操作不会在移动设备上安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端。 因此，某些管理功能受到限制。 例如，你无法在这些设备上安装软件或使用配置项目来配置这些设备。 有关可针对移动设备与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 一起使用的各种管理功能的详细信息，请参阅[选择 System Center Configuration Manager 的设备管理解决方案](../LocTest/Choose-a-device-management-solution-for-System-Center-Configuration-Manager.md)。  
  
> [!IMPORTANT]  
>  在安装 Exchange Server 连接器之前，请确认 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 支持你所使用的 Microsoft Exchange 的版本。 有关详细信息，请参阅 [System Center Configuration Manager 支持的站点和客户端操作系统](../Topic/Supported%20operating%20systems%20for%20sites%20and%20clients%20for%20System%20Center%20Configuration%20Manager.md) 中的“Exchange Server 连接器”。  
  
 在使用 Exchange Server 连接器时，可通过你在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中配置的设置来管理移动设备，而不是通过默认 Exchange ActiveSync 邮箱策略进行管理。 定义要在以下组设置中使用的设置：“常规”、“密码”、“电子邮件管理”、“安全”和“应用程序”。 例如，在“密码”组设置中，你可以配置移动设备是否需要密码、最小密码长度、密码复杂性以及是否允许密码恢复。  
  
 当你配置该组中的至少一个设置时，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将为移动设备管理该组中的所有设置。 如果不配置组中的任何设置，则 Exchange 将继续针对这些设置管理移动设备。 将仍然应用在 Exchange Server 上配置并分配给用户的任何 Exchange ActiveSync 邮箱策略。  
  
 你还可以配置 Exchange Server 连接器来管理 Exchange 访问规则，并且允许、阻止或者隔离移动设备。 你可以使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台以远程方式擦除移动设备，并且用户可以使用应用程序目录以远程方式擦除其移动设备。  
  
 当 Exchange Server 连接器管理用户的移动设备并且 Exchange Server 位于本地时，该移动设备将自动出现在应用程序目录中。 在为 Microsoft Exchange Online 配置 Exchange Server 连接器时，你必须手动配置用户设备相关性，用户的移动设备才会出现在应用程序目录中。 有关如何手动配置用户设备相关性的详细信息，请参阅[在 System Center Configuration Manager 中将用户和设备与用户设备相关性相链接](../LocTest/Link-users-and-devices-with-user-device-affinity-in-System-Center-Configuration-Manager.md)。  
  
> [!TIP]  
>  如果使用 Exchange Server 连接器管理移动设备，并且该移动设备已转让给另一名用户，请从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中删除该移动设备，之后移动设备的新所有者才能在这台转让的移动设备上配置其 Exchange 帐户。  
  
## 所需的安全权限  
 你必须具有以下安全权限才能配置 Exchange Server 连接器：  
  
-   若要添加、修改和删除注册 Exchange Server 连接器：“站点”对象的“修改”权限。  
  
-   若要要配置移动设备设置：“站点”对象的“ModifyConnectorPolicy”权限。  
  
 “完全权限管理员”安全角色包括配置 Exchange Server 连接器所需的权限。  
  
 你必须具有以下安全权限才能管理移动设备：  
  
-   若要擦除移动设备：“集合”对象的“删除资源”权限。  
  
-   若要取消擦除命令：“集合”对象的“修改资源”权限。  
  
-   允许和阻止移动设备：“集合”对象的**修改资源**权限。  
  
 “操作管理员”安全角色包括使用 Exchange Server 连接器管理移动设备所需的权限。  
  
 有关如何配置安全权限的详细信息，请参阅[为 System Center Configuration Manager 配置基于角色的管理](../LocTest/Configure-role-based-administration-for-System-Center-Configuration-Manager.md)。  
  
## 安装和配置 Exchange Server 连接器  
 使用以下过程来安装和配置 Exchange Server 连接器以便管理移动设备。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 在一个 Exchange 组织中只支持一个连接器。 完成这些步骤之后，你可以在查看显示移动设备的集合时监视连接器找到和管理的移动设备，以及通过使用移动设备的报表进行监视。  
  
> [!NOTE]  
>  [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 使用“*用户名*\_*设备类型*”格式为它找到的移动设备生成名称。 如果用户有多台具有相同设备类型的移动设备，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将在控制台和报表中为这些移动设备显示同一名称。  
  
#### 安装和配置 Exchange Server 连接器  
  
1.  决定哪个帐户将连接到 Exchange 客户端访问服务器来管理移动设备。 该帐户可以是站点服务器的计算机帐户或 Windows 用户帐户。 然后，配置此帐户以运行以下 Exchange Server cmdlet：  
  
    -   **Clear\-ActiveSyncDevice**  
  
    -   **Get\-ActiveSyncDevice**  
  
    -   **Get\-ActiveSyncDeviceAccessRule**  
  
    -   **Get\-ActiveSyncDeviceStatistics**  
  
    -   **Get\-ActiveSyncMailboxPolicy**  
  
    -   **Get\-ActiveSyncOrganizationSettings**  
  
    -   **Get\-ExchangeServer**  
  
    -   **Get\-Recipient**  
  
    -   **Set\-ADServerSettings**  
  
    -   **Set\-ActiveSyncDeviceAccessRule**  
  
    -   **Set\-ActiveSyncMailboxPolicy**  
  
    -   **Set\-CASMailbox**  
  
    -   **New\-ActiveSyncDeviceAccessRule**  
  
    -   **New\-ActiveSyncMailboxPolicy**  
  
    -   **Remove\-ActiveSyncDevice**  
  
    > [!NOTE]  
    >  以下 Exchange Server 管理角色包括这些 cmdlet：“收件人管理”、“仅限查看组织管理”和“服务器管理”。 有关 Microsoft Exchange Server 2010 中的管理角色组的详细信息，请参阅[了解管理角色组](http://go.microsoft.com/fwlink/p/?LinkId=212914)。  
  
    > [!TIP]  
    >  如果你尝试在没有所需 cmdlet 的情况下安装或使用 Exchange Server 连接器，你将在站点服务器计算机上 EasDisc.log 文件中看到随 `Invoking cmdlet <cmdlet> failed` 消息一起记录的错误。  
  
2.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“管理”。  
  
3.  在“管理”工作区中，展开“层次结构配置”，然后单击“Exchange Server 连接器”。  
  
4.  在“主页”选项卡上的“创建”组中，单击“添加 Exchange Server”。  
  
5.  完成“添加 Exchange Server 向导”：  
  
    -   如果使用 Exchange Server 的本地实例并指定客户端访问服务器，你可以为每个 Active Directory 站点指定单一服务器或客户端访问服务器阵列。 如果服务器或阵列脱机，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将尝试发现要使用的客户端访问服务器。 如果该操作失败，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将回退，使用邮箱服务器来建立与客户端访问服务器的连接。 在站点服务器计算机上的 EasDisc.log 文件中，重试操作记录为警告。 例如，搜索 `Failed to open runspace for site <site_name>`。  
  
    -   对于 Exchange Server 连接器帐户，指定你在步骤 1 中配置的帐户。  
  
    -   如果还要使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 来注册移动设备，启用选项“外部移动设备管理”以确保这些移动设备在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 注册它们后继续从 Exchange 接收电子邮件。  
  
    -   在向导的“帐户”页上，可以配置用于将电子邮件通知发送到被 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 条件访问阻止的客户端的帐户。 指定的帐户必须在 Exchange 服务器上具有一个有效邮箱。  
  
         有关详细信息，请参阅[在 System Center Configuration Manager 中管理对服务的访问](../LocTest/Manage-access-to-services-in-System-Center-Configuration-Manager.md)。  
  
6.  你可以通过使用状态消息和查看日志文件来验证 Exchange Server 连接器的安装：  
  
    -   要确认站点组件管理器已成功安装了 Exchange Server 连接器，请查找“SMS\_EXCHANGE\_CONNECTOR”组件的状态 ID“1015”。 举例来说，如果 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 由于指定的客户端访问服务器计算机脱机而无法成功安装连接器，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将每 60 分钟重试一次安装，直至安装成功或者你删除 Exchange Server 连接器为止。  
  
    -   在站点服务器计算机上，搜索 SiteComp.log 文件，然后在该日志文件中搜索 `Component SMS_EXCHANGE_CONNECTOR flagged for installation`。 随后会以下列文本记录安装成功：`STATMSG: ID=1015`。  
  
## 请参阅  
 [使用 System Center Configuration Manager 管理计算机和设备](../LocTest/Manage-computers-and-devices-with-System-Center-Configuration-Manager.md)
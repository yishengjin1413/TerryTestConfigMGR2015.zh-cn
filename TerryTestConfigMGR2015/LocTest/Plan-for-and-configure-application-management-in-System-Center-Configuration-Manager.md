---
title: "规划和配置 System Center Configuration Manager 中的应用程序管理"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-app
ms.tgt_pltfrm: na
ms.topic: get-started-article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 2be84a1d-ebb9-47ae-8982-c66d5b92a52a
caps.latest.revision: 13
caps.handback.revision: 13
author: barlanmsft
---
# 规划和配置 System Center Configuration Manager 中的应用程序管理
使用本主题中的信息来帮助你实现部署 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]中的应用程序所必需的先决条件。  
  
## 一般先决条件  
 本部分列出在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]中进行应用程序管理的先决条件。 这些先决条件分为两类，即外部依赖关系和 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]中的依赖关系。  
  
### Configuration Manager 的外部依赖关系  
 下表列出了应用程序管理的外部依赖关系。  
  
|先决条件|更多信息|  
|------------------|----------------------|  
|在运行应用程序目录网站点、应用程序目录 Web 服务点、管理点和分发点的站点系统服务器上，需要安装 Internet Information Services (IIS)。|有关此要求的详细信息，请参阅 [Supported configurations for System Center Configuration Manager](../LocTest/Supported-configurations-for-System-Center-Configuration-Manager.md)。|  
|对于 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]注册的移动设备：|在对应用程序进行代码签名以便将其部署到移动设备时，如果使用版本 3 模板（**Windows Server 2008，Enterprise Edition**）生成了证书，请勿使用此证书。 此证书模板创建的证书与用于移动设备的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 应用程序不兼容。<br /><br /> 如果使用 Active Directory 证书服务对移动设备应用程序进行代码签名，请勿使用版本 3 证书模板。|  
|如果想自动创建用户设备相关性，必须将客户端配置为审核登录事件。|[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将从客户端计算机上的本地安全策略中读取以下两个设置，以确定自动创建的用户设备相关性：<br /><br /> **审核帐户登录事件**<br /><br /> **审核登录事件**<br /><br /> 若要自动在用户和设备之间创建关系，请确保在客户端计算机上启用这两个设置。 可以使用 Windows 组策略来配置这两个设置。|  
  
### Configuration Manager 依赖关系  
 下表列出了 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中与应用程序管理相关的依赖关系。  
  
|先决条件|更多信息|  
|------------------|----------------------|  
|管理点|客户端将与管理点联系，以下载客户端策略、查找内容和连接到应用程序目录。<br /><br /> 如果客户端无法访问管理点，则无法使用应用程序目录。|  
|分发点|在可以将应用程序部署到客户端之前，层次结构中必须有至少一个分发点。 默认情况下，站点服务器在标准安装时启用分发点站点角色。 分发点的数量和位置将因企业的特定要求而异。<br /><br /> 有关如何安装分发点和管理内容的详细信息，请参阅[为 System Center Configuration Manager 管理内容和内容基础结构](../LocTest/Manage-content-and-content-infrastructure-for-System-Center-Configuration-Manager.md)。|  
|客户端设置|在客户端上安装应用程序的方式和最终用户在客户端上的体验由许多客户端设置来控制。 这些客户端设置包括：<br /><br /> - 计算机代理<br /><br /> - 计算机重启<br /><br /> - 软件部署<br /><br /> - 用户和设备相关性<br /><br /> 有关这些客户端设置的详细信息，请参阅 [About client settings in System Center Configuration Manager](../LocTest/About-client-settings-in-System-Center-Configuration-Manager.md)。<br /><br /> 有关如何配置客户端设置的信息，请参阅 [How to configure client settings in System Center Configuration Manager](../LocTest/How-to-configure-client-settings-in-System-Center-Configuration-Manager.md)。|  
|对于应用程序目录：<br /><br /> 发现的用户帐户|用户必须先被 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 发现，然后才能查看和请求应用程序目录中的应用程序。 有关详细信息，请参阅 [Configure Active Directory Discovery for Computers, Users, or Groups](../LocTest/Run-discovery-for-System-Center-Configuration-Manager.md#BKMK_ConfigADDiscGeneral) 主题中的 [Run discovery for System Center Configuration Manager](../LocTest/Run-discovery-for-System-Center-Configuration-Manager.md) 部分。|  
|必须安装 APP-V 4.6 SP1 或更高版本的客户端才能运行虚拟应用程序|为了能够在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]中成功创建虚拟应用程序，客户端计算机必须安装 App-V 4.6 SP1 或更高版本的客户端。<br /><br /> 还必须使用在知识库 [文章 2645225](http://go.microsoft.com/fwlink/p/?LinkId=237322) 中描述的修补程序来更新 App-V 客户端，才能成功部署虚拟应用程序。|  
|应用程序目录 Web 服务点|应用程序目录 Web 服务点是站点系统角色，它向应用程序目录网站提供有关软件库中可用的软件的信息。<br /><br /> 有关如何配置此站点系统角色的信息，请参阅本主题中的[配置软件中心和应用程序目录（仅适用于 Windows 电脑）](#BKMK_SWC)。|  
|应用程序目录网站点|应用程序目录网站点是站点系统角色，它向用户提供可用软件的列表。<br /><br /> 有关如何配置此站点系统角色的信息，请参阅本主题中的[配置软件中心和应用程序目录（仅适用于 Windows 电脑）](#BKMK_SWC)。|  
|Reporting Services 点|为了能够使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的报表进行应用程序管理，必须首先安装和配置 Reporting Services 点。<br /><br /> 有关详细信息，请参阅 [System Center Configuration Manager 中的报表](../LocTest/Reporting-in-System-Center-Configuration-Manager.md)。|  
|应用程序管理的安全权限|必须具有以下安全权限才能管理应用程序。<br /><br />  “应用程序作者”安全角色包含前面列出的在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]中创建、修改和停用应用程序所需的权限。<br /><br /> **若要部署应用程序，请执行以下操作：**<br /><br />  “应用程序部署管理员”安全角色包含前面列出的在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]中部署应用程序所需的权限。<br /><br /> “应用程序管理员”  安全角色包含“应用程序作者”  和“应用程序部署管理员”  安全角色中的所有权限。<br /><br /> 有关详细信息，请参阅  [Configure role-based administration for System Center Configuration Manager](../LocTest/Configure-role-based-administration-for-System-Center-Configuration-Manager.md)。|  
  
##  <a name="BKMK_SWC"></a> 配置软件中心和应用程序目录（仅适用于 Windows PC）  
 本部分描述在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]中配置应用程序目录和软件中心的步骤。  
  
### 简介  
 在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]中，对于用户如何更改设置、浏览和安装应用程序，你现在有两个选项：  
  
-   **新的软件中心** - 新的软件中心具有富有现代感的全新外观，并且本应仅出现在依赖于 Silverlight 的应用程序目录中的应用（用户可用的应用）现在将出现在“应用程序”  选项卡下的软件中心。 应用程序目录仍然可以使用软件中心的“安装状态”  选项卡下的链接进行访问。  
  
     你可以通过启用客户端设置“计算机代理” **计算机代理** > **使用新的软件中心**。  
  
    > [!IMPORTANT]  
    >  虽然最终用户不再需要连接到应用程序目录，但你仍必须配置应用程序目录网站点和应用程序目录 Web 服务点，详情如下。  
  
-   **以前的软件中心和应用程序目录** - 默认情况下，用户会继续连接到以前版本的软件中心并连接到应用程序目录（需要 Silverlight 启用的 Web 浏览器）来浏览可用的应用程序。  
  
 无论你选择使用哪个版本，当你在 Windows PC 上安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端时，都会自动安装软件中心。  
  
> [!TIP]  
>  用户看到的软件中心的版本取决于 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端设置。 这样使得你能根据你部署到集合的自定义客户端设置，灵活地控制使用哪个版本。  
  
### 安装和配置应用程序目录及软件中心的步骤  
 使用下表来了解有关步骤、详情以及有关安装和配置应用程序目录及软件中心来支持应用程序管理的详细信息。  
  
> [!IMPORTANT]  
>  在你执行这些步骤之前，请确保已满足上面的所有先决条件。  
  
|步骤|详细信息|更多信息|  
|-----------|-------------|----------------------|  
|**步骤 1：** 如果你将使用 HTTPS 连接，请确保已将 Web 服务器证书部署到站点系统服务器。|将 Web 服务器证书部署到将运行应用程序目录网站点和应用程序目录 Web 服务点的站点系统服务器。<br /><br /> 此外，如果你希望客户端从 Internet 中访问应用程序目录，请将 Web 服务器证书部署到至少一个管理点站点系统服务器，并针对来自 Internet 的客户端连接对其进行配置。|有关证书要求的信息，请参阅 [System Center Configuration Manager 的 PKI 证书要求](../LocTest/PKI-certificate-requirements-for-System-Center-Configuration-Manager.md)。|  
|**步骤 2：** 如果你将使用客户端 PKI 证书连接到管理点，请将客户端身份验证证书部署到客户端计算机。|尽管客户端不必使用客户端 PKI 证书来连接到应用程序目录，但它们必须连接到管理点，然后才能使用应用程序目录。 在以下情况下，你必须将客户端身份验证证书部署到客户端计算机：<br /><br /> - Intranet 中的所有管理点只接受 HTTPS 客户端连接。<br /><br /> - 客户端将从 Internet 连接到应用程序目录。|有关证书要求的信息，请参阅 [System Center Configuration Manager 的 PKI 证书要求](../LocTest/PKI-certificate-requirements-for-System-Center-Configuration-Manager.md)。|  
|**步骤 3：** 安装和配置应用程序目录 Web 服务点和应用程序目录网站。|你必须将这些站点系统角色安装在同一站点中。 你不必将它们安装在同一站点系统服务器上或安装在同一 Active Directory 林中。 但是，应用程序目录 Web 服务点必须位于站点数据库所在的林中。|有关站点系统角色布局的详细信息，请参阅[为 System Center Configuration Manager 规划站点系统服务器和站点系统角色](../LocTest/Plan-for-site-system-servers-and-site-system-roles-for-System-Center-Configuration-Manager.md)。<br /><br /> 要配置应用程序目录 Web 服务点和应用程序目录网站点，请参阅本主题中的以下过程： [步骤 3：安装和配置应用程序目录站点系统角色](#BKMK_HowtoInstallApplicationCatalogSiteSystems)。|  
|**步骤 4：** 为应用程序目录和软件中心配置客户端设置。|如果希望所有用户具有相同设置，请配置默认客户端设置。 否则，请为特定集合配置自定义客户端设置。|有关客户端设置的详细信息，请参阅 [About client settings in System Center Configuration Manager](../LocTest/About-client-settings-in-System-Center-Configuration-Manager.md)。<br /><br /> 有关如何配置这些客户端设置的信息，请参阅本主题中的以下过程： [步骤 4：为应用程序目录和软件中心配置客户端设置](#BKMK_ConfigureClientSettingApplicationCatalog)。|  
|**步骤 5：** 验证应用程序目录是否可正常运行。|你可以从浏览器或软件中心中直接访问应用程序目录。|请参阅本主题中的以下过程：[步骤 5：验证应用程序目录是否可正常运行](#BKMK_VerifyingApplicationCatalog)。|  
  
### 用于安装和配置应用程序目录和软件中心的补充过程  
 如果上表中的步骤需要执行补充过程，请使用以下信息。  
  
####  <a name="BKMK_HowtoInstallApplicationCatalogSiteSystems"></a> 步骤 3：安装和配置应用程序目录站点系统角色  
 这些过程为应用程序目录配置站点系统角色。 根据你是要安装新的站点系统服务器还是使用现有站点系统服务器，选择这些过程之一：  
  
-   [安装和配置应用程序目录站点系统：新建站点系统服务器](#BKMK_HowtoInstallApplicationCatalogSiteSystems_new)  
  
-   [安装和配置应用程序目录站点系统：现有站点系统服务器](#BKMK_HowtoInstallApplicationCatalogSiteSystems_existing)  
  
> [!NOTE]  
>  应用程序目录不能安装在辅助站点或管理中心站点上。  
  
#####  <a name="BKMK_HowtoInstallApplicationCatalogSiteSystems_new"></a> 安装和配置应用程序目录站点系统：新建站点系统服务器  
  
1.  在 Configuration Manager 控制台中，单击“管理” 。  
  
2.  在“管理”  工作区中，展开“站点配置” ，并单击“服务器和站点系统角色” 。  
  
3.  在“主页”  选项卡上的“创建”  组中，单击“创建站点系统服务器” 。  
  
4.  在“常规”  页上，指定站点系统的常规设置，然后单击“下一步” 。  
  
    > [!TIP]  
    >  如果希望客户端计算机通过 Internet 访问应用程序目录，请指定 Internet 完全限定的域名 (FQDN)。  
  
5.  在“系统角色选择”  页上，从可用角色列表中选择“应用程序目录 Web 服务点”  和“应用程序目录网站点”  ，然后单击“下一步” 。  
  
6.  完成向导。  
  
#####  <a name="BKMK_HowtoInstallApplicationCatalogSiteSystems_existing"></a> 安装和配置应用程序目录站点系统：现有站点系统服务器  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“管理” 。  
  
2.  在“管理”  工作区中，展开“站点配置” ，选择“服务器和站点系统角色” ，然后选择要用于应用程序目录的服务器。  
  
3.  在“主页”  选项卡上的“创建”  组中，单击“添加站点系统角色” 。  
  
4.  在“常规”  页上，指定站点系统的常规设置，然后单击“下一步” 。  
  
    > [!TIP]  
    >  如果希望客户端计算机通过 Internet 访问应用程序目录，请指定 Internet 完全限定的域名 (FQDN)。  
  
5.  在“系统角色选择”  页上，从可用角色列表中选择“应用程序目录 Web 服务点”  和“应用程序目录网站点”  ，然后单击“下一步” 。  
  
6.  完成向导。  
  
 通过使用状态消息和查看日志文件来验证这些站点系统角色的安装：  
  
1.  状态消息：使用组件“SMS_PORTALWEB_CONTROL_MANAGER”  和“SMS_AWEBSVC_CONTROL_MANAGER” 。  
  
     例如，“SMS_PORTALWEB_CONTROL_MANAGER”  的状态 ID“1015”  确认站点组件管理器已成功安装在应用程序目录网站点上。  
  
2.  日志文件：搜索 **SMSAWEBSVCSetup.log** 和 **SMSPORTALWEBSetup.log**。  
  
     要查看更详细的信息，请搜索日志文件 **awebsvcMSI.log** 和 **portlwebMSI.log**。  
  
####  <a name="BKMK_ConfigureClientSettingApplicationCatalog"></a> 步骤 4：为应用程序目录和软件中心配置客户端设置  
 此过程为应用程序目录和软件中心配置将适用于层次结构中的所有设备的默认客户端设置。 如果你希望这些设置仅适用于某些设备，则可以创建自定义客户端设置并将其部署到一个集合，该集合包含将具有特定设置的设备。 有关如何创建自定义设备设置的详细信息，请参阅 [How to Create and Deploy Custom Client Settings](../LocTest/How-to-configure-client-settings-in-System-Center-Configuration-Manager.md#BKMK_CustomClientSettings) 主题中的 [How to configure client settings in System Center Configuration Manager](../LocTest/How-to-configure-client-settings-in-System-Center-Configuration-Manager.md) 部分。  
  
###### 为应用程序目录和软件中心配置默认客户端设置  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“管理” 。  
  
2.  在“管理”工作区中，单击“客户端设置” > “默认客户端设置”。  
  
3.  在“主页”  选项卡上的“属性”  组中，单击“属性” 。  
  
4.  查看并配置与用户通知、应用程序目录和软件中心相关的设置。 例如：  
  
    1.  “计算机代理” 组：  
  
        -   **默认应用程序目录网站点**  
  
        -   **向 Internet Explorer 受信任的站点区域添加默认应用程序目录网站**  
  
        -   **软件中心中显示的组织名称**  
  
            > [!TIP]  
            >  要指定显示在应用程序目录中的组织名称并配置网站主题，请使用应用程序目录网站属性上的“自定义”  选项卡。  
  
        -   **使用新的软件中心** - 新的软件中心允许最终用户浏览和安装可用的应用而无需访问应用程序目录（需要 Silverlight 启用的 Web 浏览器），如果你要使用新的软件中心，请设置为“是”  。  
  
        -   **安装权限**  
  
        -   **显示关于新部署的通知**  
  
    2.  “电源管理” 组：  
  
        -   **允许用户从电源管理中排除其设备**  
  
    3.  “远程工具” 组：  
  
        -   **用户可以在软件中心内更改策略或通知设置**  
  
    4.  “用户和设备相关性” 组：  
  
        -   **允许用户定义其主要设备**  
  
    > [!NOTE]  
    >  有关客户端设置的详细信息，请参阅 [About client settings in System Center Configuration Manager](../LocTest/About-client-settings-in-System-Center-Configuration-Manager.md)。  
  
5.  单击“确定”  以关闭“默认客户端设置”  对话框。  
  
 当客户端计算机下一次下载客户端策略时，将使用这些设置对它们进行配置。 要为单个客户端启动策略检索，请参阅 [How to manage clients in System Center Configuration Manager](../LocTest/How-to-manage-clients-in-System-Center-Configuration-Manager.md)。  
  
####  <a name="BKMK_VerifyingApplicationCatalog"></a> 步骤 5：验证应用程序目录是否可正常运行  
 使用以下过程来验证应用程序目录是否可正常运行。 你可以从浏览器或软件中心中直接访问应用程序目录。  
  
> [!NOTE]  
>  应用程序目录需要 Microsoft Silverlight，后者将为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端先决条件自动安装。 如果通过使用未安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端的计算机从浏览器中直接访问应用程序目录，请首先验证计算机上是否安装了 Microsoft Silverlight。  
  
> [!TIP]  
>  应用程序目录在安装后无法正常运行的大多数典型原因都是未满足先决条件。 确认应用程序目录站点系统角色的站点系统角色先决条件。 可以通过使用 [Supported configurations for System Center Configuration Manager](../LocTest/Supported-configurations-for-System-Center-Configuration-Manager.md) 主题来实现此目的。  
  
> [!NOTE]  
>  如果使用域管理员帐户登录，将不会显示来自于 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端的通知消息（如指示新软件可用的消息）。  
  
###### 从浏览器中直接访问应用程序目录  
  
-   在浏览器中，键入应用程序目录网站的地址，并确认网页显示，其中包含三个选项卡：“应用程序目录” 、“我的应用程序请求” 和“我的设备” 。  
  
     为应用程序目录选用以下适当地址，其中 <server\> 是计算机名、Intranet FQDN 或 Internet FQDN：  
  
    -   HTTPS 客户端连接和默认站点系统角色设置：**https://<server\>/CMApplicationCatalog**  
  
    -   HTTP 客户端连接和默认站点系统角色设置：**http://<server\>/CMApplicationCatalog**  
  
    -   HTTPS 客户端连接和自定义站点系统角色设置：**https://<server\>:<port\>/<web application name\>**  
  
    -   HTTP 客户端连接和自定义站点系统角色设置：**http://<server\>:<port\>/<web application name\>**  
  
###### 若要从软件中心（不适用于新版本软件中心）访问应用程序目录  
  
1.  在客户端计算机上，单击 **开始** > **所有程序** > **Microsoft System Center 2012** > **Configuration Manager** > **软件中心**。  
  
2.  如果之前为软件中心配置了组织名称作为客户端设置，请确认此名称按指定方式显示。  
  
3.  单击“从应用程序目录中查找其他应用程序”  ，并确认页面显示，其中包含三个选项卡：“应用程序目录” 、“我的应用程序请求” 和“我的设备” 。  
  
> [!WARNING]  
>  安装了应用程序目录站点系统角色后，你将不会在从软件中心中单击“从应用程序目录中查找其他应用程序”  链接时立即看到应用程序目录。 在客户端下一次下载其客户端策略后，或在安装了应用程序目录站点系统角色后最多 25 个小时内，将可以从软件中心中使用应用程序目录。  
  
## 另请参阅  
 [使用 System Center Configuration Manager 部署并管理应用程序](../LocTest/Deploy-and-manage-applications-with-System-Center-Configuration-Manager.md)
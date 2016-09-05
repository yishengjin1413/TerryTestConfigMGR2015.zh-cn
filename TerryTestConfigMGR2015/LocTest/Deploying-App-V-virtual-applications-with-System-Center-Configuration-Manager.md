---
title: "使用 System Center Configuration Manager 部署 App-V 虚拟应用程序"
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
ms.assetid: ddcad9f2-a542-4079-83ca-007d7cb44995
caps.latest.revision: 11
caps.handback.revision: 8
author: barlanmsft
---
# 使用 System Center Configuration Manager 部署 App-V 虚拟应用程序
除了创建应用程序的其他 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 要求和过程，创建和部署虚拟应用程序时还必须考虑以下注意事项。  
  
 使用下列部分中的信息帮助你规划 App\-V 环境与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的集成。  
  
-   [一般注意事项](#BKMK_General)  
  
-   [受支持的 App-V 版本](#BKMK_Supp)  
  
-   [管理 APP-V 虚拟应用程序的步骤](#BKMK_Steps)  
  
-   [Configuration Manager 虚拟应用程序传递方法](#BKMK_Delivery)  
  
-   [从 APP-V 基础结构迁移到 Configuration Manager 和 App-V 基础结构](#BKMK_Migrate)  
  
-   [将 App-V 5 连接组迁移到 Configuration Manager 虚拟环境](#BKMK_Connection)  
  
-   [App-V 4.6 中的动态套件合成](#BKMK_DSC)  
  
-   [将 App-V 4.6 应用程序转换为 App-V 5 应用程序](#BKMK_Convert)  
  
-   [用户和部署配置文件](#BKMK_Config)  
  
-   [App-V 本地交互](#BKMK_Interact)  
  
-   [App-V 5 共享内容存储](#BKMK_SCS)  
  
-   [监视虚拟应用程序](#BKMK_Monitor)  
  
##  <a name="BKMK_General"></a> 一般注意事项  
 你可以使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 以应用程序中的部署类型形式安装和管理虚拟应用程序。 进行此操作时，需要考虑下列注意事项：  
  
 使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 管理虚拟应用程序时，可以获得以下好处：  
  
-   使用单一管理基础结构  
  
-   可伸缩性、部署和内容分发功能，如集合和用户设备相关性  
  
-   利用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 提供的高级应用程序管理功能  
  
-   使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 功能（如操作系统部署、软件和硬件清单、软件计数和资产智能）来支持虚拟应用程序  
  
 有关如何使用 App\-V 创建和序列化应用程序的详细信息，请参阅 TechNet 库中的[应用程序虚拟化](https://technet.microsoft.com/library/cc843848.aspx)。  
  
 为了向计算机部署虚拟应用程序，必须在计算机上安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端和 App\-V Client。 客户端设备可以包括台式机和便携计算机以及虚拟桌面基础结构 \(VDI\) 客户端。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 和 App\-V Client 软件共同提供、查找和启动虚拟应用程序包。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端管理如何向 App\-V Client 传递虚拟应用程序包。 App\-V Client 在客户端上运行虚拟应用程序。  
  
-   若要部署虚拟应用程序，必须首先使用 App\-V Application Virtualization Sequencer 创建虚拟应用程序。 Sequencer 监视应用程序的安装和设置过程，并记录应用程序在虚拟环境中运行所需的信息。 你也可以使用 Sequencer 配置适用于所有用户的文件和配置，以及用户可以自定义的配置。  
  
-   对应用程序进行序列化时，必须将包保存到 Configuration Manager 可以访问的位置。 然后，你可以创建包含此虚拟应用程序的应用程序部署。  
  
-   [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不支持使用 App\-V 的共享只读缓存功能。  
  
-   [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 支持 App\-V 5 中的共享内容存储功能。  
  
-   为虚拟应用程序创建部署类型时，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 使用应用程序清单文件的内容创建部署类型。 这是一个 XML 文件，其中包含有关虚拟应用程序的信息。 此外，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 根据 App\-V .osd 文件内容创建部署类型的要求，此文件包含有关虚拟应用程序的支持操作系统的信息。  
  
-   若要在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中部署虚拟应用程序，客户端计算机必须安装有不低于 App\-V 4.6 SP1 的或更高版本的客户端。  
  
-   此外，还必须使用在知识库文章 [2645225](https://support.microsoft.com/kb/2645225) 中描述的修补程序来更新 App\-V 客户端，才能成功部署虚拟应用程序。  
  
-   使用 Microsoft Application Virtualization 5.0 中的连接组时，部署的虚拟应用程序可以在客户端计算机上共享相同的文件系统和注册表。 与标准虚拟应用程序不同，这些应用程序可以与另一个应用程序共享数据。 此外，连接组将保留它们所包含的应用程序的用户设置。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的 App\-V 虚拟环境用于在客户端计算机上配置连接组。 在安装应用程序时，或者在客户端接下来评估已安装的应用程序时，会在客户端计算机上创建或更改虚拟环境。 可以对这些应用程序排列优先级，以便在多个应用程序尝试更改一个文件系统或注册表值时，优先级最高的应用程序优先进行修改。 有关详细信息，请参阅 [如何在 System Center Configuration Manager 中创建 App\-V 虚拟环境](../LocTest/How-to-create-App-V-virtual-environments-in-System-Center-Configuration-Manager.md)。  
  
##  <a name="BKMK_Supp"></a> 受支持的 App\-V 版本  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 支持以下版本的 App\-V：  
  
-   **App\-V 4.6：**要在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中使用虚拟应用程序，客户端计算机必须安装 App\-V 4.6 SP1、App\-V 4.6 SP2 或 App\-V 4.6 SP3 客户端。  
  
     还必须使用在知识库文章 [2645225](http://go.microsoft.com/fwlink/p/?LinkId=237322) 中描述的修补程序来更新 App\-V 4.6 SP1 客户端，才能成功部署虚拟应用程序。  
  
-   **App\-V 5、App\-V 5.0 SP1、App\-V 5.0 SP2、App\-V 5.0 SP3 和 App\-V 5.1：**对于 App\-V 5.0 SP2，必须安装[修补程序包 5](https://support.microsoft.com/en-us/kb/2963211) 或使用 APP\-V 5.0 SP3。  
  
##  <a name="BKMK_Steps"></a> 管理 APP\-V 虚拟应用程序的步骤  
 若要管理 APP\-V 虚拟应用程序，请完成以下步骤：  
  
-   **序列化** \- 序列化是使用 App\-V Sequencer 将应用程序转换为虚拟应用程序的过程。  
  
-   **创建 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 应用程序** – 使用创建部署类型向导将序列化的应用程序导入到以后可以添加到应用程序中的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 部署类型。 你也可以创建允许多个虚拟应用程序共享设置的虚拟环境。  
  
-   **分发** – 分发是在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 分发点上提供 App\-V 应用程序的过程。  
  
-   **部署** – 部署是在客户端计算机上提供应用程序的过程。 这在 APP\-V 完整基础结构中称为流式处理。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 提供以下两个选项用于部署虚拟应用程序：“流式处理”和“下载并执行”。  
  
##  <a name="BKMK_Delivery"></a> Configuration Manager 虚拟应用程序传递方法  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 支持以下两种方法来向客户端传递虚拟应用程序：流式传递和本地传递（下载和执行）：  
  
-   **流式传递**  
  
     使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 管理 App\-V 客户端时，它支持通过来自分发点的 HTTP 或 HTTPS 对虚拟应用程序进行流式处理。 默认情况下能够通过 HTTP 或 HTTPS 进行流式处理，并且在分发点属性对话框中配置了此流式处理。 如果你将虚拟应用程序部署到客户端计算机，并且用户运行虚拟应用程序，则 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端将与管理点联系以确定要使用的分发点；然后，从分发点对应用程序进行流式处理。  
  
-   **本地传递（下载并执行）**  
  
     如果使用此传递方法，则 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端首先会将整个虚拟应用程序包下载到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端缓存，然后指示 App\-V Client 将 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 缓存中的应用程序流式处理到 App\-V 缓存中。 如果将虚拟应用程序部署到客户端计算机，并且其内容不在 App\-V 缓存中，则 App\-V Client 会将 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端缓存中的应用程序内容流式处理到 App\-V 缓存中，然后运行该应用程序。 成功运行应用程序之后，你可以将 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端配置为在下一个删除周期中删除任何较旧版本的包，或者将其保留在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端缓存中。  
  
 在决定要使用的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 虚拟应用程序传递方法时，请通过使用本地传递，将流式处理传递的减少的磁盘空间要求与 App\-V 应用程序的保证可用性进行比较。 本地传递所需的增加的客户端磁盘空间可能对流式传输更好，以便用户始终能够从任何位置获取应用程序。  
  
 使用下表中的信息来帮助你选择最佳的传递方法。  
  
|传递方法|优点|缺点|  
|----------|--------|--------|  
|流式传递|此方法使用标准的网络协议对分发点中的包内容进行流式处理。<br /><br /> 虚拟应用程序的程序快捷方式调用至分发点的连接，因此可在需要时进行虚拟应用程序传递。<br /><br /> 此方法非常适合采用高带宽连接到分发点的客户端。<br /><br /> 当客户端收到通知它们当前版本已被取代的策略，并且客户端仅下载上一个版本中的更改时，可以获得在整个企业中分发的已更新虚拟应用程序。<br /><br /> 访问权限是在分发点上定义的，用于防止用户访问未授权的应用程序或包。|在用户首次运行应用程序之前，未对虚拟应用程序进行流式处理。 在此情况下，用户可能会收到虚拟应用程序的程序快捷方式，然后在首次运行虚拟应用程序之前从网络中断开。 如果用户在客户端处于脱机状态时尝试运行虚拟应用程序，则用户将看到一个错误，并且将无法运行虚拟化应用程序，因为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 分发点无法用于对应用程序进行流式处理。 在用户重新连接到网络并运行应用程序之前，应用程序将不可用。<br /><br /> 为了避免这种情况，你可以使用本地传递方法以向客户端传递虚拟应用程序，或者可以启用基于 Internet 的客户端管理以对传递进行流式传递。|  
|本地传递|标准分发点功能用于通过后台智能传输服务 \(BITS\) 下载包。<br /><br /> 虚拟应用程序包内容在本地传递至客户端，这意味着用户可以在其计算机未连接到网络时运行这些内容。<br /><br /> 此方法适合慢速或不可靠网络连接，以及仅偶尔连接到网络的计算机。<br /><br /> [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 使用远程差分压缩 \(RDC\) 仅将更新虚拟应用程序包内容时更改的文件内字节发送给客户端。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端使用 RDC 根据包的当前版本以及发送给客户端的任何更改来生成虚拟应用程序包的新版本。<br /><br /> 此方法为移动用户或断开连接的用户提供应用程序复原。 如果使用安装操作部署了虚拟应用程序，则管理员可以选择在传递之后在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 缓存中保留包。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端缓存中的包将用作可靠的本地流式处理源，以便 App\-V Client 将包请求到其缓存中。|在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 缓存中保留虚拟应用程序时，客户端上需要的磁盘空间最多为虚拟应用程序包大小的两倍。|  
  
 你也可以将虚拟应用程序预先安装到计算机上，然后创建该计算机的映像以部署到其他计算机。 但是，如果在其他站点创建了虚拟应用程序包，则将不使用二进制增量复制下载对应用程序所做的更新。 如果你想要立即提供应用程序，而不是在用户登录之后下载应用程序，则可以在虚拟桌面基础结构中使用此选项。  
  
##  <a name="BKMK_Migrate"></a> 从 APP\-V 基础结构迁移到 Configuration Manager 和 App\-V 基础结构  
 使用下表帮助你计划用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 从现有 App\-V 基础结构迁移到虚拟应用程序管理。  
  
|步骤|更多信息|  
|--------|----------|  
|检查当前虚拟应用程序以选择想要迁移到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 基础结构的应用程序。|无更多信息。|  
|评估将对其部署虚拟应用程序的用户和设备。|创建 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 集合以将要对其部署虚拟应用程序的用户和设备组合在一起。 有关详细信息，请参阅 [System Center Configuration Manager 中集合的技术参考](../LocTest/Collections-technical-reference-for-System-Center-Configuration-Manager.md)。|  
|将 App\-V 5 连接组迁移到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 虚拟环境。|有关详细信息，请参阅本主题中的 [将 App-V 5 连接组迁移到 Configuration Manager 虚拟环境](#BKMK_Connection) 部分。|  
|进行调查以了解 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 基础结构中是否存在作为完整应用程序的任何虚拟应用程序。|为了使管理更加轻松，你可以将虚拟应用程序作为新部署类型添加到现有完整应用程序中。 有关如何创建部署类型的详细信息，请参阅[如何使用 System Center Configuration Manager 创建应用程序](../LocTest/How-to-create-applications-with-System-Center-Configuration-Manager.md)。|  
|创建应用程序以替换现有 APP\-V 包。|有关如何创建 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 应用程序的详细信息，请参阅 [System Center Configuration Manager 中的应用程序管理入门](../LocTest/Get-started-with-application-management-in-System-Center-Configuration-Manager.md)和[如何使用 System Center Configuration Manager 创建应用程序](../LocTest/How-to-create-applications-with-System-Center-Configuration-Manager.md)。|  
|在首次部署虚拟应用程序之后，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将在客户端上开始管理虚拟应用程序。 此后，计算机上的所有 App\-V 应用程序都必须由 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 进行管理。|无更多信息。|  
|将内容分发到合适的分发点以启用应用程序本地传递。|有关详细信息，请参阅[为 System Center Configuration Manager 管理内容和内容基础结构](../LocTest/Manage-content-and-content-infrastructure-for-System-Center-Configuration-Manager.md)。|  
|将应用程序部署到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端。 **Note:**  如果使用不创建清单 XML 文件的 Sequencer 的早期版本创建了 App\-V 应用程序，则可以在较新版本的 Sequencer 中打开和保存此应用程序以创建文件。 使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 部署虚拟应用程序需要此文件。 App\-V 支持使用 Sequencer 的 SoftGrid 4.1 SP1 或 4.2 版本创建的虚拟应用程序包。 如果以前在本地安装了应用程序，则在部署应用程序虚拟版本之前必须卸载它们。|有关详细信息，请参阅 [如何使用 System Center Configuration Manager 部署应用程序](../LocTest/How-to-deploy-applications-with-System-Center-Configuration-Manager.md)。|  
|[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 不再支持使用包含虚拟应用程序的包和程序。 从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 2007 迁移到 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 时，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 会将这些包转换为应用程序。<br /><br /> [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 2007 播发将转换为以下部署类型：<br /><br /> -   迁移无播发的 APP\-V 包：使用默认部署类型设置的一个部署类型。<br />-   迁移具有一个播发的 App\-V 包：使用与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 2007 播发相同的设置的一个部署类型。<br />-   迁移具有多个播发的 APP\-V 包：适用于每个 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 2007 播发并使用该播发的设置的一个部署类型。|有关详细信息，请参阅[规划将 Configuration Manager 对象迁移到 System Center Configuration Manager](../LocTest/Planning-for-the-migration-of-Configuration-Manager-objects-to-System-Center-Configuration-Manager.md)。|  
  
##  <a name="BKMK_Connection"></a> 将 App\-V 5 连接组迁移到 Configuration Manager 虚拟环境  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的 App\-V 虚拟环境允许所部署的虚拟应用程序在客户端计算机上共享相同的文件系统和注册表。 这意味着这些应用程序可以互相共享数据（这与标准的虚拟应用程序不同）。 在安装应用程序时，或者在客户端接下来评估已安装的应用程序时，会在客户端计算机上创建或修改虚拟环境。 虚拟环境类似于独立 App\-V 5 中的连接组。  
  
 将独立 App\-V 5 中的连接组迁移到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 虚拟环境时，必须确保客户端计算机上已经存在的连接组由 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 正确管理，并且保留这些连接组中的用户环境。  
  
 使用下列过程来帮助你将 App\-V 5 连接组成功转换为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 虚拟环境。  
  
#### 将 App\-V 5 连接组转换为 Configuration Manager 虚拟环境  
  
1.  为 App\-V 中存在的所有应用程序创建 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 应用程序。  
  
2.  将这些应用程序部署到用户或设备（部署目的为“必需”）。 以用户为目标的部署必须部署到使用了 App\-V 中的应用程序的相同用户，而以计算机为目标的部署必须部署到拥有 App\-V 中的应用程序的相同计算机。  
  
3.  部署完成后，创建与在独立 APP\-V 中发布的连接组匹配的虚拟环境。 虚拟环境必须以相同的顺序包含相同的包，特别是 APP\-V 5 部署类型。  
  
     有关如何创建 App\-V 虚拟环境的信息，请参阅[如何在 System Center Configuration Manager 中创建 App\-V 虚拟环境](../LocTest/How-to-create-App-V-virtual-environments-in-System-Center-Configuration-Manager.md)。  
  
 或者，也可以从 App\-V Client 中删除所有连接组，然后再开始利用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 部署应用程序。 但是，可能会丢失用户可能已保存在 App\-V 连接组中的任何设置。  
  
##  <a name="BKMK_DSC"></a> App\-V 4.6 中的动态套件合成  
 动态套件合成是一种可将一个虚拟应用程序包定义为在另一虚拟应用程序包上具有依赖关系的功能。 运行应用程序时，App\-V Client 在同一个虚拟环境中为应用程序承载主包和依赖的包。  
  
 若要将此功能与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 一起使用，必须部署这两个包，并向 App\-V Client 注册它们。 为了确保在客户端计算机上以本地方式承载依赖的包的内容，请将应用程序部署配置为在本地传递（下载和执行）。  
  
 有关 App\-V 动态套件合成的详细信息，请参阅 App\-V 文档。  
  
##  <a name="BKMK_Convert"></a> 将 App\-V 4.6 应用程序转换为 App\-V 5 应用程序  
 APP\-V 4.6 与 APP\-V 5 间的应用程序包格式已更改。 不再支持使用 APP\-V 4.6 排序的应用程序。 但是，App\-V 5 包含一个包转换工具，可用于转换应用程序。 有关详细信息，请参见 [App\-V 5 文档](http://technet.microsoft.com/library/jj713472.aspx)。  
  
 使用下列步骤将 App\-V 4.6 应用程序转换为 App\-V 5 应用程序：  
  
1.  将 App\-V 4.6 包转换或重新序列化为 App\-V 5 格式。  
  
2.  将 App\-V 5 客户端部署到层次结构中的计算机。  
  
3.  创建包含适用于 App\-V 5 应用程序的部署类型的新应用程序，然后创建取代规则以取代 App\-V 4.6 应用程序。  
  
4.  根据需要创建虚拟环境。  
  
5.  将新的 App\-V 5 应用程序部署到计算机。  
  
##  <a name="BKMK_Config"></a> 用户和部署配置文件  
 用户和部署配置文件包含对应用程序的具体行为进行控制的设置。 通过使用这些文件，无需重新序列化应用程序就能更改应用程序的设置。  
  
 典型的 App\-V 5 应用程序可能包含下列文件：  
  
-   一个应用程序包 \(.appv\) 文件。  
  
-   一个用户配置文件。  
  
-   一个部署配置文件。  
  
 用户配置文件包含仅应用到已登录的用户的设置。 你可以编辑这些配置文件，以更改有关将部署到用户的应用程序快捷方式的信息。 还可以创建带有多种部署类型的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 应用程序，而且，每种部署类型都可以包含不同的用户配置文件，并可以使用要求规则来确保为相关的用户安装这些文件。  
  
 部署配置文件包含应用到计算机的设置（例如注册表设置）。 此文件还可以包含将应用到所有用户的用户设置。  
  
 如果要利用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 部署 App\-V 5 虚拟应用程序，则在你创建 App\-V 5 部署类型时，所有三个文件都必须位于相同的文件夹中。 如果文件夹中有多个文件，则 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将使用最新的文件。  
  
 有关详细信息，请参见 [App\-V 5 文档](http://technet.microsoft.com/library/jj713466.aspx)。  
  
##  <a name="BKMK_Interact"></a> App\-V 本地交互  
 在一些应用程序部署方案中，应用程序以本地方式安装在客户端计算机上，而另一些应用程序则作为虚拟应用程序部署到相同的客户端计算机上。 默认情况下，以本地方式安装的应用程序无法看到虚拟化的应用程序，也无法直接与它们通信。 这是 App\-V 提供的应用程序隔离功能的预期行为。 本地交互是 App\-V Client 的一项功能，你可以为每个应用程序启用此功能，以便允许以本地方式安装且在客户端计算机上运行的应用程序看到虚拟化的应用程序并与其通信。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 和 APP\-V 完全支持本地交互。  
  
 有关 App\-V 本地交互功能的详细信息，请参阅 App\-V 文档。  
  
##  <a name="BKMK_SCS"></a> App\-V 5 共享内容存储  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 支持 App\-V 5 共享内容存储功能。 有关详细信息，请参阅[规划 App\-V 5.0 共享内容存储 \(SCS\)](http://technet.microsoft.com/library/jj713431.aspx)。  
  
##  <a name="BKMK_Monitor"></a> 监视虚拟应用程序  
 使用本部分中的信息来规划如何在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中监视 App\-V 应用程序。  
  
### 虚拟应用程序报表  
 可以使用下列报表在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 环境中监视 App\-V：  
  
|报告名称|描述|  
|----------|--------|  
|APP\-V 虚拟环境结果|显示有关对于所选的集合处于指定状态的所选虚拟环境的信息（仅限 App\-V 5）。|  
|资产的 App\-V 虚拟环境结果|显示相关的信息，涉及到为指定的资产选择的虚拟环境，以及所选虚拟环境的任何部署类型（仅限 App\-V 5）。|  
|App\-V 虚拟环境状态|显示为所选的集合选择的虚拟环境的符合性信息。 此报表中的“保持”列显示特定虚拟环境中的资产，该虚拟环境是以前配置的，但已不再适用，不过现在保留它以便保存在它当中运行的应用程序中的用户设置（仅限 App\-V 5）。|  
|具有特定虚拟应用程序的计算机|显示特定计算机的摘要，这些计算机具有 Application Virtualization Management Sequencer 创建的且指定的 App\-V 快捷方式（仅限 App\-V 4.6）。|  
|具有特定虚拟应用程序包的计算机|显示安装了指定的 App\-V 应用程序包的计算机的列表（仅限 App\-V 4.6）。|  
|虚拟应用程序包的所有实例数|显示检测到的所有 App\-V 应用程序包的计数（仅限 App\-V 4.6）。|  
|虚拟应用程序的所有实例数|显示检测到的所有 App\-V 应用程序的计数（仅限 App\-V 4.6）。|  
  
### 日志文件  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 会在日志文件中记录有关虚拟应用程序部署的信息。 有关虚拟应用程序和 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 应用程序管理使用的日志文件的信息，请参阅 [System Center Configuration Manager 中的日志文件](../LocTest/Log-files-in-System-Center-Configuration-Manager.md)。  
  
 此外，还可以在下列位置找到 App\-V 客户端的日志：  
  
-   Windows Vista、Windows 7 和 Windows 8：**C:\\ProgramData\\Microsoft\\Application Virtualization Client**  
  
## 请参阅  
 [使用 System Center Configuration Manager 创建和部署应用程序](../LocTest/Create-and-deploy-an-application-with-System-Center-Configuration-Manager.md)
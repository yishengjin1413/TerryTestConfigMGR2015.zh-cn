---
title: "如何在 System Center Configuration Manager 中管理客户端"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-client
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 3986a992-c175-4b6f-922e-fc561e3d7cb7
caps.latest.revision: 17
caps.handback.revision: 17
---
# 如何在 System Center Configuration Manager 中管理客户端
安装了 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 客户端并将其成功分配到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点后，你将在“资产和符合性”  工作区的“设备”  节点中看到设备，并在“设备集合”  节点中看到一个或多个集合。 在选择设备或包含设备的集合时，你可以选择各种管理操作。 但是，也可以使用其他方式来管理客户端，其中可能涉及控制台中的其他工作区或不使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台的任务。  
  
 使用本主题获取有关可以从“资产和符合性” [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]**工作区管理** 客户端的任务的概述信息，以及有关其他任务的详细信息来帮助你管理 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端。 有关如何配置客户端的信息，请参阅[如何在 System Center Configuration Manager 中配置客户端设置](../LocTest/How-to-configure-client-settings-in-System-Center-Configuration-Manager.md)  
  
> [!NOTE]  
>  [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端可能已安装，但未显示在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中。 如果尚未将客户端成功分配到站点，或者必须刷新控制台或集合成员身份已更新，则可能发生此情况。  
>   
>  此外，在未安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端时，设备也可能显示在控制台中。 如果发现了设备，但未安装和分配 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端，则可能发生此情况。 通过使用 Exchange Server 连接器管理的移动设备不会安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端。 此外，通过 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 注册的设备也不会安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端。  
>   
>  使用 **控制台中的“客户端”**[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 列来确定是否安装了 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端，以便可以从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台对其进行管理。  
  
-   [通过“设备”节点管理客户端](#BKMK_ManagingClients_DevicesNode)  
  
-   [通过“设备集合”节点管理客户端](#BKMK_ManagingClients_DeviceCollectionsNode)  
  
-   [为 Configuration Manager 客户端配置客户端缓存](#BKMK_ClientCache)  
  
-   [卸载 Configuration Manager 客户端](#BKMK_UninstalClient)  
  
-   [为 Configuration Manager 客户端管理冲突的记录](#BKMK_ConflictingRecords)  
  
-   [为 Configuration Manager 客户端启动策略检索](#BKMK_PolicyRetrieval)  
  
##  <a name="BKMK_ManagingClients_DevicesNode"></a> 通过“设备”节点管理客户端  
 使用下列过程和下表，以便通过“资产和符合性”  工作区中的“设备”  节点管理一台或多台设备。  
  
> [!IMPORTANT]  
>  根据设备类型，其中某些选项可能不可用。  
  
#### 通过“设备”节点管理客户端  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性” 。  
  
2.  在“资产和符合性”  工作区中，单击“设备” 。  
  
3.  选择一台或多台设备，然后从功能区中或通过右键单击设备选择下列客户端管理任务之一：  
  
    -   **管理用户设备相关性信息**  
  
         允许你在用户和设备之间配置关联，从而使你能够高效地将软件部署到用户。  
  
         请参阅[在 System Center Configuration Manager 中将用户和设备与用户设备相关性相链接](../LocTest/Link-users-and-devices-with-user-device-affinity-in-System-Center-Configuration-Manager.md)  
  
    -   **将设备添加到新集合或现有集合**  
  
         使用这些与集合相关的操作通过直接规则将所选设备快速添加到集合。  
  
         [System Center Configuration Manager 中集合的操作和维护](../LocTest/Operations-and-maintenance-for-collections-in-System-Center-Configuration-Manager.md)  
  
    -   **通过使用客户端请求向导来安装和重新安装客户端**  
  
         客户端请求向导提供一种高效方式，用于安装和重新安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端，以便对其进行修复，或使用站点配置选项以及你为客户端请求安装指定的任何其他 client.msi 属性在运行 Windows 的计算机上对其进行重新配置。  
  
        > [!TIP]  
        >  可通过多种不同的方式来安装（和重新安装） [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端。 尽管客户端请求向导提供一种方便的客户端安装方法（因为你可从控制台中运行它），但这种客户端安装方法有许多依赖关系，并且不适合于所有环境。 如果无法通过使用客户端请求来成功安装客户端，你还可以使用许多其他客户端安装方法。 有关依赖关系的详细信息，请参阅[在 System Center Configuration Manager 中将客户端部署到 Windows 计算机的先决条件](../LocTest/Prerequisites-for-deploying-clients-to-Windows-computers-in-System-Center-Configuration-Manager.md)。 有关其他客户端安装方法的详细信息，请参阅 [System Center Configuration Manager 中的客户端安装方法](../LocTest/Client-installation-methods-in-System-Center-Configuration-Manager.md)。  
  
         请参阅 [如何使用客户端请求安装 Configuration Manager 客户端](../LocTest/How-to-deploy-clients-to-Windows-computers-in-System-Center-Configuration-Manager.md#BKMK_ClientPush)。  
  
    -   **重新分配站点**  
  
         将一个或多个客户端（包括被管理的移动设备）重新分配到层次结构中的另一个主站点。 可以单独重新分配客户端，也可以选择多个客户端并成批重新分配到新站点。  
  
    -   **以远程方式管理客户端**  
  
         你可以运行资源浏览器来查看 Windows 客户端中的硬件和软件清单信息，并通过使用远程控制、远程协助或远程桌面对其进行远程管理。  
  
         请参阅[如何使用资源浏览器来查看 System Center Configuration Manager 中的硬件清单](../LocTest/How-to-use-Resource-Explorer-to-view-hardware-inventory-in-System-Center-Configuration-Manager.md)和[如何使用资源浏览器来查看 System Center Configuration Manager 中的软件清单](../LocTest/How-to-use-Resource-Explorer-to-view-software-inventory-in-System-Center-Configuration-Manager.md)。  
  
         请参阅[如何使用 System Center Configuration Manager 远程管理 Windows 客户端计算机](../LocTest/How-to-remotely-administer-a-Windows-client-computer-by-using-System-Center-Configuration-Manager.md)。  
  
    -   **批准客户端**  
  
         当客户端通过使用 HTTP 和自签名证书与站点系统通信时，你必须批准这些客户端以将它们标识为受信任计算机。 默认情况下，站点配置会自动批准同一 Active Directory 林和受信任林中的客户端，这样你就不必手动批准每个客户端。 但是，你必须手动批准你信任的工作组计算机以及你信任但未获批准的任何其他计算机。  
  
        > [!WARNING]  
        >  尽管某些管理功能可能适合于未批准的客户端，但 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]不支持这种情况。  
  
         你不必批准始终通过使用 HTTPS（而不是 HTTP）与站点系统通信的客户端，或在通过 HTTP 与站点系统通信时使用 PKI 证书的客户端。 这些客户端通过使用 PKI 证书与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 建立信任。  
  
    -   **阻止或解除阻止客户端**  
  
         阻止你不再信任的客户端，以防止该客户端接收客户端策略并防止 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点系统与之通信。  
  
        > [!WARNING]  
        >  阻止客户端的操作只会阻止从客户端到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点系统的通信，而不会阻止与其他设备的通信。 此外，当客户端通过使用 HTTP（而不是 HTTPS）与站点系统通信时，还有一些安全限制。  
  
         如果你稍后改变主意，你可以取消阻止已阻止的客户端。 但是，如果你在阻止了为 AMT 设置的基于 Intel AMT 的计算机后取消阻止该计算机，你必须执行其他步骤，然后才能再次在带外管理该计算机。  
  
         请参阅[确定是否在 System Center Configuration Manager 中阻止客户端](../LocTest/Determine-whether-to-block-clients-in-System-Center-Configuration-Manager.md)。  
  
    -   **清除所需的 PXE 部署**  
  
         使用此选项为所选计算机重新部署任何所需的 PXE 部署。  
  
         请参阅[使用 PXE 与 System Center Configuration Manager 一起通过网络部署 Windows](../LocTest/Use-PXE-to-deploy-Windows-over-the-network-with-System-Center-Configuration-Manager.md)。  
  
    -   **管理客户端属性**  
  
         你可以查看发现数据和针对客户端的部署。 你也可以配置任务序列用于将操作系统部署到设备的任何变量。  
  
    -   **删除客户端**  
  
        > [!WARNING]  
        >  如果要卸载 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端或将其从集合中移除，请不要删除客户端。  
  
         “删除”  操作会从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 数据库中手动删除客户端记录，并且，除非用于故障排除方案，否则你通常不应使用此操作。 如果你删除客户端记录，而 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端仍处于已安装状态并与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]通信，则检测信号发现将重新创建客户端记录，并且该记录将重新出现在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，尽管客户端历史记录和任何以前的关联将丢失。  
  
        > [!NOTE]  
        >  当你删除通过 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]注册的移动设备客户端时，此操作还会吊销颁发给移动设备的 PKI 证书，并且管理点随后会拒绝此证书（即使 IIS 未检查 CRL）。 在删除这些客户端时，不会吊销移动设备旧客户端上的证书。  
  
         要卸载客户端，请参阅 [卸载 Configuration Manager 客户端](#BKMK_UninstalClient)。  
  
         要将客户端分配到一个新的主站点，请参阅[如何在 System Center Configuration Manager 中将客户端分配到一个站点](../LocTest/How-to-assign-clients-to-a-site-in-System-Center-Configuration-Manager.md)。  
  
         要从集合中删除客户端，请重新配置集合属性。 请参阅[如何在 System Center Configuration Manager 中管理集合](../LocTest/How-to-manage-collections-in-System-Center-Configuration-Manager.md)。  
  
    -   **擦除移动设备**  
  
         你可以擦除支持擦除命令的移动设备。  
  
         此操作会永久删除移动设备上的所有数据，其中包括个人设置和个人数据。 通常，此操作会将移动设备重置回出厂默认值。 在移动设备不再受信任（例如，丢失或被盗）时将其擦除。  
  
        > [!TIP]  
        >  请检查制造商的文档以了解有关移动设备如何处理远程擦除命令的详细信息。  
  
         当你发送擦除请求时，在移动设备收到擦除命令之前通常会有延迟。  
  
        -   如果移动设备是通过 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 或 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)]注册的，则客户端将在其下一次下载客户端策略时收到擦除命令。  
  
        -   如果通过 Exchange Server 连接器管理移动设备，则移动设备将在其下一次与 Exchange 同步时收到擦除命令。  
  
         你可以使用“擦除状态”  列来监视移动设备何时收到擦除命令。 在移动设备将擦除确认发送到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]之前，你可以取消擦除命令。  
  
    -   **停用移动设备**  
  
         只有 **或** 注册的移动设备才支持 [!INCLUDE[mit_next](../LocTest/includes/mit_next_md.md)][!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)]“停用”选项。  
  
         有关详细信息，请参阅 [使用 System Center Configuration Manager 的远程擦除、远程锁定或密码重置功能帮助保护数据](../Topic/Help%20protect%20your%20data%20with%20remote%20wipe,%20remote%20lock,%20or%20passcode%20reset%20using%20System%20Center%20Configuration%20Manager.md)。  
  
    -   **更改设备的所有权**  
  
         如果设备未加入域并且未安装 **客户端，那么你可以将设备的所有权更改为“公司”****或**[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] “个人”。  
  
         你可以在应用程序要求中使用此值来控制部署，也可以使用此配置来控制从用户的设备中收集多少清单。  
         
        若要查看设备列表中的所有权值，可能需要右键单击任意列标题并选择“设备所有者”将列添加到视图中。
  
         有关详细信息，请参阅[使用 System Center Configuration Manager 和 Microsoft Intune 的混合移动设备管理 (MDM)](../LocTest/Hybrid-mobile-device-management--MDM--with-System-Center-Configuration-Manager-and-Microsoft-Intune.md)。  
  
##  <a name="BKMK_ManagingClients_DeviceCollectionsNode"></a> 通过“设备集合”节点管理客户端  
 使用下列过程和下表，以便通过“资产和符合性”  工作区中的“设备集合”  节点来管理集合中的设备。  
  
 你在从“设备”  节点中选择单一设备或多台设备时可执行的许多客户端管理任务也可在集合级别执行。 这样做的优势是可将管理任务自动应用于集合中的所有合格设备。 尽管使用这种方法来同时管理多台客户端可能很方便，但它也可能生成大量的网络数据包，并增加站点服务器上的 CPU 使用率。  
  
 还有一些只能在集合级别执行的客户端管理任务，下表中列出了这些任务。  
  
 在执行集合级别客户端管理任务之前，请考虑集合中有多少设备、这些设备是否通过低带宽网络连接进行连接，以及对于所有设备任务将花费多长时间完成。 在执行客户端管理任务时，你无法从控制台中将其停止。  
  
#### 通过“设备集合”节点管理客户端  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性” 。  
  
2.  在“资产和符合性”  工作区中，单击“设备集合” 。  
  
3.  选择一个集合，然后从功能区中选择或通过右键单击集合来选择下列客户端管理任务之一：  
  
    -   **扫描计算机以查找恶意软件并下载反恶意软件定义文件。**  
  
         请参阅 [System Center Configuration Manager 中 Endpoint Protection 的操作和维护](../LocTest/Operations-and-maintenance-for-Endpoint-Protection-in-System-Center-Configuration-Manager.md)。  
  
    -   **部署软件、配置基线和任务序列。**  
  
         有关部署软件和配置基线的详细信息，请参阅下列各项：  
  
        -   [在 System Center Configuration Manager 中配置软件更新](../LocTest/Configure-software-updates-in-System-Center-Configuration-Manager.md)  
  
        -   [在 System Center Configuration Manager 中规划和配置符合性设置](../LocTest/Plan-for-and-configure-compliance-settings-in-System-Center-Configuration-Manager.md)  
  
    -   **配置电源管理设置。**  
  
         请参阅[如何在 System Center Configuration Manager 中创建并应用电源计划](../LocTest/How-to-create-and-apply-power-plans-in-System-Center-Configuration-Manager.md)。 电源计划只能用于运行 Windows 的计算机。  
  
    -   **通知计算机尽快下载策略。**  
  
         使用客户端通知来通知所选 Windows 客户端，在配置的客户端策略轮询间隔外尽快下载计算机策略。  
  
         客户端通知任务显示在“监视”  工作区的“客户端操作”  节点中。  
  
##  <a name="BKMK_ClientCache"></a> 为 Configuration Manager 客户端配置客户端缓存  
 你可以配置 Windows [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端用于在安装应用程序和程序时存储临时文件的位置和磁盘空间量。 软件更新也使用客户端缓存，但软件更新不受配置的缓存大小所限，并且将始终尝试下载到缓存。 你可以在手动安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端时、使用客户端请求安装时或在安装客户端之后配置客户端缓存设置。
 
在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 版本 1606 中，可以使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中的客户端设置来指定缓存文件夹的大小。   
  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端缓存的默认位置为 %*windir*%\ccmcache，默认磁盘空间为 5120 MB。  
  
> [!IMPORTANT]  
>  不要对用于客户端缓存的文件夹进行加密。 Configuration Manager 无法将内容下载到加密的文件夹。  
  
### 关于客户端缓存  
   
[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端会在接收部署之后立即下载所需软件的内容，但会等到部署计划时间之后才会运行。 在计划的时间， [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端将检查以确定缓存中是否有内容。 如果内容位于缓存中并且版本正确，则客户端将始终使用此缓存内容。 但是，如果内容的版本已更改或者已将内容删除以便为另一个包腾出空间，则会将内容再次下载到缓存。  
   
如果客户端尝试下载的程序或应用程序内容大小超出缓存的大小，则部署将因缓存大小不足而失败，并且 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将生成状态消息 ID 10050。 如果稍后增加了缓存大小，则下载重试行为对于所需程序和所需应用程序将不同。  
   
-   对于所需程序：客户端不会自动重试下载内容。 你必须将包和程序重新部署到客户端。  
-   对于所需应用程序：由于应用程序部署基于状态，因此客户端会在下一次下载其客户端策略时自动重试下载内容。  
   
如果客户端尝试下载的包小于缓存的大小，但缓存当前已满，则所有必需的部署将在下载超时之前或在达到缓存空间失败的重试限制之前一直重试，直至缓存空间可用为止。 如果稍后增加了缓存大小，则 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端将尝试在下一次重试间隔期间再次下载该包。 客户端将每隔四小时尝试下载内容一次，直至尝试 18 次为止。  
   
在客户端使用了缓存的内容后，将不会自动删除该内容，但会将其在缓存中保留至少一天。 如果将包属性配置为包含将内容保留在客户端缓存中的选项，则客户端不会自动从缓存中删除包内容。 如果客户端缓存空间由最近 24 小时内下载的包占用，并且客户端必须下载新包，你可以增加客户端缓存大小，或选择删除选项以删除保留的缓存内容。  
  
 使用以下过程在手动客户端安装过程中或在安装客户端之后配置客户端缓存。  
  
### 在使用手动客户端安装来安装客户端时配置客户端缓存  
  
从安装源位置运行 CCMSetup.exe 命令，并指定所需的以下属性，用空格分隔：  
  
   -   DISABLECACHEOPT  
 
    -   SMSCACHEDIR  
  
    -   SMSCACHEFLAGS  
  
    -   SMSCACHESIZE  
        
        > [!NOTE]
        > 对于版本 1606，请使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中**客户端设置**的可用缓存大小设置而不是 SMSCACHESIZE。 有关详细信息，请参阅[客户端缓存设置](../LocTest/About-client-settings-in-System-Center-Configuration-Manager.md#Client-Cache-Settings)。
  
有关如何使用 CCMSetup.exe 的这些命令行属性的详细信息，请参阅[关于 System Center Configuration Manager 中的客户端安装属性](../LocTest/About-client-installation-properties-in-System-Center-Configuration-Manager.md)。  
  
### 在使用客户端请求安装来安装客户端时配置客户端缓存文件夹  
  
1.  在 Configuration Manager 控制台中，单击“管理”   
  
2.  在“管理”  工作区中，展开“站点配置” ，然后单击“站点” 。  
  
3.  在“站点”  列表中，选择要为其配置自动站点范围客户端请求安装的站点。  
  
4.  在“主页”  选项卡上的“设置”  组中，单击“客户端安装设置” ，然后单击“安装属性” 选项卡。  
  
5.  在“安装属性”  选项卡上，指定所需的以下属性，并使用空格分隔各个属性：  
  
    -   DISABLECACHEOPT  
  
    -   SMSCACHEDIR  
  
    -   SMSCACHEFLAGS  
  
    -   SMSCACHESIZE  
        
        > [!NOTE]
        > 对于版本 1606，请使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中**客户端设置**的可用缓存大小设置而不是 SMSCACHESIZE。 有关详细信息，请参阅[客户端缓存设置](../LocTest/About-client-settings-in-System-Center-Configuration-Manager.md#Client-Cache-Settings)。
  
       有关如何使用 CCMSetup.exe 的这些命令行属性的详细信息，请参阅[关于 System Center Configuration Manager 中的客户端安装属性](../LocTest/About-client-installation-properties-in-System-Center-Configuration-Manager.md)。  
  
6.  单击“确定”  保存已指定的属性。  
  
### 在客户端计算机上配置客户端缓存文件夹  
  
1.  在客户端计算机上的控制面板中，导航到“Configuration Manager”  ，然后双击以打开属性。  
  
2.  单击“缓存”  选项卡。  
  
3.  指定要为客户端缓存保留的磁盘空间。  
  
4.  要更改客户端缓存文件夹的位置，请单击“更改位置” ，然后指定新位置。 默认位置为 *%windir%*\ccmcache。  
  
5.  要删除当前存储在客户端缓存文件夹中的文件，请单击“删除文件” 。  
  
6.  单击“确定”  以关闭“Configuration Manager 属性” 。  

### 在客户端设置中配置客户端缓存大小

从版本 1606 开始，可以在无需重新安装客户端的情况下调整客户端缓存文件夹的大小。 若要执行此操作，请在 Configuration Manager 控制台中使用客户端设置配置客户端缓存大小。  

1. 在 Configuration Manager 控制台中，转到“管理” > “客户端设置”。 

2. 双击“默认客户端设置”。 
  还可以创建自定义客户端设置，以便更有选择性地应用缓存大小。 有关默认客户端设置和自定义客户端设置的详细信息，请参阅[如何在 System Center Configuration Manager 中配置客户端设置](../LocTest/How-to-configure-client-settings-in-System-Center-Configuration-Manager.md)。
  
 3. 单击“客户端缓存设置”，然后为“配置客户端缓存大小”选择“是”。 
 
 4. 使用 **MB** 或**磁盘设置的百分比**调整最大缓存大小。 缓存可调整为任何小于最大缓存的大小。
 
 5. 单击" **确定**"。
 
    在下载下一个客户端策略时，Configuration Manager 客户端将使用这些设置配置缓存大小。 
  
##  <a name="BKMK_UninstalClient"></a> 卸载 Configuration Manager 客户端  
 可通过将 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] CCMSetup.exe **与** /Uninstall **属性一起使用从计算机卸载 Windows** 客户端软件。 在单独的计算机上从命令提示符运行 CCMSetup.exe，或部署包和程序为计算机集合卸载客户端。  
  
> [!WARNING]  
>  你无法从移动设备中卸载 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端。 如果必须从移动设备中删除 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端，你必须擦除设备，从而会删除移动设备上的所有数据。  
  
 使用以下过程来从计算机中卸载 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端。  
  
#### 通过命令提示符卸载 Configuration Manager 客户端  
  
1.  打开 Windows 命令提示符，并将文件夹更改到 CCMSetup.exe 所在的位置。  
  
2.  键入 **Ccmsetup.exe /uninstall**，然后按   
  
> [!NOTE]  
>  卸载过程无提示，并且不会在屏幕上显示结果。 要验证客户端卸载是否成功，请检查客户端计算机上 **%windir%\ ccmsetup** 文件夹中的日志文件 *CCMSetup.log* 。  
  
##  <a name="BKMK_ConflictingRecords"></a> 为 Configuration Manager 客户端管理冲突的记录  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 使用硬件 ID 来尝试标识可能重复的客户端，并向你发出有关冲突的记录的警报。 例如，你重新安装计算机，则硬件 ID 将相同，但 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 使用的 GUID 可能已更改。  
  
 当 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 能够通过使用计算机帐户的 Windows 身份验证或来自受信任来源的 PKI 证书解决冲突时，将为你自动解决冲突。 但是，当 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 无法解决冲突时，它将使用层次结构设置，该设置会在检测到重复的硬件 ID 时自动合并记录（默认设置），或允许你决定是合并、阻止还是创建新客户端记录。 如果你决定手动管理重复记录，则必须通过使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台手动解决冲突的记录。  
  
#### 更改用于管理冲突的记录的层次结构设置  
  
1.  在 Configuration Manager 控制台中，单击“管理”   
  
2.  在“管理”  工作区中，展开“站点配置” ，然后单击“站点” 。  
  
3.  在“站点”  组中，单击“层次结构设置” ，然后单击“客户端批准和冲突的记录”  选项卡。  
  
4.  单击“自动解决冲突的记录”  以自动合并冲突的记录，或单击“手动解决冲突的记录” ，然后单击“确定” 。  
  
    > [!NOTE]  
    >  当 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 可通过使用计算机帐户或 PKI 证书解决冲突时，将忽略此设置，并且冲突会自动得到解决。  
  
#### 手动解决冲突的记录  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“监视”   
  
2.  在“监视”  工作区中，展开“系统状态” ，然后单击“冲突的记录” 。  
  
3.  在结果窗格中，选择一个或多个冲突的记录，然后单击“冲突的记录” 。  
  
4.  在“冲突的记录”  对话框中，选择以下各项之一，然后单击“确定” ：  
  
    -   选择“合并” 以将新检测到的记录与现有客户端记录合并，从而创建一个统一记录。  
  
    -   选择“新建” 为冲突的客户端记录创建新记录。  
  
    -   选择“阻止” 为冲突的客户端记录创建新记录，但将其标记为已阻止。  
  
##  <a name="BKMK_PolicyRetrieval"></a> 为 Configuration Manager 客户端启动策略检索  
 Windows [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端按你配置为客户端设置的计划下载其客户端策略。 但是，有时你希望从客户端中启动临时策略检索，例如，在疑难解答方案中或在进行测试时，你可能希望这样做。  
  
 使用以下过程，通过 Configuration Manager 客户端上的“操作”  选项卡或在计算机上运行脚本，在其计划的轮询间隔外从客户端中启动临时策略检索。 你必须使用本地管理权限登录到客户端计算机才能执行这些过程。  
  
> [!NOTE]  
>  你可以使用客户端通知在计划的客户端策略轮询间隔外启动客户端策略检索。  
>   
>  你可以管理运行 Linux 和 UNIX 的客户端。 有关运行 Linux 和 UNIX 的客户端的策略检索的信息，请参阅 [Computer policy for Linux and UNIX servers](../LocTest/How-to-manage-clients-for-Linux-and-UNIX-servers-in-System-Center-Configuration-Manager.md#BKMK_PolicyforLnU)。  
  
#### 要使用客户端通知启动客户端策略检索  
  
1.  在 Configuration Manager 控制台中，单击“资产和符合性” 。  
  
2.  在“资产和符合性”  工作区中，单击“设备集合” 。  
  
3.  选择包含要下载策略的计算机的设备集合，然后在“主页”  选项卡中的“集合”  组中，单击“客户端通知”  ，然后单击“下载计算机策略” 。  
  
    > [!NOTE]  
    >  你也可以使用客户端通知为显示在“设备”  节点下的临时集合节点中的一台或多台所选设备启动策略检索。  
  
#### 使用 Configuration Manager 客户端上的“操作”选项卡手动启动客户端策略检索  
  
1.  在计算机的控制面板中选择“Configuration Manager”  。  
  
2.  单击“操作”  选项卡。  
  
3.  单击“计算机策略检索和评估周期”以启动计算机策略，然后单击“立即运行”。  
  
4.  单击“确定”  确认提示。  
  
5.  为所需的任何其他操作（例如用户客户端设置的“用户策略检索和评估周期”）重复步骤 3 和 4。  
  
6.  单击“确定”  以关闭“Configuration Manager 属性” 。  
  
#### 使用脚本手动启动客户端策略检索  
  
1.  打开文本编辑器，例如记事本。  
  
2.  将以下内容复制并粘贴到文件中：  
  
    ```  
    on error resume next  
  
    dim oCPAppletMgr 'Control Applet manager object.  
    dim oClientAction 'Individual client action.  
    dim oClientActions 'A collection of client actions.  
  
    'Get the Control Panel manager object.  
    set  oCPAppletMgr=CreateObject("CPApplet.CPAppletMgr")  
    if err.number <> 0 then  
        Wscript.echo "Couldn't create control panel application manager"  
        WScript.Quit  
    end if  
  
    'Get a collection of actions.  
    set oClientActions=oCPAppletMgr.GetClientActions  
    if err.number<>0 then  
        wscript.echo "Couldn't get the client actions"  
        set oCPAppletMgr=nothing  
        WScript.Quit  
    end if  
  
    'Display each client action name and perform it.  
    For Each oClientAction In oClientActions  
  
        if oClientAction.Name = "Request & Evaluate Machine Policy" then  
            wscript.echo "Performing action " + oClientAction.Name   
            oClientAction.PerformAction  
        end if  
    next  
  
    set oClientActions=nothing  
    set oCPAppletMgr=nothing  
    ```  
  
3.  以 .vbs 扩展名保存文件。  
  
4.  在客户端计算机上，使用下列方法之一运行该文件：  
  
    -   使用 Windows 资源管理器导航到该文件，然后双击脚本文件。  
  
    -   打开命令提示符，然后键入：**cscript <path\filename.vbs>**。  
  
5.  在“Windows 脚本宿主”  对话框中单击“确定”  。  
  
## 另请参阅  
 [在 System Center Configuration Manager 中监视和管理客户端](../LocTest/Monitor-and-manage-clients-in-System-Center-Configuration-Manager.md)
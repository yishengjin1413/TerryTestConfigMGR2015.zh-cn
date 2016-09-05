---
title: "在 System Center Configuration Manager 中准备操作系统部署的站点系统角色"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-osd
ms.tgt_pltfrm: na
ms.topic: get-started-article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 0ef5f3ce-b0e4-4775-b5c2-b245e45b4194
caps.latest.revision: 11
caps.handback.revision: 10
---
# 在 System Center Configuration Manager 中准备操作系统部署的站点系统角色
若要在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]中部署操作系统，你首先必须准备以下需要特定的配置和注意事项的站点系统角色：  
  
-   [分发点](#BKMK_DistributionPoints)  
  
    -   [分发点的其他规划注意事项](#BKMK_AdditionalPlanning)  
  
    -   [配置分发点以接受 PXE 请求](#BKMK_PXEDistributionPoint)  
  
    -   [配置分发点以支持多播](#BKMK_DPMulticast)  
  
-   [状态迁移点](#BKMK_StateMigrationPoints)  
  
##  <a name="BKMK_DistributionPoints"></a> 分发点  
 分发点站点系统角色包含供客户端下载的源文件，例如应用程序内容、软件更新、操作系统映像以及启动映像。 你可以通过使用带宽、限制和计划选项来控制内容分发。  
  
 有足够的分发点支持部署到计算机的操作系统非常重要。 将这些分发点放置在你的层次结构中的规划也同样重要。 你将在[为 System Center Configuration Manager 管理内容和内容基础结构](../LocTest/Manage-content-and-content-infrastructure-for-System-Center-Configuration-Manager.md)中找到这一规划的大部分信息。 但是，有一些特定于操作系统部署的分发点的其他规划注意事项。  
  
###  <a name="BKMK_AdditionalPlanning"></a> 分发点的其他规划注意事项  
 以下为分发点要考虑的其他规划事项：  
  
-   **如何避免不需要的操作系统部署?**  
  
     [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不会从集合中的其他目标计算机区分站点服务器。 如果将所需的任务序列部署到包含站点服务器的集合，则站点服务器会以该集合中的任何其他计算机运行任务序列的方式来运行任务序列。 确保你的操作系统部署使用包含你打算运行部署的客户端的集合。  
  
     你可以管理高风险任务序列部署的行为。 高风险部署在客户端上自动安装且可能产生意外结果。 例如，一个用途为“必需”且部署操作系统的任务序列。 若要降低不需要的高风险部署的风险，可以配置部署验证设置。 有关详细信息，请参阅 [Settings to manage high-risk deployments for System Center Configuration Manager](../LocTest/Settings-to-manage-high-risk-deployments-for-System-Center-Configuration-Manager.md)。  
  
-   **一次有多少台计算机可以接收来自单个分发点的操作系统映像？**  
  
     若要预估需要多少个分发点，必须考虑分发点的处理速度和磁盘 I/O 性能、网络上的可用带宽以及映像包的大小对这些资源的影响。 例如，在 100 兆字节 (MB) 的以太网上，如果不考虑任何其他服务器资源因素，则一小时内可以处理 4 千兆字节 (GB) 映像包的计算机的最大数量是 11 台。  
  
     `100 Megabits/sec = 12.5 Megabytes/sec = 750 Megabytes/min = 45 Gigabytes/hour = 11 images @ 4GB per image.`  
  
     如果必须在特定的时间段内将操作系统部署到特定数量的计算机，请将映像分发到适当数量的分发点。  
  
-   **是否可以将操作系统部署到分发点吗？**  
  
     可以将操作系统部署到分发点，但必须从其他分发点接收操作系统映像。  
  
###  <a name="BKMK_PXEDistributionPoint"></a> 配置分发点以接受 PXE 请求  
 要将操作系统部署到发出 PXE 启动请求的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端，你必须配置一个或多个分发点以接受 PXE 请求。 配置分发点后，此分发点将响应 PXE 启动请求，并确定要执行的适当部署操作。 
  
> [!IMPORTANT]  
>  [Windows Deployment Services](../LocTest/Infrastructure-requirements-for-operating-system-deployment-in-System-Center-Configuration-Manager.md#BKMK_WDS) 必须安装在所有 PXE 启用的分发点上。  
  
 使用以下过程来修改现有分发点，使其可接受 PXE 请求。 有关如何安装新分发点的信息，请参阅 [Install or modify a distribution point](../LocTest/Manage-content-and-content-infrastructure-for-System-Center-Configuration-Manager.md#bkmk_Iinstall)。  
  
##### 修改现有分发点以接受 PXE 请求  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台，单击“管理”，然后展开“概述”并单击“分发点”。  
  
2.  选择要配置的分发点，然后在“主页”选项卡上的“属性”组中，单击“属性”。  
  
3.  在分发点的属性页上，单击“PXE”  选项卡。 然后选择“为客户端启用 PXE 支持”以在此分发点上启用 PXE。  
  
4.  在“查看 PXE 的所需端口”对话框中，单击“是”，以确认你想要启用 PXE。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将在 Windows 防火墙上自动配置默认端口。 如果你使用其他防火墙，则必须手动配置这些端口。  
  
    > [!NOTE]  
    >  如果在同一台服务器上安装 WDS 和 DHCP，则必须配置 WDS 以侦听不同端口（因为 DHCP 在同一个端口上侦听）。 有关详细信息，请参阅 [WDS 和 DHCP 在同一个服务器上时的注意事项](../LocTest/Infrastructure-requirements-for-operating-system-deployment-in-System-Center-Configuration-Manager.md#BKMK_WDSandDHCP)。  
  
5.  选择“允许此分发点响应传入的 PXE 请求”以启用 WDS，以便它会响应传入的 PXE 服务请求。 可以使用此设置来启用和禁用服务，而不从分发点中删除 PXE 功能。  
  
6.  选择“启用未知计算机支持”将操作系统部署到不是由 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 托管的计算机。  
  
7.  选择“当计算机使用 PXE 时要求密码”，然后指定一个强密码，为 PXE 部署提供额外的安全保护。  
  
8.  在“用户设备相关性”列表中，选择你希望分发点如何将用户与 PXE 部署的目标计算机关联。  
  
    -   选择“不使用用户设备相关性”以不将用户与目标计算机关联。  
  
    -   选择“通过手动批准允许用户设备相关性”  以在将用户与目标计算机关联之前等待管理用户批准。  
  
    -   选择“通过自动批准允许用户设备相关性”  以自动将用户与目标计算机关联，而不等待批准。  
  
     有关详细信息，请参阅[将用户与 System Center Configuration Manager 中的目标计算机关联](../LocTest/Associate-users-with-a-destination-computer-in-System-Center-Configuration-Manager.md)。  
  
9. 指定分发点响应来自所有网络接口或来自特定网络接口的 PXE 请求。 如果你选择使分发点响应特定网络接口，请为每个网络接口提供 MAC 地址。  
  
10. 指定在使用了多个启用 PXE 的分发点时分发点在响应计算机请求之前延迟的时间长度（以秒为单位）。  
  
11. 单击“确定”  更新分发点的属性。  

###  <a name="BKMK_RamDiskTFTP"></a> 在启用 PXE 的分发点上自定义 RamDisk TFTP 块大小和窗口大小  
你可以为启用 PXE 的分发点自定义 RamDisk TFTP 块大小和窗口大小。 如果自定义了网络，则可能导致启动映像下载由于超时错误而失败，因为块大小或窗口大小太大。 通过 RamDisk TFTP 块大小和窗口大小自定义可以在使用 PXE 时优化 TFTP 流量，以满足特定网络要求。   
需要在环境中测试自定义设置以确定最高效的设置。  
  
-   **TFTP 块大小**：块大小是服务器发送到下载文件（如 RFC 2347 中所述）的客户端的数据包大小。 较大的块大小使服务器可以发送较少的数据包，因此服务器与客户端之间的往返延迟较少。 但是，较大的块大小会导致零碎的数据包，而大多数 PXE 客户端实现不支持这一点。  
  
-   **TFTP 窗口大小**：对于发送的每个数据块，TFTP 需要确认 (ACK) 数据包。 服务器在收到上一个块的 ACK 数据包之前，不会发送序列中的下一个块。 TFTP 窗口是 Windows 部署服务中的一个功能，使你可以定义填满窗口所需的数据块数。 服务器在窗口填满之前会背靠背地发送数据块，随后客户端会发送 ACK 数据包。 增加此窗口大小会减少客户端与服务器之间的往返延迟数，并缩短下载启动映像所需的总体时间。  
   
  
#### 修改 RamDisk TFTP 窗口大小  
  
-   在启用 PXE 的分发点上添加以下注册表项以自定义 RamDisk TFTP 窗口大小：  
  
     **位置**：HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SMS\DP  
    名称：RamDiskTFTPWindowSize  
  
     **类型**：REG_DWORD  
  
     **值**：<customized window size\>  
  
 默认值为 1（1 个数据块填满窗口）  
  
#### 修改 RamDisk TFTP 块大小  
  
-   在启用 PXE 的分发点上添加以下注册表项以自定义 RamDisk TFTP 窗口大小：  
  
     **位置**：HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SMS\DP  
    名称：RamDiskTFTPBlockSize  
  
     **类型**：REG_DWORD  
  
     **值**：<customized block size\>  
  
 默认值为 4096 (4k)。  


###  <a name="BKMK_DPMulticast"></a> 配置分发点以支持多播  
 当多个客户端可能同时下载同一个操作系统映像时，多播是一种可以在分发点上使用的网络优化方法。 使用多播时，多台计算机可以同时下载操作系统映像，因为映像已由分发点多播，而不必使分发点通过单独连接向每个客户端发送数据的副本。 必须至少配置一个分发点以支持多播。 有关详细信息，请参阅[使用多播与 System Center Configuration Manager 一起通过网络部署 Windows](../LocTest/Use-multicast-to-deploy-Windows-over-the-network-with-System-Center-Configuration-Manager.md)。  
  
 在部署操作系统之前，你必须配置分发点以支持多播。 使用下列过程来修改现有分发点以支持多播。 有关如何安装新分发点的信息，请参阅 [Install or modify a distribution point](../LocTest/Manage-content-and-content-infrastructure-for-System-Center-Configuration-Manager.md#bkmk_Iinstall)。  
  
##### 为分发点启用多播  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“管理” 。  
  
2.  在“管理”  工作区中，展开“概述” ，然后选择“分发点”  节点。  
  
3.  选择要用于对操作系统映像进行多播的分发点。  
  
4.  在“主页”  选项卡上的“属性”  组中，单击“属性” 。  
  
5.  选择“多播”  选项卡，并配置以下选项：  
  
    -   **启用多播**：你必须选择此选项以用于分发点支持多播。  
  
    -   **多播连接帐户**：指定用于连接到站点数据库的帐户。  
  
    -   **多播地址设置**：指定 IP 地址以将数据发送到目标计算机。 默认情况下，IP 地址是从为分发多播地址启用的 DHCP 服务器中获得的。 根据网络环境，你可以指定介于 239.0.0.0 和 239.255.255.255 之间的 IP 地址范围。  
  
        > [!IMPORTANT]  
        >  请求操作系统映像的目标计算机必须可访问这些 IP 地址。 这意味着，必须将目标计算机和站点服务器之间的路由器和防火墙配置为允许多播流量。  
  
    -   **UDP 端口范围**：指定 UDP 端口的范围以将数据发送到目标计算机。  
  
        > [!IMPORTANT]  
        >  请求操作系统映像的目标计算机必须可访问这些端口。 这意味着，必须将目标计算机和站点服务器之间的路由器和防火墙配置为允许多播流量。  
  
    -   **启用计划的多播**：指定 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 如何控制开始将操作系统部署到目标计算机的时间。 单击“启用计划的多播” ，然后选择下列选项。  
  
         在“会话启动延迟”  框中，指定 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 在响应第一个部署请求之前等待的分钟数。  
  
         在“最小会话大小”  框中，指定在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 开始部署操作系统之前必须收到的请求数。  
  
    -   **传输速率**：选择将数据下载到目标计算机的传输速率。  
  
    -   **最大客户端数**：指定可从此分发点下载操作系统的目标计算机的最大数量。  
  
6.  单击" **确定**"。  
  
##  <a name="BKMK_StateMigrationPoints"></a> 状态迁移点  
 状态迁移点在一台计算机上存储捕获的用户状态数据，然后在另一台计算机上还原这些数据。 但是，当你在同一台计算机上捕获操作系统部署的用户设置时，例如在目标计算机上刷新操作系统的部署，你可以选择是通过使用硬链接还是使用状态迁移点来储存数据在同一台计算机上。 对于一些计算机部署，当你创建状态存储时， [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 会自动在状态存储和目标计算机之间创建关联。 在规划状态迁移点时，请考虑以下因素。  
  
### 用户状态大小  
 用户状态大小直接影响到状态迁移点上的磁盘存储和迁移期间的网络性能。 请考虑用户状态大小和要迁移的计算机数量， 以及要从计算机迁移哪些设置。 例如，如果“我的文档”  已备份到服务器，那么，你可能无需将其作为映像部署的一部分进行迁移。 避免不必要的迁移可以减小用户状态的总大小，并且减轻它本来对网络性能和状态迁移点上的磁盘存储造成的影响。  
  
### 用户状态迁移工具  
 若要在部署操作系统的过程中捕获和还原用户状态，必须使用指向 USMT 源文件的用户状态迁移工具 (USMT) 包。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将在“软件库” > “应用程序管理” > “包”中的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中自动创建此包。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 使用在 Windows 评估和部署工具包 (Windows ADK) 中分发的 USMT 10.0，从一个操作系统捕获用户状态，然后将其还原到另一个操作系统。  
  
 有关 USMT 10.0 的不同迁移方案的说明，请参阅 [常见迁移方案](https://technet.microsoft.com/library/mt299169\(v=vs.85\).aspx)。  
  
### 保留策略  
 在配置状态迁移点时，可以指定在其上存储的用户状态数据的保留时间。 此数据在状态迁移点上的保留时间取决于两个因素：  
  
-   所存储的数据对磁盘存储的影响。  
  
-   将数据保留一段时间以防重新迁移数据这一潜在要求。  
  
 状态迁移分两个阶段进行：捕获数据和还原数据。 在捕获数据时，收集用户状态数据并将其保存到状态迁移点。 在还原数据时，从状态迁移点检索用户状态数据，然后将其写入目标计算机。之后，“发布状态存储”  任务序列步骤发布所存储的数据。 在发布数据时，保留计时器启动。 如果选择与立即删除迁移的数据有关的选项，则在发布用户状态数据后会立即将其删除。 如果选择与将数据保留一段时间有关的选项，则在发布状态数据之后，经过这段时间就会删除数据。 将保持期设置得越长，可能需要的磁盘空间就越多。  
  
### 选择要用于储存用户状态迁移数据的驱动器  
 在配置状态迁移点时，必须在服务器上指定用于存储用户状态迁移数据的驱动器。 从固定的驱动器列表中选择驱动器。 但是，一些驱动器可能代表不可写入的驱动器，例如 CD 驱动器或非网络共享的驱动器。 此外，一些驱动器号可能无法映射到计算机上的任何驱动器。 在配置状态迁移点时，必须指定一个可写入的共享驱动器。  
  
### 配置状态迁移点  
 你可以使用下列方法来配置状态迁移点以存储用户状态数据：  
  
-   使用“创建站点系统服务器向导”  为状态迁移点创建一个新站点系统服务器。  
  
-   使用“添加站点系统角色向导”  将状态迁移点添加到现有服务器。  
  
 在使用这些向导时，会提示你提供状态迁移点的下列信息：  
  
-   用于存储用户状态数据的文件夹。  
  
-   可在状态迁移点上存储数据的客户端的最大数量。  
  
-   供状态迁移点存储用户状态数据的最小可用空间。  
  
-   角色的删除策略。 你可以指定在计算机上还原用户状态数据之后立即删除该数据，或在计算机上还原用户数据后特定天数之后再删除该数据。  
  
-   状态迁移点是否仅响应还原用户状态数据的请求。 如果启用此选项，你将无法使用状态迁移点来存储用户状态数据。  
  
 有关安装站点系统角色的步骤，请参阅 [Add site system roles for System Center Configuration Manager](../LocTest/Add-site-system-roles-for-System-Center-Configuration-Manager.md)。  
  
## 另请参阅  
 [System Center Configuration Manager 中的操作系统部署计划](../LocTest/Plan-for-operating-system-deployment-in-System-Center-Configuration-Manager.md)
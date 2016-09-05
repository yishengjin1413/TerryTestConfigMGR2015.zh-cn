---
title: "如何配置软件更新点以使用网络负载平衡 (NLB) 群集"
ms.custom: na
ms.date: 09/02/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 5685fa28-b50f-4f0d-8858-91111cb9a437
caps.latest.revision: 4
caps.handback.revision: 3
---
# 如何配置软件更新点以使用网络负载平衡 (NLB) 群集
> [!NOTE]  
>  本主题中的信息仅适用于不带 Service Pack 的 [!INCLUDE[cm5long](../LocTest/includes/cm5long_md.md)]。 有关是否配置软件更新点以在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中使用网络负载平衡 \(NLB\) 的详细信息，请参阅[Software Update Point Configured to Use an NLB](assetId:///bcf8ed65-3bea-4bec-8bc5-22d9e54f5a6d#BKMK_NLBSUPSP1)主题中的[Planning for Software Updates in Configuration Manager](assetId:///bcf8ed65-3bea-4bec-8bc5-22d9e54f5a6d)部分。  
  
 本主题提供有关如何在不带 Service Pack 的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中配置 NLB 的步骤。 NLB 可以提高网络的可靠性和性能。 你可以设置共享单一 SQL Server 故障转移群集的多个 WSUS 服务器，然后将软件更新点配置为使用 NLB，但此配置要求你在 WSUS 设置过程中执行额外的步骤。  
  
> [!NOTE]  
>  可配置为网络负载平衡群集一部分的 WSUS 服务器的最大数量为 4。  
  
 使用下列部分将活动软件更新点配置为使用 NLB 群集：  
  
-   针对网络负载平衡的软件更新点站点系统准备网络环境。  
  
-   安装 WSUS 3.0（在将承载软件更新点站点系统角色的每个服务器上安装）。  
  
-   安装软件更新点站点系统角色（在将作为软件更新点网络负载平衡群集一部分的每个服务器上安装）。  
  
-   为安装的软件更新站点系统配置 Windows Server 网络负载平衡群集。  
  
-   为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点配置活动软件更新点组件作为软件更新点网络负载平衡群集。  
  
 [针对网络负载平衡配置 WSUS](http://go.microsoft.com/fwlink/p/?LinkId=232412)  
  
##  <a name="BKMK_PrepareNetworkForNLB"></a> 针对 NLB 软件更新点站点系统准备网络环境  
 使用下列过程来针对软件更新点准备网络环境以使用 NLB 群集。  
  
###  <a name="BKMK_PrepareNetwork"></a> 针对 NLB 软件更新点站点系统准备网络环境  
  
1.  创建或确定要用作软件更新点连接帐户的域用户帐户。  
  
2.  向将作为 NLB 群集一部分的每个服务器上的本地管理员组中添加将配置为软件更新点 NLB 群集一部分的每个站点系统的计算机帐户。  
  
    > [!NOTE]  
    >  群集节点的计算机帐户必须能够写入 WSUS 数据库。 如果从 SQL Server 上的 SysAdmin 角色中删除了本地管理员组，计算机帐户将无法写入 WSUS 数据库，并且软件更新点将无法安装，直至将计算机帐户添加到 SysAdmin 角色为止。  
  
3.  创建可供将成为软件更新点 NLB 群集一部分的所有 WSUS 服务器使用的 DFS 共享或标准网络共享文件夹，以用作 WSUS 资源内容共享。 应为每个远程 WSUS 服务器授予对共享文件夹根目录的更改权限（除“完全控制”外的所有标准 NTFS 权限）。 如果在将成为 NLB 群集一部分的站点系统之一上创建了共享，则站点系统的网络访问帐户必须具有共享文件夹根目录的更改权限。 用于运行 WSUS 安装程序的用户帐户必须对共享具有相同的权限。  
  
4.  确定运行 SQL Server 以承载 WSUS 数据库的计算机。 WSUS 数据库可安装在承载站点数据库的同一 SQL Server 数据库服务器实例上，或安装在其他 SQL Server 数据库服务器上。  
  
    > [!NOTE]  
    >  有关可用于 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中站点系统的受支持 SQL Server 版本的列表，请参阅 [SQL Server Site Database Configurations](assetId:///c1e93ef9-761f-4f60-8372-df9bf5009be0#BKMK_SupConfigSQLDBconfig)。  
  
5.  WSUS 3.0 管理控制台必须安装在主站点服务器上，才能允许站点服务器和远程 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台配置以及与 WSUS 同步。  
  
6.  如果 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点配置为通过使用 SSL 身份验证进行通信，则必须在将配置为 NLB 一部分的每个软件更新点站点系统上配置 Web 服务器签名证书。 有关为网络负载平衡软件更新点配置 Web 服务器签名证书的详细信息，请参阅 [PKI Certificate Requirements for Configuration Manager](assetId:///19dedcfb-fb97-4c43-b777-e2701e935be7)。  
  
##  <a name="BKMK_InstallWSUS"></a> 安装 WSUS 3.0（在将承载软件更新点站点系统角色的每个服务器上安装）  
  
> [!NOTE]  
>  必须在将成为软件更新点 NLB 群集一部分的每个服务器上执行下列过程。  
  
#### 安装 WSUS 3.0 以支持 Configuration Manager 软件更新点站点系统角色  
  
1.  在将成为软件更新点 NLB 群集的一部分的服务器上，创建以下文件夹：*\<Program Files 目录\>***\\Update Services**。  
  
2.  在将成为软件更新点 NLB 群集成员的每个服务器上安装 WSUS 3.0。 有关安装 WSUS 的详细信息，请参阅 Windows Server Update Services 文档库中的 [Install the WSUS 3.0 SP2 Server Software Though the User Interface（通过用户界面安装 WSUS 3.0 SP2 服务器软件）](http://go.microsoft.com/fwlink/p/?LinkID=232835)。 在安装过程中，请考虑下列设置：  
  
    -   在“选择更新源”页上，选中“本地存储更新”复选框，并输入路径 *\<Program Files 目录\>***\\Update Services**。  
  
    -   在“数据库选项”页上，执行下列操作之一。  
  
        -   如果在承载 WSUS SQL Server 数据库的服务器上运行 WSUS 安装程序，请选择“使用此计算机上现有的数据库服务器”，并从下拉列表中选择要使用的实例名称。  
  
        -   如果在将不承载 WSUS SQL Server 数据库的计算机上运行 WSUS 安装程序，请选择“使用远程计算机上现有的数据库服务器”，并输入将承载 WSUS 数据库的 SQL Server 的 FQDN，后跟实例名称（如果未使用默认实例）。  
  
        > [!WARNING]  
        >  如果已将另一个将成为 NLB 群集一部分的 WSUS 服务器配置为使用同一 SQL Server 数据库服务器，请选择“使用现有数据库”。  
  
3.  将软件更新点连接帐户添加到服务器上的本地“WSUS 管理员”组。  
  
4.  在承载 WSUS 数据库的 SQL Server 计算机上，为软件更新点连接帐户提供针对 **SUSDB** 数据库的 dbo\_owner 权限。  
  
5.  配置 Internet Information Services \(IIS\) 以启用内容共享访问。  
  
    1.  打开 Internet Information Services \(IIS\) 管理器控制台。  
  
    2.  依次展开*“\<服务器名称\>”*、“站点”，然后展开 WSUS 网站的“站点”节点（“默认网站”或“WSUS 管理”）。  
  
    3.  配置虚拟目录内容，以使用在本主题[To prepare the network environment for network load balanced software update point site systems](assetId:///07683847-1b69-40d2-9dbd-74dec415bef8#BKMK_PrepareNetwork)过程的第 3 步中创建的共享的 UNC 共享名。  
  
    4.  使用本主题[To prepare the network environment for network load balanced software update point site systems](assetId:///07683847-1b69-40d2-9dbd-74dec415bef8#BKMK_PrepareNetwork)过程的第 1 步中创建的“软件更新点连接帐户”的用户名和密码配置用于连接到虚拟目录的凭据。  
  
6.  在 Internet Information Services \(IIS\) 中配置 SSL 身份验证。  
  
    > [!IMPORTANT]  
    >  只有软件更新点将配置为使用 SSL 进行通信的情况下，才需要此步骤。 如果未将软件更新点配置为使用 SSL，请跳到步骤 6。  
  
    1.  打开 Internet Information Services \(IIS\) 管理器。  
  
    2.  展开“网站”，然后展开 WSUS 管理网站（“默认网站”或“WSUS 管理”）。  
  
    3.  将 WSUS 管理网站的下列虚拟目录配置为使用 SSL：“APIRemoting30”、“ClientWebService”、“DSSAuthWebService”、“ServerSyncWebService”和“SimpleAuthWebService”。  
  
    4.  关闭 Internet Information Services \(IIS\) 管理器。  
  
    5.  从\<*WSUS 安装文件夹*\>\\Tools 运行以下命令：**WSUSUtil.exe configuressl \<***软件更新点站点系统节点的 Intranet FQDN* **\>**。  
  
7.  将本地内容目录移动到本主题[To prepare the network environment for network load balanced software update point site systems](assetId:///07683847-1b69-40d2-9dbd-74dec415bef8#BKMK_PrepareNetwork)过程的第 3 步中创建的 WSUS 资源内容共享。  
  
    > [!IMPORTANT]  
    >  必须为与 WSUS 资源内容共享不在同一服务器上的每个前端 WSUS 服务器执行此步骤  
  
    1.  打开命令窗口，并导航到 WSUS 服务器上的 WSUS 工具目录：**cd Program Files\\Update Services\\Tools**  
  
    2.  在要配置的第一个 WSUS 服务器上的命令提示符处，键入下列命令：  
  
         **wsusutil movecontent** *\<WSUSContentsharename\>* *\<logfilename\>*  
  
         其中 *\<WSUSContentsharename\>* 是应将内容转移到其中的 WSUS 内容资源位置共享的名称，*logfilename* 是将用于记录内容转移过程的日志文件的名称。  
  
    3.  在要配置的后续 WSUS 服务器上的命令提示符处，键入下列命令：  
  
         **wsusutil movecontent** *\<WSUSContentsharename\>* *\<logfilename\>* **\/skipcopy**  
  
         其中 *\<WSUSContentsharename\>* 是应将内容转移到其中的 WSUS 内容资源位置共享的名称，*logfilename* 是将用于记录内容转移过程的日志文件的名称。  
  
        > [!NOTE]  
        >  要验证内容转移是否成功，请查看在过程中创建的日志文件，并使用注册表编辑器来查看“HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Update Services\\Server\\Setup&#124;ContentDir”注册表项，以确保值已更改为 WSUS 内容资源位置共享名称。  
  
## 安装软件更新点站点系统角色  
 在将成为软件更新点 NLB 群集一部分的每个软件更新点上使用下列过程。  
  
#### 在将成为网络负载平衡群集一部分的服务器上安装软件更新点站点系统角色  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“管理”。  
  
2.  在“管理”工作区中，展开“站点配置”，并单击“服务器和站点系统角色”。  
  
3.  使用关联的步骤将软件更新点站点系统角色添加到新的或现有的站点系统服务器：  
  
    > [!NOTE]  
    >  有关安装站点系统角色的详细信息，请参阅[Install and Configure Site System Roles for Configuration Manager](assetId:///5c669a3c-404f-4a5d-88f0-bc40443ebaae)。  
  
    -   **新建站点系统服务器**：在“主页”选项卡上的“创建”组中，单击“创建站点系统服务器”。 创建站点系统服务器向导将会打开。  
  
    -   **现有站点系统服务器**：单击要在其中安装软件更新点站点系统角色的服务器。 单击服务器时，会在详细信息窗格中显示服务器上已经安装的站点系统角色的列表。  
  
         在“主页”选项卡上的“服务器”组中，单击“添加站点系统角色”。 添加站点系统角色向导将会打开。  
  
4.  在“常规”页上，指定站点系统服务器的一般设置。 向现有站点系统服务器添加软件更新点时，请验证以前配置的值。  
  
5.  在“系统角色选择”页上，从可用角色列表中选择“软件更新点”，然后单击“下一步”。  
  
6.  在“软件更新点”页上，验证站点服务器是否将在同步软件更新和下载软件更新文件时使用代理服务器，以及是否使用凭据来连接到代理服务器。 单击“下一步”。  
  
7.  在“活动设置”页上，单击“下一步”，然后单击“关闭”退出向导并创建非活动软件更新点。  
  
## 为安装的软件更新点站点系统配置 Windows Server 网络负载平衡群集  
  
#### 为安装的软件更新点站点系统配置 Windows Server 网络负载平衡群集  
  
1.  要为安装的软件更新点站点系统配置 Windows Server NLB 群集，请按照为站点系统上运行的操作系统部署 NLB 的说明进行操作。 对于 Windows Server 2008 和 Windows Server 2008 R2，请参阅 [Network Load Balancing Deployment Guide（网络负载平衡部署指南）](http://go.microsoft.com/fwlink/p/?LinkId=232840)。  
  
2.  验证 NLB 群集成功运行后，你可以将活动软件更新点配置为使用 NLB 群集。  
  
## 将活动软件更新点配置为使用 NLB 群集  
 使用下列过程将站点的活动软件更新点配置为使用 NLB 群集。  
  
#### 将活动软件更新点配置为使用 NLB 群集  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“管理”。  
  
2.  在“管理”工作区中，展开“站点配置”，并单击“服务器和站点系统角色”。  
  
3.  在“主页”选项卡上，单击“配置站点组件”，然后单击“软件更新点”。 软件更新点组件属性将打开。  
  
4.  在“常规”选项卡上，选择“为活动软件更新点使用网络负载平衡群集”。  
  
5.  
  
6.  单击“设置”并配置下列 NLB 设置：  
  
    1.  **NLB 地址类型**：选择“FQDN”。  
  
    2.  “Intranet FQDN 或 IP 地址”：输入在[Prepare the network environment for network load balanced software update point site systems](assetId:///07683847-1b69-40d2-9dbd-74dec415bef8#BKMK_PrepareNetworkForNLB)的第 6 步中创建的 FQDN。  
  
     单击"**确定**"。  
  
7.  单击“设置”，然后选择将“软件更新点连接帐户”配置为使用本主题 [To prepare the network environment for network load balanced software update point site systems](assetId:///07683847-1b69-40d2-9dbd-74dec415bef8#BKMK_PrepareNetwork) 过程的第 1 步中创建的 Windows 用户帐户。  
  
     选择“现有帐户”以指定以前配置为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 帐户的 Windows 用户帐户，或者选择“新帐户”以指定当前未配置为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 帐户的 Windows 用户帐户。 用户将显示在“管理”工作区内“安全”节点的“帐户”子文件夹中，名称为“软件更新点连接帐户”。 单击“确定”。  
  
8.  确定要用于活动软件更新点的通信设置，然后单击“确定”。  
  
## 请参阅  
 [Configuring Software Updates in Configuration Manager](assetId:///912bfec1-fd19-4f56-a840-4ecd643c541b)
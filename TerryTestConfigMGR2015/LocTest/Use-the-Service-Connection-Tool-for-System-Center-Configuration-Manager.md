---
title: "使用适用于 System Center Configuration Manager 的服务连接工具"
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
ms.assetid: 6e4964c5-43cb-4372-9a89-b62ae6a4775c
caps.latest.revision: 11
caps.handback.revision: 11
---
# 使用适用于 System Center Configuration Manager 的服务连接工具
当 Configuration Manager 站点系统服务器未连接到 Internet 但你仍想保持 Configuration Manager 的最新更新时，请使用**服务连接工具**。  
  
 该工具使你能够连接到 Configuration Manager 云服务以手动上载你层次结构的使用情况信息和下载更新。 必须上载使用情况数据才能启用云服务以为你的部署提供正确的更新。  
  
 **使用服务连接工具的先决条件：**  
  
-   已安装服务连接点，并将它设置为“脱机，按需连接”。  
  
-   该工具必须从命令提示符中运行。  
  
-   运行该工具的每个计算机（服务连接点计算机以及连接到 Internet 的计算机）必须是 x64 位系统并且必需安装以下软件：  
  
    -   **Visual C++ Redistributable** x86 和 x64 文件。   默认情况下，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 在承载服务连接点的计算机上安装 x64 版本。  
  
         若要下载 Visual C++ 文件的副本，请访问 Microsoft 下载中心的 [Visual C++ Redistributable Packages for Visual Studio 2013](http://www.microsoft.com/download/details.aspx?id=40784)。  
  
    -   .NET Framework 4.5.2 或更高版本。  
  
-   用于运行工具的帐户必须：
    -   在承载服务连接点的计算机上（工具在此计算机上运行）具有**本地管理员**权限。
    -   具有对站点数据库的**读取**权限。  
        
     
  
-   你将需要具有可存储文件和更新的足够可用空间的 U 盘，或需要另一种方法以在服务连接点计算机与有权访问 Internet 的计算机之间传输文件。 （此方案假设你的站点和托管计算机未直接连接到 Internet。）  
  
 **使用服务连接工具主要有三个步骤：**  
  
1.  **准备**：此步骤将使用情况数据放入 .cab 文件中并将其存储在 U 盘上（或指定的替代传输位置）。  
  
2.  **连接**：此步骤将使你在连接到 Internet 的远程计算机上运行该工具以上传数据和下载更新。  
  
3.  **导入**：此步骤将 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的更新导入你的站点，以便可以从 [!INCLUDE[cmconsole](../LocTest/includes/cmconsole_md.md)] 查看并安装更新。  

从版本 1606 开始，当连接到 Microsoft 时，可以一次性上传多个 .cab 文件（每个文件来自不同的层次结构），并指定代理服务器和代理服务器的用户。   

**若要上传多个 .cab 文件，请执行以下操作：**
 -  将从独立的层次结构中导出的每个 .cab 文件放在同一文件夹中。 每个文件的名称必须是唯一的，如有必要，可以手动重命名。
 -  然后，当运行命令将数据上传到 Microsoft 时，指定包含 .cab 文件的文件夹。 （在更新 1606 之前，每次仅可以从一个层次结构上传数据，并且此工具需要你指定文件夹中的 .cab 文件的名称。）
 -  然后，在层次结构的服务连接点上运行导入任务时，此工具仅自动导入该层次结构的数据。  
 
 **若要指定代理服务器，请执行以下操作：**  
 可以使用以下可选参数来指定代理服务器（有关使用这些参数的详细信息可在本主题的命令行参数部分中找到）：
  - **-proxyserveruri [FQDN_of_proxy_sever]** 使用此参数指定要用于此连接的代理服务器。 
  -  **-proxyusername [username]** 当必须为代理服务器指定用户时，请使用此参数。


  
## 使用服务连接工具  
 你可以在 **%path%/smssetup/tools/ServiceConnectionTool** 文件夹中的 Configuration Manager 安装媒体中找到服务连接工具 (**serviceconnectiontool.exe**)。  
  
 在此过程中，命令行示例使用了以下文件名和文件夹位置（你不需要使用这些路径和文件名，可以改为使用与你的环境和首选项匹配的其他选择）：  
  
-   用于存储数据以在服务器之间进行传输的 USB 记忆棒的路径：**D:\USB\\**  
  
-   包含从你的站点导出的数据的 .cab 文件的名称：**UsageData.cab**  
  
-   用于存储 Configuration Manager 的已下载更新以在服务器之间进行传输的空文件夹的名称：**UpdatePacks**  
  
 在承载服务连接点的计算机上：  
  
-   使用管理特权打开命令提示符，然后将目录更改为包含 **serviceconnectiontool.exe** 的位置。  
  
     默认情况下，你可以在 **%path%\smssetup/tools\ServiceConnectionTool** 文件夹中的 Configuration Manager 安装媒体中找到此工具。 此文件夹中的所有文件必须位于同一个文件夹中，这样服务连接工具才能工作。  
  
 运行以下命令时，该工具会准备包含使用情况信息的 .cab 文件并将它复制到你指定的位置。 .cab 文件中的数据基于站点配置为收集的诊断使用情况数据的级别。 （请参阅 [System Center Configuration Manager 的诊断和使用情况数据](../LocTest/Diagnostics-and-usage-data-for-System-Center-Configuration-Manager.md)）。  运行以下命令以创建 .cab 文件：  
  
-   **serviceconnectiontool.exe -prepare -usagedatadest D:\USB\UsageData.cab**  
  
 你还需要将 ServiceConnectionTool 文件夹及其所有内容复制到 U 盘中，或者采用其他方法使它在步骤 3 和 4 即将使用的计算机上可用。  
  
#### 若要使用服务连接点工具  
  
1.  在承载服务连接点的计算机上：  
  
    -   使用管理特权打开命令提示符，然后将目录更改为包含 **serviceconnectiontool.exe** 的位置。  
  
   
2.  运行以下命令以使工具准备包含使用情况信息的 .cab 文件并将其复制到指定的位置：  
  
    -   **serviceconnectiontool.exe -prepare -usagedatadest D:\USB\UsageData.cab**  
  
      如果同时上传多个层次结构中的 .cab 文件，则文件夹中的每个 .cab 文件的必须具有一个唯一的名称。 你可以手动重命名添加到该文件夹的文件。
      
      如果你想要查看收集并上传到 Configuration Manager 云服务的使用情况信息，请运行以下命令将相同的数据以 .csv 文件导出，然后可以使用像 Excel 之类的应用程序查看该文件：  
  
    -   **serviceconnectiontool.exe -export -dest D:\USB\UsageData.csv**  
  
3.  完成准备步骤后，将 U 盘移动到（或通过另一种方法将导出的数据传输到）有权访问 Internet 的计算机。  
  
4.  在可访问 Internet 的计算机上，使用管理特权打开命令提示符，然后将目录更改为包含工具 **serviceconnectiontool.exe** 的副本以及该文件夹中其他文件的位置。  
  
5.  运行以下命令以开始上载使用情况信息和下载 Configuration Manager 更新：  
  
    -   **serviceconnectiontool.exe -connect -usagedatasrc D:\USB\UsageData.cab -updatepackdest D:\USB\UpdatePacks**  
    
    有关此命令行的更多示例，请参阅本主题后的[命令行选项](../LocTest/Use-the-Service-Connection-Tool-for-System-Center-Configuration-Manager.md#bkmk_cmd)部分。 
  
    > [!NOTE]  
    >  运行该命令行以连接到 Configuration Manager 云服务时，可能会发生如下错误：  
    >   
    >  -   未经处理的异常：System.UnauthorizedAccessException：  
    >   
    >      对路径“C:\  
    >     Users\br\AppData\Local\Temp\extractmanifestcab\95F8A562.sql”的访问被拒绝。  
    >   
    >  你可以直接忽略此错误并关闭错误窗口，然后继续。  
  
6.  下载完 Configuration Manager 的更新后，将 U 盘移动到（或通过另一种方法将导出的数据传输到）承载服务连接点的计算机上。  
  
7.  在承载服务连接点的计算机上，使用管理特权打开命令提示符，将目录更改为包含 **serviceconnectiontool.exe** 的位置，然后运行以下命令：  
  
    -   **serviceconnectiontool.exe -import -updatepacksrc D:\USB\UpdatePacks**  
  
8.  导入完成后，可以关闭命令提示符。 （仅导入适用的层次结构的更新）。  
  
9. 打开 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台并导航至“管理” >“云服务” > “更新和服务”。 现在即可安装之前导入的更新。 有关安装更新的信息，请参阅[安装 System Center Configuration Manager 在控制台的更新](../LocTest/Install-in-console-updates-for-System-Center-Configuration-Manager.md)。  
  
## <a name="bkmk_cmd"></a> 命令行选项  
 若要查看服务连接点工具的帮助信息，请打开包含该工具的文件夹的命令提示符并运行命令：**serviceconnectiontool.exe**。  
  
|命令行选项|详细信息|  
|---------------------------|-------------|  
|**-prepare -usagedatadest [drive:][path][filename.cab]**|此命令会将当前的使用情况数据存储于 .cab 文件中。<br /><br /> 在承载服务连接点的服务器上以**本地管理员**身份运行此命令。<br /><br /> 示例：**-prepare -usagedatadest D:\USB\Usagedata.cab**|    
|**-connect -usagedatasrc [drive:][path] -updatepackdest [drive:][path] -proxyserveruri [FQDN of proxy server] -proxyusername [username]** <br /> <br /> 如果使用 1606 之前的 Configuration Manager 版本，则必须指定 .cab 文件的名称，并且不能使用代理服务器的选项。  支持的命令参数是： <br /> **-connect -usagedatasrc [drive:][path][filename] -updatepackdest [drive:][path]** |此命令连接到 Configuration Manager 云服务以从指定位置上传使用情况数据 .cab 文件并下载可用的更新包和控制台内容。 代理服务器的选项是可选选项。<br /><br /> 在可连接到 Internet 的计算机上以**本地管理员**身份运行此命令。<br /><br /> 连接时不使用代理服务器的示例：**-connect -usagedatasrc D:\USB\ -updatepackdest D:\USB\UpdatePacks** <br /><br /> 连接时使用代理服务器的示例：**-connect -usagedatasrc D:\USB\Usagedata.cab -updatepackdest D:\USB\UpdatePacks -proxyserveruri itgproxy.redmond.corp.microsoft.com -proxyusername Meg** <br /><br /> 如果使用 1606 之前的版本，则必须为 .cab 文件指定文件名称，并且不能指定代理服务器。 使用以下示例命令行：**-connect -usagedatasrc D:\USB\Usagedata.cab -updatepackdest D:\USB\UpdatePacks**|      
|**-import -updatepacksrc [drive:][path]**|此命令会将之前下载的更新包和控制台内容导入到 Configuration Manager 控制台中。<br /><br /> 在承载服务连接点的服务器上以**本地管理员**身份运行此命令。<br /><br /> 示例：**-import -updatepacksrc D:\USB\UpdatePacks**|  
|**-export -dest [drive:][path][filename.csv]**|此命令会将使用情况数据导出为 .csv 文件，然后你可以进行查看。<br /><br /> 在承载服务连接点的服务器上以**本地管理员**身份运行此命令。<br /><br /> 示例：**-export -dest D:\USB\usagedata.csv**|  
  
## 另请参阅  
 [System Center Configuration Manager 的更新](../LocTest/Updates-for-System-Center-Configuration-Manager.md)
 
 
 
 
 
 
 
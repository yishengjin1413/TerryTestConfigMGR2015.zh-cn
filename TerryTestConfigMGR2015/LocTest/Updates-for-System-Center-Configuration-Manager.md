---
title: "System Center Configuration Manager 的更新"
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
ms.assetid: 3a832943-580a-4a40-b454-961d0854ac2b
caps.latest.revision: 51
caps.handback.revision: 43
translationtype: Human Translation
---
# System Center Configuration Manager 的更新
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 使用称为**更新和服务**的控制台中服务方法，可轻松为你的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 基础结构找到并安装建议的更新。此控制台中服务方法由带外更新补充，例如适用于需要解决其环境特定问题的客户的修补程序。  
  
 **以下主题可帮助你了解如何查找和安装 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 的不同更新类型：**  
  
-   [为 System Center Configuration Manager 安装控制台内部更新](../LocTest/Install-in-console-updates-for-System-Center-Configuration-Manager.md)  
  
-   [使用适用于 System Center Configuration Manager 的服务连接工具](../LocTest/Use-the-Service-Connection-Tool-for-System-Center-Configuration-Manager.md)  
  
-   [使用更新注册工具将修补程序导入 System Center Configuration Manager](../LocTest/Use-the-Update-Registration-Tool-to-import-hotfixes-to-System-Center-Configuration-Manager.md)  
  
-   [使用修补程序安装程序来安装 System Center Configuration Manager 的更新](../LocTest/Use-the-Hotfix-Installer-to-install-updates-for-System-Center-Configuration-Manager.md)  
  
-   [用于从 System Center Configuration Manager 版本 1511 更新为 1602 的清单](../Topic/Checklist%20for%20updating%20from%20System%20Center%20Configuration%20Manager%20version%201511%20to%201602.md)  
  
## <a name="bkmk_Baselines"></a>基准和更新版本  
System Center Configuration Manager 当前分支的初始版本为版本 1511。 以下是基准版本：  
  
-   在新的层次结构中安装新站点时，请使用最新的基准版本。  
  
-   必须使用基准版本从 System Center 2012 Configuration Manager 升级。  
  
-   我们会定期发布新的基准版本。 使用较新的基准版本来安装新的层次结构时，请避免先安装原始 1511 基准版本，再升级基础结构。  
  
安装基准版本之后，其他版本的 Configuration Manager 都可用作控制台中更新。 控制台中更新可将你的基础结构更新为最新版本的 Configuration Manager。  
  
-   请安装控制台中更新来更新顶层站点的版本。  
  
-   在管理中心站点上安装的更新将自动安装到子主站点，除非主站点中配置的维护窗口阻止。  
  
-   必须手动在控制台中将辅助站点更新到新的更新版本。  
  
安装更新时，更新会将该版本的安装文件存储在站点服务器上名为 CD.Latest 的文件夹中。 有关这些文件的详细信息，请参阅 [System Center Configuration Manager 的 CD.Latest 文件夹](../LocTest/The-CD.Latest-folder-for-System-Center-Configuration-Manager.md)。  
  
-   可以使用 CD.Latest 文件夹中的文件来进行站点恢复，以及在不再运行基准版本的层次结构中安装其他站点。  
  
-   不能使用 CD.Latest 中的安装文件来安装新层次结构的首个站点，或从 System Center 2012 Configuration Manager 升级站点。  
  
Configuration Manager 的某些更新可用作现有基础结构的控制台中更新版本，以及新的基准版本。  
  
以下版本的 Configuration Manager 可用作基准和\/或更新：  
  
|版本|可用日期|Baseline|控制台中更新|  
|------|--------|------------|----------|  
|**1511**<br /><br />5.00.8325.1000|2015 年 12 月 8 日|是|否|  
|**1602**<br /><br />5.00.8355.1000|2016 年 3 月 11 日|否|是|  
  
若要检查 Configuration Manager 站点的版本，请在控制台中，转至控制台左上角的**“关于 System Center Configuration Manager”**，新站点和控制台版本将会显示在那里。  
  
## <a name="bkmk_inconsole"></a>控制台中更新和服务  
使用 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 的生产就绪安装（也称为当前分支）时，可以通过“更新和服务”渠道提供你安装的大部分更新。 此方法标识、下载并提供适用于你当前基础结构版本和配置的更新，并且仅包含 Microsoft 针对所有客户建议的更新。 其中包括:  
  
-   新版本，如版本 1602  
  
-   更新，包括当前版本的新功能  
  
-   修补程序，适用于你的 Configuration Manager 版本，所有客户都应安装  
  
控制台中更新可提供更强的稳定性并解决常见的问题。 它们可替代早期产品版本的更新类型，如服务包、累积更新、适用于所有客户的修补程序以及 Extension for Microsoft Intune。 这些更新可应用于以下一种或多种设备：  
  
-   主站点和管理中心站点服务器  
  
-   站点系统角色和站点系统服务器  
  
-   SMS 提供程序的实例  
  
-   [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台  
  
-   [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端  
  
同步服务连接点站点系统角色与 Microsoft 云服务时，Configuration Manager 会为你发现新的更新：  
  
-   当服务连接点处于联机模式时，站点将每天与 Microsoft 同步，以自动确定适用于你的基础结构的新更新。 有关详细信息，请参阅 [为 System Center Configuration Manager 安装控制台内部更新](../LocTest/Install-in-console-updates-for-System-Center-Configuration-Manager.md)。  
  
-   当服务连接点处于脱机模式时，请使用服务连接工具手动与 Microsoft 云同步。 有关详细信息，请参阅 [使用适用于 System Center Configuration Manager 的服务连接工具](../LocTest/Use-the-Service-Connection-Tool-for-System-Center-Configuration-Manager.md)。  
  
-   凭借控制台中更新，无需再单独查找和安装单个更新、服务包和新功能。  
  
-   只安装选择的控制台中更新，并且安装某些更新时，可以选择要启用和使用的各个功能。 有关详细信息，请参阅 [Enable optional features from updates](../LocTest/Install-in-console-updates-for-System-Center-Configuration-Manager.md#bkmk_options)。  
  
安装控制台中更新时：  
  
-   它将自动运行先决条件检查。 也可以先运行此检查，再开始安装。  
  
-   它自动在管理中心站点（如果有）和主站点上安装。 你可以通过使用 [Service Windows for site servers](../LocTest/Install-in-console-updates-for-System-Center-Configuration-Manager.md#bkmk_ServiceWindow) 控制允许每个主站点服务器更新其基础结构的时间。  
  
-   站点服务器更新后，受影响的所有站点系统角色 （包括 SMS 提供程序的实例）会自动更新。 在站点安装更新后，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台还会提示控制台用户更新控制台。  
  
-   如果更新包括 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端，还会提供在预生产中测试更新或立即将更新应用到所有客户端的选项。  
  
-   更新主站点后，辅助站点不会自动更新。 而必须启动辅助站点更新。  
  
> [!NOTE]  
> 生产版 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]（当前分支）和技术预览版 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 是不同的版本。 因此，当前分支版本的更新不适用于技术预览版 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]。    同样，技术预览的更新也不适用于当前分支版本。  
  
## <a name="bkmk_outofband"></a>带外修补程序  
一些修补程序在发布时的可用性受到限制，用于解决特定的问题，或者虽然适用于所有客户，但不能使用控制台中方法进行安装。 这些修补程序在带外提供，Microsoft 云服务不会发现。  
  
一般而言，可从 Microsoft 客户支持服务、知识库文章或 [System Center Configuration Manager Team blog](https://blogs.technet.microsoft.com/configmgrteam)（System Center Configuration Manager 团队博客）了解带外修复程序，以寻求修复或解决 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 部署问题的方法。  
  
请使用以下两种方法中的一种手动安装这些修补程序：  
  
-   **更新注册工具：**使用此工具，可手动将修补程序导入 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台，然后可以根据需要在控制台中安装自动发现的控制台中更新。 此方法适用于使用以下文件名结构的更新：**.update.exe**.  此类修补程序的完整文件名类似于：**\<产品\>\-\<产品版本\>\-\<知识库文章 ID\>\-ConfigMgr.Update.exe**  
  
    有关详细信息，请参阅[使用更新注册工具将修补程序导入 System Center Configuration Manager](../LocTest/Use-the-Update-Registration-Tool-to-import-hotfixes-to-System-Center-Configuration-Manager.md)。  
  
-   **修补程序安装工具：**此工具用于手动安装无法使用控制台中方法安装的修补程序。 此方法用于使用以下文件名结构的修补程序：**\<产品\>\-\<产品版本\>\-\<知识库文章 ID\>\-\<平台\>\-\<语言\>.exe**  
  
    有关详细信息，请参阅[使用修补程序安装程序来安装 System Center Configuration Manager 的更新](../LocTest/Use-the-Hotfix-Installer-to-install-updates-for-System-Center-Configuration-Manager.md)。  
  
## 请参阅
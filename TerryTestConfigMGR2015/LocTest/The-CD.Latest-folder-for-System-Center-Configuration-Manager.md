---
title: "System Center Configuration Manager 的 CD.Latest 文件夹"
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
ms.assetid: 8db92d67-5d9c-4e9c-80d0-ae6fa0dd4817
caps.latest.revision: 6
caps.handback.revision: 6
translationtype: Human Translation
---
# System Center Configuration Manager 的 CD.Latest 文件夹
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 引入新的更新过程，该过程从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台内为产品提供更新。 为了支持这种更新 Configuration Manager 的新方法，创建了一个名为 **CD.Latest** 的新文件夹，其中包含用于站点的更新版本的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 安装文件副本。  

从更新 1606 开始，CD.Latest 文件夹包含一个名为 **Redist** 的文件夹，该文件夹包含安装程序下载和使用的可再发行文件。 这些文件与在该 CD.Latest 文件夹中找到的 Configuration Manager 文件的版本相匹配。 当从 CD.Latest 文件夹运行安装程序时，必须使用与该安装程序的版本相匹配的文件。 为此，可以指示安装程序从 Microsoft 下载新文件和当前文件，或指示安装程序使用包含在 CD.Latest 文件夹中的 Redist 文件夹中的文件。 

> [!TIP]
> 如果尚未安装版本 1606，则必须确保使用的 redist 文件是最新文件。 如果你最近没有下载 redist 文件，请计划允许安装程序从 Microsoft 执行该操作。   
  
 下面是在管理中心站点或主站点服务器上创建或更新 CD.Latest 文件夹的方案：  
  
-   从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中安装更新或修补程序：在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 安装文件夹中创建或更新该文件夹。  
  
-   运行内置 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 备份任务：在指定备份文件夹位置下创建或更新该文件夹。  
  
 对于以下各项支出 CD.Latest 文件夹中的源文件：  
  
1.  **备份和恢复：**CD.Latest 文件夹包含用于在站点恢复过程中重新安装站点的源文件。 若要恢复 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点，站点备份必须包括 CD.Latest 文件夹（内置站点备份任务会在站点备份中自动包括此文件夹）。  
  
    -   **当你在站点恢复中重新安装站点时，**会从包含在你的备份中的 CD.Latest 文件夹安装站点。 此操作会使用与你的站点备份和站点数据库匹配的文件版本安装站点。  
  
        > [!IMPORTANT]  
        >  如果你没有正确的可用 CD.Latest 文件夹及其内容，则无法恢复站点，必须重新安装它。  
  
    -   当你没有 CD.Latest 文件夹，但是具有正常运行的子主站点或管理中心站点时，可以将该站点用作站点恢复的引用站点。  
  
2.  **安装子主站点：**要在安装了一个或多个控制台内部更新的管理中心站点下安装新的子主站点，必须使用来自管理中心站点的 CD.Latest 文件夹中的安装程序和源文件。 安装程序从来自管理中心站点的 CD.Latest 文件夹副本运行时，它使用与管理中心站点版本匹配的安装源文件。 有关详细信息，请参阅[使用安装向导来安装站点](../LocTest/Use-the-Setup-Wizard-to-install-System-Center-Configuration-Manager-sites.md)。  
  
3.  **扩展独立主站点：**要通过安装新的管理中心站点来扩展独立主站点时，必须使用来自主站点的 CD.Latest 文件夹中的安装程序和源文件来安装新的管理中心站点。 从来自主站点的 CD.Latest 文件夹副本运行时，它使用与主站点版本匹配的安装源文件。 有关详细信息，请参阅[使用安装向导来安装站点](../LocTest/Use-the-Setup-Wizard-to-install-System-Center-Configuration-Manager-sites.md)中的[扩展独立主站点](../LocTest/Use-the-Setup-Wizard-to-install-System-Center-Configuration-Manager-sites.md#bkmk_expand))
  
> [!IMPORTANT]  
>  对于以下各项不支持更新后的 CD.Latest 源文件：  
>   
>  -   为新层次结构安装新站点  
> -   将 [!INCLUDE[cm5long](../LocTest/includes/cm5long_md.md)] 站点升级到 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]
---
title: "System Center Configuration Manager 应用程序的管理任务"
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
ms.assetid: c4041e21-21ff-4d95-ab05-14007e0047cf
caps.latest.revision: 8
caps.handback.revision: 5
author: barlanmsft
translationtype: Human Translation
---
# System Center Configuration Manager 应用程序的管理任务
使用下列部分中的信息来帮助你管理 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 应用程序和部署类型。  
  
-   [如何管理应用程序](#BKMK_Applicat)  
  
-   [如何管理部署类型](#BKMK_DeplType)  
  
 有关如何创建应用程序和部署类型的信息，请参阅 [如何使用 System Center Configuration Manager 创建应用程序](../LocTest/How-to-create-applications-with-System-Center-Configuration-Manager.md)。  
  
> [!IMPORTANT]  
>  取决于应用程序类型或部署类型，某些管理点可能不可用。  
  
##  <a name="BKMK_Applicat"></a> 如何管理应用程序  
 在“软件库”工作区中，展开“应用程序管理”，选择“应用程序”，选择要管理的应用程序，然后选择管理任务。  
  
 使用下表以详细了解可能需要一些信息才能让你选择的管理任务。  
  
|任务|详细信息|更多信息|  
|--------|----------|----------|  
|**管理访问帐户**|打开“管理访问帐户”对话框，在其中你可以为与所选应用程序关联的内容指定允许的访问级别。||  
|**创建预留内容文件**|打开“创建预留的内容文件向导”，它可帮助你管理将内容分发到远程分发点的过程。 在计划和限制未能为远程分发点提供有效的解决方案时，你可以在分发点上预留内容。|请参阅[为 System Center Configuration Manager 管理内容和内容基础结构](../LocTest/Manage-content-and-content-infrastructure-for-System-Center-Configuration-Manager.md)。|  
|**修订版本历史记录**|打开“应用程序修订版本历史记录”对话框，它可让你查看对此应用程序所做的修订的属性、删除旧的应用程序修订版本和还原此应用程序的旧版本。|请参阅[如何在 System Center Configuration Manager 中修订和取代应用程序](../LocTest/How-to-revise-and-supersede-applications-in-System-Center-Configuration-Manager.md)。|  
|**创建部署类型**|打开“创建部署类型向导”，它可让你将新的部署类型添加到所选的应用程序中。|请参阅[如何使用 System Center Configuration Manager 创建应用程序](../LocTest/How-to-create-applications-with-System-Center-Configuration-Manager.md)。|  
|**更新统计信息**|更新在“监视”工作区的“部署”节点中显示的、有关此应用程序的部署的信息。|请参阅[监视 System Center Configuration Manager 控制台中的应用程序](../LocTest/Monitor-applications-from-the-System-Center-Configuration-Manager-console.md)。|  
|**恢复**|此选项恢复以前使用“停用”管理任务停用的应用程序。|无更多信息。|  
|**停用**|在停用某应用程序时，它不能再用于部署，但不会删除此应用程序及其任何部署。 也不会删除在客户端计算机上安装的此应用程序的现有副本。 将在 60 天后从 Configuration Manager 中删除对应用程序的任何修订。 但是，不会删除此应用程序的任何已安装的副本。 **Important:**  若要删除应用程序，必须先停用应用程序，删除任何部署，删除其他部署对它的引用，然后删除其所有修订版本。|请参阅[如何在 System Center Configuration Manager 中修订和取代应用程序](../LocTest/How-to-revise-and-supersede-applications-in-System-Center-Configuration-Manager.md)。|  
|**导出**|打开“导出应用程序向导”，它可让你将所选的应用程序导出为 .zip 文件，然后你可以将其存档或安装到另一个站点上。 如果选择导出应用程序内容，则会创建一个包含此内容的文件夹。<br /><br /> 还可以导出应用程序依赖关系、取代关系和条件以及应用程序及其依赖关系的内容。 **Tip:**  Windows PowerShell cmdlet **Export\-CMApplication** 执行相同的功能。 有关详细信息，请参阅 [!INCLUDE[cm5long](../LocTest/includes/cm5long_md.md)] SP1 Cmdlet 参考文档中的 [http:\/\/go.microsoft.com\/fwlink\/p\/?LinkID\=258880](http://go.microsoft.com/fwlink/p/?LinkID=258880)。||  
|**删除**|删除当前所选的应用程序。 **Note:**  在下列情况下无法删除某应用程序：其他应用程序依赖它，它具有活动的部署，或者它具有依赖的任务序列。||  
|**模拟部署**|打开“模拟应用程序部署向导”，在其中你无需安装或卸载应用程序就能测试将应用程序部署到计算机的结果。|请参阅[如何使用System Center Configuration Manager 模拟应用程序部署](../LocTest/How-to-simulate-application-deployments-with-System-Center-Configuration-Manager.md)。|  
|**部署**|打开“部署软件向导”，在其中你可以将所选的应用程序部署到层次结构中的一组计算机。|请参阅[如何使用 System Center Configuration Manager 部署应用程序](../LocTest/How-to-deploy-applications-with-System-Center-Configuration-Manager.md)。|  
|**分发内容**|打开“分发内容向导”，在其中你可以将所选应用程序的内容复制到层次结构中的分发点。|请参阅[为 System Center Configuration Manager 管理内容和内容基础结构](../LocTest/Manage-content-and-content-infrastructure-for-System-Center-Configuration-Manager.md)。|  
|**查看关系**|显示一幅图形，其中显示了所选应用程序与其他应用程序的关系。 选择以下选项之一：<br /><br /> -   “依赖关系”\- 显示依赖所选应用程序的应用程序，以及所选应用程序依赖的应用程序。<br />-   “取代”\- 显示被取代的应用程序，以及取代所选项目的应用程序。<br />-   “全局条件”\- 显示此应用程序引用的全局条件。|请参阅[如何在 System Center Configuration Manager 中修订和取代应用程序](../LocTest/How-to-revise-and-supersede-applications-in-System-Center-Configuration-Manager.md)。<br /><br /> 请参阅[如何在 System Center Configuration Manager 中创建全局条件](../LocTest/How-to-create-global-conditions-in-System-Center-Configuration-Manager.md)。|  
  
##  <a name="BKMK_DeplType"></a> 如何管理部署类型  
 在“软件库”工作区中，展开“应用程序管理”，选择“应用程序”，选择包含要管理的部署类型的应用程序，然后，在详细信息窗格中，单击“部署类型”选项卡，选择要管理的部署类型，然后选择管理任务。  
  
 使用下表以详细了解可能需要一些信息才能让你选择的管理任务。  
  
|任务|详细信息|  
|--------|----------|  
|**提高优先级**|提高所选部署类型的优先级。 部署类型按次序接受评估。 在某种部署类型符合指定的要求时，将会运行它，之后不会评估优先级列表上的其他部署类型。|  
|**降低优先级**|降低所选部署类型的优先级。|  
|删除|删除所选的部署类型。 **Important:**  如果另一个应用程序中的部署类型正在引用某部署类型，则无法删除此部署类型。 若要删除某部署类型，则必须删除在其他部署类型中包含的、此部署类型的任何依赖关系。 此外，如果任何应用程序包含的部署类型引用了你要删除的部署类型，则还必须删除这些应用程序以前的修订版本。|  
|**更新内容**|刷新所选部署类型的内容。<br /><br /> 在为包含虚拟应用程序的部署类型启动此向导时，会启动“更新内容向导”。 该向导可让你修改所选虚拟应用程序的发布选项和要求规则。 有关详细信息，请参阅 [如何使用 System Center Configuration Manager 创建应用程序](../LocTest/How-to-create-applications-with-System-Center-Configuration-Manager.md)。 **Important:**  在刷新部署类型的内容时，会创建此应用程序的新的修订版本。 这可能会导致用新的应用程序来更新客户端设备。|  
  
## 请参阅  
 [使用 System Center Configuration Manager 管理和保护应用](../LocTest/Manage-and-protect-apps-with-System-Center-Configuration-Manager.md)
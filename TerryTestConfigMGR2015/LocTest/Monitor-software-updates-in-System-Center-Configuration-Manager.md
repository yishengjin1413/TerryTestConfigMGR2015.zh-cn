---
title: "在 System Center Configuration Manager 中监视软件更新"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-sum
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 9afd7b0f-5c8e-48bc-9a65-1f7d74103688
caps.latest.revision: 5
caps.handback.revision: 4
translationtype: Human Translation
---
# 在 System Center Configuration Manager 中监视软件更新
为了帮助你监视软件更新对象、过程和符合性信息，[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 控制台提供下列项目：  
  
-   [软件更新的警报](#BKMK_SUAlerts)  
  
-   [软件更新同步状态](#BKMK_SUSyncStatus)  
  
-   [软件更新部署状态](#BKMK_SUDeployStatus)  
  
-   [软件更新报表](#BKMK_SUReports)  
  
-   [监视内容](#BKMK_MonitorContent)  
  
    -   [内容状态监视](#BKMK_ContentStatus)  
  
    -   [分发点组状态](#BKMK_DPGroupStatus)  
  
    -   [分发点配置状态](#BKMK_DPConfigStatus)  
  
##  <a name="BKMK_SUAlerts"></a> 软件更新的警报  
 可以配置软件更新的警报，以便在软件更新部署的符合性级别低于已配置的百分比时通知管理用户。 可以在下列位置中配置软件更新部署的警报：  
  
-   ADR 设置：可以在“自动部署规则向导”中和 ADR 的属性中配置警报设置。  
  
-   部署设置：可以在“部署软件更新向导”中和部署属性中配置警报设置。  
  
 配置警报设置后，如果出现指定的条件，则 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 会生成警报。 可以在下列位置中查看软件更新警报：  
  
1.  在“软件库”工作区的“软件更新”节点中查看最新警报。  
  
2.  在“监视”工作区的“警报”节点中管理已配置的警报。  
  
##  <a name="BKMK_SUSyncStatus"></a> 软件更新同步状态  
 启动同步过程之后，可以通过 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台监视层次结构中的所有软件更新点的同步过程。 使用下列过程来监视软件更新同步过程。  
  
#### 监视软件更新同步过程  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“监视”。  
  
2.  在“监视”工作区中，单击“软件更新点同步状态”。  
  
     [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 层次结构中的软件更新点显示在结果窗格中。 从此视图中，你可以监视所有软件更新点的同步状态。 若要了解有关同步过程的更多详细信息，请查看每台站点服务器上的 \<*ConfigMgrInstallationPath*\>\\Logs 中的 wsyncmgr.log 文件。  
  
##  <a name="BKMK_SUDeployStatus"></a> 软件更新部署状态  
 在软件更新组中部署软件更新或部署单个软件更新之后，可以监视部署状态。 使用下列过程来监视软件更新组或软件更新的部署状态。  
  
#### 监视部署状态  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“监视”。  
  
2.  在“监视”工作区中，单击“部署”。  
  
3.  单击要监视其部署状态的软件更新组或软件更新。  
  
4.  在“主页”选项卡上的“部署”组中，单击“查看状态”。  
  
##  <a name="BKMK_SUReports"></a> 软件更新报表  
 软件更新的状态消息提供了有关软件更新的符合性的信息，以及有关软件更新部署的评估和强制状态的信息。 可以运行软件更新报表以显示这些状态消息。 可以使用 30 多个预定义的软件更新报表。 它们分为几个类别，可用于报告有关软件更新和部署的特定信息。 除了使用预先配置的报表之外，还可以按照企业的需求创建自定义软件更新报表。 有关详细信息，请参阅 [System Center Configuration Manager 中报告的操作和维护](../LocTest/Operations-and-maintenance-for-reporting-in-System-Center-Configuration-Manager.md)。  
  
##  <a name="BKMK_MonitorContent"></a> 监视内容  
 可以在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中监视内容，以查看与关联的分发点相关的所有包类型的状态。 这可以包括包中的内容的内容验证状态、分配给特定分发点组的内容的状态、分配给分发点的内容的状态和每个分发点的可选功能（内容验证、PXE 和多播）的状态。  
  
###  <a name="BKMK_ContentStatus"></a> 内容状态监视  
 “监视”工作区中的“内容状态”节点提供有关内容包的信息。 可以查看有关包的常规信息、包的分发状态和有关包的详细状态信息。 使用下列过程来查看内容状态。  
  
##### 监视内容状态  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“监视”。  
  
2.  在“监视”工作区中，展开“分发状态”，然后单击“内容状态”。 此时会显示包。  
  
3.  选择要查看其详细状态信息的包。  
  
4.  在“主页”选项卡上，单击“查看状态”。 此时会显示包的详细状态信息。  
  
###  <a name="BKMK_DPGroupStatus"></a> 分发点组状态  
 “监视”工作区中的“分发点组状态”节点提供有关分发点组的信息。 可以查看有关分发点组的常规信息（例如分发点组状态和符合性比率），以及分发点组的详细状态信息。 使用下列过程来查看分发点组状态。  
  
##### 监视分发点组状态  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“监视”。  
  
2.  在“监视”工作区中，展开“分发状态”，然后单击“分发点组状态”。 此时会显示分发点组。  
  
3.  选择要查看其详细状态信息的分发点组。  
  
4.  在“主页”选项卡上，单击“查看状态”。 此时会显示分发点组的详细状态信息。  
  
###  <a name="BKMK_DPConfigStatus"></a> 分发点配置状态  
 “监视”工作区中的“分发点配置状态”节点提供有关分发点的信息。 可以查看为分发点启用的属性，例如 PXE、多播和内容验证。 还可以查看分发点的详细状态信息。 使用下列过程来查看分发点配置状态。  
  
##### 监视分发点配置状态  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“监视”。  
  
2.  在“监视”工作区中，展开“分发状态”，然后单击“分发点配置状态”。 此时会显示分发点。  
  
3.  选择要查看其分发点状态信息的分发点。  
  
4.  在结果窗格中，单击“详细信息”选项卡。 此时会显示分发点的状态信息。  
  
## 请参阅  
 [在 System Center Configuration Manager 中部署并管理软件更新](../LocTest/Deploy-and-manage-software-updates-in-System-Center-Configuration-Manager.md)
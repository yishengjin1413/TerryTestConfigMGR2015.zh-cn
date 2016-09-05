---
title: "System Center Configuration Manager 的站点组件"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-other
ms.tgt_pltfrm: na
ms.topic: get-started-article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 5fccbbeb-0faa-4943-83c2-e67db62d392d
caps.latest.revision: 9
caps.handback.revision: 7
---
# System Center Configuration Manager 的站点组件
在每个 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 站点上，均可以配置站点组件来修改站点系统角色和站点状态报告的行为。 站点组件配置适用于站点以及站点中适用的站点系统角色的每个实例。  
  
## 有关站点组件  
 在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中查看时，各种站点组件的大多选项均一目了然。 但是，以下详细信息可帮助解释一些更复杂的配置或将指引你找到对其进行说明的附加内容：  
  
 **软件分发：**  
  
-   **内容分发设置：**可以配置设置，该设置可修改站点服务器将内容传输到其分发点的方式。 当增加用于并发分发设置的值时，内容分发可以使用更多的网络带宽。  
  
-   **网络访问帐户：**有关配置和使用网络访问帐户的信息，请参阅 [System Center Configuration Manager 中内容管理的基本概念](../LocTest/Fundamental-concepts-for-content-management-in-System-Center-Configuration-Manager.md) 中的 [Network Access Account](../LocTest/Fundamental-concepts-for-content-management-in-System-Center-Configuration-Manager.md#bkmk_NAA)  
  
 **软件更新点：**  
  
-   有关软件更新点组件的配置选项的信息，请参阅 [在 System Center Configuration Manager 中配置软件更新](../LocTest/Configure-software-updates-in-System-Center-Configuration-Manager.md)。  
  
 **管理点：**  
  
 **状态报告：**  
  
-   这些设置直接配置详细级别（包括在来自站点和客户端的状态报告中）。  
  
 **电子邮件通知：**  
  
-   指定帐户和电子邮件服务器的详细信息以启用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 发送电子邮件警报通知。  
  
 **集合成员身份评估：**  
  
-   使用此任务来设置以增量方式对集合成员身份进行评估的频率。 增量评估仅使用新资源或已更改资源来更新集合成员身份。  
  
#### 编辑站点上的站点组件  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“管理”\>“站点配置”\>“站点”，然后选择具备将要配置的站点组件的站点。  
  
2.  在“主页”选项卡上的“设置”组中，单击“配置站点组件”，然后选择要配置的站点组件。  
  
##  <a name="BKMK_ServiceMgr"></a> 使用 Configuration Manager 服务管理器管理站点组件  
 可使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 服务管理器来控制 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 服务并查看任何 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 服务或工作线程（统称为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 组件）的状态：  
  
-   [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 组件可在任何站点系统上运行。  
  
-   管理组件的方式与你在 Windows 中管理服务的方式相同；你可以启动、停止、暂停、恢复或查询 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 组件。  
  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 服务会在其有要执行的操作时（通常，在将配置文件写入组件的收件箱时）运行。 如果必须确定操作中涉及的组件，你可以使用 **[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 服务管理器**来操作各种 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 服务和线程，然后查看 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的行为因此所发生的变化。 例如，你可以一次停止一个 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 服务，直至排除了特定响应为止。 通过这样做，你将能够确定哪个服务导致了该行为。  
  
> [!TIP]  
>  可以使用下列过程来操作 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 组件操作。  
  
#### 使用 Configuration Manager 服务管理器  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“监视”\>“系统状态”，然后单击“组件状态”。  
  
2.  在“主页”选项卡上的“组件”组中，单击“启动”，然后选择“Configuration Manager 服务管理器”。  
  
3.  当 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 服务管理器打开时，连接到要管理的站点。  
  
     如果看不到要管理的站点，请单击“站点”，单击“连接”，然后输入正确的站点的站点服务器的名称。  
  
4.  展开站点并导航到“组件”或“服务器”，具体情况视你要管理的组件位于何处而定。  
  
5.  在右侧窗格中选择一个或多个组件，然后在“组件”菜单上单击“查询”以更新所选组件的状态。  
  
6.  更新了组件的状态后，使用“组件”菜单上四个基于操作的选项之一来修改组件操作。 请求操作之后，你必须查询组件以显示组件的新状态。  
  
7.  修改完组件的操作状态后，关闭 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 服务管理器。  
  
## 请参阅  
 [配置 System Center Configuration Manager 的站点和层次结构](../LocTest/Configure-sites-and-hierarchies-for-System-Center-Configuration-Manager.md)
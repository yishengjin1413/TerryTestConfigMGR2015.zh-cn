---
title: "配置源层次结构和源站点以迁移到 System Center Configuration Manager"
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
ms.assetid: ccce7cb5-e18f-4337-8adf-2018edca3c00
caps.latest.revision: 5
caps.handback.revision: 4
---
# 配置源层次结构和源站点以迁移到 System Center Configuration Manager
为了能够将数据迁移到 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 环境，你必须配置支持的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 源层次结构，以及该层次结构中一个或多个包含要迁移的数据的源站点。  
  
> [!NOTE]  
>  迁移的操作在目标层次结构中的顶层站点上运行。 如果在使用连接到主子站点的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台时配置迁移，你必须留出时间让配置复制到管理中心站点，开始运行，然后将状态复制回连接到的主站点。  
  
 使用下列部分中的信息和过程来指定源层次结构以及添加其他源站点。 完成这些过程之后，你可以创建迁移作业，并开始将数据从源层次结构迁移到目标层次结构。  
  
-   [为迁移指定源层次结构](#BKBM_ConfigSrcHierarchy)  
  
-   [确定源层次结构的其他源站点](#BKBM_ConfigSrcSites)  
  
##  <a name="BKBM_ConfigSrcHierarchy"></a> 为迁移指定源层次结构  
 要将数据迁移到目标层次结构，你必须指定支持的源层次结构，其中包含要迁移的数据。 默认情况下，该层次结构的顶层站点成为源层次结构的源站点。 如果从 [!INCLUDE[cm4short](../LocTest/includes/cm4short_md.md)] 层次结构中迁移，在从初始源站点中收集了数据后，你可以随后为迁移配置其他源站点。 如果从 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 或 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 层次结构中迁移，则不必配置其他源站点以从源层次结构中迁移数据。 这是因为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的这些版本使用在源层次结构的顶层站点可用的共享数据库。 共享数据库包含你可以迁移的所有信息。  
  
 使用下列过程来为迁移指定源层次结构以及确定 [!INCLUDE[cm4short](../LocTest/includes/cm4short_md.md)] 层次结构中的其他源站点。  
  
 使用连接到目标层次结构的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台执行此过程。  
  
#### 配置源层次结构  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“管理”。  
  
2.  在“管理”工作区中，展开“迁移”，然后单击“源层次结构”。  
  
3.  在“主页”选项卡上的“迁移”组中，单击“指定源层次结构”。  
  
4.  在“指定源层次结构”对话框中，为“源层次结构”选择“新源层次结构”。  
  
5.  对于“顶级 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点服务器”，输入受支持源层次结构的首要网站的名称或 IP 地址。  
  
6.  指定具有下列权限的源站点访问帐户：  
  
    -   源站点帐户：针对源层次结构中指定顶层站点的 SMS 提供程序的“读取”权限。  
  
    -   源站点数据库帐户：针对源层次结构中指定顶层站点的 SQL Server 数据库的“读取”和“执行”权限。  
  
     如果指定使用计算机帐户，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将使用目标层次结构的顶层站点的计算机帐户。 对于此选项，请确保此帐户是源层次结构的顶层站点所在域中“分布式 COM 用户”安全组的成员。  
  
7.  要在源层次结构和目标层次结构之间共享分发点，请选中“为源站点服务器启用分发点共享”复选框。 如果此时不启用分发点共享，你可以在数据收集完成后通过编辑源站点的凭据来启用分发点共享。  
  
8.  单击“确定”保存配置。 这将打开“数据收集状态”对话框，并且数据收集将自动开始。  
  
9. 数据收集完成后，单击“关闭”以关闭“数据收集状态”对话框并完成配置。  
  
##  <a name="BKBM_ConfigSrcSites"></a> 确定源层次结构的其他源站点  
 在配置支持的源层次结构时，会将该层次结构的顶层站点自动配置为源站点，并且会自动从该站点中收集数据。 接下来进行的操作取决于源层次结构运行的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的版本：  
  
-   对于 [!INCLUDE[cm4short](../LocTest/includes/cm4short_md.md)] 源层次结构，在初始源站点的数据收集完成后，你可以开始仅从该初始源站点中进行迁移，或者可以配置源层次结构中的其他源站点。 你将为 [!INCLUDE[cm4short](../LocTest/includes/cm4short_md.md)] 层次结构配置其他源站点以迁移仅从子站点中可用的数据。 例如，要迁移的内容是在源层次结构中的子站点上创建的，并且在源层次结构的顶层站点上不可用，则可以配置其他源站点来收集有关该内容的数据。  
  
-   对于 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 或 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 源层次结构，你无需配置其他源站点。 这是因为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的这些版本使用在源层次结构的顶层站点可用的共享数据库。 共享数据库包含你可从该源层次结构中的所有站点迁移的所有信息、 这样，你将可以在源层次结构的顶层站点中找到可迁移的数据。  
  
 在为 [!INCLUDE[cm4short](../LocTest/includes/cm4short_md.md)] 源层次结构配置其他源站点时，你必须在源层次结构中按自上而下的顺序配置其他源站点。 在将父站点的任何子站点配置为源站点之前，你必须将该父站点配置为源站点。  
  
 使用下列过程来为 [!INCLUDE[cm4short](../LocTest/includes/cm4short_md.md)] 源层次结构配置其他源站点。  
  
#### 确定源层次结构中的其他源站点  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“管理”。  
  
2.  在“管理”工作区中，展开“迁移”，然后单击“源层次结构”。  
  
3.  单击要配置为源站点的站点。  
  
4.  在“主页”选项卡上的“源站点”组中，单击“配置”  
  
5.  在“源站点凭据”对话框中，为源站点访问帐户指定具有以下权限的帐户：  
  
    -   源站点帐户：针对源层次结构中指定顶层站点的 SMS 提供程序的“读取”权限。  
  
    -   源站点数据库帐户：针对源层次结构中指定顶层站点的 SQL Server 数据库的“读取”和“执行”权限。  
  
     如果指定使用计算机帐户，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将使用目标层次结构的顶层站点的计算机帐户。 对于此选项，请确保此帐户是源层次结构的顶层站点所在域中“分布式 COM 用户”安全组的成员。  
  
6.  要在源层次结构和目标层次结构之间共享分发点，请选中“为源站点服务器启用分发点共享”复选框。 如果此时不启用分发点共享，你可以在数据收集完成后通过编辑源站点的凭据来启用分发点共享。  
  
7.  单击“确定”保存配置。 这将打开“数据收集状态”对话框，并且数据收集将自动开始。  
  
8.  数据收集完成后，单击“关闭”完成配置。  
  
## 请参阅  
 [在 System Center Configuration Manager 中层次结构之间迁移数据](../LocTest/Migrate-data-between-hierarchies-in-System-Center-Configuration-Manager.md)
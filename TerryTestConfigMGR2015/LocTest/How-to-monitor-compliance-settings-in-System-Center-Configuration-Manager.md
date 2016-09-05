---
title: "如何在 System Center Configuration Manager 中监视符合性设置"
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
ms.assetid: 92c1ccca-a748-44cd-a52e-e41d34bf981d
caps.latest.revision: 6
caps.handback.revision: 5
---
# 如何在 System Center Configuration Manager 中监视符合性设置
在向层次结构中的计算机部署 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 配置基线后，你可以使用以下一个或多个过程来显示配置基线的符合性状态：  
  
-   [如何在 Configuration Manager 控制台中查看符合性结果](#BKMK_Console)  
  
-   [如何使用报表来查看符合性结果](#BKMK_Reports)  
  
-   [如何在 Configuration Manager Windows 客户端上查看符合性结果](#BKMK_Client)  
  
-   [如何根据配置基线符合性创建集合](#BKMK_Create)  
  
> [!NOTE]  
>  符合性设置报表中的验证条件字段（客户端报表的等价内容是“约束”）显示基础服务建模语言 \(SML\)。 如果在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中创作配置项目的管理员不具备 SML 的相关知识，则难以了解验证条件是什么。 在这种情况下，使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中的“监视”工作区来查看配置项目的属性及其验证条件。  
  
##  <a name="BKMK_Console"></a> 如何在 Configuration Manager 控制台中查看符合性结果  
 使用此过程在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中查看有关所部署配置基线的符合性的详细信息。  
  
#### 在 Configuration Manager 控制台查看符合性结果  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“监视”。  
  
2.  在“监视”工作区中，单击“部署”。  
  
3.  在“部署”列表中，选择要查看其符合性信息的配置基线部署。  
  
4.  可以在主页上查看有关配置基线部署符合性的摘要信息。 若要查看更详细的信息，请选择配置基线部署，然后在“主页”选项卡上的“部署”组中，单击“查看状态”以打开“部署状态”页。  
  
     “部署状态”页包含下列选项卡：  
  
    -   **符合**：显示基于受影响资产数量的配置基线符合性。 你可以单击规则以在“资产和符合性”工作区中的“用户”或“设备”节点下创建一个临时节点，其中包含符合此规则的所有用户或设备。 “资产详细信息”窗格显示符合配置基线的用户或设备。 双击列表中的用户或设备以显示其他信息。  
  
        > [!IMPORTANT]  
        >  如果未检测到配置项目规则或该规则在客户端计算机上不适用，则不会评估配置项目规则，但是该规则返回的状态为符合。  
  
    -   **错误**：显示基于受影响资产数量的所选配置基线部署的所有错误的列表。 你可以单击规则以在“资产和符合性”工作区的“用户”或“设备”节点下创建一个临时节点，其中包含对于此规则生成了错误的所有用户或设备。 当你选择某个用户或设备时，“资产详细信息”窗格将显示受所选问题影响的用户或设备。 双击列表中的用户或设备以显示有关问题的其他信息。  
  
    -   **不符合**：显示基于受影响资产数量的配置基线内所有不符合规则的列表。 你可以单击规则以在“资产和符合性”工作区的“用户”或“设备”节点下创建一个临时节点，其中包含不符合此规则的所有用户或设备。 当你选择某个用户或设备时，“资产详细信息”窗格将显示受所选问题影响的用户或设备。 双击列表中的用户或设备以显示有关问题的进一步信息。  
  
    -   **未知**：显示没有为所选配置基线部署报告符合性的所有用户和设备的列表，以及设备的当前客户端状态。  
  
5.  在“部署状态”页上，你可以查看有关所部署配置基线的符合性的详细信息。 将在“部署”节点下创建一个临时节点，该节点可帮助你快速再次找到此信息。  
  
##  <a name="BKMK_Reports"></a> 如何使用报表来查看符合性结果  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的符合性设置包括大量内置报表，可让你监视有关配置项目、配置基线和部署的信息。 这些报表的报表类别为“符合性和设置管理”。  
  
> [!IMPORTANT]  
>  在符合性设置报表中使用参数“设备筛选器”和“用户筛选器”时，你必须使用通配符 \(**%**\) 字符。  
  
 有关如何配置 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的报告的详细信息，请参阅 [System Center Configuration Manager 中的报表](../LocTest/Reporting-in-System-Center-Configuration-Manager.md)  
  
##  <a name="BKMK_Client"></a> 如何在 Configuration Manager Windows 客户端上查看符合性结果  
 使用此过程在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端中查看有关所部署配置基线的符合性的详细信息。  
  
> [!NOTE]  
>  如果使用域来宾帐户登录，则不能在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] Windows 客户端中查看信息。  
  
#### 若要在 Configuration Manager Windows 客户端中查看符合性结果  
  
1.  导航到客户端计算机控制面板中的“Configuration Manager”，然后双击它以打开其属性。  
  
2.  单击“配置”选项卡，然后查看部署的配置基线列表。  
  
3.  查看每个配置基线的“符合性状态”：  
  
    > [!IMPORTANT]  
    >  评估结果将在客户端上缓存 15 分钟。 如果你在 15 分钟内启动重新评估，则将从此缓存而不是新评估中返回符合性结果。 因此，如果您在客户端上进行了可能影响符合性评估结果的更改，则在启动重新评估之前请等待 15 分钟。  
  
    -   **符合**：客户端计算机符合评估的配置基线。  
  
    -   **不符合**：客户端计算机不符合评估的配置基线。  
  
    -   **未知**：客户端计算机尚未评估配置基线。 如果想要启动符合性评估计划以外的评估，请选择要评估的配置基线，然后单击“评估”。  
  
        > [!NOTE]  
        >  如果你具有客户端计算机的本地管理员证书，则可以查看每个已评估配置基线的详细信息，以确定报告了不符合状态的配置项目。 为此，请选择配置基线，然后单击“查看报表”。  
  
4.  单击"**确定**"。  
  
##  <a name="BKMK_Create"></a> 如何根据配置基线符合性创建集合  
 使用以下过程，根据具有指定符合性的设备创建 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 集合。 你可以基于以下符合性状态创建集合：  
  
-   **是否满足条件**  
  
-   **错误**  
  
-   **不相容**  
  
-   **未知**  
  
#### 若要基于符合性状态创建集合  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”。  
  
2.  在“资产和符合性”工作区中，展开“符合性设置”，然后单击“配置基线”。  
  
3.  在“配置基线”列表中，选择要基于其创建集合的配置基线。  
  
4.  在“部署”选项卡上的“部署组”中，单击“创建新集合”，然后在下拉列表中选择要为其创建集合的符合性级别。  
  
5.  “创建用户集合向导”或“创建设备集合向导”将打开，具体取决于是向用户还是设备部署了配置项目。 该向导自动填充正确的值以创建集合；但是，你可以编辑这些值。  
  
6.  完成向导后，该集合显示在“资产和符合性”工作区中的“用户集合”或“设备集合”节点下。  
  
## 请参阅  
 [System Center Configuration Manager 的符合性设置技术参考](../LocTest/Compliance-settings-technical-reference-for-System-Center-Configuration-Manager.md)
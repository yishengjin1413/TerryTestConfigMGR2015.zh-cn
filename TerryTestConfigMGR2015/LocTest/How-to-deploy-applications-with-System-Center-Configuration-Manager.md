---
title: "如何使用 System Center Configuration Manager 部署应用程序"
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
ms.assetid: 2629c376-ec43-4f0e-a78b-4223cc9302bf
caps.latest.revision: 10
caps.handback.revision: 10
author: barlanmsft
---
# 如何使用 System Center Configuration Manager 部署应用程序
||  
|-|  
|[!INCLUDE[cm1602disclaimer](../LocTest/includes/cm1602disclaimer_md.md)]|  
  
 你至少必须为应用程序创建一种部署类型，然后才能部署 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 应用程序。 有关创建应用程序和部署类型的详细信息，请参阅[如何使用 System Center Configuration Manager 创建应用程序](../LocTest/How-to-create-applications-with-System-Center-Configuration-Manager.md)。  
  
> [!IMPORTANT]  
>  你可以部署（安装/卸载）所需的应用程序，但不能部署包或软件更新。 移动设备也不支持模拟部署。  
>   
>  此外，移动设备不支持部署软件向导中的用户体验和计划设置。  
  
 还可以模拟应用程序部署。 此类型的部署在不安装或卸载应用程序的情况下测试将它部署到计算机的适用性。 模拟部署将评估部署类型的检测方法、要求和依赖关系，然后在“监视”  工作区的“部署”  节点中报告结果。 有关详细信息，请参阅[如何使用 System Center Configuration Manager 模拟应用程序部署](../LocTest/How-to-simulate-application-deployments-with-System-Center-Configuration-Manager.md)。  
  
### 部署应用程序  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“软件库” 。  
  
2.  在“软件库”  工作区中，展开“应用程序管理” ，然后单击“应用程序” 。  
  
3.  在“应用程序”  列表中，选择要部署的应用程序。 然后在“主页”  选项卡上的“部署”  组中，单击“部署” 。  
  
4.  在“部署软件向导”的“常规”  页上，指定以下信息：  
  
    -   **软件** – 此信息显示要部署的应用程序。 你可以单击“浏览”  以选择其他应用程序。  
  
    -   **集合** - 单击“浏览”  以选择要在其中部署应用程序的集合。  
  
    -   **使用与此集合关联的默认分发点组** – 如果要将应用程序内容存储在集合的默认分发点组上，则选择此选项。 如果未将所选集合与分发点组关联，则此选项不可用。  
  
    -   **为依赖关系自动分发内容** – 如果启用了此选项，并且应用程序中的任何部署类型包含依赖关系，则也会将从属应用程序内容发送到分发点。  
  
        > [!IMPORTANT]  
        >  如果在部署了主应用程序之后更新从属应用程序，则不会自动分发依赖项的任何新内容。  
  
    -   **备注(可选)** – 根据需要输入此部署的描述。  
  
5.  在向导的“内容”  页上，单击“添加”  以将与此部署关联的内容添加到分发点或分发点组。 如果在向导的“常规”  页上选择了“使用与此集合关联的默认分发点”，则会自动填充此选项，并且只有“应用程序管理员”  安全角色的成员才能对其进行修改。  
  
6.  单击“下一步” 。  
  
7.  在“部署软件向导”的“部署设置”  页上，指定以下信息：  
  
    -   **操作** – 从下拉列表中，选择此部署的意图是“安装”  还是  “卸载”应用程序。  
  
        > [!NOTE]  
        >  如果将应用程序部署到设备两次，一次使用“安装”  操作，一次使用“卸载” 操作，则使用“安装”  操作的应用程序部署将优先。  
        >   
        >  你不能在创建部署之后更改部署的操作。  
  
    -   **目的** – 从下拉列表中，选择以下选项之一：  
  
        -   **可用** - 如果将应用程序部署到用户，则用户将在软件中心看到发布的应用程序，并可根据需要进行安装。  
  
        -   **必需** - 依据配置的计划自动部署应用程序。 不过，用户可以跟踪应用程序部署状态（如果未隐藏），并且可从软件中心在截止时间之前安装该应用程序。  
  
            > [!NOTE]  
            >  将部署操作设置为“卸载” 时，部署目的将自动设置为“必需”  ，并且无法更改。  
  
    -   无论用户是否登录都依据计划自动部署 – 如果部署到用户，请选择此选项以将应用程序部署到用户的主要设备。 在该部署运行之前，此设置不需要用户登录。 如果用户必须提供输入才能完成安装，请勿选择此选项。 只有当部署的目的是“必须” 时，此选项才可用。  
  
    -   **发送唤醒数据包** – 如果部署目的设置为“必需”  ，并且选择了此选项，则会在安装部署之前向计算机发送一个唤醒数据包，以在安装截止时将计算机从休眠中唤醒。 必须针对“LAN 唤醒”配置计算机和网络，然后才能使用此选项。  
  
    -   **允许客户端使用按流量计费的 Internet 连接在安装截止时间之后下载内容，这可能会导致附加成本** – 只有当部署的目的是“必需” 时，此选项才可用。  
  
    -   **如果用户请求此应用程序，则需要管理员批准** – 如果选择了此选项，则管理员必须批准针对应用程序的任何用户请求，然后才能安装应用程序。 如果部署目的为“必需”  或者应用程序部署到设备集合，则此选项不可用。  
  
        > [!NOTE]  
        >  应用程序批准请求显示在“软件库”  工作区中“应用程序管理”  下的“批准请求”  节点中。 如果批准请求在 45 天内未获批准，则会将其删除。 此外，重新安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端可能会取消任何挂起的批准请求。  
  
    -   **自动升级此应用程序的任何取代版本** – 如果选择此选项，则会使用取代应用程序升级应用程序的任何取代版本。  
  
8.  在“部署软件向导”的“计划”  页上，配置何时部署此应用程序或将其提供给客户端设备。  
    视部署操作设置为“可用”  还是“必需” 而定，此页上的选项将有所不同。  
  
9. 如果你部署的应用程序取代另一个应用程序，则可以配置安装截止时间，届时用户将收到新应用程序。 通过使用“安装截止时间”  设置升级具有被取代的应用程序来执行此操作。  
  
10. 在“部署软件向导”的“用户体验”  页上，指定有关用户如何能与应用程序安装交互的信息。  
  
     将应用程序部署到启用了写入筛选器的 Windows Embedded 设备时，你可以指定将应用程序安装在临时覆盖上并稍后提交更改，或者在安装截止时或在维护时段内提交更改。 如果在安装截止时或在维护时段内提交更改，则需要重新启动，而且更改将保留在设备上。  
  
    > [!NOTE]  
    >  将应用程序部署到 Windows Embedded 设备时，确保设备是配置了维护时段的集合的成员。 有关在将应用程序部署到 Windows Embedded 设备时如何使用维护时段的详细信息，请参阅[使用 System Center Configuration Manager 创建 Windows Embedded 应用程序](../LocTest/Creating-Windows-Embedded-applications-with-System-Center-Configuration-Manager.md)。  
    >   
    >  如果部署目的设置为“可用”  ，则不使用选项“软件安装”  和“系统重新启动(如果要求完成安装)” 。 你还可以配置在安装应用程序时用户看到的通知的级别。  
  
11. 在“部署软件向导”的“警报”  页上，配置 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 和 System Center Operations Manager 为此部署生成警报的方式。 你可以配置用于报告警报的阈值，并在部署持续时间内关闭报告。  
  
12. （仅适用于 iOS 应用）- 在向导的“应用配置策略”页上，单击“新建”，将此部署与 iOS 应用配置策略（如果已创建策略）相关联。 有关此类型策略的详细信息，请参阅[使用 System Center Configuration Manager 中的应用配置策略配置 iOS 应用](../LocTest/Configure-iOS-apps-with-app-configuration-policies-in-System-Center-Configuration-Manager.md)。  
  
13. 在“部署软件向导”的“摘要”  页上，查看此部署将进行的操作，然后单击“下一步”  完成向导。  
  
 新部署将显示在“监视”  工作区的“部署”  节点中的“部署”  列表中。 你可以从应用程序详细信息窗格的“部署”  选项卡中编辑此部署的属性或删除部署。  
  
### 删除应用程序部署  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“软件库” 。  
  
2.  在“软件库”  工作区中，展开“应用程序管理” ，然后单击“应用程序” 。  
  
3.  在“应用程序”  列表中，选择要为其删除部署的应用程序。  
  
4.  在 <application name\> 列表的“部署”选项卡中，选择要删除的应用程序部署。 然后，在“部署”  选项卡的“部署”  组中，单击“删除” 。  
  
 删除应用程序部署时，不会删除已安装的应用程序的任何实例。 要删除这些应用程序，你必须使用“卸载” 操作将应用程序部署到计算机。 如果删除应用程序部署，或从部署到的集合中删除资源，则应用程序将不再显示在软件中心中。  
  
## 另请参阅  
 [System Center Configuration Manager 中应用程序管理的技术参考](../LocTest/Application-management-technical-reference-for-System-Center-Configuration-Manager.md)
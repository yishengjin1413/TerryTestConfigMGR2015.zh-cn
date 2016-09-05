---
title: "System Center Configuration Manager 用于创建和部署配置基线的常见任务"
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
ms.assetid: 4bb6afeb-d267-4f9b-ade2-26e5400c223b
caps.latest.revision: 6
caps.handback.revision: 5
translationtype: Human Translation
---
# System Center Configuration Manager 用于创建和部署配置基线的常见任务
本主题包含帮助了解有关如何创建和部署 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 配置基线的常用方案。  
  
 如果已熟悉符合性设置，可以在 [如何在 System Center Configuration Manager 中创建配置基线](../LocTest/How-to-create-configuration-baselines-in-System-Center-Configuration-Manager.md) 和 [如何在 System Center Configuration Manager 中部署配置基线](../LocTest/How-to-deploy-configuration-baselines-in-System-Center-Configuration-Manager.md) 主题中找到有关你使用的所有功能的详细文档。  
  
 在开始之前，请阅读 [System Center Configuration Manager 中的符合性设置入门](../LocTest/Get-started-with-compliance-settings-in-System-Center-Configuration-Manager.md) 来了解有关符合性设置的一些基本知识，并请参阅 [在 System Center Configuration Manager 中规划和配置符合性设置](../LocTest/Plan-for-and-configure-compliance-settings-in-System-Center-Configuration-Manager.md) 实现任何必需的先决条件。  
  
## 创建配置基线  
 在本例中，已创建了仅针对运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端的Windows 10 电脑的配置项目。  
  
 此配置项目强制要求在 Windows 10 电脑上输入至少 6 位字符的密码。 配置项目名为“Windows 10 密码实施”。  
  
 在下面的过程中，你将了解如何将此配置项目添加到配置基线以准备部署。  
  
#### 若要创建配置基线  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”。  
  
2.  在“资产和符合性”工作区中，展开“符合性设置”，然后单击“配置基线”。  
  
3.  在“主页”选项卡上的“创建”组中，单击“创建配置基线”。  
  
4.  在“创建配置基线”对话框中，配置以下项：  
  
    -   **名称** – 输入 **Windows 10 密码**（或你选择的另一名称）  
  
5.  单击“添加”\>“配置项目”。  
  
6.  在“添加配置项目”对话框中，选择之前创建的“Windows 10 密码实施”配置项目，然后单击“添加”。  
  
7.  单击“确定”以关闭“添加配置项目”对话框并返回“创建配置基线”对话框，其外观类似于此屏幕截图：  
  
     ![Create Configuration Baseline dialog box](../LocTest/media/Create-Configuration-Baseline.png "Create)  
  
8.  单击“确定”以关闭“创建配置基线”对话框。  
  
 现在，可以看到刚才在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台的“配置基线”节点中创建的配置基线。  
  
## 部署配置基线  
 在本例中，会将前一过程中创建的配置基线部署到计算机集合中。  
  
#### 若要部署配置基线  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”。  
  
2.  在“资产和符合性”工作区中，展开“符合性设置”，然后单击“配置基线”。  
  
3.  从配置基线列表中选择“Windows 10 密码”。  
  
4.  在“主页”选项卡上的“部署”组中，单击“部署”。  
  
5.  在“部署配置基线”对话框中，配置以下项：  
  
    -   **所选配置基线** – 确保“Windows 10 密码”配置基线已自动添加到此列表中。  
  
    -   **支持时修正不符合规则** – 勾选此框，以确保如果目标设备上没有正确的设置，则通过 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 进行修正。  
  
    -   **集合** – 单击“浏览”以选择在其上评估配置基线并针对符合性进行修正的计算机集合。 在本例中，已将配置基线部署到内置“所有台式计算机和服务器客户端”集合。  
  
        > [!TIP]  
        >  不要担心选择的集合是否包含不运行 Windows 10 的计算机或设备。 只要在创建的配置项目中配置支持的平台，只有 Windows 10 电脑会评估符合性。  
  
    -   如果需要，配置用于评估配置基线的计划。 否则，请保留默认值“7 天”。  
  
6.  现在，对话框外观如下所示：  
  
     ![Deploy configuration baselines dialog box](../LocTest/media/Deploy-configuration-baselines.png "Deploy)  
  
7.  单击“确定”以关闭“部署配置基线”对话框并创建部署。  
  
 如果想要快速了解此部署的合规性统计信息，请在“监视”工作区中，单击“部署”。 在屏幕底部，可看到“合规性统计信息”图表。  
  
 有关如何监视配置基线的详细信息，请参阅 [如何在 System Center Configuration Manager 中监视符合性设置](../LocTest/How-to-monitor-compliance-settings-in-System-Center-Configuration-Manager.md)  
  
## 请参阅  
 [使用 System Center Configuration Manager 管理符合性的常见任务](../LocTest/Common-tasks-for-managing-compliance-with-System-Center-Configuration-Manager.md)
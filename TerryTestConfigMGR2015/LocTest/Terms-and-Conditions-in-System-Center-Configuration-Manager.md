---
title: "Terms and Conditions in System Center Configuration Manager"
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
ms.assetid: 4d3f9e6b-4d71-4fc4-9b91-47f1bfbd8c70
caps.latest.revision: 9
caps.handback.revision: 8
translationtype: Human Translation
---
# Terms and Conditions in System Center Configuration Manager
你可以将 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 条款和条件部署到用户组，以解释设备如何注册、访问工作资源以及使用公司门户对设备和用户有何影响。 用户必须接受这些条款和条件，然后才能使用公司门户进行注册或访问工作。  
  
 [!INCLUDE[cm1602disclaimer](../LocTest/includes/cm1602disclaimer_md.md)]  
  
## 使用 System Center Configuration Manager 中的条款和条件策略  
 你可以创建和部署多组条款和条件。 也可以用不同的语言生成相同条款和条件的不同版本，然后将它们部署到相应的组。  
  
#### 创建条款和条件  
  
1.  在 Configuration Manager 控制台中，转到“资产和符合性” > “概述” > “符合性设置” > “条款和条件”。  
  
2.  单击“创建条款和条件”  以创建新的条款和条件。  
  
3.  在“常规”  页面上，指定下列信息：  
  
    -   “名称” - [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中显示的唯一名称  
  
    -   “说明” - 可帮助识别 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中的条款和条件的详细信息  
  
     然后单击 **“下一步”**。  
  
4.  在“条款”  页上，指定下列信息：  
  
    -   “标题” - 公司门户中向用户显示的标题  
  
    -   “条款文本” - 在公司门户向用户显示的条款和条件  
  
    -   **解释用户接受条款和条件表示什么意思的文本** - 用户看到的关于接受的标签。 **示例**：“我同意条款和条件。”  
  
     然后单击 **“下一步”**。  
  
5.  完成向导以创建新的条款和条件。 在“资产和符合性”工作区的“条款和条件”节点中显示的新的条款和条件。  
  
#### 部署条款和条件  
  
1.  在 Configuration Manager 控制台中，转到“资产和符合性” > “概述” > “符合性设置” > “条款和条件”。  
  
2.  在“条款和条件”列表中，选择要部署的项，然后单击“部署”。  
  
3.  单击“浏览” 查看条款和条件要部署到的“集合”  ，然后单击“确定” 。  
  
     当目标设备访问公司门户应用时，将显示所部署的条款和条件。 用户必须接受这些条款，然后才能访问公司资源。  
  
    > [!NOTE]  
    >  如果将一组条款部署到用户所属的多个用户集合，则该用户在打开公司门户时将看到相同术语的多个副本。 由于用户只可接受或拒绝所有条款，因此当用户同时接受和拒绝条款时不存在接受状态不明确的风险。 对于每位用户的每组条款，条款和条件接受报表将仅包括一行，因此报表中没有错误。  
  
#### 监视条款和条件  
  
1.  从 1602 版开始，可在 Configuration Manager 控制台中监视条款和条件部署。 在 Configuration Manager 控制台中，转至“监控” > “概述” > “部署”。  
  
2.  选择条款和条件部署。 从部署列表  
  
     摘要区域将显示以下统计信息：  
  
    -   **合规** - 用户已接受最新版本的条款和条件  
  
    -   **错误**  
  
    -   **不合规** - 用户已接受某版本的条款和条件，但未接受最新版本  
  
    -   **未知** - 用户从未接受条款和条件，包括不具有已注册设备的用户  
  
3.  选择条款和条件部署然后选择“运行摘要”，以查看各用户的部署状态。  
  
     在“部署状态”屏幕中，可选择状态选项卡以查看具有该状态的用户。 可单击“运行摘要”以在整个层次结构中更新数据。 单击“刷新”以在控制台中更新数据  
  
#### 查看条款和条件报告  
  
1.  在 Configuration Manager 控制台中，转至“监视” > “概述” > “报告” > “报表”。  
  
2.  选择“条款和条件接受”，然后单击“运行”。 将打开条款和条件接受报表。 此报告显示已向其部署条款和条件的每个用户。 字段包括：  
  
    -   条款和条件的名称  
  
    -   用户名  
  
    -   已接受版本  
  
    -   已接受数据  
  
    -   已接受最新版本  
  
###  <a name="BKMK_TCVers"></a> 条款和条件的更新和版本控制  
 当编辑现有条款和条件时，可以在部署该条款和条件时选择该行为。 使用以下过程帮助你更新现有的条款和条件。  
  
##### 如何使用多个版本的条款和条件  
  
1.  在 Configuration Manager 控制台中，转到“资产和符合性” > “概述” > “符合性设置” > “条款和条件”。  
  
2.  选择要编辑的条款和条件实例，然后双击将其打开。  
  
3.  可以修改“常规”  或“条款”  页上的内容，以进行任何所需的编辑。  
  
4.  随后可在“条款”  页上指定该新版本是要求所有用户接受条款和条件，还是仅新用户能看到新版本。  
  
     我们建议增加版本号，并在条款和条件发生重大变更时要求用户接受。 如果修改错别字或更改格式设置，则维持当前版本号。
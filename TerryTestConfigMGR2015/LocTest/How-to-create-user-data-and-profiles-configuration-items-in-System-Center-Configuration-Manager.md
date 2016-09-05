---
title: "如何在 System Center Configuration Manager 中创建用户数据和配置文件的配置项目"
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
ms.assetid: 9fcbcc81-cd6f-496e-b075-ef1afa2b8ccc
caps.latest.revision: 6
caps.handback.revision: 5
---
# 如何在 System Center Configuration Manager 中创建用户数据和配置文件的配置项目
使用以下过程创建、部署和监视 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 用户数据和配置文件的配置项目。  
  
 使用此过程之前，请确保你已阅读[使用 System Center Configuration Manager 中的用户数据和配置文件的配置项目](../LocTest/Working-with-user-data-and-profiles-configuration-items-in-System-Center-Configuration-Manager.md)中的介绍信息和先决条件。  
  
 与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的其他配置项目不同，无需向随后将部署的配置基线添加用户数据和配置文件的配置项目。 而只需使用“部署用户数据和配置文件的配置项目”对话框直接部署配置项目。  
  
### 若要创建用户数据和配置文件的配置项目  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”。  
  
2.  在“资产和符合性”工作区中，展开“符合性设置”，然后单击“用户数据和配置文件”。  
  
3.  在“主页”选项卡上的“创建”组中，单击“创建用户数据和配置文件的配置项目”。  
  
4.  在“创建用户数据和配置文件的配置项目向导”的“常规”页上，指定以下信息：  
  
    -   **名称**：输入配置项目的唯一名称。 最多可以使用 256 个字符。  
  
    -   **描述**：提供对配置项目进行概述的描述，以及可帮助在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中识别该配置项目的其他相关信息。 最多可以使用 256 个字符。  
  
    -   **文件夹重定向**：如果你想要为此配置项目配置文件夹重定向设置，请选中此框。  
  
    -   **脱机文件**：如果你想要为此配置项目配置脱机文件设置，请选中此框。  
  
    -   **漫游用户配置文件**：如果你想要为此配置项目配置漫游用户配置文件设置，请选中此框。  
  
5.  在“创建用户数据和配置文件的配置项目向导”的“文件夹重定向”页上，指定你希望接收此配置项目的用户的客户端计算机如何管理文件夹重定向。 你可以为用户登录的任何设备配置设置，也可仅为用户的主要设备配置设置。 有关文件夹重定向的详细信息，请参阅你的 Windows Server 文档。  
  
    > [!NOTE]  
    >  仅当你选中向导中“常规”页上的“文件夹重定向”复选框时，才会显示向导的此页。  
  
6.  在“创建用户数据和配置文件的配置项目向导”的“脱机文件”页上，可以为接受此配置项目并针对脱机文件的行为配置设置的用户启用或禁用脱机文件的使用。 也可指定在用户登录的任何计算机上总是可用的脱机文件。 有关脱机文件的详细信息，请参阅你的 Windows Server 文档。  
  
    > [!NOTE]  
    >  仅当你选中向导中“常规”页上的“脱机文件”复选框时，才会显示向导的此页。  
  
7.  在“创建用户数据和配置文件的配置项目向导”的“漫游配置文件”页上，你可以配置漫游配置文件在用户登录的计算机上是否可用，还可以配置有关这些配置文件的行为方式的进一步信息。 有关漫游配置文件的详细信息，请参阅你的 Windows Server 文档。  
  
    > [!NOTE]  
    >  仅当你选中向导中“常规”页上的“漫游用户配置文件”复选框时，才会显示向导的此页。  
  
8.  完成向导。  
  
 新的用户数据和配置文件的配置项目显示在“资产和符合性”工作区的“用户数据和配置文件”节点中。  
  
### 若要部署用户数据和配置文件的配置项目  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”。  
  
2.  在“资产和符合性”工作区中，展开“符合性设置”，然后单击“用户数据和配置文件”。  
  
3.  选择要部署的用户数据和配置文件的配置项目，然后，在“主页”选项卡上的“部署”组中单击“部署”。  
  
4.  在“部署用户数据和配置文件的配置项目”对话框中，指定以下信息。  
  
    -   **集合** \- 单击“浏览”以选择要在其中部署配置项目的用户集合。  
  
        > [!IMPORTANT]  
        >  仅可向用户集合部署用户数据和配置文件的配置项目。  
  
    -   **在支持时修正非符合性规则** – 启用此选项可自动修正客户端计算机上评估为不符合的任何规则。  
  
    -   **允许维护时段外的修正** \- 如果已为你向其部署配置项目的集合配置了维护时段，请启用此选项以让符合性设置在维护时段外修正值。 有关维护时段的详细信息，请参阅[如何在 Configuration Manager 中使用维护时段](../LocTest/How-to-use-maintenance-windows-in-System-Center-Configuration-Manager.md)。  
  
    -   **生成警报** \- 启用此选项可配置一个警报，如果在指定日期和时间之前配置项目符合性小于指定百分比，则生成该警报。 你也可以指定是否希望将警报发送到 System Center Operations Manager。  
  
    -   **指定此配置项目的符合性评估计划** \- 指定在客户端计算机上对部署的配置项目进行评估所依据的计划。 这可以是简单计划或自定义计划。  
  
5.  单击“确定”关闭“部署用户数据和配置文件的配置项目”对话框并创建部署。  
  
## 监视用户数据和配置文件的配置项目  
 监视此类配置项目的方法与监视其他符合性设置的方法相同。  
  
 有关详细信息，请参阅[如何在 System Center Configuration Manager 中监视符合性设置](../LocTest/How-to-monitor-compliance-settings-in-System-Center-Configuration-Manager.md)。  
  
## 请参阅  
 [System Center Configuration Manager 的符合性设置技术参考](../LocTest/Compliance-settings-technical-reference-for-System-Center-Configuration-Manager.md)
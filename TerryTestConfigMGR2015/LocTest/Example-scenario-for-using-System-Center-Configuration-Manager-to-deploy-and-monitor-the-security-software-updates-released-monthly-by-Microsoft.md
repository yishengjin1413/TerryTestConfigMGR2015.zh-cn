---
title: "使用 System Center Configuration Manager 部署和监视 Microsoft 每月发布的安全软件更新的示例方案"
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
ms.assetid: c32f757a-02da-43f2-b055-5cfd097d8c43
caps.latest.revision: 6
caps.handback.revision: 3
translationtype: Human Translation
---
# 使用 System Center Configuration Manager 部署和监视 Microsoft 每月发布的安全软件更新的示例方案
本主题提供一个示例方案，以说明如何使用 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的软件更新来部署和监视 Microsoft 每月发布的安全软件更新。  
  
 在此方案中，John 是 Woodgrove Bank 的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 管理员。 John 需要创建一个具有以下条件和要求的软件更新部署策略：  
  
-   Microsoft 在每月的第二个星期二发布安全软件更新，而一周后将会出现活跃的软件更新部署活动。 此事件通常称为“周二补丁日”。  
  
-   在分发点上下载并暂存软件更新。 然后，在部分客户端中测试部署，之后 John 在生产环境中全面部署软件更新。  
  
-   John 必须能够按月或按年监视软件更新的符合性。  
  
 此方案假定已经实施了软件更新点基础结构。 使用下表中的信息来规划和配置 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 中的软件更新。  
  
|过程|参考|  
|--------|--------|  
|查看软件更新的关键概念。|[System Center Configuration Manager 中的软件更新简介](../LocTest/Introduction-to-software-updates-in-System-Center-Configuration-Manager.md)|  
|规划软件更新。 此信息帮助你制定计划以全面考虑容量问题，以及确定软件更新点基础结构、软件更新点的安装、同步设置和软件更新的客户端设置。|[在 System Center Configuration Manager 中规划软件更新](../LocTest/Plan-for-software-updates-in-System-Center-Configuration-Manager.md)|  
|配置软件更新。 此信息帮助你在层次结构中安装和配置软件更新点，并帮助你配置和同步软件更新。 **Important:**  John 将软件更新同步计划配置为在每月的第二个星期三执行，以确保他获得 Microsoft 发布的最新安全软件更新。|[在 System Center Configuration Manager 中配置软件更新](../LocTest/Configure-software-updates-in-System-Center-Configuration-Manager.md)|  
  
 本主题中的下列部分提供了过程步骤示例，以帮助你在贵组织中部署和监视 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 安全软件更新：  
  
-   [步骤 1：为每年符合性创建软件更新组](#BKMK_Step1)  
  
-   [步骤 2：为当月创建自动部署规则](#BKMK_Step2)  
  
-   [步骤 3：验证软件更新是否做好部署准备](#BKMK_Step3)  
  
-   [步骤 4：部署软件更新组](#BKMK_Step4)  
  
-   [步骤 5：监视所部署的软件更新的符合性](#BKMK_Step5)  
  
-   [步骤 6：将每月的软件更新添加到每年更新组](#BKMK_Step6)  
  
##  <a name="BKMK_Step1"></a> 步骤 1：为每年符合性创建软件更新组  
 John 创建一个软件更新组，可用于监视他在 2012 年发布的所有安全软件更新的符合性。 他执行下表中的步骤。  
  
|过程|参考|  
|--------|--------|  
|John 从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中的“所有软件更新”节点添加条件以仅显示满足以下条件的于 2015 年发布或修订的安全软件更新：<br /><br /> -   “条件”：发布或修订日期<br />     **条件**：大于或等于特定日期<br />     “值”：1\/1\/2015<br />-   “条件”：更新分类<br />     “值”：安全更新<br />-   “条件”：已过期<br />     “值”：否|无更多信息|  
|John 将所有经过筛选的软件更新添加到一个具有以下要求的新的软件更新组中：<br /><br /> -   “名称”：符合性组 \- Microsoft 安全更新2015<br />-   “描述”：软件更新|[将软件更新添加到更新组](../LocTest/Manage-software-updates-in-System-Center-Configuration-Manager.md#BKMK_AddUpdatesToGroup)|  
  
##  <a name="BKMK_Step2"></a> 步骤 2：为当月创建自动部署规则  
 John 为 Microsoft 在当月发布的安全软件更新创建自动部署规则。 他执行下表中的步骤。  
  
|过程|参考|  
|--------|--------|  
|John 创建具有以下要求的自动部署规则：<br /><br /> <ol><li>在“常规”选项卡上，John 进行以下配置：<br /><br /> <ul><li>他为该名称指定 **Monthly Security Updates**。</li><li>他选择一个包含有限客户端的测试集合。</li><li>他选择“创建新的软件更新组”。</li><li>他确认并未选中“运行此规则后启用部署”。</li></ul></li><li>在“部署设置”选项卡上，John 选择默认设置。</li><li>在“软件更新”页上，John 配置以下属性筛选器和搜索条件：<br /><br /> <ul><li>发布或修订日期 **最近 1 个月**。</li><li>更新分类 **安全更新**。</li></ul></li><li>在“评估”页上，John 使此规则能够按照为每月第二个星期二制定的计划运行。 John 还确认将同步计划设置为在每月第二个星期三运行。</li><li>John 使用“部署计划”、“用户体验”、“警报”和“下载设置”页上的默认设置。</li><li>在“部署包”页上，John 指定新的部署包。</li><li>John 使用“下载位置”和“语言选择”页上的默认设置。</li></ol>|[自动部署软件更新](../LocTest/Manage-software-updates-in-System-Center-Configuration-Manager.md#BKMK_AutoDeploy)|  
  
##  <a name="BKMK_Step3"></a> 步骤 3：验证软件更新是否做好部署准备  
 在每月的第二个星期二，John 都会验证软件更新是否做好部署准备。 他执行下表中的步骤。  
  
|过程|参考|  
|--------|--------|  
|John 验证软件更新同步是否已成功完成。|无更多信息|  
  
##  <a name="BKMK_Step4"></a> 步骤 4：部署软件更新组  
 在 John 确认软件更新已做好部署准备后，他部署软件更新。 他执行下表中的步骤。  
  
|过程|参考|  
|--------|--------|  
|John 为新的软件更新组创建两个测试部署。 他为每个部署设想以下环境：<br /><br /> <br /><br /> **工作站测试部署**：对于工作站测试部署，John 有以下考虑：<br /><br /> -   他指定一个包含了部分工作站客户端的部署集合，以验证部署。<br />-   他配置适用于其环境中的工作站客户端的部署设置。<br /><br /> **服务器测试部署**：对于服务器测试部署，John 有以下考虑：<br /><br /> -   他指定一个包含了部分服务器客户端的部署集合，以验证部署。<br />-   他配置适用于其环境中的服务器客户端的部署设置。|[部署软件更新](../LocTest/Manage-software-updates-in-System-Center-Configuration-Manager.md#BKMK_SUMDeploy)|  
|John 验证测试部署是否已成功部署。|[在 System Center Configuration Manager 中监视软件更新](../LocTest/Monitor-software-updates-in-System-Center-Configuration-Manager.md)|  
|John 利用包含其生产工作站和服务器的新集合更新这两个部署。|无更多信息|  
  
##  <a name="BKMK_Step5"></a> 步骤 5：监视所部署的软件更新的符合性  
 John 监视其软件更新部署的符合性。 他执行下表中的步骤。  
  
|过程|参考|  
|--------|--------|  
|John 在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中监视软件更新部署状态，并检查通过该控制台提供的软件更新部署报表。|[在 System Center Configuration Manager 中监视软件更新](../LocTest/Monitor-software-updates-in-System-Center-Configuration-Manager.md)|  
  
##  <a name="BKMK_Step6"></a> 步骤 6：将每月的软件更新添加到每年更新组  
 John 将每月软件更新组中的软件更新添加到每年软件更新组。 他执行下表中的步骤。  
  
|过程|参考|  
|--------|--------|  
|John 选择每月软件更新组中的软件更新，然后将它们添加到他为每年符合性创建的软件更新组。 他跟踪软件更新符合性，并创建用于管理的不同报表。|[将软件更新添加到已部署的更新组中](../LocTest/Manage-software-updates-in-System-Center-Configuration-Manager.md#BKMK_AddUpdatesToExistingGroup)|  
  
 John 已成功完成每月的安全软件更新部署。 他继续监视和报告软件更新符合性，以确保其环境中的客户端处于可接受的符合性级别内。  
  
##  <a name="BKMK_MonthlyProcess"></a> 每月定期进行的软件更新部署过程  
 在 John 部署软件更新的第一个月之后，他执行步骤三到步骤六，以部署 Microsoft 发布的每月安全软件更新。  
  
## 请参阅  
 [软件更新 System Center Configuration Manager 的技术参考](../LocTest/Software-updates-technical-reference-for-System-Center-Configuration-Manager.md)
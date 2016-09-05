---
title: "在 System Center Configuration Manager 中配置 Endpoint Protection"
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
ms.assetid: e63f2394-6eb1-4a33-bec5-8377fc62a34e
caps.latest.revision: 21
caps.handback.revision: 15
translationtype: Human Translation
---
# 在 System Center Configuration Manager 中配置 Endpoint Protection
必须先执行本主题中详述的配置步骤，然后才能使用 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 管理 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 客户端计算机上的安全性和恶意软件。  
  
## 如何在 Configuration Manager 中配置 Endpoint Protection  
 System Center 2012 Configuration Manager 中的 Endpoint Protection 具有外部依赖关系和产品中的依赖关系。  
  
### 在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中配置 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 的步骤  
 使用下表来了解有关如何配置 Endpoint Protection 的步骤、详情及更多信息。  
  
> [!IMPORTANT]  
>  如果你为 Windows 10 计算机管理 endpoint protection，则必须配置 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 以更新和分发适用于 Windows Defender 的恶意软件定义。 由于 Windows 10 中包含了 Windows Defender，所以无需将 endpoint protection 代理部署到客户端计算机。  
  
|步骤|详细信息|更多信息|  
|--------|----------|----------|  
|**步骤 1：**创建 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 点站点系统角色。|必须先安装 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 点站点系统角色，然后才能使用 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)]。 必须将其仅安装在一个站点系统服务器上，并且必须将其安装在管理中心站点或独立主站点上层次结构的顶部。|请参阅本主题中的 [步骤 1：创建 Endpoint Protection 点站点系统角色](../LocTest/Configuring-Endpoint-Protection-in-System-Center-Configuration-Manager.md#BKMK_Step1)。|  
|**步骤 2：**配置 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 的警报。|当特定事件发生（如恶意软件感染）时，警报将通知管理员。 警报显示在“监视”工作区的“警报”节点中，或（可选）可通过电子邮件发送至指定用户。|请参阅[步骤 2：为 Endpoint Protection 配置警报](../LocTest/Configuring-Endpoint-Protection-in-System-Center-Configuration-Manager.md#BKMK_EPalerts)。|  
|**步骤 3：**配置 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端的定义更新源。|[!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 可以配置为使用各种源来下载定义更新。|请参阅[步骤 3：为 Endpoint Protection 配置定义更新](../LocTest/Configuring-Endpoint-Protection-in-System-Center-Configuration-Manager.md#BKMK_EPdefs)。|  
|**步骤 4：**配置默认反恶意软件策略并创建任何自定义反恶意软件策略。|当安装 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端时，将应用默认反恶意软件策略。 在部署客户端的 60 分钟内将默认应用已部署的任何自定义策略。 请确保在部署 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端之前已配置了反恶意软件策略。|请参阅[如何在 System Center Configuration Manager 中为 Endpoint Protection 创建和部署反恶意软件策略](../LocTest/How-to-create-and-deploy-antimalware-policies-for-Endpoint-Protection-in-System-Center-Configuration-Manager.md)。|  
|**步骤 5：**为 Endpoint Protection 配置自定义客户端设置。|使用自定义客户端设置为层次结构中计算机的集合配置 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 设置。 **Important:**  除非你确信要将这些设置应用于层次结构中的所有计算机，否则请不要配置默认 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端设置。|请参阅本主题中的 [步骤 5：为 Endpoint Protection 配置自定义客户端设置。](../LocTest/Configuring-Endpoint-Protection-in-System-Center-Configuration-Manager.md#BKMK_EPclient)。|  
  
###  <a name="BKMK_Step1"></a> 步骤 1：创建 Endpoint Protection 点站点系统角色  
 根据你是要为 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 安装新的站点系统服务器还是使用现有站点系统服务器，使用以下过程之一：  
  
> [!IMPORTANT]  
>  当你安装 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 点时，将在承载 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 点的服务器上安装 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端。 在此客户端上禁用服务和扫描以使其能够与服务器上安装的任何现有反恶意软件解决方案共存。 如果你之后启用此服务器以便由 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 进行管理，并选择可删除任何第三方反恶意软件解决方案的选项，将不会删除第三方产品。 必须手动卸载此产品。  
  
##### 若要安装和配置 Endpoint Protection 点站点系统角色：新站点系统服务器  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“管理”。  
  
2.  在“管理”工作区中，展开“站点配置”，然后单击“服务器和站点系统角色”。  
  
3.  在“主页”选项卡上的“创建”组中，单击“创建站点系统服务器”。  
  
4.  在“常规”页上，指定站点系统的常规设置，然后单击“下一步”。  
  
5.  在“系统角色选择”页上的可用角色列表中选择“Endpoint Protection 点”，然后单击“下一步”。  
  
6.  在“Endpoint Protection”页上，选择“我接受 Endpoint Protection 许可条款”复选框，然后单击“下一步”。  
  
    > [!IMPORTANT]  
    >  除非你接受许可条款，否则不能使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)]。  
  
7.  在“Microsoft Active Protection Service”页上，选择你想要发送到 Microsoft 的信息的级别以帮助开发新的定义，然后单击“下一步”。  
  
    > [!NOTE]  
    >  此选项配置默认使用的 Microsoft Active Protection Service 设置。 然后可以为你创建的每个反恶意软件策略配置自定义设置。 加入 Microsoft Active Protection Service，通过为 Microsoft 提供有助于 Microsoft 将反恶意软件定义保持为最新状态的恶意软件示例，帮助你的计算机保持日益安全的状态。 此外，当你加入 Microsoft Active Protection Service 后，[!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端可以使用动态签名服务在新定义发布到 Windows Update 之前将其下载。 有关详细信息，请参阅 [如何在 System Center Configuration Manager 中为 Endpoint Protection 创建和部署反恶意软件策略](../LocTest/How-to-create-and-deploy-antimalware-policies-for-Endpoint-Protection-in-System-Center-Configuration-Manager.md)。  
  
8.  完成向导。  
  
##### 若要安装和配置 Endpoint Protection 点站点系统角色：现有站点系统服务器  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“管理”。  
  
2.  在“管理”工作区中，展开“站点配置”，单击“服务器和站点系统角色”，然后选择你想用于 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 的服务器。  
  
3.  在“主页”选项卡上的“服务器”组中，单击“添加站点系统角色”。  
  
4.  在“常规”页上，指定站点系统的常规设置，然后单击“下一步”。  
  
5.  在“系统角色选择”页上的可用角色列表中选择“Endpoint Protection 点”，然后单击“下一步”。  
  
6.  在“Endpoint Protection”页上，选择“我接受 Endpoint Protection 许可条款”复选框，然后单击“下一步”。  
  
    > [!IMPORTANT]  
    >  除非你接受许可条款，否则不能使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)]。  
  
7.  在“Microsoft Active Protection Service”页上，选择你想要发送到 Microsoft 的信息的级别以帮助开发新的定义，然后单击“下一步”。  
  
    > [!NOTE]  
    >  此选项配置默认使用的 Microsoft Active Protection Service 设置。 然后可以为你配置的每个反恶意软件策略配置自定义设置。 有关详细信息，请参阅 [如何在 System Center Configuration Manager 中为 Endpoint Protection 创建和部署反恶意软件策略](../LocTest/How-to-create-and-deploy-antimalware-policies-for-Endpoint-Protection-in-System-Center-Configuration-Manager.md)。  
  
8.  完成向导。  
  
###  <a name="BKMK_EPalerts"></a> 步骤 2：为 Endpoint Protection 配置警报  
 你可以在 [!INCLUDE[cm5long](../LocTest/includes/cm5long_md.md)] 中配置 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 警报以在层次结构中发生特定安全事件时通知管理用户。 通知显示在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 仪表板中的报表中，并且你可以将其配置为通过电子邮件发送至指定收件人。  
  
 使用本主题中的下列步骤和补充过程在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中为 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 配置警报。  
  
> [!IMPORTANT]  
>  你必须具有集合的“强制实施安全”权限才能配置 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 警报。  
  
#### 在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中为 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 配置警报的步骤  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”。  
  
2.  在“资产和符合性”工作区中，单击“设备集合”。  
  
3.  在“设备集合”列表中，选择要为其配置警报的集合，然后，在“主页”选项卡中的“属性”组中单击“属性”。  
  
    > [!NOTE]  
    >  无法为用户集合配置警报。  
  
4.  如果你想要在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台的“监视”工作区中查看有关此集合的反恶意软件操作的详细信息，则在*\<集合名称\>*“属性”对话框的“警报”选项卡中，选择“在 Endpoint Protection 仪表板中查看此集合”。  
  
    > [!NOTE]  
    >  此选项不可用于“所有系统”集合。  
  
5.  在 *\<Collection Name\>*“属性”对话框的“警报”选项卡上，单击“添加”。  
  
6.  在“添加新的集合警报”对话框中的“这些条件适用时生成警报”部分中，选择在指定的 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 事件发生时想要 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 生成的警报，然后单击“确定”。  
  
7.  在“警报”选项卡的“条件”列表中，选择每个 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 警报，然后指定下列信息：  
  
    -   “警报名称”\- 接受默认名称，或者输入新的警报名称。  
  
    -   “警报严重性” – 在列表中，选择要在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中显示的警报级别。  
  
8.  根据你选择的警报，指定以下其他信息。  
  
    |警报名称|所需的其他信息|  
    |----------|-------------|  
    |**恶意软件检测**|如果在所监视集合中的任何计算机上检测到恶意软件，则会生成此警报。<br /><br /> 指定以下信息以配置此警报：<br /><br /> “恶意软件检测阈值：” \- 指定生成此警报时的恶意软件检测级别。 在列表中，选择下面中的一项：<br /><br /> -   “高 – 所有检测” \- 当在指定集合中的一台或多台计算机上检测到任何恶意软件时且无论 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端执行何种操作，将生成此警报。<br />-   “中 – 检测到，挂起操作” \- 当在指定集合中的一台或多台计算机上检测到恶意软件时且必须手动删除此恶意软件，将生成此警报。<br />-   “低 – 检测到，仍处于活动状态” \- 当在指定集合中的一台或多台计算机上检测到恶意软件且软件仍处于活动状态时，将生成此警报。|  
    |**恶意软件爆发**|如果在你监视的集合中指定百分比的计算机上检测到指定的恶意软件，则将生成此警报。<br /><br /> 指定以下信息以配置此警报：<br /><br /> -   “检测到恶意软件的计算机的百分比” – 当集合中检测到恶意软件的计算机的百分比超过你指定的百分比时，将生成此警报。 指定介于“1”到“99”之间的百分比。 **Note:**      百分比值基于集合中的计算机数，但不包括没有安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端的计算机。 其中包括尚未安装 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端的计算机。|  
    |**重复恶意软件检测**|如果在你监视的集合中的计算机上，在指定的小时数内检测到特定恶意软件的次数超出指定次数，则会生成此警报。<br /><br /> 指定以下信息以配置此警报：<br /><br /> -   **检测到恶意软件的次数：**\- 当在集合中的计算机上检测到同一恶意软件的次数超过指定次数时，则会生成此警报。 指定一个介于“2”到“32”之间的数字。<br />-   **检测间隔（小时）：**指定在其间必须发生指定的恶意软件检测次数的检测间隔（以小时为单位）。 指定一个介于“1”到“168”之间的数字。|  
    |**多恶意软件检测**|如果在所监视集合中的计算机上，在指定的小时数内检测到的恶意软件类型超出指定数量，则会生成此警报。<br /><br /> 指定以下信息以配置此警报：<br /><br /> -   **检测到的恶意软件类型数：**当在集合中的计算机上检测到指定数量的不同恶意软件类型时，则会生成此警报。 指定一个介于“2”到“32”之间的数字。<br />-   **检测间隔（小时）：**指定在其间必须发生指定的恶意软件检测次数的检测间隔（以小时为单位）。 指定一个介于“1”到“168”之间的数字。|  
  
9. 单击“确定”关闭 *\<Collection Name\>*“属性”对话框。  
  
###  <a name="BKMK_EPdefs"></a> 步骤 3：为 Endpoint Protection 配置定义更新  
 通过 [!INCLUDE[cm5long](../LocTest/includes/cm5long_md.md)] 中的 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)]，你可以使用若干可用方法中的任何方法使反恶意软件定义在层次结构中的客户端计算机上保持最新。 本主题中的信息可以帮助你选择和配置这些方法。  
  
 若要更新反恶意软件定义，可以使用以下方法中的一种或多种：  
  
-   从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中分发的更新 – 此方法使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 软件更新将定义和引擎更新传送到层次结构中的计算机。  
  
-   从 Windows Server Update Services \(WSUS\) 分发的更新 – 此方法使用 WSUS 基础结构将定义和引擎更新传送到计算机。  
  
-   从 Microsoft 更新分发的更新 – 此方法允许计算机直接连接到 Microsoft 更新以下载定义和引擎更新。 对于不经常连接到企业网络的计算机，此方法会很有用。  
  
-   从 Microsoft 恶意软件防护中心分发的更新 – 此方法将从 Microsoft 恶意软件防护中心下载定义更新。  
  
-   来自 UNC 文件共享的更新 – 使用此方法，你可以将最新的定义和引擎更新保存到网络共享上。 然后客户端便可访问网络以安装更新。  
  
 你可以配置多个定义更新源，并控制对其进行评估和应用的顺序。 将在创建反恶意软件策略时，在“配置定义更新源”对话框中完成此操作。  
  
> [!IMPORTANT]  
>  如果你管理 Windows 10 Technical Preview 计算机，则必须配置 Endpoint Protection 以更新 Windows Defender 的恶意软件定义。  
  
#### 如何配置定义更新源  
 使用以下过程配置要用于每个反恶意软件策略的定义更新源。  
  
###### 若要配置定义更新源  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”。  
  
2.  在“资产和符合性”工作区中，展开“Endpoint Protection”，然后单击“反恶意软件策略”。  
  
3.  打开“默认反恶意软件策略”的属性页，或创建新的反恶意软件策略。 有关如何创建反恶意软件策略的详细信息，请参阅[如何在 System Center Configuration Manager 中为 Endpoint Protection 创建和部署反恶意软件策略](../LocTest/How-to-create-and-deploy-antimalware-policies-for-Endpoint-Protection-in-System-Center-Configuration-Manager.md)。  
  
4.  在反恶意软件属性对话框的“定义更新”部分中，单击“设置源”。  
  
5.  在“配置定义更新源”对话框中，选择要用于定义更新的源。 可以单击“向上”或“向下”来修改使用这些源的顺序。  
  
6.  单击“确定”以关闭“配置定义更新源”对话框。  
  
####  <a name="BKMK_EPsup"></a> 使用 Configuration Manager 软件更新来提供定义更新  
 可以配置 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 软件更新以将定义更新提供给客户端计算机。 可通过配置自动部署规则完成此操作。 在开始创建自动部署规则之前，请确保你已配置了 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 软件更新。 有关详细信息，请参阅 [System Center Configuration Manager 中的软件更新简介](../LocTest/Introduction-to-software-updates-in-System-Center-Configuration-Manager.md)。  
  
> [!NOTE]  
>  此过程仅用于必须专门为 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 配置的项。 有关创建自动部署规则向导的详细信息，请参阅[在 System Center Configuration Manager 中管理软件更新](../LocTest/Manage-software-updates-in-System-Center-Configuration-Manager.md)。  
  
###### 若要配置自动部署规则以提供定义更新  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“软件库”。  
  
2.  在“软件库”工作区中，展开“软件更新”，然后单击“自动部署规则”。  
  
3.  在“主页”选项卡上的“创建”组中，单击“创建自动部署规则”。  
  
4.  在“创建自动部署规则向导”的“常规”页上，指定下列信息：  
  
    -   “名称”：输入自动部署规则的唯一名称。  
  
    -   **集合**：选择你想要将定义更新部署到的客户端计算机的集合。  
  
        > [!NOTE]  
        >  不能将定义更新部署到用户集合。  
  
5.  单击“添加到现有软件更新组”。  
  
6.  确保选中“运行此规则后启用部署”复选框，然后单击“下一步”。  
  
7.  在向导的“部署设置”页上的“详细信息级别”列表中，选择“最小”，然后单击“下一步”。  
  
    > [!NOTE]  
    >  在“详细信息级别”列表中，选择“最小”（不带 Service Pack 的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]）或“仅错误消息” \([!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]\)。 这将减少定义部署返回的状态消息数。 此配置有助于降低 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 服务器上的 CPU 处理使用率。  
  
8.  在“属性筛选器”列表中，选择“更新分类”复选框。  
  
9. 在“搜索条件”列表中，单击“\<要查找的项\>”。 然后，在“搜索条件”对话框中的“指定要搜索的值”列表中，选择“定义更新”。  
  
10. 单击“确定”以关闭“搜索条件”对话框。  
  
11. 在“属性筛选器”列表中，选择“产品”复选框。  
  
12. 在“搜索条件”列表中，单击“\<要查找的项\>”。 然后，在“搜索条件”对话框中的“指定要搜索的值”列表中，选择适用于 Windows 8.1 及更早版本的“Forefront Endpoint Protection 2010”或适用于 Windows 10 及更高版本的“Windows Defender”。  
  
13. 单击“确定”以关闭“搜索条件”对话框，然后单击“下一步”。  
  
14. 在“属性筛选器”列表中，选择“被取代”复选框。  
  
15. 在“搜索条件”列表中，单击“\<要查找的项\>”。 然后，在“搜索条件”对话框中的“指定要搜索的值”列表中，选择“否”。  
  
16. 单击“确定”以关闭“搜索条件”对话框，然后单击“下一步”。  
  
17. 在向导的“评估计划”页中，选择“启用规则以按计划运行”，然后配置下载定义更新所依据的计划。 至少将规则设置为在每个软件更新点同步之后运行两个小时。 单击“下一步”。  
  
18. 在向导的“部署计划”页上配置下列设置：  
  
    -   “时间根据”：如果希望层次结构中的所有客户端同时安装最新定义，则选择“UTC”。 实际安装时间将在两小时时段内有所变化。 此设置是建议的最佳方案。  
  
    -   **软件可用时间**：指定可用于由此规则创建的部署的时间。 指定的时间必须至少为自动部署规则运行之后的一小时。 这有助于确保有足够时间将内容复制到层次结构中的分发点。 一些定义更新还可能包括反恶意软件引擎更新，这些更新可能要花更长时间才能到达分发点。  
  
    -   **安装截止时间**：选择“尽快”。  
  
        > [!NOTE]  
        >  软件更新截止时间在两小时时间段内变化，以防止所有客户端在同一时间请求更新。  
  
19. 单击“下一步”。  
  
20. 在向导的“用户体验”页上，在“用户通知”列表中，选择“在软件中心和所有通知中隐藏”。   这可确保以无提示方式安装定义更新。 单击“下一步”。  
  
21. 在向导的“警报”页中，你无需配置任何警报。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 会生成任何可能需要的警报。 单击“下一步”。  
  
22. 在向导的“下载设置”页中，选择必要的软件更新下载行为，然后单击“下一步”。  
  
23. 在向导的“部署包”页中，选择现有部署包或创建新的部署包，以包含与规则关联的软件更新文件。  
  
    > [!NOTE]  
    >  考虑将定义更新放置在不包含其他软件更新的包中。 此策略可保持定义更新包的大小较小，从而使其可以更快复制到分发点。  
  
24. 在向导的“分发点”页中，选择此包的内容将被复制到的一个或多个分发点，然后单击“下一步”。  
  
25. 在向导的“下载位置”页中，选择“从 Internet 下载软件更新”，然后单击“下一步”。  
  
26. 在向导的“语言选择”页中，选择要下载的更新的每个语言版本，然后单击“下一步”。  
  
27. 完成“创建自动部署规则向导”。  
  
28. 验证新规则显示在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台的“自动部署规则”节点中。  
  
#### 使用 Windows Server Update Services \(WSUS\) 提供定义  
 如果使用 WSUS 来使反恶意软件定义保持最新，可以将其配置为自动批准定义更新。 尽管推荐的方法是使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 软件更新使定义保持最新，但还可以将 WSUS 配置为一个方法以允许用户手动启动更新的定义。 使用以下过程将 WSUS 配置为定义更新源。  
  
##### 配置更新同步  
 若要将 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 软件更新配置为同步 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 定义更新，请使用以下过程。  
  
###### 若要在 Configuration Manager 中同步 Endpoint Protection 定义更新  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“管理”。  
  
2.  在“管理”工作区中，展开“站点配置”，然后单击“站点”。  
  
3.  选择包含你的软件更新点的站点。 在“设置”组中，单击“配置站点组件”，然后单击“软件更新点”。  
  
4.  在“软件更新点组件属性”对话框的“分类”选项卡中，选择“定义更新”复选框。  
  
5.  指定使用 WSUS 更新的“产品”：  
  
    -   对于 Windows 8.1 和更早版本，在“软件更新点组件属性”对话框的“产品”选项卡上，选择“Forefront Endpoint Protection 2010”复选框。  
  
    -   对于 Windows 10 及更高版本，在“软件更新点组件属性”对话框的“产品”选项卡上，选择“Windows Defender”和“Windows Technical Preview 2”复选框。  
  
6.  单击“确定”以关闭“软件更新点组件属性”对话框。  
  
 当你的 WSUS 服务器未集成到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 环境中时，则使用以下过程配置 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 更新。  
  
###### 若要在独立 WSUS 中同步 Endpoint Protection 定义更新  
  
1.  在 WSUS 管理控制台中，展开“计算机”，单击“选项”，然后再单击 “产品和分类”。  
  
2.  指定使用 WSUS 更新的“产品”：  
  
    -   对于 Windows 8.1 和更早版本，在“软件更新点组件属性”对话框的“产品”选项卡上，选择“Forefront Endpoint Protection 2010”复选框。  
  
    -   对于 Windows 10 及更高版本，在“软件更新点组件属性”对话框的“产品”选项卡上，选择“Windows Defender”和“Windows Technical Preview 2”复选框。  
  
3.  在“产品和分类”对话框的“分类”选项卡上，选择“定义更新”和“更新”复选框。  
  
##### 批准定义更新  
 必须先批准 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 定义更新并将其下载到 WSUS 服务器，然后再将其提供给请求可用更新列表的客户端。 客户端连接到 WSUS 服务器以检查适用的更新，然后请求最新批准的定义更新。  
  
###### 若要在 WSUS 中批准定义和更新  
  
1.  在 WSUS 管理控制台中，单击“更新”，然后单击“所有更新”或想要批准的更新的分类。  
  
2.  在更新列表中，右键单击想要批准以安装的更新，然后单击“批准”。  
  
3.  在“批准更新”对话框中，选择想要为其批准更新的计算机组，然后单击“批准安装”。  
  
 除手动批准以外，还可以为定义更新和 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 更新设置自动批准规则。 这会将 WSUS 配置为自动批准 WSUS 下载的 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 定义更新。  
  
###### 若要配置自动批准规则  
  
1.  在 WSUS 管理控制台中，单击“选项”，然后单击“自动批准”。  
  
2.  在“更新规则”选项卡上，单击“新规则”。  
  
3.  在“添加规则”对话框中，在“步骤 1：选择属性”下选择“当更新在某个特定分类中时”复选框。  
  
4.  在“步骤 2：编辑属性”下，单击“任何分类”。  
  
5.  清除除“定义更新”以外的所有复选框，然后单击“确定”。  
  
6.  在“添加规则”对话框中，在“步骤 1：选择属性”下选择“当更新在某个特定产品中时”复选框。  
  
7.  在“步骤 2：编辑属性”下，单击“任何产品”。  
  
8.  除适用于 Windows 8.1 及更早版本的“Forefront Endpoint Protection”或适用于 Windows 10 及更高版本的“Windows Defender”以外，清除其余所有复选框，然后单击“确定”。  
  
9. 在“步骤 3：指定一个名称”下，为该规则输入名称，然后单击“确定”。  
  
10. 在“自动批准”对话框中，选择用于新创建的规则的复选框，然后单击“运行规则”。  
  
> [!NOTE]  
>  若要使 WSUS 服务器和客户端计算机上的性能最大化，则拒绝旧定义更新。 若要完成此任务，可以配置自动批准修订和自动拒绝过期更新。 有关详细信息，请参阅 [Microsoft 知识库文章 938947](http://go.microsoft.com/fwlink/p/?LinkId=204078)。  
  
#### 使用 Microsoft 更新下载定义  
 当你选择从 Microsoft 更新下载定义更新时，客户端将按照反恶意软件策略对话框的“定义更新”部分中定义的间隔检查 Microsoft 更新网站。  
  
 当客户端不具有到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点的连接或当你希望用户能够启动定义更新时，此方法会很有用。  
  
> [!IMPORTANT]  
>  客户端必须在 Internet 上具有对 Microsoft 更新的访问权限，才能够使用此方法下载定义更新。  
  
#### 使用 Microsoft 恶意软件防护中心下载定义  
 你可以将客户端配置为从 Microsoft 恶意软件防护中心下载定义更新。 如果 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端未能够从另一源下载更新，则使用此选项下载定义更新。 如果你的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 基础结构存在阻止更新交付的问题，此更新方法会很有用。  
  
> [!IMPORTANT]  
>  客户端必须在 Internet 上具有对 Microsoft 更新的访问权限，才能够使用此方法下载定义更新。  
  
#### 从网络上的共享下载定义  
 你可以手动从 Microsoft 下载最新定义更新，然后将客户端配置为从网络上的共享文件夹下载这些定义。 用户还可以在你使用此更新源时启动定义更新。  
  
> [!NOTE]  
>  客户端必须具有对共享文件夹的读取访问权限，才能够下载定义更新。  
  
 有关如何下载要存储在文件共享上的定义和引擎更新的详细信息，请参阅[安装最新的 Microsoft Forefront Security 定义更新](http://www.microsoft.com/security/portal/Definitions/HowToForeFront.aspx)。  
  
###### 若要从文件共享配置定义下载  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”。  
  
2.  在“资产和符合性”工作区中，展开“Endpoint Protection”，然后单击“反恶意软件策略”。  
  
3.  打开“默认反恶意软件策略”的属性页，或创建新的反恶意软件策略。 有关如何创建反恶意软件策略的详细信息，请参阅[如何在 System Center Configuration Manager 中为 Endpoint Protection 创建和部署反恶意软件策略](../LocTest/How-to-create-and-deploy-antimalware-policies-for-Endpoint-Protection-in-System-Center-Configuration-Manager.md)。  
  
4.  在反恶意软件属性对话框的“定义更新”部分中，单击“设置源”。  
  
5.  在“配置定义更新源”对话框中，选择“来自 UNC 文件共享的更新”。  
  
6.  单击“确定”以关闭“配置定义更新源”对话框。  
  
7.  单击“设置路径”。 然后，在“配置定义更新 UNC 路径”对话框中，添加一个或多个指向网络共享上定义更新文件位置的 UNC 路径。  
  
8.  单击“确定”以关闭“配置定义更新 UNC 路径”对话框。  
  
### 步骤 4：为 Endpoint Protection 创建和部署反恶意软件策略  
 请参阅[如何在 System Center Configuration Manager 中为 Endpoint Protection 创建和部署反恶意软件策略](../LocTest/How-to-create-and-deploy-antimalware-policies-for-Endpoint-Protection-in-System-Center-Configuration-Manager.md)。  
  
###  <a name="BKMK_EPclient"></a> 步骤 5：为 Endpoint Protection 配置自定义客户端设置。  
 此过程为 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 配置自定义客户端设置，前者可部署到层次结构中的计算机集合。  
  
> [!IMPORTANT]  
>  除非你确信要将这些设置应用于层次结构中的所有计算机，否则请不要配置默认 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端设置。  
  
##### 若要启用 Endpoint Protection 并配置自定义客户端设置  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“管理”。  
  
2.  在“管理”工作区中，单击“客户端设置”。  
  
3.  在“主页”选项卡上的“创建”组中，单击“创建自定义客户端设备设置”。  
  
4.  在“创建自定义客户端设备设置”对话框中，为设置组提供名称和描述，然后选择“Endpoint Protection”。  
  
5.  配置所需的 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端设置。 有关可以配置的 Endpoint Protection 客户端设置的完整列表，请参阅[关于 System Center Configuration Manager 中的客户端设置](../LocTest/About-client-settings-in-System-Center-Configuration-Manager.md)主题中的 Endpoint Protection 部分。  
  
    > [!IMPORTANT]  
    >  必须先安装 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 站点系统角色，然后才能为 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 配置客户端设置。  
  
6.  单击“确定”关闭“创建自定义客户端设备设置”对话框。 新的客户端设置显示在“管理”工作区的“客户端设置”节点中。  
  
7.  在可以使用自定义客户端设置之前，必须将它们部署到集合。 选择你想要部署的自定义客户端设置，然后在“主页”选项卡的“客户端设置” 组中，单击“部署”。  
  
8.  在“选择集合”对话框中，选择你想要将客户端设置部署到的集合，然后单击“确定”。 新的部署显示在细节窗格的“部署”选项卡中。  
  
 当客户端计算机下一次下载客户端策略时，将使用这些设置对它们进行配置。 若要为单一客户端启动策略检索，请参阅[如何在 System Center Configuration Manager 中管理客户端](../LocTest/How-to-manage-clients-in-System-Center-Configuration-Manager.md)中的“为 Configuration Manager 客户端启动策略检索”部分。  
  
## 如何在 Configuration Manager 中设置磁盘映像中的 Endpoint Protection 客户端  
 你可以将 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端安装在打算用作 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 操作系统部署的磁盘映像源的计算机上。 此计算机通常称为引用计算机。 创建操作系统的映像之后，你可以随后使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 操作系统部署将可能包含软件包（包括 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)]）的映像部署到客户端计算机。  
  
 使用本主题的过程来帮助你在引用计算机上安装和配置 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端  
  
### 在引用计算机上安装 Endpoint Protection 客户端的先决条件  
 下面的列表包含在引用计算机上安装 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端软件的必需先决条件。  
  
-   你必须具有对 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端安装包 **scepinstall.exe** 的访问权限。 可在站点服务器上的 [!INCLUDE[cm5long](../LocTest/includes/cm5long_md.md)] 安装文件夹的“客户端”文件夹中找到此包。  
  
-   若要确保使用机构中所需的配置部署 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端，请创建一个反恶意软件策略，然后导出该策略。 你可以随后指定要在手动安装 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端时使用的反恶意软件策略。 有关详细信息，请参阅 [如何在 System Center Configuration Manager 中为 Endpoint Protection 创建和部署反恶意软件策略](../LocTest/How-to-create-and-deploy-antimalware-policies-for-Endpoint-Protection-in-System-Center-Configuration-Manager.md)。  
  
    > [!NOTE]  
    >  无法导出“默认客户端反恶意软件策略”。  
  
-   如果要使用最新的定义安装 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端，你必须从 [Microsoft Malware Protection Center（Microsoft 恶意软件防护中心）](http://go.microsoft.com/fwlink/?LinkID=200965)下载这些定义。  
  
### 如何在引用计算机上安装 Endpoint Protection 客户端软件  
 你可以通过命令提示符以本地方式在引用计算机上安装 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端。 为此，你必须首先获取安装文件“scepinstall.exe”。 你也可以使用预先配置的反恶意软件策略或以前导出的反恶意软件策略来安装客户端。  
  
##### 通过命令提示符安装 Endpoint Protection 客户端  
  
1.  将 **scepinstall.exe** 从 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 安装媒体上的“客户端”文件夹复制到想要安装 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端软件的计算机上。  
  
2.  使用管理员权限打开命令提示符，导航到“scepinstall.exe”所在的文件夹，然后运行下列命令，同时添加所需的任何其他命令行属性：  
  
    ```  
    scepinstall.exe  
    ```  
  
     你可以指定下列命令行属性之一：  
  
    |属性|描述|  
    |--------|--------|  
    |\/s|指定将执行无提示安装。|  
    |\/q|指定将执行安装程序文件的无提示提取。|  
    |\/i|指定应执行正常安装。|  
    |\/noreplace|指定在安装过程中不卸载第三方反恶意软件。|  
    |\/policy|指定要用于在安装过程中配置客户端的反恶意软件策略文件。|  
    |\/sqmoptin|指定选择将此客户端软件安装加入 Microsoft 客户体验改善计划。|  
  
3.  请按照屏幕说明进行操作以完成客户端安装。  
  
4.  如果下载了最新的更新定义包，请将该包复制到客户端计算机，然后双击该定义包进行安装。  
  
    > [!NOTE]  
    >  [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端安装完成后，客户端将自动执行定义更新检查。 如果此更新检查成功，则你不必手动安装最新的定义更新包。  
  
##### 通过命令提示符使用反恶意软件策略安装客户端软件  
  
1.  将 **scepinstall.exe** 和导出的或预配置的反恶意软件政策复制到想要安装 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端软件的计算机上。  
  
2.  使用管理员权限打开命令提示符，导航到“scepinstall.exe”和反恶意软件策略所在的文件夹，然后运行下列命令：  
  
    ```  
    scepinstall.exe /policy <full path>\<policy file>  
    ```  
  
3.  请按照屏幕说明进行操作以完成客户端安装。  
  
4.  如果下载了最新的定义包，请将该包复制到客户端计算机，然后双击该定义包进行安装。  
  
    > [!NOTE]  
    >  [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端安装完成后，客户端将自动执行定义更新检查。 如果此更新检查成功，则你不必手动安装最新的定义更新包。  
  
### 验证是否正确安装了 Endpoint Protection 客户端  
 在引用计算机上安装 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端之后，请验证该客户端是否正常工作。  
  
##### 验证是否正确安装了 Endpoint Protection 客户端  
  
1.  在引用计算机上，从 Windows 通知区域中打开“System Center 2012 Endpoint Protection”。  
  
2.  在“System Center 2012 Endpoint Protection”对话框的“主页”选项卡上，验证“实时保护”是否设置为“启用”。  
  
3.  验证是否为“病毒和间谍软件定义”显示了“最新”。  
  
4.  为了确保引用计算机已针对映像做好准备，请在“扫描选项”下选择“完全”，然后单击“立即扫描”。  
  
### 如何针对映像准备 Endpoint Protection 客户端  
 验证 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端是否已正确安装在引用计算机上后，你可以针对映像准备计算机。 执行下列步骤以针对映像准备 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端。  
  
 有关 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中操作系统部署的详细信息，请参阅[使用 System Center Configuration Manager 管理操作系统映像](../LocTest/Manage-operating-system-images-with-System-Center-Configuration-Manager.md)。  
  
##### 针对映像准备 Endpoint Protection 客户端  
  
1.  在引用计算机上，以具有管理权限的用户身份登录。  
  
2.  从 TechNet 上的 [Windows SysInternals 站点](http://go.microsoft.com/fwlink/?LinkId=215263)下载并安装 **PsTools**。  
  
3.  打开提升的命令提示符，导航到你在其中安装了 PsTools 的文件夹，然后键入下列命令  
  
    ```  
    Psexec.exe –s –i regedit.exe  
    ```  
  
    > [!IMPORTANT]  
    >  以此方式运行注册表编辑器时请小心；PsExec.exe 中的 –s 选项使用 LocalSystem 权限运行注册表编辑器。  
  
4.  在注册表编辑器中，导航到下列每个注册表项，并将其删除。  
  
    > [!IMPORTANT]  
    >  必须在对引用计算机进行映像之前的最后一步骤删除这些注册表项。[!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端启动后，会重新创建注册表项。 如果重启引用计算机，你必须再次删除这些注册表项。  
  
    -   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Microsoft Antimalware\\InstallTime**  
  
    -   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Microsoft Antimalware\\Scan\\LastScanRun**  
  
    -   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Microsoft Antimalware\\Scan\\LastScanType**  
  
    -   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Microsoft Antimalware\\Scan\\LastQuickScanID**  
  
    -   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Microsoft Antimalware\\Scan\\LastFullScanID**  
  
    -   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\RemovalTools\\MRT\\GUID**  
  
 完成前面的步骤后，即可针对映像准备引用计算机。 有关 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中操作系统部署的详细信息，请参阅[使用 System Center Configuration Manager 管理操作系统映像](../LocTest/Manage-operating-system-images-with-System-Center-Configuration-Manager.md)。  
  
 在部署包含 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端软件的映像时，[!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端将自动向计算机所分配到的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点报告信息，并且会下载和应用适用于客户端计算机的策略。
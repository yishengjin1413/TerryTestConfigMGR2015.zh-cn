---
title: "如何在 System Center Configuration Manager 中创建远程连接配置文件"
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
ms.assetid: 8c6eabc4-5dda-4682-b03e-3a450e6ef65a
caps.latest.revision: 8
caps.handback.revision: 7
translationtype: Human Translation
---
# 如何在 System Center Configuration Manager 中创建远程连接配置文件
使用下列必需的步骤，通过使用 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]**创建远程连接配置文件向导**来创建远程连接配置文件。  
  
 使用此过程之前，请确保你已阅读[在 System Center Configuration Manager 中使用远程连接配置文件](../LocTest/Working-with-remote-connection-profiles-in-System-Center-Configuration-Manager.md)中的介绍信息和先决条件。  
  
## 创建并部署远程连接配置文件  
  
#### 若要创建远程连接配置文件  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”。  
  
2.  在“资产和符合性”工作区中，展开“符合性设置”，然后单击“远程连接配置文件”。  
  
3.  在“主页”选项卡上的“创建”组中，单击“创建远程连接配置文件”。  
  
4.  在**创建远程连接配置文件向导**的“常规”页上，使用最多 256 个字符为每个配置文件指定名称和可选描述。  
  
5.  在向导的“配置文件”设置页面上，为远程连接配置文件指定以下设置:  
  
    -   **远程桌面网关服务器的完整名称和端口\(可选\)** \- 指定用于连接的远程桌面网关服务器的名称。  
  
        > [!NOTE]  
        >  [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不支持在此框中使用国际化域名指定服务器。  
        >   
        >  服务器名称的长度不能超过 256 个字符，可以包含用句点分隔的大写字符、小写字符、数字字符以及“–”和“\_”字符。  
  
    -   **只允许通过网络级别身份验证运行远程桌面的计算机中的连接**  
  
6.  为下列每个连接设置选择“已启用”或“已禁用”：  
  
    -   **允许至工作计算机的远程连接**  
  
    -   **允许工作计算机的所有主要用户进行远程连接**  
  
    -   **对 Windows 域和专用网络上的连接允许 Windows 防火墙例外**  
  
    > [!IMPORTANT]  
    >  所有三个设置必须相同，然后你才能继续通过向导的此页。  
  
7.  在向导的“摘要”页上，查看要执行的操作，然后完成向导。  
  
 新的远程连接配置文件将显示在“资产和符合性”工作区的“远程连接配置文件”节点中。  
  
#### 部署远程连接配置文件  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”。  
  
2.  在“资产和符合性”工作区中，展开“符合性设置”，然后单击“远程连接配置文件”。  
  
3.  在“远程连接配置文件”列表中，选择要部署的远程连接配置文件，然后，在“主页”选项卡上的“部署”组中单击“部署”。  
  
4.  在“部署远程连接配置文件”对话框中，指定下列信息：  
  
    -   **集合** \- 单击“浏览”以选择要在其中部署远程连接配置文件的设备集合。  
  
    -   **在支持时修正非符合性规则** \- 启用此选项，以便在设备上发现远程连接配置文件不符合（例如，不存在时）时自动修正该配置文件。  
  
    -   **允许维护时段外的修正** \- 如果为你向其中部署远程连接配置文件的集合配置了维护时段，请启用此选项以让 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 在维护时段外修正远程连接配置文件。 有关维护时段的详细信息，请参阅[如何在 Configuration Manager 中使用维护时段](../LocTest/How-to-use-maintenance-windows-in-System-Center-Configuration-Manager.md)。  
  
    -   **生成警报** \- 启用此选项以配置一个警报，如果在指定日期和时间之前远程连接配置文件符合性小于指定百分比，则生成该警报。 你也可以指定是否希望将警报发送到 System Center Operations Manager。  
  
    -   **指定此配置基线的符合性评估计划** \- 指定在设备上对部署的远程连接配置文件进行评估所依据的计划。 你可以指定简单计划或自定义计划。  
  
    > [!TIP]  
    >  如果设备离开向其中部署了远程连接配置文件的集合，则会在该设备上禁用远程连接配置文件设置。 但是，要使此进程正常发生，你必须已至少部署了一个配置项目或包含站点中的配置项目的配置基线。  
    >   
    >  当用户登录时，设备将评估配置文件。  
    >   
    >  如果两个远程连接配置文件部署到同一设备集合，在其中一个配置文件中选中“在支持时修正非符合性规则”，在另外一个配置文件中，取消选中相同的选项，并且两个远程连接配置文件包含不同的连接设置，则取消选中此选项的配置文件可能会替代另一个配置文件中的设置。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不支持这种类型的远程连接配置文件部署。  
  
5.  单击“确定”关闭“部署远程连接配置文件”对话框并创建部署。  
  
## 监视远程连接配置文件  
  
### 在 Configuration Manager 控制台中查看符合性结果  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“监视”。  
  
2.  在“监视”工作区中，单击“部署”。  
  
3.  在“部署”列表中，选择要查看其符合性信息的远程连接配置文件部署。  
  
4.  你可以在主页上查看有关远程连接配置文件部署符合性的摘要信息。 若要查看更详细的信息，请选择远程连接配置文件部署，然后在“主页”选项卡上的“部署”组中，单击“查看状态”以打开“部署状态”页。  
  
     “部署状态”页包含下列选项卡：  
  
    -   **符合：**显示基于受影响资产数量的远程连接配置文件的符合性。 你可以双击规则以在“资产和符合性”工作区中的“用户”节点下创建一个临时节点。 此节点包含符合远程连接配置文件的所有设备。 “资产详细信息”窗格也显示符合此配置文件的设备。 双击列表中的设备以显示其他信息。  
  
        > [!IMPORTANT]  
        >  如果某个远程连接配置文件在客户端设备上不适用，则不会评估该配置文件。 但是，它返回的状态为符合。  
  
    -   **错误：**显示基于受影响资产数量的所选远程连接配置文件部署的所有错误的列表。 你可以双击规则以在“资产和符合性”工作区的“用户”节点下创建一个临时节点。 此节点包含对于此配置文件生成了错误的所有设备。 当你选择某台设备时，“资产详细信息”窗格将显示受所选问题影响的设备。 双击列表中的设备以显示有关问题的其他信息。  
  
    -   **不符合：**显示基于受影响资产数量的远程连接配置文件内所有不符合规则的列表。 你可以双击规则以在“资产和符合性”工作区的“用户”节点下创建一个临时节点。 此节点包含不符合此配置文件的所有设备。 当你选择某台设备时，“资产详细信息”窗格将显示受所选问题影响的设备。 双击列表中的设备以显示有关问题的其他信息。  
  
    -   **未知：**显示没有为所选远程连接配置文件部署报告符合性的所有设备的列表，以及设备的当前客户端状态。  
  
5.  在“部署状态”页上，你可以查看有关所部署的远程连接配置文件的符合性的详细信息。 将在“部署”节点下创建一个临时节点，该节点可帮助你快速再次找到此信息。  
  
### 使用报表查看符合性结果  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中包括内置报表，可用于监视有关远程连接配置文件的信息。 这些报表的报表类别为“符合性和设置管理”。  
  
> [!IMPORTANT]  
>  在符合性设置报表中使用参数“设备筛选器”和“用户筛选器”时，你必须使用通配符 \(%\) 字符。  
  
 有关如何配置 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的报告的详细信息，请参阅 [System Center Configuration Manager 中的报表](../LocTest/Reporting-in-System-Center-Configuration-Manager.md)。  
  
## 请参阅  
 [System Center Configuration Manager 的符合性设置技术参考](../LocTest/Compliance-settings-technical-reference-for-System-Center-Configuration-Manager.md)
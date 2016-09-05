---
title: "如何在 System Center Configuration Manager 中部署证书配置文件"
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
ms.assetid: 1ecfe2c6-45bc-4d8a-a7f6-53525c958e0f
caps.latest.revision: 7
caps.handback.revision: 6
---
# 如何在 System Center Configuration Manager 中部署证书配置文件
若要在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中将证书部署到用户或设备，你必须将证书配置文件部署到一个或多个用户或设备集合。  
  
 你可以部署受信任的证书颁发机构 \(CA\) 证书以及用户或设备证书。 在部署用户或设备证书之前，请检查设备是否已为这些证书安装了受信任的根 CA 证书。 如果设备没有受信任的根证书，则可能是因为它不是域成员或者它来自不受信任的林，除了部署用户或设备证书外，你还必须将根 CA 证书部署到设备。  
  
 使用“部署证书配置文件”对话框配置证书配置文件的部署。 此配置包括定义将向其中部署证书配置文件的集合，以及指定对证书配置文件的符合性进行评估的频率。  
  
> [!NOTE]  
>  如果将多个公司资源访问配置文件部署到同一个用户或设备，会出现下列行为：  
>   
>  -   如果冲突的设置中包含一个可选值，则它将不会发送到设备。  
> -   如果冲突设置包含必需的值，则默认值将发送到设备。 如果没有默认值，则整个公司资源访问配置文件将失败。  
  
> [!NOTE]  
>  你必须首先配置基础结构并创建证书配置文件，然后才能部署证书配置文件。 有关详细信息，请参阅下列主题：  
>   
>  -   [在 System Center Configuration Manager 中配置证书配置文件](../LocTest/Configuring-certificate-profiles-in-System-Center-Configuration-Manager.md)  
> -   [如何在 System Center Configuration Manager 中创建证书配置文件](../LocTest/How-to-create-certificate-profiles-in-System-Center-Configuration-Manager.md)  
  
### 部署证书配置文件  
  
1.  在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 控制台中，单击“资产和符合性”。  
  
2.  在“资产和符合性”工作区中，展开“符合性设置”，展开“公司资源访问”，然后单击“证书配置文件”。  
  
3.  在“证书配置文件”列表中，选择要部署的证书配置文件。  
  
4.  在“主页”选项卡上的“部署”组中，单击“部署”。  
  
5.  在“部署证书配置文件”对话框中，指定下列信息：  
  
    -   **集合**：单击“浏览”可选择要在其中部署证书配置文件的用户或设备集合。  
  
    -   **生成警报**：启用此选项以配置一个警报，如果在指定日期和时间之前证书配置文件符合性小于指定百分比，则生成该警报。 你也可以指定是否希望将警报发送到 Microsoft System Center Operations Manager。  
  
    -   **随机延迟\(小时\)**：（仅适用于包含简单证书注册协议设置的证书配置文件）– 指定一个延迟时段以避免对网络设备注册服务进行过度处理。 默认值为 **64** 小时。  
  
    -   **指定此证书配置文件的符合性评估计划**：指定在客户端计算机上对部署的证书配置文件进行评估所依据的计划。 这可以是简单计划或自定义计划。  
  
        > [!NOTE]  
        >  当用户登录时，客户端计算机上将评估配置文件。  
  
6.  单击“确定”关闭“部署证书配置文件”对话框并创建部署。 有关如何监视部署的详细信息，请参阅 [如何在 System Center Configuration Manager 中监视证书配置文件](../LocTest/How-to-monitor-certificate-profiles-in-System-Center-Configuration-Manager.md)。  
  
## 请参阅  
 [System Center Configuration Manager 中证书配置文件的操作和维护](../LocTest/Operations-and-maintenance-for-certificate-profiles-in-System-Center-Configuration-Manager.md)
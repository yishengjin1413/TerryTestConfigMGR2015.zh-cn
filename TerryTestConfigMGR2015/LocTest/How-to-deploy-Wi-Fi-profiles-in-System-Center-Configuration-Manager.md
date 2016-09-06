---
title: "如何在 System Center Configuration Manager 中部署 Wi-Fi 配置文件"
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
ms.assetid: 3753608d-b539-44dc-8e3f-b631319e7687
caps.latest.revision: 5
caps.handback.revision: 2
translationtype: Human Translation
---
# 如何在 System Center Configuration Manager 中部署 Wi-Fi 配置文件
必须将 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的 Wi\-Fi 配置文件部署到一个或多个集合，然后才能使用这些配置文件。  
  
 使用“部署 Wi\-Fi 配置文件”对话框配置 Wi\-Fi 配置文件的部署。 在配置过程中，你可以定义将向其中部署 Wi\-Fi 配置文件的集合，以及指定对 Wi\-Fi 配置文件的符合性进行评估的频率。  
  
> [!NOTE]  
>  如果部署多个公司资源访问配置文件到同一个用户时，会出现下列行为：  
>   
>  -   如果冲突的设置中包含一个可选值，则它将不会发送到设备。  
> -   如果冲突设置包含必需的值，则默认值将发送到设备。 如果没有默认值，则整个公司资源访问配置文件将失败。  
  
> [!NOTE]  
>  在删除 Wi\-Fi 配置文件部署时，不会从客户端设备中删除 Wi\-Fi 配置文件。 如果要从设备中删除配置文件，你必须将其手动删除。  
  
## 部署 Wi\-Fi 配置文件  
  
#### 部署 Wi\-Fi 配置文件  
  
1.  在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 控制台中，单击“资产和符合性”。  
  
2.  在“资产和符合性”工作区中，展开“符合性设置”，展开“公司资源访问”，然后单击“Wi\-Fi 配置文件”。  
  
3.  在“Wi\-Fi 配置文件”列表中，选择要部署的 Wi\-Fi 配置文件，然后，在“主页”选项卡上的“部署”组中单击“部署”。  
  
4.  在“部署 Wi\-Fi 配置文件”对话框中，指定下列信息：  
  
    -   **集合** \- 单击“浏览”以选择要在其中部署 Wi\-Fi 配置文件的集合。  
  
    -   **生成警报** \- 启用此选项以配置一个警报，如果在指定日期和时间之前 Wi\-Fi 配置文件符合性小于指定百分比，则生成该警报。 你也可以指定是否希望将警报发送到 System Center Operations Manager。  
  
    -   **指定此 Wi\-Fi 配置文件的符合性评估计划** \- 指定在客户端计算机上对部署的 Wi\-Fi 配置文件进行评估所依据的计划。 该计划可以是简单计划或自定义计划。  
  
        > [!NOTE]  
        >  当用户登录时，客户端计算机将评估配置文件。  
  
5.  单击“确定”关闭“部署 Wi\-Fi 配置文件”对话框并创建部署。 若要深入了解如何监视部署，请参阅[如何在 System Center Configuration Manager 中监视 Wi\-Fi 配置文件](../LocTest/How-to-monitor-Wi-Fi-profiles-in-System-Center-Configuration-Manager.md)。  
  
## 请参阅  
 [System Center Configuration Manager 中 Wi\-Fi 配置文件的操作和维护](../LocTest/Operations-and-maintenance-for-Wi-Fi-Profiles-in-System-Center-Configuration-Manager.md)
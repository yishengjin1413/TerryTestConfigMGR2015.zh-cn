---
title: "在 System Center Configuration Manager 中规划和配置符合性设置"
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
ms.assetid: 9ea20b01-676a-4cc2-b328-0098a41b202e
caps.latest.revision: 8
caps.handback.revision: 7
---
# 在 System Center Configuration Manager 中规划和配置符合性设置
在开始使用 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 符合性设置之前，需要了解几个先决条件，并且需要执行一些配置任务。  
  
## 符合性设置的先决条件  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 符合性设置需要进行以下操作：  
  
|先决条件|更多信息|  
|----------|----------|  
|必须启用 Windows [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端并配置符合性评估。|[配置 Windows 计算机的符合性设置](#BKMK_Configure)|  
|如果你想要运行报表，就必须为站点配置报告。|[System Center Configuration Manager 中的报表](../LocTest/Reporting-in-System-Center-Configuration-Manager.md)|  
|必须授予管理员必要的安全权限。|“符合性设置管理员”安全角色包括管理符合性设置、用户数据和配置文件配置项目和远程连接配置文件必需的权限。<br /><br /> [为 System Center Configuration Manager 配置基于角色的管理](../LocTest/Configure-role-based-administration-for-System-Center-Configuration-Manager.md)|  
  
##  <a name="BKMK_Configure"></a> 配置 Windows 计算机的符合性设置  
 一旦你准备好必需的先决条件，你可以在你的层次结构中配置符合性设置。  
  
 此过程为符合性设置配置默认客户端设置并应用于你的层次结构中的所有计算机。 如果希望这些设置仅应用于某些计算机，请创建一个自定义设备客户端设置，并将其分配给包含要使用符合性设置的计算机的集合。 有关如何创建自定义设备设置的详细信息，请参阅 [如何在 System Center Configuration Manager 中配置客户端设置](../LocTest/How-to-configure-client-settings-in-System-Center-Configuration-Manager.md)。  
  
> [!TIP]  
>  其他设备类型不需要任何特定的配置以评估符合性设置。  
  
#### 若要启用并配置 Windows 计算机的符合性设置  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“管理”。  
  
2.  在“管理”工作区中，单击“客户端设置”\>“默认设置”。  
  
3.  在“主页”选项卡上的“属性”组中，单击“属性”。  
  
4.  在“默认设置”对话框中，单击“符合性设置”。  
  
5.  为符合性设置配置下列客户端设置：  
  
    |客户端设置名|更多信息|  
    |------------|----------|  
    |**启用客户端上的符合性评估**|如果想要评估客户端设备上的符合性，请设置为“True”。|  
    |**计划符合性评估**|如果你想要修改客户端设备上的默认符合性评估，请单击“计划”。|  
    |**启用用户数据和配置文件**|如果想要向 Windows 计算机创建并部署用户数据和配置文件配置项目，则启用该选项。 有关详细信息，请参阅[使用 System Center Configuration Manager 中的用户数据和配置文件的配置项目](../LocTest/Working-with-user-data-and-profiles-configuration-items-in-System-Center-Configuration-Manager.md)。|  
  
6.  单击“确定”来关闭“默认设置”对话框。  
  
 当客户端计算机下一次下载客户端策略时，将使用这些设置进行配置。  
  
## 请参阅  
 [使用 System Center Configuration Manager 确保设备的合规性](../LocTest/Ensure-device-compliance-with-System-Center-Configuration-Manager.md)
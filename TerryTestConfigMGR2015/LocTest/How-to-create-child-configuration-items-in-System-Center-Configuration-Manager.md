---
title: "如何在 System Center Configuration Manager 中创建子配置项目"
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
ms.assetid: 113984fa-6150-41a1-89ed-d2a83b979732
caps.latest.revision: 5
caps.handback.revision: 4
translationtype: Human Translation
---
# 如何在 System Center Configuration Manager 中创建子配置项目
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的子配置项目是与原始配置项目保持关系的配置项目的副本；因此，它们从父配置项目继承原始配置。  
  
 当在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中查看子配置项目的属性时，你可以查看，但无法编辑所继承的对象和设置及其验证条件。 但是，您可以将其他验证条件添加到子配置项目并进行编辑，也可以向子配置项目添加新的对象和设置。 因此，创建和编辑子配置项目的通常目的在于改进原始配置项目以满足您的业务要求。  
  
> [!NOTE]  
>  只能从类型为“Windows 台式机和服务器\(自定义\)”的配置项目创建子配置项目。  
  
## 创建子配置项目  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”。  
  
2.  在“资产和符合性”工作区中，展开“符合性设置”，然后单击“配置项目”。  
  
3.  在“配置项目”列表中，选择要为其创建子配置项目的配置项目，然后在“主页”选项卡上的“配置项目”组中，单击“创建子配置项目”。  
  
4.  在“创建子配置项目向导”的“常规”页上，可以选择要用于创建子级的父配置项目的特定修订版本。 此向导中的其他步骤与用于创建标准配置项目的步骤相同。 有关详细信息，请参阅[如何为使用 System Center Configuration Manager 客户端管理的 Windows 台式机和服务器计算机创建配置项目](../LocTest/How-to-create-custom-configuration-items-for-Windows-desktop-and-server-computers-managed-with-the-System-Center-Configuration-Manager-client.md)。  
  
5.  完成向导。 新的子配置项目会显示在“配置项目”列表中。  
  
## 请参阅  
 [System Center Configuration Manager 的符合性设置技术参考](../LocTest/Compliance-settings-technical-reference-for-System-Center-Configuration-Manager.md)
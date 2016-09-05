---
title: "如何在 System Center Configuration Manager 中卸载应用程序"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-app
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 0ea3edaa-27c6-4391-9896-cd97d9c5d06d
caps.latest.revision: 4
caps.handback.revision: 3
author: barlanmsft
translationtype: Human Translation
---
# 如何在 System Center Configuration Manager 中卸载应用程序
执行下列步骤，以使用 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 卸载应用程序：  
  
-   在“创建部署类型向导”的“内容”页上，指定用于卸载部署类型内容的命令行。  
  
-   使用“卸载”这项部署操作来部署应用程序。  
  
> [!IMPORTANT]  
>  某些应用程序类型不支持卸载。  
  
 以下列表提供了有关应用程序卸载行为的详细信息：  
  
-   在卸载某个 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 应用程序时，不会自动卸载依赖它的任何应用程序。  
  
-   如果将使用“卸载”操作的应用程序部署到某用户，则会为计算机的所有用户安装该应用程序，但是，如果此用户的帐户没有卸载该应用程序的权限，则卸载可能会失败。  
  
-   如果从应用程序部署到的集合中删除用户或设备，则不会自动从设备中删除应用程序。  
  
-   部署目的为“卸载”的部署不会检查要求规则。 如果在运行部署的计算机上安装应用程序，则将会卸载它。  
  
> [!IMPORTANT]  
>  在可以利用“卸载”这项部署操作来部署应用程序之前，必须删除部署到集合的应用程序的任何现有部署或模拟部署。  
  
 有关如何创建部署类型的详细信息，请参阅[如何使用 System Center Configuration Manager 创建应用程序](../LocTest/How-to-create-applications-with-System-Center-Configuration-Manager.md)。  
  
 有关如何部署应用程序的详细信息，请参阅[如何使用 System Center Configuration Manager 部署应用程序](../LocTest/How-to-deploy-applications-with-System-Center-Configuration-Manager.md)。  
  
### 卸载应用程序  
  
1.  使用下列方法之一，通过卸载命令行来配置应用程序部署类型：  
  
    -   在“创建部署类型向导”的“常规”页上，选择选项“从安装文件中自动识别有关此部署类型的信息”。 如果安装文件中提供了此信息，则卸载命令行会自动添加到部署类型属性中。  
  
    -   在“创建部署类型向导”的“内容”页上，在“卸载程序”字段中指定用于卸载应用程序的命令行。  
  
        > [!NOTE]  
        >  只有在“创建部署类型向导”的“常规”页上选择了选项“手动指定部署类型信息”后，才会显示“内容”页面。  
  
    -   在 *\<deployment type name\>*“属性”对话框“程序”选项卡的“卸载程序”字段中指定命令行卸载应用程序。  
  
2.  在“部署软件向导”的“部署设置”页面中，部署应用程序并选择部署操作“卸载”  
  
    > [!NOTE]  
    >  在选择部署操作“卸载”时，部署目的会自动配置为“必需”。  
  
## 请参阅  
 [System Center Configuration Manager 中应用程序管理的技术参考](../LocTest/Application-management-technical-reference-for-System-Center-Configuration-Manager.md)
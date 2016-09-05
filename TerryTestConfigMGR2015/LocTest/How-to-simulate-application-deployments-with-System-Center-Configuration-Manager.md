---
title: "如何使用System Center Configuration Manager 模拟应用程序部署"
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
ms.assetid: 28b240a4-d358-40ce-8006-c697b1622ece
caps.latest.revision: 6
caps.handback.revision: 5
author: barlanmsft
translationtype: Human Translation
---
# 如何使用System Center Configuration Manager 模拟应用程序部署
如果想在不安装或卸载某个应用程序的情况下测试将它部署到计算机的适用性，请使用模拟部署。 模拟部署将评估部署类型的检测方法、要求和依赖关系，然后在“监视”工作区的“部署”节点中报告结果。 请使用本主题中的过程模拟 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的应用程序部署。  
  
> [!NOTE]  
>  不能将模拟部署用于移动设备的集合。  
>   
>  如果某个应用程序的模拟部署处于活动状态，则不能出于“卸载”这个部署目的而部署此应用程序。  
  
## 如何模拟应用程序部署  
  
#### 模拟应用程序部署  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，选择以下一项：  
  
    -   用户集合。  
  
    -   设备集合。  
  
    -   一个 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 应用程序。  
  
2.  在“主页”选项卡的“部署”组中，单击“模拟部署”。  
  
3.  在“模拟应用程序部署向导”中，指定以下信息：  
  
    -   **应用程序** \- 单击“浏览”，然后选择要为其创建模拟部署的应用程序。  
  
    -   **集合** \- 单击“浏览”，然后选择要用于模拟部署的集合。  
  
    -   **操作** \- 在下拉列表中，选择是要模拟所选应用程序的安装还是模拟其卸载。  
  
    -   **使用或不使用用户登录信息自动登录** \- 如果选中此选项，则客户端将评估模拟部署，而不管用户是否登录客户端。  
  
4.  单击“下一步”，查看“摘要”页上的信息，然后完成向导以创建模拟应用程序部署。  
  
5.  模拟的应用程序将出现在“监视”工作区的“部署”节点中，其用途为“模拟”。 有关如何监视应用程序部署的详细信息，请参阅[监视 System Center Configuration Manager 控制台中的应用程序](../LocTest/Monitor-applications-from-the-System-Center-Configuration-Manager-console.md)。  
  
## 请参阅  
 [System Center Configuration Manager 中应用程序管理的技术参考](../LocTest/Application-management-technical-reference-for-System-Center-Configuration-Manager.md)
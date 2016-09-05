---
title: "如何在 System Center Configuration Manager 中监视客户端部署状态"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-client
ms.tgt_pltfrm: na
ms.topic: get-started-article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 20a573b3-53cb-4ed5-bae1-7542f533ed20
caps.latest.revision: 11
caps.handback.revision: 11
translationtype: Human Translation
---
# 如何在 System Center Configuration Manager 中监视客户端部署状态
在站点间部署客户端需要时间，并且首次进行某些安装并不会成功。 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 控制台提供了一种通过实时报告客户端部署状态，从而关注集合内客户端部署的方法。  
  
> [!NOTE]  
>  使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台（如本文所述）是监视客户端部署的最佳方法，也是最可靠的方法。 控制台中“监视”工作区的“客户端状态”部分可实时准确地提供客户端部署状态。 也可以使用其他工具来监视客户端部署，例如 Windows Server 中的服务器管理器或 System Center Operations Manager，但是这样可能会从正常的客户端安装活动收到警报。 由于客户端安装程序 (CCMSetup.exe) 在不同环境中的运行方式，这些其他工具可能会生成不能准确反映客户端部署状态的假警报和警告。  
  
 在控制台的“监视”工作区中，可以监视指定集合内发生的客户端部署的以下状态：  

-   未启动   

-   是否满足条件  
  
-   正在进行  
  
-   不符合  
  
-   已失败  
  
-   未知  
  
 Configuration Manager 报告生产客户端或预生产客户端的部署。 Configuration Manager 控制台还提供指定时间内失败的客户端部署的图表，以帮助你确定随着时间的推移，要为排除部署问题而采取的措施是否提高了部署成功率。  
  
## 监视客户端部署  
  
-   在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“监视” > “客户端状态”。  
  
-   根据想要监视的客户端版本，单击“生产客户端部署”或“预生产客户端部署”。  
  
-   查看客户端部署状态和客户端部署失败的图表。  
  
-   如果想更改报告的范围，单击“浏览...” 并选择其他集合。  
  
 若要了解有关预生产客户端部署的详细信息，请参阅[如何在 System Center Configuration Manager 中的预生产集合中测试客户端升级](../LocTest/How-to-test-client-upgrades-in-a-preproduction-collection-in-System-Center-Configuration-Manager.md)。
 
 > [!NOTE]
 > 即使在已成功部署客户端时，托管预生产集合中站点系统角色的计算机上的部署状态也可能被报告为“未启动”。 当你将客户端提升为生产时，则会正常报告部署状态。   
  
 若要监视已部署客户端的状态，请参阅[如何在 System Center Configuration Manager 中监视客户端](../LocTest/How-to-monitor-clients-in-System-Center-Configuration-Manager.md)  
  
 可以使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 报告来了解有关站点中的客户端状态的详细信息。 有关如何运行报表的详细信息，请参阅 [System Center Configuration Manager 中的报表](../LocTest/Reporting-in-System-Center-Configuration-Manager.md)。  
  
## 另请参阅  
 [System Center Configuration Manager 的客户端部署任务](../LocTest/Client-deployment-tasks-for-System-Center-Configuration-Manager.md)
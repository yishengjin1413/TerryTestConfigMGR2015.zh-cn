---
title: "如何在 System Center Configuration Manager 中的预生产集合中测试客户端升级"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-client
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 49ef2ed2-2e15-4637-8b63-1d5b7f9c17e1
caps.latest.revision: 10
caps.handback.revision: 10
---
# 如何在 System Center Configuration Manager 中的预生产集合中测试客户端升级
对于在 Windows PC 和设备上升级 Configuration Manager 客户端，可以在升级站点的其余部分之前，在预生产集合中测试新客户端版本。  执行此操作时，只有属于预生产集合一部分的设备才能升级到新客户端。 只要有机会在此预生产集合中测试客户端，你就可以升级客户端，从而使客户端软件的新版本可用于该站点的其余部分。  
  
 在预生产环境中测试客户端包含三个基本步骤  
  
1.  [若要配置自动客户端升级以使用预生产集合](#BKMK_config) 以使用预生产集合。  
  
2.  [若要安装包括新版本客户端的 Configuration Manager 更新](#BKMK_install) 包括客户端新版本。 在安装过程中，请指定要用于新客户端软件的预生产集合。  
  
3.  [若要将新客户端提升至生产](#BKMK_promote) 在预生产环境中充分测试后）。  
  
> [!TIP]  
>  [!INCLUDE[cm-client-upgrade-tip](../LocTest/includes/cm-client-upgrade-tip_md.md)]  
  
##  <a name="BKMK_config"></a> 若要配置自动客户端升级以使用预生产集合  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，打开“管理”>“站点配置”>“站点”，然后单击“层次结构设置”。  
  
     在“层次结构设置属性”  的“客户端升级” 选项卡上：  
  
    -   选择“使用预生产客户端自动升级预生产集合中的全部客户端”   
  
    -   输入要用作预生产集合的集合的名称  
  
2.  单击“确定”  以保存客户端升级设置。  
  
##  <a name="BKMK_install"></a> 若要安装包括新版本客户端的 Configuration Manager 更新  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，打开“管理”>“云服务”>“更新和服务”，选择“可用”更新，然后单击“安装更新包”  
  
     有关安装更新的详细信息，请参阅 [System Center Configuration Manager 的更新](../LocTest/Updates-for-System-Center-Configuration-Manager.md)  
  
2.  在安装更新的过程中，在向导的“客户端选项”  页面中，选择“在预生产集合中测试” ，并单击“下一步” 。  
  
3.  完成向导中的其余步骤，安装更新包。  
  
     完成向导后，预生产集合中的客户端将开始部署更新的客户端。 你可以通过转到“监视” > “客户端状态” > “预生产客户端部署”监视已升级客户端的部署。 有关详细信息，请参阅[如何在 System Center Configuration Manager 中监视客户端部署状态](../LocTest/How-to-monitor-client-deployment-status-in-System-Center-Configuration-Manager.md)。
     
    > [!NOTE]
    > 即使在已成功部署客户端时，托管预生产集合中站点系统角色的计算机上的部署状态也可能被报告为“未启动”。 当你将客户端提升为生产时，则会正常报告部署状态。
  
##  <a name="BKMK_promote"></a> 若要将新客户端提升至生产  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，打开“管理”>“云服务”>“更新和服务”，然后单击“提升预生产客户端”。

    > [!TIP]
    > 在控制台中通过“监视” > 客户端状态” > “预生产客户端部署”监视客户端部署时，还可使用“提升预生产客户端”按钮。
  
2.  在对话框中，查看生产和预生产中的客户端版本，确保已指定正确的预生产集合，然后单击“提升”。 在确认框中，单击“是”。  
  
3.  对话框关闭后，更新的客户端版本将替代当前在你的层次结构中使用的客户端版本。 然后可以为整个站点升级客户端。 有关详细信息，请参阅[如何在 System Center Configuration Manager 中升级 Windows 计算机的客户端](../LocTest/How-to-upgrade-clients-for-Windows-computers-in-System-Center-Configuration-Manager.md)。  
  
## 另请参阅  
 [在 System Center Configuration Manager 中升级客户端](../LocTest/Upgrade-clients-in-System-Center-Configuration-Manager.md)
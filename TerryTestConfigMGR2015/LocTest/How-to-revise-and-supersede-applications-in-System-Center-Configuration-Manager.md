---
title: "如何在 System Center Configuration Manager 中修订和取代应用程序"
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
ms.assetid: 30170d70-489f-47f7-bebf-9ed0115db26b
caps.latest.revision: 7
caps.handback.revision: 4
author: barlanmsft
translationtype: Human Translation
---
# 如何在 System Center Configuration Manager 中修订和取代应用程序
在本主题中，你将学习如何处理 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 应用程序版本以及如何使用新版本取代应用程序。  
  
## 应用程序修订  
 修订应用程序或应用程序中包含的部署类型时，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 会创建应用程序的新版本。 你可以显示每个应用程序修订版本的历史记录。 也可以查看其属性、还原应用程序的以前版本或删除旧版本。  
  
#### 显示应用程序修订版本历史记录  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“软件库”。  
  
2.  在“软件库”工作区中，展开“应用程序管理”，单击“应用程序”，然后单击所需的应用程序。  
  
3.  在“主页”选项卡上的“应用程序”组中，单击“修订版本历史记录”以打开“应用程序修订版本历史记录”对话框。  
  
#### 查看应用程序修订版本  
  
1.  在“应用程序修订版本历史记录”对话框中，选择应用程序修订版本，然后单击“查看”。  
  
2.  在“属性”对话框中，检查所选应用程序的属性。  
  
    > [!NOTE]  
    >  所显示的应用程序属性为只读。  
  
3.  关闭“属性”对话框。  
  
#### 还原应用程序修订版本  
  
1.  在“应用程序修订版本历史记录”对话框中，选择应用程序修订版本，然后单击“还原”。  
  
2.  在“确认修订版本还原”对话框中，单击“是”以还原所选应用程序修订版本。  
  
#### 删除应用程序修订版本  
  
1.  在“应用程序修订版本历史记录”对话框中，选择应用程序修订版本，然后单击“删除”。  
  
2.  在“删除应用程序修订版本”对话框中，单击“是”。  
  
> [!IMPORTANT]  
>  只有当应用程序已停止使用并且不包含参考时才能删除当前应用程序修订版本。  
  
## 应用程序取代  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的应用程序管理允许你通过使用取代关系升级或替换现有应用程序。 在取代应用程序时，你可以指定新部署类型来替换被取代应用程序的部署类型，还可配置是否在安装取代应用程序之前升级或卸载被取代应用程序。  
  
> [!IMPORTANT]  
>  如果选择了卸载被取代部署类型的选项，则部署类型无法由部署到其他集合类型的部署类型取代。  例如，如果选择了卸载被取代部署类型的选项，则部署到设备集合的部署类型无法由部署到用户集合的部署类型取代。  
  
### 决定是升级还是替换应用程序  
 在应用程序属性对话框的“指定取代关系”对话框中指定是替换还是升级应用。 取代类型取决于是否在此对话框中选中“卸载”选项：  
  
-   如果希望更新到同一应用程序（具有相同应用程序 ID）的较新版本，请“勿”勾选“卸载”。  
  
-   如果希望更改为其他应用程序（具有不同应用程序 ID），请选中“卸载”。 将需要删除应用程序的被取代版本。  
  
### 取代从属应用程序  
 在此示例中，“主应用程序”是指要部署的包含依赖项的应用。  
  
 可以创建一个取代关系，用于将从属应用程序更新到新版本。  
  
1.  确保新的从属应用程序和原始从属应用程序位于主应用程序的同一依赖关系组中。  
  
2.  创建一个取代关系，用于将原始从属应用程序取代为新的从属应用程序。  
  
 在主应用程序的新安装期间，将安装新的从属应用程序。 主应用程序的现有安装将与新的从属应用程序一起更新。  
  
 最终结果是主应用程序的所有部署都将使用新的从属应用程序。  
  
#### 更多注意事项  
  
-   可为从属应用程序指定多个取代关系。 将安装取代链中依赖性最高的从属应用程序。  
  
-   必须将从属应用程序部署到安装了主应用程序的设备，否则将不会安装该从属应用程序。  
  
-   对于主应用程序的新安装，当具有多个依赖项时，依赖关系顺序决定要安装的从属应用程序版本。  
  
### 如何指定取代关系  
  
##### 指定取代关系  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“软件库”。  
  
2.  在“软件库”工作区中，展开“应用程序管理”，单击“应用程序”，然后单击将取代另一个应用程序的应用程序。  
  
3.  在“主页”选项卡的“属性”组中，单击“属性”打开*“\<Application Name\>* 属性”对话框。  
  
4.  在*“\<Application Name\>* 属性”对话框的“取代”选项卡上，单击“添加”。  
  
5.  在“指定取代关系”对话框中，单击“浏览”。  
  
6.  在“选择应用程序”对话框中，选择要取代的应用程序，然后单击“确定”。  
  
7.  在“指定取代关系”对话框中，选择将替代被取代应用程序的部署类型的部署类型。  
  
    > [!NOTE]  
    >  默认情况下，新部署类型将不会卸载被取代应用程序的部署类型。 当你希望将升级部署到现有应用程序时，将使用此方案。 选择“卸载”以在安装新部署类型之前删除现有部署类型。 如果你决定升级应用程序，请确保先在实验室环境中测试这一点。  
  
8.  单击“确定”关闭“指定取代关系”对话框。  
  
9. 单击“确定”以关闭 *\<应用程序名称\>*“属性”对话框。  
  
##### 显示取代当前应用程序的应用程序  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“软件库”。  
  
2.  在“软件库”工作区中，展开“应用程序管理”，单击“应用程序”，然后单击所需的应用程序。  
  
3.  在“主页”选项卡的“属性”组中，单击“属性”打开*“\<Application Name\>* 属性”对话框。  
  
4.  在*“\<Application Name\>* 属性”对话框的“引用”选项卡上，从“关系类型”下拉列表中选择“可取代此应用程序的应用程序”。  
  
5.  查看可取代所选应用程序的应用程序列表，然后单击“确定”以关 *“\<Application Name\>* 属性”对话框。  
  
## 请参阅  
 [System Center Configuration Manager 中应用程序管理的技术参考](../LocTest/Application-management-technical-reference-for-System-Center-Configuration-Manager.md)
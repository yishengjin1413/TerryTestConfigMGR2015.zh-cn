---
title: "使用 System Center Configuration Manager 中的用户数据和配置文件的配置项目"
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
ms.assetid: a9439076-6a27-4361-a544-49bbfe7abc8a
caps.latest.revision: 6
caps.handback.revision: 5
translationtype: Human Translation
---
# 使用 System Center Configuration Manager 中的用户数据和配置文件的配置项目
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的用户数据和配置文件配置项目包含的设置可为层次结构中的用户管理运行 Windows 8 的计算机上的文件夹重定向、脱机文件和漫游配置文件。 例如，你能够：  
  
-   将用户的 Documents 文件夹重定向到网络共享。  
  
-   确保存储在网络上的指定文件在网络连接不可用时可用于用户的计算机。  
  
-   配置用户漫游配置文件中哪些文件在用户日志打开和关闭时与网络共享同步。  
  
 与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的其他配置项目不同，无需向随后将部署的配置基线添加用户数据和配置文件的配置项目。 而只需使用“部署用户数据和配置文件的配置项目”对话框直接部署配置项目。  
  
> [!IMPORTANT]  
>  仅可向用户集合部署用户数据和配置文件的配置项目。  
  
## 为符合性设置启用用户数据和配置文件  
 使用以下过程来配置用于用户数据和配置文件符合性设置的默认客户端设置，这些设置将应用于层次结构中的所有计算机。 如果希望这些设置仅应用于某些计算机，请创建一个自定义设备客户端设置，并将其分配给包含要使用用户数据和配置文件符合性设置的计算机的集合。 有关如何创建自定义设备设置的详细信息，请参阅 [如何在 System Center Configuration Manager 中配置客户端设置](../LocTest/How-to-configure-client-settings-in-System-Center-Configuration-Manager.md)。  
  
#### 如何为符合性设置启用用户数据和配置文件  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“管理”。  
  
2.  在“管理”工作区中，单击“客户端设置”。  
  
3.  单击“默认设置”。  
  
4.  在“主页”选项卡上的“属性”组中，单击“属性”。  
  
5.  在“默认设置”对话框中，单击“符合性设置”。  
  
6.  从“启用用户数据和配置文件”下拉菜单中，选择“是”。  
  
7.  单击“确定”来关闭“默认设置”对话框。  
  
## 后续步骤  
 接下来，你可能想要开始创建并部署用户数据和配置文件配置项目。  
  
 有关可以使用的所有设置的帮助，请参阅 [如何在 System Center Configuration Manager 中创建用户数据和配置文件的配置项目](../LocTest/How-to-create-user-data-and-profiles-configuration-items-in-System-Center-Configuration-Manager.md)。  
  
## 请参阅  
 [使用 System Center Configuration Manager 确保设备的合规性](../LocTest/Ensure-device-compliance-with-System-Center-Configuration-Manager.md)
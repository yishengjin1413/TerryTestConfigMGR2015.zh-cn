---
title: "如何在 System Center Configuration Manager 中创建配置基线"
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
ms.assetid: 678c9622-c61b-47d1-ba25-690616e431c7
caps.latest.revision: 5
caps.handback.revision: 3
---
# 如何在 System Center Configuration Manager 中创建配置基线
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的配置基线包含预定义的配置项目，还可包含其他配置基线。 在创建配置基线之后，可以将其部署到集合以便该集合中的设备下载配置基线并评估其符合性。  
  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的配置基线可以包含配置项目的特定修订版本，或者配置为始终使用最新版的配置项目。 有关配置项目修订版本的详细信息，请参阅 [针对 System Center Configuration Manager 中配置数据的管理任务](../LocTest/Management-tasks-for-configuration-data-in-System-Center-Configuration-Manager.md)。  
  
 可以使用两种方法来创建 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的配置基线：  
  
-   从文件中导入配置数据。 要启动“导入配置数据向导”，请在“资产和符合性”工作区中的“配置项目”或“配置基线”节点中，单击“导入配置数据”。  
  
-   使用“创建配置基线”对话框来创建一个新的配置基线。  
  
 通过“创建配置基线”对话框，使用以下过程来创建配置基线。  
  
### 若要创建配置基线  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”。  
  
2.  在“资产和符合性”工作区中，展开“符合性设置”，然后单击“配置基线”。  
  
3.  在“主页”选项卡上的“创建”组中，单击“创建配置基线”。  
  
4.  在“创建配置基线”对话框中，输入配置基线的唯一名称和描述。 描述最多可使用 255 个字符，描述最多可使用 512 个字符。  
  
5.  “配置数据”列表将显示此配置基线中包含的所有配置项目或配置基线。 单击“添加”可向列表中添加新配置项目或配置基线。 您可以选择下列项目:  
  
    -   **配置项目**  
  
    -   **软件更新**  
  
    -   **配置基线**  
  
6.  使用“更改目的”列表来指定在“配置数据”列表中选择的配置项目的行为。 从以下选项中选择：  
  
    -   “需要”如果客户端设备上未检测到配置项目，将配置基线评估为不符合要求。 如果检测到，则评估符合性  
  
    -   “可选”只有客户端计算机上找到它所引用的应用程序，才会评估配置项目的符合性。 如果找不到该应用程序，则不会将配置基线标记为不符合要求（仅适用于应用程序配置项目）。  
  
    -   “禁止”如果客户端计算机上检测到配置项目（仅适用于应用程序配置项目），则将配置基线评估为不符合要求。  
  
    > [!NOTE]  
    >  “更改目的”列表只有在勾选“创建配置项目向导”中“常规”页面中的“此配置项目包含应用程序设置”选项时才可用。  
  
7.  使用“更改修订版本”列表可选择特定版本或最新版本的配置项目来评估客户端设备上的符合性，或选择“始终使用最新”以始终使用最新版本。 有关配置项目修订版本的详细信息，请参阅 [针对 System Center Configuration Manager 中配置数据的管理任务](../LocTest/Management-tasks-for-configuration-data-in-System-Center-Configuration-Manager.md)。  
  
8.  如果要从配置基线中删除配置项目，请选择配置项目，然后单击“删除”。  
  
9. 单击“确定”可关闭“创建配置基线”对话框，并创建配置基线。  
  
## 请参阅  
 [System Center Configuration Manager 的符合性设置技术参考](../LocTest/Compliance-settings-technical-reference-for-System-Center-Configuration-Manager.md)
---
title: "如何使用资源浏览器来查看 System Center Configuration Manager 中的软件清单"
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
ms.assetid: 4b7aa5f6-5ebd-49be-b7f3-4206caadc187
caps.latest.revision: 5
caps.handback.revision: 4
author: barlanmsft
translationtype: Human Translation
---
# 如何使用资源浏览器来查看 System Center Configuration Manager 中的软件清单
使用 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的资源浏览器来查看从层次结构中的计算机收集的软件清单的相关详细。  
  
> [!NOTE]  
>  在要连接的客户端上运行软件清单周期后，资源浏览器才会显示清单数据。  
  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的资源浏览器包含与软件清单相关的以下部分：  
  
-   **软件** – 资源浏览器的软件部分包含四部分：  
  
    -   **收集的文件** – 显示在软件清单期间所收集的文件的相关信息。  
  
    -   **文件详细信息** – 显示在软件清单期间清点的与特定产品或制造商无关联的文件的相关信息。  
  
    -   **上次软件扫描** – 显示在客户端计算机上运行的最后一个软件清单和文件集合的日期和时间。  
  
    -   **产品详细信息** – 按制造商分组显示由软件清单清点的软件产品的相关信息。  
  
## 若要从 Configuration Manager 控制台运行资源浏览器  
 在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中使用以下过程运行资源浏览器。  
  
#### 若要从 Configuration Manager 控制台运行资源浏览器  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”。  
  
2.  在“资产和符合性”工作区中，单击“设备”或打开显示设备的任何集合。  
  
3.  单击包含想要查看的清单的计算机，然后在“主页”选项卡上的“设备”组中，单击“启动”，然后单击“资源浏览器”。 随即打开资源浏览器窗口。  
  
4.  可以右键单击资源浏览器窗口右窗格中的任意项，然后单击“属性”以打开 *\<item name\>*“属性”对话框，从而有助于以更加易读的格式查看收集的清单信息。  
  
5.  当完成后，请关闭“资源浏览器”窗口。  
  
## 请参阅  
 [System Center Configuration Manager 中软件清单的操作和维护](../LocTest/Operations-and-maintenance-for-software-inventory-in-System-Center-Configuration-Manager.md)
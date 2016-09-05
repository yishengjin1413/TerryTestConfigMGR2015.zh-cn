---
title: "如何使用资源浏览器来查看 System Center Configuration Manager 中的硬件清单"
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
ms.assetid: 375912f5-436d-4315-bdbe-d77afee6c9f3
caps.latest.revision: 7
caps.handback.revision: 7
author: barlanmsft
---
# 如何使用资源浏览器来查看 System Center Configuration Manager 中的硬件清单
使用 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的资源浏览器来查看从层次结构中的客户端收集的硬件清单相关信息。  
  
> [!NOTE]  
>  资源浏览器不会显示数据的硬件清单周期已在运行之前客户端上您要连接到任何库存量。  
  
 在资源浏览器 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 包含与硬件清单相关的以下部分：  
  
-   **硬件** -包含最新的硬件清单收集从指定 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端设备。 您可以查看库存物料 **工作站状态** 来发现设备上次执行硬件清单的日期和时间。  
  
-   **硬件历史记录** – 包含已列出清单的项执行的最后一个硬件清单以来已更改的历史记录。 列表中的每项都包含一个“当前”节点以及一个或多个 *<date\>* 节点。 您可以比较当前节点为要发现客户端计算机的硬件清单中已更改的项的历史节点之一中的信息。  
  
    > [!NOTE]  
    >  [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 会按“删除过期的清单历史记录”  站点维护任务中指定的天数保留硬件清单历史记录  
  
> [!NOTE]  
>  若要了解如何在运行 Linux 和 UNIX 的客户端查看硬件清单，请参阅 [How to monitor clients for Linux and UNIX servers in System Center Configuration Manager](../LocTest/How-to-monitor-clients-for-Linux-and-UNIX-servers-in-System-Center-Configuration-Manager.md)。  
  
### 如何从 Configuration Manager 控制台运行资源浏览器  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击 **资产和符合性**。  
  
2.  在“资产和符合性”  工作区中，单击“设备”  或打开显示设备的任何集合。  
  
3.  单击包含您想要查看的清单的计算机，然后在 **主页** 选项卡上，在 **设备** 组中，单击 **启动** 然后单击 **资源浏览器**。 **资源浏览器** 窗口将打开。  
  
4.  可以右键单击“资源浏览器”窗口右窗格中的任意项，然后单击“属性”以打开 <item name\>“属性”对话框，从而有助于以更加易读的格式查看收集的清单信息。  
  
5.  在完成后，请关闭 **资源浏览器** 窗口。  
  
## 另请参阅  
 [System Center Configuration Manager 中硬件清单的操作和维护](../LocTest/Operations-and-maintenance-for-hardware-inventory-in-System-Center-Configuration-Manager.md)
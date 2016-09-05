---
title: "在 System Center Configuration Manager 中升级客户端"
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
ms.assetid: 446c83b5-c292-4e74-ba19-0792ac6b3472
caps.latest.revision: 8
caps.handback.revision: 8
---
# 在 System Center Configuration Manager 中升级客户端
可以使用不同的方法在企业的 Windows 计算机、UNIX 和 Linux 服务器以及 Mac 计算机上升级 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 客户端软件。 以下部分概述了每种客户端升级方法的优点和缺点，以帮助你确定哪种方法最适合你的组织。  
  
> [!TIP]  
>  [!INCLUDE[cm-client-upgrade-tip](../LocTest/includes/cm-client-upgrade-tip_md.md)]  
  
## 组策略安装  
 **支持的客户端平台：**Windows  
  
 **优点**  
  
-   在可以升级客户端之前，无需发现计算机。  
  
-   可用于安装新客户端或执行升级。  
  
-   计算机可以读取已发布到 Active Directory 域服务的客户端安装属性。  
  
-   你无需为目标客户端计算机配置和维护安装帐户。  
  
 **缺点**  
  
-   如果升级大量客户端，可能会导致网络流量很高。  
  
-   如果没有为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]扩展 Active Directory 架构，则必须使用组策略设置将客户端安装属性添加到站点中的计算机。  
  
 有关详细信息，请参阅[如何使用组策略安装 Configuration Manager 客户端](../LocTest/How-to-deploy-clients-to-Windows-computers-in-System-Center-Configuration-Manager.md#BKMK_ClientGP)。  
  
## 登录脚本安装  
 **支持的客户端平台：**Windows  
  
 **优点**  
  
-   在可以安装客户端之前，无需发现计算机。  
  
-   可用于安装新客户端或执行升级。  
  
-   支持使用 CCMSetup 的命令行属性。  
  
 **缺点**  
  
-   如果在短时间内升级大量客户端，可能会导致网络流量很高。  
  
-   如果用户并非经常登录到网络，则可能需要很长时间才能升级到所有客户端计算机。  
  
 有关详细信息，请参阅[如何使用登录脚本安装 Configuration Manager 客户端](../LocTest/How-to-deploy-clients-to-Windows-computers-in-System-Center-Configuration-Manager.md#BKMK_ClientLogonScript)。  
  
## 手动安装  
 **支持的客户端平台：**Windows、UNIX/Linus、Mac OS X  
  
 **优点**  
  
-   在可以升级客户端之前，无需发现计算机。  
  
-   可用于测试目的。  
  
-   支持使用 CCMSetup 的命令行属性。  
  
 **缺点**  
  
-   无自动化，因此耗费时间。  
  
 有关详细信息，请参阅下列主题：  
  
-   [如何手动安装 Configuration Manager 客户端](../LocTest/How-to-deploy-clients-to-Windows-computers-in-System-Center-Configuration-Manager.md#BKMK_Manual)  
  
-   [如何在 System Center Configuration Manager 中升级 Linux 和 UNIX 服务器的客户端](../LocTest/How-to-upgrade-clients-for-Linux-and-UNIX-servers-in-System-Center-Configuration-Manager.md)  
  
-   [如何在 System Center Configuration Manager 中升级 Mac 计算机的客户端](../LocTest/How-to-upgrade-clients-on-Mac-computers-in-System-Center-Configuration-Manager.md)  
  
## 升级安装（应用程序管理）  
 **支持的客户端平台：**Windows  
  
> [!NOTE]  
>  使用此方法无法升级 [!INCLUDE[cm4short](../LocTest/includes/cm4short_md.md)] 客户端。 在此情况下，你可以从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点中以包的形式部署 [!INCLUDE[cm4short](../LocTest/includes/cm4short_md.md)] 客户端，或者可以使用自动客户端升级，这种方法可自动创建和部署包含客户端最新版本的包。  
  
 **优点**  
  
-   支持使用 CCMSetup 的命令行属性。  
  
 **缺点**  
  
-   将客户端分发到大型集合时，可能会导致网络流量很高。  
  
-   只能用于在已发现并分配到站点的计算机上升级客户端软件。  
  
 有关详细信息，请参阅[如何通过使用包和程序来安装 Configuration Manager 客户端](../LocTest/How-to-deploy-clients-to-Windows-computers-in-System-Center-Configuration-Manager.md#BKMK_ClientApp)。  
  
## 自动客户端升级  
  
> [!NOTE]  
>  可用于将 [!INCLUDE[cm4short](../LocTest/includes/cm4short_md.md)] 客户端升级到 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 客户端。 [!INCLUDE[cm4short](../LocTest/includes/cm4short_md.md)]客户端可分配给 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点，但无法执行除自动客户端升级外的任何操作。  
  
 **支持的客户端平台：**Windows  
  
 **优点**  
  
-   可用于自动让站点中的客户端的版本保持最新。  
  
-   需要管理用户进行的管理最少。  
  
 **缺点**  
  
-   只能用于升级客户端软件，不能用于安装新客户端。  
  
-   不适用于同时升级多个客户端。  
  
-   适用于层次结构中分配到站点的所有客户端。 无法按集合来限定范围。  
  
-   有限的计划选项。  
  
 有关详细信息，请参阅[如何在 System Center Configuration Manager 中升级 Windows 计算机的客户端](../LocTest/How-to-upgrade-clients-for-Windows-computers-in-System-Center-Configuration-Manager.md)。  
  
## 客户端测试  
 **支持的客户端平台：**Windows  
  
 **优点**  
  
-   可用于在较小的预生产集合中测试新的客户端版本。  
  
-   测试完成后，预生产中的客户端将被提升到生产，并将在整个 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点中自动进行升级。  
  
 **缺点**  
  
-   只能用于升级客户端软件，不能用于安装新客户端。  
  
 [如何在 System Center Configuration Manager 中的预生产集合中测试客户端升级](../LocTest/How-to-test-client-upgrades-in-a-preproduction-collection-in-System-Center-Configuration-Manager.md)  
  
## 另请参阅  
 [使用 System Center Configuration Manager 管理计算机客户端](../LocTest/Manage-computer-clients-with-System-Center-Configuration-Manager.md)
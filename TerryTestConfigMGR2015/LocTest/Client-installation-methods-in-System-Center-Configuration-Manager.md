---
title: "System Center Configuration Manager 中的客户端安装方法"
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
ms.assetid: 51b5964b-374d-4abc-8619-414a9fffad2d
caps.latest.revision: 9
caps.handback.revision: 9
---
# System Center Configuration Manager 中的客户端安装方法
可以使用不同的方法在企业的 Windows 设备、UNIX/Linux 服务器以及 Mac 计算机上安装 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 客户端软件。 可以按照自己的要求使用这些方法中的一种或其任意组合。  
  
 以下部分概述了每种客户端安装方法的优点和缺点，以帮助你确定哪种方法最适合贵组织。  
  
## 客户端请求安装  
 **支持的客户端平台：**Windows  
  
 **优点**  
  
-   可用于将客户端安装在一台计算机、一组计算机或查询到的计算机上。  
  
-   可用于自动将客户端安装在发现的所有计算机上。  
  
-   自动使用在“客户端请求安装属性”  对话框中的“客户端”  选项卡上定义的客户端安装属性。  
  
 **缺点**  
  
-   在推送到大型集合时，可能会导致网络流量很高。  
  
-   只能在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]已发现的计算机上使用。  
  
-   无法用于在工作组中安装客户端。  
  
-   必须指定在目标客户端计算机中具有管理权限的客户端请求安装帐户。  
  
-   必须在客户端计算机上配置 Windows 防火墙例外，以便能够完成客户端请求安装。  
  
-   无法取消客户端请求安装。 在将此客户端安装方法用于站点时， [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 会尝试将客户端安装在发现的所有资源上，并会重试任何失败的安装（不超过 7 天）。  
  
 有关安装方法的详细信息，请参阅[如何在 System Center Configuration Manager 中将客户端部署到 Windows 计算机](../LocTest/How-to-deploy-clients-to-Windows-computers-in-System-Center-Configuration-Manager.md)。  
  
## 基于软件更新点的安装  
 **支持的客户端平台：**Windows  
  
 **优点：**  
  
-   可以使用现有的软件更新基础架构来管理客户端软件。  
  
-   如果正确配置 Windows Server Update Services (WSUS) 和 Active Directory 域服务中的组策略设置，则可以自动在新计算机上安装客户端软件。  
  
-   在可以安装客户端之前，无需发现计算机。  
  
-   计算机可以读取已发布到 Active Directory 域服务的客户端安装属性。  
  
-   如果删除了客户端软件，将会重新安装它。  
  
-   你无需为目标客户端计算机配置和维护安装帐户。  
  
 **缺点：**  
  
-   需要正常运行的软件更新基础结构作为必备组件。  
  
-   必须将相同的服务器用于客户端安装和软件更新，而且此服务器必须位于主站点中。  
  
-   若要安装新的客户端，必须利用客户端的活动软件更新点和端口来配置 Active Directory 域服务中的组策略对象 (GPO)。  
  
-   如果没有为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]扩展 Active Directory 架构，则必须使用组策略设置来设置计算机的客户端安装属性。  
  
 有关安装方法的详细信息，请参阅[如何在 System Center Configuration Manager 中将客户端部署到 Windows 计算机](../LocTest/How-to-deploy-clients-to-Windows-computers-in-System-Center-Configuration-Manager.md)。  
  
## 组策略安装  
 **支持的客户端平台：**Windows  
  
 **优点：**  
  
-   在可以安装客户端之前，无需发现计算机。  
  
-   可用于安装新客户端或执行升级。  
  
-   计算机可以读取已发布到 Active Directory 域服务的客户端安装属性。  
  
-   你无需为目标客户端计算机配置和维护安装帐户。  
  
 **缺点：**  
  
-   如果安装大量客户端，可能会导致网络流量很高。  
  
-   如果没有为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]扩展 Active Directory 架构，则必须使用组策略设置将客户端安装属性添加到站点中的计算机。  
  
 有关安装方法的详细信息，请参阅[如何在 System Center Configuration Manager 中将客户端部署到 Windows 计算机](../LocTest/How-to-deploy-clients-to-Windows-computers-in-System-Center-Configuration-Manager.md)。  
  
## 登录脚本安装  
 **支持的客户端平台：**Windows  
  
 **优点：**  
  
-   在可以安装客户端之前，无需发现计算机。  
  
-   支持使用 CCMSetup 的命令行属性。  
  
 **缺点：**  
  
-   如果在短时间内安装大量客户端，可能会导致网络流量很高。  
  
-   如果用户并非经常登录到网络，则可能需要很长时间才能安装到所有客户端计算机。  
  
 有关安装方法的详细信息，请参阅[如何在 System Center Configuration Manager 中将客户端部署到 Windows 计算机](../LocTest/How-to-deploy-clients-to-Windows-computers-in-System-Center-Configuration-Manager.md)。  
  
## 手动安装  
 **支持的客户端平台：**Windows、UNIX/Linux、Mac OS X  
  
 **优点：**  
  
-   在可以安装客户端之前，无需发现计算机。  
  
-   可用于测试目的。  
  
-   支持使用 CCMSetup 的命令行属性。  
  
 **缺点：**  
  
-   无自动化，因此耗费时间。  
  
 有关如何在每个平台上手动安装客户端的详细信息，请参阅以下内容：  
  
-   [如何在 System Center Configuration Manager 中部署客户端到 Windows 计算机](../LocTest/How-to-deploy-clients-to-Windows-computers-in-System-Center-Configuration-Manager.md)  
  
-   [在 System Center Configuration Manager 中如何将客户端部署到 UNIX 和 Linux 服务器](../LocTest/How-to-deploy-clients-to-UNIX-and-Linux-servers-in-System-Center-Configuration-Manager.md)  
  
-   [How to deploy clients to Macs in System Center Configuration Manager](../LocTest/How-to-deploy-clients-to-Macs-in-System-Center-Configuration-Manager.md)  
  
## 另请参阅  
 [在 System Center Configuration Manager 中部署客户端的规划注意事项](../LocTest/Planning-considerations-for-deploying-clients-in-System-Center-Configuration-Manager.md)
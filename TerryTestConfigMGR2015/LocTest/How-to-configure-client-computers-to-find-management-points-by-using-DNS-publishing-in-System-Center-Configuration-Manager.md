---
title: "如何在 System Center Configuration Manager 中配置客户端计算机以使用 DNS 发布查找管理点"
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
ms.assetid: 03cec407-0f9f-454f-a360-b005af738d29
caps.latest.revision: 6
caps.handback.revision: 5
translationtype: Human Translation
---
# 如何在 System Center Configuration Manager 中配置客户端计算机以使用 DNS 发布查找管理点
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的客户端必须找到管理点才能完成站点分配，并作为持续的进程一直受到管理。 Active Directory 域服务为 Intranet 上的客户端提供了找到管理点的最安全的方法。 但是，如果客户端无法使用此服务位置方法（例如，你未扩展 Active Directory 架构，或者客户端来自工作组），则使用 DNS 发布作为首选的备用服务位置方法。  
  
> [!NOTE]  
>  在安装 Linux 和 UNIX 的客户端时，必须指定用作初始联系点的管理点。 有关如何安装 Linux 和 UNIX 的客户端的信息，请参阅 [在 System Center Configuration Manager 中如何将客户端部署到 UNIX 和 Linux 服务器](../LocTest/How-to-deploy-clients-to-UNIX-and-Linux-servers-in-System-Center-Configuration-Manager.md)。  
  
 在为管理点使用 DNS 发布之前，请确保 Intranet 上的 DNS 服务器具有服务位置资源记录 \(SRV RR\)，以及站点的管理点的相应主机（A 或 AAA）资源记录。 服务位置资源记录可以由 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 自动创建，也可以由在 DNS 中创建记录的 DNS 管理员手动创建。  
  
 有关 DNS 发布作为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端的服务定位方法的详细信息，请参阅[了解客户端如何查找 System Center Configuration Manager 的站点资源和服务](../LocTest/Understand-how-clients-find-site-resources-and-services-for-System-Center-Configuration-Manager.md)。  
  
 默认情况下，客户端将搜索 DNS 以在其 DNS 域中查找管理点。 但是，如果客户端的域中没有发布的管理点，则必须将客户端手动配置为具有管理点 DNS 后缀。 你可以在客户端安装过程中或之后在客户端上配置此 DNS 后缀：  
  
-   若要在客户端安装过程中针对管理点后缀配置客户端，请配置 CCMSetup Client.msi 属性。  
  
-   若要在客户端安装之后针对管理点后缀配置客户端，请在“控制面板”中配置“Configuration Manager 属性”。  
  
#### 在客户端安装过程中针对管理点后缀配置客户端  
  
-   利用下列 CCMSetup Client.msi 属性安装客户端：  
  
    -   **DNSSUFFIX\=** *\<management point domain\>*  
  
         如果站点具有多个管理点，而且这些管理点位于多个域中，则仅指定一个域。 在客户端连接到此域中的管理点时，它们下载可用管理点的列表（将包含其他域中的管理点）。  
  
     有关 CCMSetup 命令行属性的详细信息，请参阅[关于 System Center Configuration Manager 中的客户端安装属性](../LocTest/About-client-installation-properties-in-System-Center-Configuration-Manager.md)。  
  
#### 在客户端安装之后针对管理点后缀配置客户端  
  
1.  在客户端计算机的“控制面板”中，导航到“Configuration Manager”，然后双击“属性”。  
  
2.  在“站点”选项卡上，指定管理点的 DNS 后缀，然后单击“确定”。  
  
     如果站点具有多个管理点，而且这些管理点位于多个域中，则仅指定一个域。 在客户端连接到此域中的管理点时，它们下载可用管理点的列表（将包含其他域中的管理点）。  
  
## 请参阅  
 [在 System Center Configuration Manager 中部署客户端的准备步骤](../LocTest/Preparation-steps-for-deploying-clients-in-System-Center-Configuration-Manager.md)
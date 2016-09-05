---
title: "关于 System Center Configuration Manager 中的发布到 Active Directory 域服务的客户端安装属性"
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
ms.assetid: 101d7d4d-92db-419d-b2ae-3c1c1dea68e9
caps.latest.revision: 6
caps.handback.revision: 3
translationtype: Human Translation
---
# 关于 System Center Configuration Manager 中的发布到 Active Directory 域服务的客户端安装属性
在扩展 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 的 Active Directory 架构并将站点发布到 Active Directory 域服务时，会将许多客户端安装属性发布到 Active Directory 域服务。 如果计算机可以找到这些客户端安装属性，则它可以在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端的部署过程中使用这些属性。  
  
 使用 Active Directory 域服务发布客户端安装属性的优点包括：  
  
-   基于软件更新点的客户端安装和组策略客户端安装不需要在每台计算机上设置安装参数。  
  
-   由于此信息自动生成，消除了与手动输入安装属性关联的人为错误风险。  
  
> [!NOTE]  
>  有关如何为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 扩展 Active Directory 架构以及如何发布站点的详细信息，请参阅[为 System Center Configuration Manager 准备网络环境](../LocTest/Prepare-your-network-environment-for-System-Center-Configuration-Manager.md)。  
  
 只有在未使用下列任何方法来指定任何其他属性时，客户端安装 \(CCMSetup\) 才会使用发布到 Active Directory 域服务的客户端安装属性：  
  
-   手动安装  
  
-   使用组策略设置客户端安装属性  
  
> [!NOTE]  
>  客户端安装属性用于安装客户端，不过，在安装客户端并成功将其分配到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点之后，为其分配的站点中的新设置可能会覆盖这些属性。  
  
 使用下表来确定哪些 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端安装方法使用 Active Directory 域服务获取客户端安装属性。  
  
|安装方法|注释|  
|----------|--------|  
|客户端请求安装|客户端请求安装不使用 Active Directory 域服务来获取安装属性。<br /><br /> 实际上，你可以在“客户端请求安装属性”对话框的“客户端”选项卡中指定 client.msi 安装属性。 这些选项和有关客户端的站点设置存储在一个文件中，客户端在客户端安装过程中将读取此文件。 **Note:**  你无需在“客户端”选项卡中为客户端请求安装指定任何 CCMSetup 属性，或者指定回退状态点或受信任的根密钥。 在使用客户端请求安装来安装客户端时，会自动向客户端提供这些设置。 <br /><br /> 如果将站点发布到 Active Directory 域服务，则你在“客户端”选项卡中指定的任何 client.msi 属性都会发布到 Active Directory 域服务。 通过运行不带安装属性的 CCMSetup 来进行的客户端安装将读取这些设置。|  
|基于软件更新点的安装|基于软件更新点的安装方法不支持将安装属性添加到 CCMSetup 命令行中。<br /><br /> 如果没有使用组策略在客户端计算机上设置命令行属性，则 CCMSetup 会在 Active Directory 域服务中搜索安装属性。|  
|组策略安装|组策略安装方法不支持将安装属性添加到 CCMSetup 命令行中。<br /><br /> 如果没有在客户端计算机上设置命令行属性，则 CCMSetup 会在 Active Directory 域服务中搜索安装属性。|  
|手动安装|在下列情况下，CCMSetup 将在 Active Directory 域服务中搜索安装属性：<br /><br /> -   在 CCMSetup.exe 命令后未指定命令行属性。<br />-   未使用组策略设置计算机的安装属性。|  
|登录脚本安装|在下列情况下，CCMSetup 将在 Active Directory 域服务中搜索安装属性：<br /><br /> -   在 CCMSetup.exe 命令后未指定命令行属性。<br />-   未使用组策略设置计算机的安装属性。|  
|软件分发安装|在下列情况下，CCMSetup 将在 Active Directory 域服务中搜索安装属性：<br /><br /> -   在 CCMSetup.exe 命令后未指定命令行属性。<br />-   未使用组策略设置计算机的安装属性。|  
|无法访问 Active Directory 域服务以获取已发布信息的客户端的安装：<br /><br /> -   工作组计算机<br />-   被分配至未发布到 Active Directory 域服务的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点的客户端<br />-   在安装时位于 Internet 上的客户端|这些客户端计算机无法从 Active Directory 域服务读取安装属性，因此将无法访问已发布的安装属性。|  
  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将下列客户端安装属性发布到 Active Directory 域服务。 有关各项的详细信息，请参阅[关于 System Center Configuration Manager 中的客户端安装属性](../LocTest/About-client-installation-properties-in-System-Center-Configuration-Manager.md)。  
  
-   [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点代码。  
  
-   站点服务器签名证书。  
  
-   受信任的根密钥。  
  
-   用于 HTTP 和 HTTPS 的客户端通信端口。  
  
-   回退状态点。 如果站点具有多个回退状态点，则只会将安装的第一个回退状态点发布到 Active Directory 域服务。  
  
-   指示客户端只能使用 HTTPS 进行通信的设置。  
  
-   与 PKI 证书相关的设置：  
  
    -   是否使用客户端 PKI 证书。  
  
    -   证书的选择条件（如果因客户端具有多个可用于 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的有效 PKI 证书而需要选择证书）。  
  
    -   在执行证书选择过程后确定要使用的证书的设置（如果客户端具有多个有效证书）。  
  
    -   证书颁发者列表（包含受信任的根 CA 证书的列表）。  
  
-   在“客户端请求安装属性”对话框的“客户端”选项卡中指定的 Client.msi 安装属性。  
  
## 请参阅  
 [System Center Configuration Manager 中客户端管理的技术参考](../LocTest/Client-management-technical-reference-for-System-Center-Configuration-Manager.md)
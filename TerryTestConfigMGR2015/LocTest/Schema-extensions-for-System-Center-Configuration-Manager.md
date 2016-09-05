---
title: "System Center Configuration Manager 的架构扩展"
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
ms.assetid: 95c13c00-909f-4fbb-bbaa-1eba9d54d8c5
caps.latest.revision: 8
caps.handback.revision: 7
robots: noindex
translationtype: Human Translation
---
# System Center Configuration Manager 的架构扩展
你可以扩展 Active Directory 架构以支持 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]。 这将编辑林 Active Directory 架构，以添加由 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点使用的新容器和某些特性，从而将 Active Directory 关键信息发布到客户可以安全访问的位置。  此信息可以简化客户端部署和配置，并帮助客户端找到站点资源（例如具有部署的内容或向客户端提供多种服务的服务器）。  
  
-   扩展 Active Directory 架构不是必需的，但是建议这样做。  
  
 在 [扩展 Active Directory 架构](https://msdnstage.redmond.corp.microsoft.com/en-US/library/mt345589\(TechNet.10\).aspx)之前，你应该熟悉 Active Directory 域服务并熟悉 [修改 Active Directory 架构](https://technet.microsoft.com/library/cc759402\(v=ws.10\).aspx)。  
  
## 扩展 Configuration Manager 的 Active Directory 架构时的注意事项  
  
-   [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 的 Active Directory 架构扩展与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 2007 和 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 2012 使用的那些扩展相比并无变化。 如果此前扩展了任一架构，则无需再次扩展该架构。  
  
-   扩展架构是全林性、一次性、不可逆的操作。  
  
-   扩展架构仅可由作为架构管理员组成员的用户或已被授予足够的架构修改权限的用户来完成。  
  
-   虽然在运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 安装程序之前或之后都可以扩展架构，但是我们建议你在开始配置站点和层次结构设置之前执行此操作。  这样可以简化许多后续配置步骤。  
  
-   在扩展架构之后，Active Directory 全局目录被复制到整个林中。 因此，需要在复制流量不会对其他网络相关程序带来负面影响时扩展架构：  
  
    -   在 Windows 2000 林中，扩展此架构会导致整个全局目录的完全同步。  
  
    -   从 Windows 2003 林开始，只会复制新添加的属性  
  
 **不使用 Active Directory 架构的设备和客户端：**  
  
-   由 Exchange Server 连接器管理的移动设备  
  
-   Mac 计算机的客户端  
  
-   Linux 和 UNIX 服务器的客户端  
  
-   注册的移动设备 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]  
  
-   注册的移动设备 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)]  
  
-   移动设备旧客户端  
  
-   配置为仅通过 Internet 进行客户端管理的 Windows 客户端  
  
-   [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 检测到位于 Internet 上的 Windows 客户端  
  
## 受益于扩展架构的功能  
 **客户端计算机安装和站点分配** \- 在 Windows 计算机上安装新的客户端时，此客户端可以在 Active Directory 域服务中搜索安装属性。  
  
-   **工作方法：** 如果不扩展此架构，则必须使用下列选项之一来提供计算机在安装时所需的配置详细信息：  
  
    -   <bpt id="p1">**</bpt>使用客户端推送安装**。 在使用客户端安装方法之前，请确保满足所有先决条件。 有关详细信息，请参阅计算机客户端的先决条件中的“安装方法依赖关系”部分。  
  
    -   **手动安装客户端**，并使用 CCMSetup 安装命令行属性来提供客户端安装属性。 这必须包括下列操作：  
  
        -   在客户端安装过程中，在 CCMSetup 命令行上通过使用 CCMSetup property **\/mp:\=\<management point name computer name\>** 或 **\/source:\<path to client source files\>**，指定计算机可以从中下载安装文件的管理点或源路径。  
  
        -   指定供客户端使用的初始管理点的列表，以便它可以分配到站点，然后下载客户端策略和站点设置。 使用 CCMSetup Client.msi 的 SMSMP 属性来执行此操作。  
  
    -   **在 DNS 或 WINS 中发布管理点** ，然后配置客户端以使用此服务位置方法。  
  
 **客户端与服务器通信的端口配置** \- 在安装客户端时，会为其配置存储在 Active Directory 中的端口信息。 如果后来更改了站点的客户端与服务器通信端口，则客户端可以通过 Active Directory 域服务获得此新的端口设置。  
  
-   **工作方法：** 如果不扩展架构，则使用以下其中一个选项向现有客户端提供新的端口配置：  
  
    -   **使用配置新端口的选项重新安装客户端** 。  
  
    -   **将自定义脚本部署到可更新端口信息的客户端**。 如果客户端因端口改变而无法与站点通信，则无法使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 来部署此脚本。 例如，可以使用组策略。  
  
 **内容部署方案** \- 当在一个站点中创建内容，然后将该内容部署到层次结构中的另一个站点时，接收站点必须能够验证已签名的内容数据的签名。 这需要访问你在其中创建此数据的源站点的公钥。 在扩展 Configuration Manager 的 Active Directory 架构时，站点的公钥将提供给层次结构中的所有站点使用。  
  
-   **工作方法：** 如果不扩展 Active Directory 架构，则可以使用层次结构维护工具“preinst.exe” 在站点之间交换安全密钥信息。  
  
     例如，你计划在主站点中创建内容，然后将该内容部署到另一个主站点下面的辅助站点，那么，你必须扩展 Active Directory 架构，以使此辅助站点能够获得源主站点的公钥，或者你必须使用 preinst.exe 直接在这两个站点之间共享密钥。  
  
## Active Directory 特性和类  
 在扩展 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]的架构时，会向架构添加以下类和属性，且它们对 Active Directory 林中的任何 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点都可用。  
  
-   属性：  
  
    -   cn\=mS\-SMS\-Assignment\-Site\-Code  
  
    -   cn\=mS\-SMS\-Capabilities  
  
    -   cn\=MS\-SMS\-Default\-MP  
  
    -   cn\=mS\-SMS\-Device\-Management\-Point  
  
    -   cn\=mS\-SMS\-Health\-State  
  
    -   cn\=MS\-SMS\-MP\-Address  
  
    -   cn\=MS\-SMS\-MP\-Name  
  
    -   cn\=MS\-SMS\-Ranged\-IP\-High  
  
    -   cn\=MS\-SMS\-Ranged\-IP\-Low  
  
    -   cn\=MS\-SMS\-Roaming\-Boundaries  
        启用  
  
    -   cn\=MS\-SMS\-Site\-Boundaries  
  
    -   cn\=MS\-SMS\-Site\-Code  
  
    -   cn\=mS\-SMS\-Source\-Forest  
  
    -   cn\=mS\-SMS\-Version  
  
-   类：  
  
    -   cn\=MS\-SMS\-Management\-Point  
  
    -   cn\=MS\-SMS\-Roaming\-Boundary\-Range  
  
    -   cn\=MS\-SMS\-Server\-Locator\-Point  
  
    -   cn\=MS\-SMS\-Site  
  
> [!NOTE]  
>  架构扩展可能包含了从该产品的以前版本中带入的、但没有被 Configuration Manager 2015 使用的属性和类。 例如：  
>   
>  -   属性：cn\=MS\-SMS\-Site\-Boundaries  
> -   类：cn\=MS\-SMS\-Server\-Locator\-Point  
  
 你可以通过查看 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 安装媒体的 **\\SMSSETUP\\BIN\\x64** 文件夹中的 **ConfigMgr\_ad\_schema.LDF**文件来确保前面的列是最新的。  
  
## 另请参阅  
 [System Center Configuration Manager 的站点和层级结构基础结构技术参考](../LocTest/Site-and-hierarchy-infrastructure-technical-reference-for-System-Center-Configuration-Manager.md)
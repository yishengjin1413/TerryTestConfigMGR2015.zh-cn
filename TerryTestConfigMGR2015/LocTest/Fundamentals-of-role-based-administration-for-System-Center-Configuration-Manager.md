---
title: "System Center Configuration Manager 的基于角色的管理基础"
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
ms.assetid: 0a2d6c3f-a4e4-4c19-b087-3caada480de9
caps.latest.revision: 10
caps.handback.revision: 9
---
# System Center Configuration Manager 的基于角色的管理基础
在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中，使用使用基于角色的管理来保护对管理员 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 以及你管理的对象（例如集合、部署和站点）的访问权限。   了解在本主题中引入的概念后，你可以[为 System Center Configuration Manager 配置基于角色的管理](../LocTest/Configure-role-based-administration-for-System-Center-Configuration-Manager.md)。  
  
 此基于角色的管理模式使用以下内容为所有站点和站点设置集中定义并管理层次结构范围的安全访问设置：  
  
-   **安全角色** \- 会分配给管理用户，并将这些用户（或用户组）权限（例如创建或更改客户端设置的权限）提供给不同的 Configuration Manager 对象。  
  
-   **安全作用域** \- 管理用户负责管理的对象的特定于组的对象，例如安装 Microsoft Office 2010 的应用程序。  
  
-   **集合** \- 这是用于指定管理用户可管理的用户和设备资源组的方式。  
  
 安全角色、安全作用域和集合的组合允许你分离满足组织要求的管理分配，它们共同定义用户的管理作用域（用户可以在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 部署中查看和管理的内容）。  
  
 **基于角色的管理提供了以下好处：**  
  
-   站点不再用作管理边界  
  
-   你为层次结构创建管理用户，并仅需将安全性分配给他们一次  
  
-   所有安全分配都已复制，并在整个层次结构中可用  
  
-   具有多个内置的安全角色可分配给常见的管理任务，而且，你可以创建自己的自定义安全角色，以满足你的特定业务需求  
  
-   管理用户仅可查看他们有权管理的对象  
  
-   你可以审核管理安全操作。  
  
 为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 设计和实现管理安全性时，使用以下内容为为管理用户创建一个**管理作用域**：  
  
-   [安全角色](#bkmk_Planroles)  
  
-   [集合](#bkmk_planCol)  
  
-   [安全作用域](#bkmk_PlanScope)  
  
 管理作用域控制管理用户可以在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中查看的对象，以及该用户对这些对象所具有的权限。 基于角色的管理配置作为全局数据复制到层次结构中的每个站点，然后应用到所有管理连接。  
  
> [!IMPORTANT]  
>  站点间复制的延迟可能会阻止站点收到基于角色的管理的变化。 有关如何监视站点间数据库复制的信息，请参阅 [System Center Configuration Manager 中的站点间数据传输](../LocTest/Data-transfers-between-sites-in-System-Center-Configuration-Manager.md)主题。  
  
##  <a name="bkmk_Planroles"></a> 安全角色  
 安全角色用于向管理用户授予安全权限。 安全角色是安全权限的组合，你将这些权限分配给管理用户，以便他们能够执行管理任务。 这些安全权限定义管理用户可以执行的管理操作，以及为特定对象类型授予的权限。 最佳安全方案是分配提供最低权限的安全角色。  
  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 具有多个内置的安全角色，能支持常见的管理任务组合，而且，你可以创建自己的自定义安全角色，以满足你的特定业务需求。 内置安全角色的示例：  
  
-   “完全权限管理员”：此安全角色授予 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的所有权限。  
  
-   “资产分析师”：此安全角色允许管理用户查看使用资产智能、软件清单、硬件清单和软件计数收集的数据。 管理用户可以创建计数规则以及资产智能类别、家族和标签。  
  
-   “软件更新管理员”：此安全角色授予定义和部署软件更新的权限。 与此角色关联的管理用户可以创建集合、软件更新组、部署和模板，并能让软件更新与网络访问保护 \(NAP\) 一起使用。  
  
> [!TIP]  
>  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，可以查看内置的安全角色和你创建的自定义安全角色的列表（包括它们的描述）。 若要这样做，请在“管理”工作区中展开“安全”，然后选择“安全角色”。  
  
 每个安全角色都有针对不同对象类型的特定权限。 例如，“应用程序管理员”安全角色具有下列针对应用程序的权限：“批准”、“创建”、“删除”、“修改”、“修改文件夹”、“移动对象”、“读取\/部署”、“设置安全作用域”。 无法更改内置安全角色的权限，但可以复制角色，进行更改，然后将所做的更改另存为新的自定义安全角色。 还可以导入从另一个层次结构（例如测试网络）中导出的安全角色。 查看安全角色及其权限，以确定是使用内置的安全角色还是必须创建自己的自定义安全角色。  
  
 **使用下列步骤帮助你规划安全角色：**  
  
1.  确定管理用户在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中执行的任务。 这些任务可能关系到一个或多个管理任务组，例如部署应用程序和包、部署操作系统和符合性设置、配置站点和安全性、审核、远程控制计算机以及收集清单数据。  
  
2.  将这些管理任务对应到一个或多个内置的安全角色。  
  
3.  如果某些管理用户执行多个安全角色的任务，则将多个安全角色分配给这些管理用户，而不是创建一个组合此类任务的新的安全角色。  
  
4.  如果你确定的任务未能对应到内置的安全角色，则创建并测试新的安全角色。  
  
 有关如何创建和配置安全角色以实现基于角色的管理的信息，请参阅[为 System Center Configuration Manager 配置基于角色的管理](../LocTest/Configure-role-based-administration-for-System-Center-Configuration-Manager.md)主题中的[创建自定义安全角色](../LocTest/Configure-role-based-administration-for-System-Center-Configuration-Manager.md#BKMK_CreateSecRole)和[配置安全角色](../LocTest/Configure-role-based-administration-for-System-Center-Configuration-Manager.md#BKMK_ConfigSecRole)部分。  
  
##  <a name="bkmk_planCol"></a> 集合  
 集合指定管理用户可以查看或管理的用户和计算机资源。 例如，若要使管理用户能够部署应用程序或运行远程控制，必须将它们分配到相应的安全角色，此角色授予对包含这些资源的集合的访问权限。 可以选择用户或设备的集合。  
  
 有关集合的详细信息，请参阅 [System Center Configuration Manager 中的集合简介](../LocTest/Introduction-to-collections-in-System-Center-Configuration-Manager.md)。  
  
 在配置基于角色的管理之前，请检查你是否必须出于下列任一原因创建新的集合：  
  
-   功能组织。 例如，独立的服务器和工作站集合。  
  
-   地理位置协调。 例如，独立的北美洲和欧洲集合。  
  
-   安全要求和业务流程。 例如，独立的生产计算机和测试计算机集合。  
  
-   组织协调。 例如，每个业务单位的独立集合。  
  
 有关如何创建和配置安全角色以实现基于角色的管理的信息，请参阅 [为 System Center Configuration Manager 配置基于角色的管理](../LocTest/Configure-role-based-administration-for-System-Center-Configuration-Manager.md) 主题中的 [配置集合来管理安全性](../LocTest/Configure-role-based-administration-for-System-Center-Configuration-Manager.md#BKMK_ConfigColl)。  
  
##  <a name="bkmk_PlanScope"></a> 安全作用域  
 使用安全作用域为管理用户提供对安全对象的访问。 安全作用域是安全对象的命名集合，这些对象作为一组分配给管理用户。 必须将所有安全对象分配到一个或多个安全作用域。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 具有两个内置的安全作用域：  
  
-   “全部”：此内置的安全作用域授予对所有作用域的访问权限。 无法将对象分配到此安全作用域。  
  
-   “默认”：默认情况下，此内置的安全作用域用于所有对象。 在初次安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 时，所有对象均分配到此安全作用域。  
  
 如果想限制管理用户可以查看和管理的对象，则必须创建并使用你自己的自定义安全作用域。 安全作用域不支持层次结构，而且不能嵌套。 安全作用域可以包含一个或多个对象类型，其中包括下列类型：  
  
-   警报订阅  
  
-   应用程序  
  
-   启动映像  
  
-   边界组  
  
-   配置项目  
  
-   自定义客户端设置  
  
-   分发点和分发点组  
  
-   驱动程序包  
  
-   全局条件  
  
-   迁移作业  
  
-   操作系统映像  
  
-   操作系统安装包  
  
-   包  
  
-   查询  
  
-   站点  
  
-   软件计数规则  
  
-   软件更新组  
  
-   软件更新包  
  
-   任务序列包  
  
-   Windows CE 设备设置项目和包  
  
 还有一些对象是无法包含在安全作用域中的，因为它们仅由安全角色保护。 无法将对这些对象进行的管理性访问限制在一部分可用的对象内。 例如，管理用户可能创建了用于特定站点的边界组。 由于边界对象不支持安全作用域，因此，无法向此用户分配这样一个安全作用域：仅提供对可能与该站点关联的边界的访问。 由于边界对象无法关联到安全作用域，因此，在向用户分配包含对边界对象的访问的安全角色时，该用户可以访问层次结构中的每个边界。  
  
 不受安全作用域限制的对象包括：  
  
-   Active Directory 林  
  
-   管理用户  
  
-   警报  
  
-   反恶意软件策略  
  
-   边界  
  
-   计算机关联  
  
-   默认客户端设置  
  
-   部署模板  
  
-   设备驱动程序  
  
-   Exchange Server 连接器  
  
-   迁移站点间映射  
  
-   移动设备注册配置文件  
  
-   安全角色  
  
-   安全作用域  
  
-   站点地址  
  
-   站点系统角色  
  
-   软件标题  
  
-   软件更新  
  
-   状态消息  
  
-   用户设备相关性  
  
 在必须限制对独立的对象实例的访问时，请创建安全作用域。 例如：  
  
-   你有一组管理用户，他们必须能够查看生产应用程序而不是测试应用程序。 请为生产应用程序创建一个安全作用域，并为测试应用程序创建另一个安全作用域。  
  
-   不同的管理用户需要对某个对象类型的一些实例进行不同的访问。 例如，一组管理用户需要特定软件更新组的“读取”权限，而另一组管理用户需要其他软件更新组的“修改”和“删除”权限。 请为这些软件更新组创建不同的安全作用域。  
  
 有关如何配置安全作用域以实现基于角色的管理的信息，请参阅 [为 System Center Configuration Manager 配置基于角色的管理](../LocTest/Configure-role-based-administration-for-System-Center-Configuration-Manager.md) 主题中的 [配置对象的安全作用域](../LocTest/Configure-role-based-administration-for-System-Center-Configuration-Manager.md#BKMK_ConfigSecScope)。  
  
## 请参阅  
 [System Center Configuration Manager 基础结构的规划](../LocTest/Plan-for-System-Center-Configuration-Manager-infrastructure.md)
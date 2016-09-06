---
title: "System Center Configuration Manager 中迁移的先决条件"
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
ms.assetid: ec976930-7467-4d3c-b33c-991bf408a74a
caps.latest.revision: 10
caps.handback.revision: 10
translationtype: Human Translation
---
# System Center Configuration Manager 中迁移的先决条件
要从支持的源层次结构中进行迁移，你必须拥有每个适用的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 源站点的访问权限以及 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 目标站点内的权限才能配置和运行迁移操作。  
  
 使用下列部分中的信息来帮助你了解迁移支持的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 版本以及必需的配置。  
  
-   [迁移支持的 Configuration Manager 版本](#BKMK_SupportedMigrationVersions)  
  
-   [迁移支持的源站点语言](#BKMK_SorceSiteLanguage)  
  
-   [迁移所需的配置](#BKMK_Required_Configurations)  
  
##  <a name="BKMK_SupportedMigrationVersions"></a> 迁移支持的 Configuration Manager 版本  
 你可以从运行任何以下版本的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]的源层次结构迁移数据：  
  
-   [!INCLUDE[cm4short](../LocTest/includes/cm4short_md.md)] SP2（为了迁移，不考虑源站点上的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 2007 R2 或 R3。 只要源站点运行 SP2，均支持安装有 R2 或 R3 加载项的站点迁移到 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]）  
  
-   [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] SP2 或 System Center 2012 R2 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] SP1  
  
    > [!TIP]  
    >  除了迁移，你还可以将运行 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 的站点就地升级到 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]。  
  
-   相同或更低版本的 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 层次结构 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]  
  
##  <a name="BKMK_SorceSiteLanguage"></a> 迁移支持的源站点语言  
 在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 层次结构之间迁移数据时，数据将采用 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]的语言中性格式存储在目标层次结构中。 由于 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]2007 不采用语言中性格式存储数据，因此在从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 2007 进行迁移的过程必须在迁移期间将对象转换为此格式。 因此，迁移只支持使用以下语言安装的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 2007 源站点：  
  
-   英语  
  
-   法语  
  
-   德语  
  
-   日语  
  
-   朝鲜语  
  
-   俄语  
  
-   简体中文  
  
-   繁体中文  
  
 从 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 或 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 层次结构中迁移数据时，没有源站点语言限制。 源站点数据库中的对象已采用语言中性格式。  
  
##  <a name="BKMK_Required_Configurations"></a> 迁移所需的配置  
 下面列出了使用迁移所需的配置以及迁移操作：  
  
-   **在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中配置、运行和监视迁移：**  
  
     在目标站点中，必须为你的帐户分配基于角色的管理安全角色“基础结构管理员” 。 此安全角色授予用于管理所有迁移操作的权限，这些操作包括创建迁移作业、清理、监视以及共享和升级分发点的操作。  
  
-   **数据收集：**  
  
     要使目标站点能够收集数据，你必须配置以下两个源站点访问帐户以与每个源站点一起使用：  
  
    -   **源站点帐户：** 此帐户用于访问源站点的 SMS 提供程序。  
  
        -   对于 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]2007 SP2 源站点，此帐户需要所有源站点对象的 **2007 站点服务器上“站点”** 权限。  
  
        -   对于 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 或 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 源站点，此帐户需要所有源站点对象的 **2007 站点服务器上“站点”** 权限，你通过使用基于角色的管理向帐户授予此权限。 有关如何使用基于角色的管理的信息，请参阅 [Fundamentals of role-based administration for System Center Configuration Manager](../LocTest/Fundamentals-of-role-based-administration-for-System-Center-Configuration-Manager.md)。  
  
    -   **源站点数据库帐户：** 此帐户用于访问源站点的 SQL Server 数据库，并需要源站点数据库的 **Connect**、 **Execute**和 **Select** 权限。  
  
     你可以在配置新的源层次结构、其他源站点的数据收集或在为源站点重新配置凭据时配置这些帐户。 这些帐户可以使用域用户帐户，或者你可以指定目标层次结构的顶层站点的计算机帐户。  
  
    > [!IMPORTANT]  
    >  如果你为任一访问帐户使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 计算机帐户，请确保此帐户是源站点所在域中“分布式 COM 用户”  安全组的成员。  
  
     在收集数据时，将使用以下网络协议和端口：  
  
    -   NetBIOS/SMB – 445 (TCP)  
  
    -   RPC (WMI) - 135 (TCP)  
  
    -   SQL Server - 源站点数据库和目标站点数据库同时使用的 TCP 端口。  
  
-   **迁移软件更新：**  
  
     在迁移软件更新之前，你必须配置包含软件更新点的目标层次结构。 有关详细信息，请参阅[规划软件更新迁移](../LocTest/Planning-for-the-migration-of-Configuration-Manager-objects-to-System-Center-Configuration-Manager.md#Plan_migrate_Software_updates)。  
  
-   **共享分发点：**  
  
     要成功共享源站点中的任何分发点，目标层次结构中的至少一个主站点或管理中心站点必须为客户端请求使用与源站点一样的端口号。 有关客户端请求端口的信息，请参阅[如何在 System Center Configuration Manager 中配置客户端通信端口](../LocTest/How-to-configure-client-communication-ports-in-System-Center-Configuration-Manager.md)  
  
     对于每个源站点，只会共享在使用 FQDN 配置的站点系统服务器上安装的分发点。  
  
     此外，要共享 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 或 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 源站点中的分发点，“源站点帐户”  （访问源站点服务器的 SMS 提供程序）必须具有源站点上“站点”  对象的“修改”  权限。 通过使用基于角色的管理来向帐户授予此权限。 有关如何使用基于角色的管理的信息，请参阅 [Fundamentals of role-based administration for System Center Configuration Manager](../LocTest/Fundamentals-of-role-based-administration-for-System-Center-Configuration-Manager.md)。  
  
-   **共享分发点：**  
  
     要成功共享源站点中的任何分发点，目标层次结构中的至少一个主站点或管理中心站点必须为客户端请求使用与源站点一样的端口号。 有关客户端请求端口的信息，请参阅[如何在 System Center Configuration Manager 中配置客户端通信端口](../LocTest/How-to-configure-client-communication-ports-in-System-Center-Configuration-Manager.md)  
  
     对于每个源站点，只会共享在使用 FQDN 配置的站点系统服务器上安装的分发点。  
  
     此外，要共享 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 或 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 源站点中的分发点，“源站点帐户”  （访问源站点服务器的 SMS 提供程序）必须具有源站点上“站点”  对象的“修改”  权限。 通过使用基于角色的管理来向帐户授予此权限。 有关如何使用基于角色的管理的信息，请参阅 [Fundamentals of role-based administration for System Center Configuration Manager](../LocTest/Fundamentals-of-role-based-administration-for-System-Center-Configuration-Manager.md)。  
  
-   **升级或重新分配分发点：**  
  
     配置为从源站点的 SMS 提供程序中收集数据的“源站点访问帐户”  必须拥有以下权限：  
  
    -   若要升级 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]2007 分发点，则帐户需要对 **2007 站点服务器上“站点”****类的“读取”****、“执行”****和“删除”**[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]权限以成功从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]2007 源站点删除分发点  
  
    -   若要重新分配 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 或 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 分发点，该帐户必须拥有源站点上的“站点”  对象的“修改”  权限。 通过使用基于角色的管理来向帐户授予此权限。 有关如何使用基于角色的管理的信息，请参阅 [Fundamentals of role-based administration for System Center Configuration Manager](../LocTest/Fundamentals-of-role-based-administration-for-System-Center-Configuration-Manager.md)。  
  
     若要成功将分发点升级或重新分配到新层次结构，为源层次结构中用于管理分发点的站点上的客户端请求配置的端口必须与为将用于管理分发点的目标站点上的客户端请求配置的端口匹配。 有关客户端请求端口的信息，请参阅[如何在 System Center Configuration Manager 中配置客户端通信端口](../LocTest/How-to-configure-client-communication-ports-in-System-Center-Configuration-Manager.md)。  
  
## 另请参阅  
 [规划迁移到 System Center Configuration Manager](../LocTest/Planning-for-migration-to-System-Center-Configuration-Manager.md)
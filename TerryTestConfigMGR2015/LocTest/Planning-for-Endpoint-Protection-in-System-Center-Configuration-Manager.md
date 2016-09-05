---
title: "在 System Center Configuration Manager 中规划 Endpoint Protection"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-other
ms.tgt_pltfrm: na
ms.topic: get-started-article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 7610bbd3-a67f-4a09-8115-e35d40d43b42
caps.latest.revision: 16
caps.handback.revision: 16
translationtype: Human Translation
---
# 在 System Center Configuration Manager 中规划 Endpoint Protection
使用本部分中的以下主题来帮助你在 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 中规划 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)]的使用。  
  
## Configuration Manager 中的 Endpoint Protection 管理员工作流  
 将以下工作流用作参考，以帮助你启用、配置、管理和监视 System Center 2012 Configuration Manager 中的 Endpoint Protection。  
  
|步骤|更多信息|  
|----------|----------------------|  
|检查 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)]的先决条件信息。|[Planning for Endpoint Protection in Configuration Manager](../LocTest/Planning-for-Endpoint-Protection-in-System-Center-Configuration-Manager.md)。|  
|创建 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 点站点系统角色。|[在 System Center Configuration Manager 中配置 Endpoint Protection](../LocTest/Configuring-Endpoint-Protection-in-System-Center-Configuration-Manager.md)。|  
|配置的警报 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)]。|[在 System Center Configuration Manager 中配置 Endpoint Protection](../LocTest/Configuring-Endpoint-Protection-in-System-Center-Configuration-Manager.md)|  
|将配置定义更新方法来更新客户端计算机。|请参阅[在 System Center Configuration Manager 中配置 Endpoint Protection](../LocTest/Configuring-Endpoint-Protection-in-System-Center-Configuration-Manager.md) 中的“如何在 Configuration Manager 中为 Endpoint Protection 配置定义更新”|  
|配置的计算机集合的反恶意软件设置。|[如何在 System Center Configuration Manager 中为 Endpoint Protection 创建和部署反恶意软件策略](../LocTest/How-to-create-and-deploy-antimalware-policies-for-Endpoint-Protection-in-System-Center-Configuration-Manager.md)|  
|配置客户端设置 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)]。|[在 System Center Configuration Manager 中配置 Endpoint Protection](../LocTest/Configuring-Endpoint-Protection-in-System-Center-Configuration-Manager.md)|  
|创建并将防火墙策略部署到的计算机的集合。|[如何在 System Center Configuration Manager 中为 Endpoint Protection 创建和部署 Windows 防火墙策略](../LocTest/How-to-create-and-deploy-Windows-Firewall-policies-for-Endpoint-Protection-in-System-Center-Configuration-Manager.md)。|  
|监视器 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 活动。|[如何在 System Center Configuration Manager 中监视 Endpoint Protection](../LocTest/How-to-monitor-Endpoint-Protection-in-System-Center-Configuration-Manager.md)。|  
  
## 终结点保护在 Configuration Manager 的先决条件  
 System Center 2012 Configuration Manager 中的 Endpoint Protection 具有外部依赖关系和产品中的依赖关系。  
  
### 外部依赖关系 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]  
 下表列出了用于运行的外部依赖关系 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 中 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]。  
  
 **依赖关系**  
  
-   如果您想要使用，Windows Server Update Services (WSUS) 必须是已安装且已配置为软件更新同步 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 用于提供定义和引擎更新的软件更新。 请参阅 [System Center Configuration Manager 中软件更新的先决条件](../LocTest/Prerequisites-for-software-updates-in-System-Center-Configuration-Manager.md)  
  
-   某些定义更新方法要求使用客户端计算机具有 Internet 访问权限。 如果使用任何以下方法来更新客户端计算机上的定义，客户端计算机必须能够访问 Internet：  
  
    -   从 Microsoft 更新分发的更新  
  
    -   从 Microsoft 恶意软件防护中心分发的更新  
  
    > [!IMPORTANT]  
    >  客户端通过使用内置系统帐户下载定义更新。 必须为此帐户配置代理服务器才能使这些客户端连接到 Internet。 Windows 组策略可用于在多台计算机上配置代理服务器。  
  
-   如果想要发送电子邮件警报的 SMTP 服务器。 请参阅第 1 步（可选）：[在 System Center Configuration Manager 中配置 Endpoint Protection ](../LocTest/Configuring-Endpoint-Protection-in-System-Center-Configuration-Manager.md) 主题中的配置警报的电子邮件设置。  
  
-   若要部署 Windows 防火墙策略的修补程序要求。 如果您想要将 Windows 防火墙策略部署到运行 Windows Server 2008 和 Windows Vista Service Pack 1 的计算机，则必须先安装 [修补程序 kb971800，以](http://go.microsoft.com/fwlink/p/?LinkId=231239) 在这些计算机上。  
  
### Configuration Manager 依赖关系  
 下表列出了内部依赖关系 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 运行 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)]。  
  
 **依赖关系**  
  
-   您的独立主或管理中心站点必须运行 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 并且具有 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 点站点系统角色安装和配置。 有关 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 点站点系统角色的要求的详细信息，请参阅 [System Center Configuration Manager 支持的配置](../LocTest/Supported-configurations-for-System-Center-Configuration-Manager.md)中的“站点系统要求”部分。 有关安装此站点系统角色的详细信息，请参阅[在 System Center Configuration Manager 中配置 Endpoint Protection](../LocTest/Configuring-Endpoint-Protection-in-System-Center-Configuration-Manager.md)。  
  
    > [!IMPORTANT]  
    >  必须先安装 Endpoint Protection 点站点系统角色，然后才能使用 Endpoint Protection。 必须将其仅安装在一个站点系统服务器上，并且必须将其安装在管理中心站点或独立主站点上层次结构的顶部。  
  
-   如果希望使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 软件更新来提供定义和引擎更新，则必须安装和配置软件更新点站点系统角色用于提供定义更新。 有关对软件更新点站点系统角色的要求的详细信息，请参阅 [Supported configurations for System Center Configuration Manager](../LocTest/Supported-configurations-for-System-Center-Configuration-Manager.md)的“站点系统要求”部分。 有关如何安装此站点系统角色和为 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 配置此站点系统角色的详细信息，请参阅[在 System Center Configuration Manager 中配置软件更新](../LocTest/Configure-software-updates-in-System-Center-Configuration-Manager.md)和[在 System Center Configuration Manager 中配置 Endpoint Protection](../LocTest/Configuring-Endpoint-Protection-in-System-Center-Configuration-Manager.md)。  
  
-   安装 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端和配置 Endpoint Protection 的客户端设置。 有关如何为 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 配置客户端设置的详细信息，请参阅[在 System Center Configuration Manager 中配置 Endpoint Protection](../LocTest/Configuring-Endpoint-Protection-in-System-Center-Configuration-Manager.md) 中的“配置自定义客户端设置”。  
  
-   Reporting services 点站点系统角色必须安装之前 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 可以显示报表。 请参阅 [System Center Configuration Manager 中的报表](../LocTest/Reporting-in-System-Center-Configuration-Manager.md)  
  
-   管理 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)]。 必须具有以下安全权限才能管理 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)]：  
  
    -   若要创建和管理对 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 警报的订阅：针对“警报订阅” 对象，进行“创建” 、“删除” 、“修改” 、“读取”  、“设置安全作用域”  操作。  
  
    -   若要创建和修改 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)]的警报：针对“警报” 对象，进行“创建” 、“删除” 、“修改” 、“修改报告” 、“读取”  、“运行报表”  操作。  
  
    -   若要创建和修改反恶意软件策略：针对“反恶意软件策略” 对象，进行“创建” 、“删除” 、“修改” 、“修改默认” 、“修改报表” 、“读取” 、“读取默认”  、“运行报表”  操作。  
  
    -   若要将反恶意软件和 Windows 防火墙策略部署到计算机：针对“集合” 对象，进行“审核安全性” 、“删除” 、“部署反恶意软件策略” 、“部署防火墙策略” 、“强制安全性” 、“读取”  、“读取资源”   操作。  
  
    -   若要在 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 控制台中查看和管理 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] ：针对“站点”  对象，设置“读取”  权限。  
  
    -   若要创建和修改 Windows 防火墙策略：针对“Windows 防火墙策略” 对象，进行“创建策略” 、“删除策略” 、“修改策略” 、“读取策略”  、“读取设置”  操作。  
  
     **[!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] Manager** 安全角色包括管理时需要这些权限 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 中 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]。  
  
    > [!NOTE]  
    >  若要执行以下操作，你必须是“完全权限管理员”  安全角色的成员。  
    >   
    >  -   配置 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 点站点系统角色。  
    > -   为 Endpoint Protection 警报配置电子邮件通知。  
  
## Configuration Manager 中的 Endpoint Protection 最佳方案  
 使用以下 System Center 2012 Configuration Manager 中的 Endpoint Protection 的最佳方案。  
  
### 为 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)]  
 当您配置的客户端设置 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)], ，不要使用默认客户端设置，因为它们将设置应用于您的层次结构中的所有计算机。 相反，配置自定义客户端设置并将这些设置分配给您的层次结构中的计算机的集合。  
  
 在配置自定义客户端设置时，可以执行以下操作：  
  
-   自定义您的组织的不同部分的反恶意软件和安全设置。  
  
-   测试运行的效果 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 小的一组之前将其部署到整个层次结构的计算机上。  
  
-   向一段时间逐步部署的集合中添加更多客户端 [!INCLUDE[epshort](../LocTest/includes/epshort_md.md)] 客户端。  
  
### 通过使用软件更新的分发定义更新  
 如果您使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 用于将定义更新分发的软件更新可考虑将定义更新放在不包含其他软件更新包中。 这会使定义更新包的大小较小这使得它能够复制到更快地分发点。
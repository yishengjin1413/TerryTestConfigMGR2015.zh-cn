---
title: "System Center Configuration Manager 的诊断使用情况数据收集的级别"
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
ms.assetid: 9e614ae1-47d2-4a93-ba0a-89dc50d1e266
caps.latest.revision: 4
caps.handback.revision: 4
translationtype: Human Translation
---
# System Center Configuration Manager 的诊断使用情况数据收集的级别
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 收集三个级别的诊断和使用情况数据：**基本**、**增强**和**完全**。 默认情况下，此功能设置为增强级别。 以下部分提供在每个级别收集哪些数据的其他详细信息。  
  
> [!IMPORTANT]  
>  [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不会收集基本或增强级别的站点代码或站点名称、IP 地址、用户名或计算机名、物理地址或电子邮件地址。 在完全级别收集的信息没有目的性（可能包括在日志文件或内存快照等高级诊断信息中），Microsoft 不会使用这些信息识别你的身份、与你联系或用于广告目的。  
  
##  <a name="bkmk_change"></a> 如何更改级别  
 如果管理员基于角色的管理作用域包括对**站点**对象类的**修改**权限，则其可以通过 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中的诊断和使用情况数据设置更改收集的数据的级别。  
  
##  <a name="bkmk_level1"></a> 级别 1 - 基本  
 基本级别包括有关层次结构的数据，需要此级别才可帮助改进安装或升级体验，以及帮助确定哪些 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 更新适合你的层次结构。  
  
 从 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 版本 1511 开始，此级别包括以下内容：  
  
> [!NOTE]  
>  [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 版本 1602 针对为此级别收集的数据引入了一些更改。 本主题将在这些详细信息可用时立即使用它们进行更新。  
  
-   安装信息（内部版本、安装类型、语言包、启用的功能、更新包部署状态和错误）  
  
-   数据库性能指标（复制处理信息、按处理器和磁盘使用情况排在前面的 SQL Server 存储过程）  
  
-   基本数据库配置（处理器、群集配置、分布式视图配置）  
  
-   [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 数据库架构（所有对象定义的哈希）  
  
-   [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端版本和操作系统版本的计数  
  
-   托管设备的操作系统和 Exchange Connector 所设置的策略计数  
  
-   客户端语言和区域设置计数  
  
-   Windows 10 设备（按分支和内部版本）计数  
  
-   基本 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点层次结构数据（站点列表、类型、版本、状态、客户端计数和时区）  
  
-   基本站点系统服务器信息（使用的站点系统角色、Internet 和 SSL 状态、操作系统、处理器、物理计算机或虚拟机）  
  
-   基本用户发现统计信息（用户发现计数、最小/最大/平均组大小）  
  
-   基本 Endpoint Protection 信息（反恶意软件客户端版本）  
  
-   基本应用程序和部署类型计数（应用总数、包含多个部署类型的应用总数、包含依赖项的应用总数、被取代的应用总数、使用中的部署技术数）  
  
-   基本 OSD 计数（映像）  
  
-   分发点和管理点类型以及基本配置信息（受保护、预留、PXE、多播、SSL 状态、请求/对等分发点、启用 MDM、启用 SSL 等。）  
  
-   遥测统计信息（运行时间、运行时、错误）  
  
##  <a name="bkmk_level2"></a> 级别 2 - 增强  
 安装后的默认级别为增强级别。 此级别包括在基本级别收集的数据，以及特定于功能的数据（频率和持续使用时间）、[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端设置（组件名称、状态和轮询间隔等特定设置）和有关软件更新的基本信息。  
  
 此级别为 Microsoft 提供对将来版本的产品和服务进行有用改进所需的最小数据，因此是推荐的级别。 此级别不收集对象名称（站点、用户、计算机或对象）、安全相关对象的详细信息或需要软件更新的系统计数等漏洞。  
  
 从 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 版本 1511 开始，此级别包括以下内容：  
  
-   **应用程序管理：**  
  
    -   组织内使用的部署类型的基本使用情况/目标信息（用户与目标设备、所需设备与可用设备）  
  
    -   应用程序部署信息（安装/卸载、需要批准、已启用/禁用用户交互）  
  
    -   可用应用程序请求统计信息  
  
    -   包（按类型）计数  
  
    -   应用程序适用性（按操作系统）计数  
  
    -   包/程序部署计数  
  
    -   App-V 环境和部署属性计数  
  
    -   Windows 10 授权应用程序许可证计数  
  
    -   每个用户/设备的应用程序部署的最大/最小/平均数目  
  
    -   维护时段类型和持续时间  
  
-   **客户端：**  
  
    -   已启用客户端代理的列表/计数  
  
    -   从每个源位置类型进行的客户端安装计数  
  
    -   客户端安装失败计数  
  
-   **符合性设置：**  
  
    -   配置项目计数（按类型）  
  
    -   基本配置基线信息（计数、部署数目和引用数目）  
  
    -   引用内置设置（不捕获设置的值）的部署计数  
  
    -   为自定义设置创建的规则和部署计数  
  
    -   部署的简单证书注册协议模板计数  
  
-   **内容：**  
  
    -   边界（按类型）计数  
  
    -   边界组信息（分配给每个边界组的边界和站点系统的计数）  
  
    -   分发点组信息（分配给每个分发点组的包和分发点的计数）  
  
    -   分发点配置信息（分支缓存的使用、分发点监视）  
  
    -   分发管理器配置信息（线程、重试延迟、重试次数、请求分发点设置）  
  
-   **Endpoint Protection：**  
  
    -   Endpoint Protection 反恶意软件和 Windows 防火墙策略的使用情况（分配给组的唯一策略数；这不包括策略中包含的有关设置的任何信息）  
  
    -   Endpoint Protection 部署错误（Endpoint Protection 策略部署错误代码计数）  
  
    -   选择在 Endpoint Protection 仪表板中显示的集合数  
  
    -   为 Endpoint Protection 功能配置的警报数  
  
-   **移动应用程序管理 (MAM)：**  
  
    -   启用了 MAM 的 Office 和业务线应用程序与和策略（按操作系统）计数  
  
    -   MAM 应用程序/策略部署的计数  
  
    -   创建的规则（按 MAM 设置）计数  
  
-   **移动设备管理 (MDM)：**  
  
    -   已发出的移动设备操作（锁定、固定剩余部分、擦除和停用）命令的计数  
  
    -   由 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 和 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 托管的移动设备计数和这些设备的注册方式（批量、基于用户）  
  
    -   移动设备轮询计划和移动设备持续时间检查统计信息  
  
    -   移动设备策略计数  
  
    -   具有多个注册移动设备的用户计数  
  
-   **[!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 故障排除：**  
  
    -   从中下载的状况、状态、清单、RDR、DDR、UDX、租户状况、POL、LOG、证书、CRP、重新同步、CFD、RDO、BEX、ISM 和符合性消息的计数和大小 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)]  
  
    -   复制到其中的设备操作（擦除、停用、锁定）、遥测和数据消息的计数和大小 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)]  
  
    -   其完全和增量用户同步统计信息 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)]  
  
-   **本地移动设备管理 (MDM)：**  
  
    -   本地 MDM 应用程序部署的部署成功/失败统计信息  
  
    -   Windows 10 批量注册包和配置文件计数  
  
-   **操作系统部署：**  
  
    -   启动映像、驱动程序、驱动程序包、启用多播的分发点、启用 PXE 的分发点以及任务序列的计数  
  
-   **软件更新：**  
  
    -   部署了软件更新的集合的总数目/平均数目和已部署更新的最大/平均数目  
  
    -   与同步绑定的自动部署规则数  
  
    -   创建新的更新或将更新添加到现有组的自动部署规则数  
  
    -   自动部署规则中使用的可用和截止时间增量  
  
    -   每个更新的平均和最大分配数  
  
    -   使用 System Center Update Publisher 创建和部署的更新数  
  
    -   更新组和分配的计数  
  
    -   更新包的数目和包的目标分发点的最大/最小/平均数目  
  
    -   更新组的数目和每个组的更新的最小/最大/平均数目  
  
    -   更新数和已更新、已过期、被取代、已下载和包含 EULA 的更新所占百分比  
  
    -   更新扫描错误代码和计算机计数  
  
    -   客户端更新评估和扫描计划  
  
    -   软件更新点同步计划  
  
    -   具有多个部署的自动部署规则数  
  
    -   用于活动 Windows 10 服务计划的配置  
  
    -   Windows 10 仪表板内容版本  
  
    -   使用 Windows Update for Business 的 Windows 10 客户端计数  
  
    -   群集修补统计信息  
  
    -   已部署 Office 365 更新计数  
  
-   **SQL/性能数据：**  
  
    -   最大数据库表计数  
  
    -   SQL 始终可用副本信息  
  
    -   集合（按类型）计数  
  
##  <a name="bkmk_level3"></a> 级别 3 - 完全  
 完全级别包括基本和增强级别的所有数据。 它还包括有关 Endpoint Protection、更新符合性百分比和软件更新信息的其他信息。  此级别还可包括系统文件和内存快照（可能包含捕获时存在于内存或日志文件中的个人信息）等高级诊断信息。  
  
 从 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 版本 1511 开始，此级别包括以下内容：  
  
-   集合评估与刷新统计信息  
  
-   Endpoint Protection 运行摘要（包括受保护、有风险、未知与不支持客户端的计数）  
  
-   Endpoint Protection 策略设置  
  
-   软件更新部署信息（客户端与UTC 时间、必须、可选与无提示、重启抑制的目标部署所占百分比）  
  
-   软件更新部署的总体符合性  
  
-   自动部署规则评估计划信息  
  
-   包含网络访问保护策略的客户端的计数  
  
-   软件更新部署错误代码和计数  
  
-   软件更新部署集合中停用客户端的最小/最大/平均数目  
  
-   包含已过期软件更新的组的计数  
  
-   每个包的软件更新的最小/最大/平均数目  
  
-   软件更新扫描成功百分比  
  
-   上次软件更新扫描后的最小/最大/平均小时数  
  
## 另请参阅  
 [System Center Configuration Manager 的诊断和使用情况数据](../LocTest/Diagnostics-and-usage-data-for-System-Center-Configuration-Manager.md)   
 [如何将诊断和使用情况数据用于 System Center Configuration Manager](../LocTest/How-diagnostics-and-usage-data-is-used-for-System-Center-Configuration-Manager.md)   
 [System Center Configuration Manager 如何收集诊断和使用情况数据](../LocTest/How-diagnostics-and-usage-data-is-collected-by-System-Center-Configuration-Manager.md)   
 [如何查看 System Center Configuration Manager 的诊断和使用情况数据](../LocTest/How-to-view-diagnostics-and-usage-data-for-System-Center-Configuration-Manager.md)
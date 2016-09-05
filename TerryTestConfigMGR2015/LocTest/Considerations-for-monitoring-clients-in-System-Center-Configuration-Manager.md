---
title: "有关监视 Configuration Manager 中的计算机和设备的注意事项"
ms.custom: na
ms.date: 09/02/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 79f90efe-06f1-459b-bf91-7df71e6183f5
caps.latest.revision: 6
caps.handback.revision: 5
---
# 有关监视 Configuration Manager 中的计算机和设备的注意事项
使用 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 控制台的“监视”工作区中的“客户端状态”节点来监视层次结构中的客户端计算机的运行状况与活动。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 使用以下两种方法来评估客户端计算机的总体状态。  
  
 “客户端活动”：你可以配置阈值来确定客户端是否处于活动状态，例如：  
  
-   客户端是否在最后七天内请求策略。  
  
-   检测信号发现是否在最后七天内找到客户端。  
  
-   客户端是否在最后七天内发送了硬件清单。  
  
 如果超出所有这些阈值，则认为客户端为不活动状态。  
  
 “客户端检查”：随 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端一起安装了客户端评估引擎，此引擎定期评估 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端的运行状况及其依赖关系。 此引擎可以检查或修正 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端的一些问题。  
  
 在运行 Windows 7 的计算机上，客户端检查将作为计划任务运行。 在更高版本的操作系统上，客户端检查将在 Windows 维护时段自动运行。  
  
 你可以将修正配置为不在特定计算机（例如关键业务服务器）上运行。 此外，如果想要评估其他项，则可以使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 符合性设置提供全面的解决方案，以监视组织中计算机的总体健康状况、活动和符合性。 有关符合性设置的详细信息，请参阅 [在 System Center Configuration Manager 中规划和配置符合性设置](../LocTest/Plan-for-and-configure-compliance-settings-in-System-Center-Configuration-Manager.md)。  
  
 客户端状态使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的监视和报告功能在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中提供关于客户端健康状况和活动的信息。 你可以将警报配置为在以下情况下通知你：客户端检查结果或客户端活跃状况低于集合中客户端的指定百分比，或者修正针对指定百分比的客户端失败。  
  
 有关如何配置客户端状态的信息，请参阅 [如何在 System Center Configuration Manager 中配置客户端状态](../LocTest/How-to-configure-client-status-in-System-Center-Configuration-Manager.md)。  
  
##  <a name="BKMK_ClientHealth"></a> 客户端检查进行的检查和修正  
 客户端检查可以执行以下检查和修正。  
  
|客户端检查|修正操作|更多信息|  
|-----------|----------|----------|  
|验证最近是否运行了客户端检查|运行客户端检查|检查在过去三天中是否至少运行了一次客户端检查。|  
|验证是否已安装客户端必备组件|安装客户端必备组件|检查是否安装了客户端必备组件。 阅读客户端安装文件夹中的 ccmsetup.xml 文件以发现必备组件。|  
|WMI 存储库完整性测试|重新安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端|检查 WMI 中是否存在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端条目。|  
|验证客户端服务是否正在运行|启动客户端（SMS 代理主机）服务|无更多信息|  
|WMI 事件接收器测试。|重新启动客户端服务|检查与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 相关的 WMI 事件接收器是否丢失|  
|验证 Windows Management Instrumentation \(WMI\) 服务是否存在|无修正|无更多信息|  
|验证是否正确安装了客户端|重新安装客户端|无更多信息|  
|WMI 存储库读取和写入测试|重新启动 WMI 存储库，然后重新安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端|仅在运行 Windows Server 2003、Windows XP（64 位）或更早版本的计算机上执行此客户端检查的修正。|  
|验证反恶意软件服务的启动类型是否为自动|将服务启动类型重置为自动|无更多信息|  
|验证反恶意软件服务是否正在运行|启动反恶意软件服务|无更多信息|  
|验证 Windows 更新服务启动类型是自动还是手动|将服务启动类型重置为自动|无更多信息|  
|验证客户端服务（SMS 代理主机）启动类型是否为自动|将服务启动类型重置为自动|无更多信息|  
|验证 Windows Management Instrumentation \(WMI\) 服务是否正在运行。|启动 Windows Management Instrumentation 服务|无更多信息|  
|验证 Microsoft SQL CE 数据库是否正常|重新安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端|无更多信息|  
|Microsoft 策略平台 WMI 完整性测试|修复 Microsoft 策略平台|无更多信息|  
|验证 Microsoft 策略平台服务是否存在|修复 Microsoft 策略平台|无更多信息|  
|验证 Microsoft 策略平台服务启动类型是否为手动|将服务启动类型重置为手动|无更多信息|  
|验证是否存在后台智能传输服务|无修正|无更多信息|  
|验证后台智能传输服务启动类型是自动还是手动|将服务启动类型重置为自动|无更多信息|  
|验证网络检查服务启动类型是否为手动|将服务（如果已安装）启动类型重置为手动|无更多信息|  
|验证 Windows Management Instrumentation \(WMI\) 服务启动类型是否为自动|将服务启动类型重置为自动|无更多信息|  
|验证 Windows 8 计算机上的 Windows 更新服务启动类型是自动还是手动|将服务启动类型重置为手动|无更多信息|  
|请验证客户端（SMS 代理主机）服务是否存在。|无修正|无更多信息|  
|验证 Configuration Manager 远程控制服务启动类型是自动还是手动|将服务启动类型重置为自动|无更多信息|  
|验证 Configuration Manager 远程控制服务是否正在运行|启动远程控制服务|无更多信息|  
|验证客户端 WMI 提供程序是否正常|重新启动 Windows Management Instrumentation 服务|仅在运行 Windows Server 2003、Windows XP（64 位）或更早版本的计算机上执行此客户端检查的修正。|  
|验证唤醒代理服务（ConfigMgr 唤醒代理）是否正在运行|启动 ConfigMgr 唤醒代理服务|仅当在支持的客户端操作系统上将客户端设置“电源管理: 启用唤醒代理”设置为“是”时，才会进行此客户端检查。|  
|验证唤醒代理服务（ConfigMgr 唤醒代理）启动类型是否为自动|将 ConfigMgr 唤醒代理服务启动类型重置为自动|仅当在支持的客户端操作系统上将客户端设置“电源管理: 启用唤醒代理”设置为“是”时，才会进行此客户端检查。|
---
title: "有关 System Center Configuration Manager 的诊断和使用情况数据的常见问题"
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
ms.assetid: 3fe32aa2-d594-4ad0-a291-b8f5395ac50b
caps.latest.revision: 6
caps.handback.revision: 5
translationtype: Human Translation
---
# 有关 System Center Configuration Manager 的诊断和使用情况数据的常见问题
以下是有关 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 的诊断和使用情况数据的常见问题：  
  
###  <a name="bkmk_off"></a> 如何关闭遥测？  
 需要定期更新 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的当前分支才可支持新版本的 Windows 10 和 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)]。 Microsoft 至少需要基本级别的诊断和使用情况数据来使产品保持最新状态、改进更新体检以及提高产品的质量和安全性。  
  
###  <a name="bkmk_retention"></a> 数据保留期为多久？  
 诊断和使用数据的保留期为一年。  
  
###  <a name="bkmk_update"></a> 安装或更新产品时是否发送了诊断和使用情况数据？  
 否。 仅当安装站点且可对其进行操作之后，才发送诊断和使用情况数据。  
  
###  <a name="bkmk_frequency"></a> 发送数据的频率是多高？  
 SQL 存储过程每七天（自安装站点之日起）运行一次。 在联机模式下，服务连接点配置为在查询运行后上传数据。 在脱机模式下，管理员使用服务连接工具上传数据。 \(（注意：安装站点后七天之内，数据最初不可脱机使用。）\)  
  
###  <a name="bkmk_network"></a> 可否将数据用于形成网络映射？  
 如 [System Center Configuration Manager 的诊断使用情况数据收集的级别](../LocTest/Levels-of-diagnostic-usage-data-collection-for-System-Center-Configuration-Manager.md)中所介绍，站点详细信息包括每个站点中的时区信息。 这可让你能够深入了解层次结构中站点的广泛的地理位置和全球分布。 但是，不会收集网络详细信息，例如 IP 地址或更详细的地理位置信息。  
  
###  <a name="bkmk_tables"></a> 可以查看自定义表中的数据吗？  
 否。 通过 SQL 存储过程，针对数据库中的默认产品表收集诊断和使用情况数据（所有表都带有前缀 **TEL\_**）。 作为 SQL 架构检测查询的一部分，对所有表名称进行了哈希处理，以便与已知默认值进行比较。 这可以确定数据库（由默认值扩展而来的数据库架构）中存在自定义表，但不能确定这些表中包含的任何数据。  
  
###  <a name="bkmk_databases"></a> 你能看到其他数据库的名称或其他数据库中的数据吗？  
 否。 用于收集数据的存储过程仅限于站点数据库。  
  
## 另请参阅  
 [System Center Configuration Manager 的诊断和使用情况数据](../LocTest/Diagnostics-and-usage-data-for-System-Center-Configuration-Manager.md)
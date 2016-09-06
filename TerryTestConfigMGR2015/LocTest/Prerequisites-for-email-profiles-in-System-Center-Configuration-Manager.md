---
title: "System Center Configuration Manager 中电子邮件配置文件的先决条件"
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
ms.assetid: dccf0b73-43bd-4545-8914-114168ebad36
caps.latest.revision: 5
caps.handback.revision: 2
translationtype: Human Translation
---
# System Center Configuration Manager 中电子邮件配置文件的先决条件
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的电子邮件配置文件在产品外部与产品内均有依赖关系。  
  
## Configuration Manager 依赖关系  
  
|依赖关系|更多信息|  
|----------|----------|  
|必须授予特定的安全权限来管理电子邮件配置文件|你必须具有以下安全权限才能管理公司资源访问设置，例如电子邮件配置文件：<br /><br /> -   如要查看和管理电子邮件配置文件的警报和报表：需要对“警报”对象的“创建”、“删除”、“修改”、“修改报表”、“读取”和“运行报表”权限。<br />-   若要创建和管理证书配置文件：需要对“证书配置文件”对象的“创作策略”、“修改报表”、“读取”和“运行报表”权限。<br />-   若要管理电子邮件配置文件部署：需要对“集合”对象的“部署配置策略”、“修改客户端状态警报”、“读取”和“读取资源”权限。<br />-   若要管理所有配置策略：需要对“配置策略”对象的“创建”、“删除”、“修改”、“读取”和“设置安全作用域”权限。<br />-   若要运行与电子邮件配置文件相关的查询：需要对“查询”对象的“读取”权限。<br />-   若要在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 控制台中查看电子邮件配置文件信息：需要对“站点”对象的“读取”权限。<br />-   若要查看电子邮件配置文件的状态消息：需要对“状态消息”对象的“读取”权限。<br />-   若要创建和管理电子邮件配置文件：需要对“通信设置配置文件”对象的“创作策略”、“修改报表”、“读取”和“运行报表”权限。<br /><br /> “公司资源访问管理器”安全角色包括在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中管理电子邮件配置文件所需的这些权限。 有关详细信息，请参阅 [配置 System Center Configuration Manager 中的安全性](../LocTest/Configure-security-in-System-Center-Configuration-Manager.md)。|  
|Active directory 中的邮件属性|如果想要通过使用用户的主 SMTP 地址生成电子邮件配置文件中的用户电子邮件地址，则必须配置 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 用户发现来发现 Active Directory 的“邮件”属性（默认情况下配置此项）。|  
  
## 外部依赖关系  
  
|依赖关系|更多信息|  
|----------|----------|  
|Active directory 中的邮件属性|如果想要通过使用用户的主 SMTP 地址生成电子邮件配置文件中的用户电子邮件地址，则此地址必须存在于 Active Directory 的“邮件”属性中。<br /><br /> 有关详细信息，请参阅 Windows Server 文档。|
---
title: "System Center Configuration Manager 中的 Unicode 和 ASCII 支持"
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
ms.assetid: 2bdec799-905f-48bc-aed5-2d92134739e8
caps.latest.revision: 6
caps.handback.revision: 5
translationtype: Human Translation
---
# System Center Configuration Manager 中的 Unicode 和 ASCII 支持
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 使用 Unicode 字符来创建大部分对象。 但是，有几个对象仅支持 ASCII 字符，或者具有其他限制。  
  
 下列部分列出了只能使用 ASCII 字符集中的字符或者具有其他限制的对象。  
  
-   [使用 ASCII 字符的对象](#BKMK_ASCIIchar)  
  
-   [其他限制](#BKMK_OtherCharLimitations)  
  
-   [未本地化的 Configuration Manager 对象](#BKMK_LangNonLocalize)  
  
##  <a name="BKMK_ASCIIchar"></a> 使用 ASCII 字符的对象  
 仅在你创建下列对象时，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 才支持 ASCII 字符集：  
  
-   站点代码  
  
-   所有站点系统服务器计算机的名称  
  
-   下列 Configuration Manager 帐户：  
  
    > [!NOTE]  
    >  在以俄语运行的站点上，这些帐户支持 ASCII 字符和 RUS 字符。  
  
    -   客户端请求安装帐户  
  
    -   健康状况引用发布帐户  
  
    -   健康状况引用查询帐户  
  
    -   管理点数据库连接帐户  
  
    -   网络访问帐户  
  
    -   包访问帐户  
  
    -   标准发件人帐户  
  
    -   站点系统安装帐户  
  
    -   软件更新点连接帐户  
  
    -   软件更新点代理服务器帐户  
  
    > [!NOTE]  
    >  你为基于角色的管理指定的帐户支持 Unicode。  
    >   
    >  Reporting Services 点帐户支持 Unicode（RUS 字符除外）。  
  
-   站点服务器和站点系统的 FQDN  
  
-   Configuration Manager 的安装路径  
  
-   SQL Server 实例名称  
  
-   下列站点系统角色的路径：  
  
    -   应用程序目录 Web 服务点  
  
    -   应用程序目录网站点  
  
    -   注册点  
  
    -   注册代理点  
  
    -   Reporting Services 点  
  
    -   状态迁移点  
  
-   下列文件夹的路径：  
  
    -   存储客户端状态迁移数据的文件夹  
  
    -   包含 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 报表的文件夹  
  
    -   存储 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 备份的文件夹  
  
    -   存储站点安装程序的安装源文件的文件夹。  
  
    -   存储所下载的、供安装程序使用的必备组件的文件夹  
  
-   下列对象的路径：  
  
    -   IIS 网站  
  
    -   虚拟应用程序安装路径  
  
    -   虚拟应用程序名称  
  
-   用于 AMT 和带外管理的下列对象：  
  
    -   基于 AMT 的计算机的 FQDN  
  
    -   基于 AMT 的计算机的计算机名  
  
    -   域 NetBIOS 名称  
  
    -   无线配置文件名称和 SSID  
  
    -   受信任的根证书颁发机构的名称  
  
    -   证书颁发机构 \(CA\) 的名称和模板名称  
  
    -   IDE 重定向映像文件的文件名和路径  
  
    -   AMT 数据存储的内容  
  
-   启动媒体 .ISO 文件名  
  
##  <a name="BKMK_OtherCharLimitations"></a> 其他限制  
 下面是针对支持的字符集和语言版本的其他限制：  
  
-   [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不支持更改站点服务器计算机的区域设置。  
  
-   企业证书颁发机构 \(CA\) 不支持使用双字节字符集 \(DBCS\) 的客户端计算机名称。 可以使用的客户端计算机名称受到 IA5 字符集的 PKI 限制的制约。 此外，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不支持使用 DBCS 的 CA 名称或使用者名称值。  
  
##  <a name="BKMK_LangNonLocalize"></a> 未本地化的 Configuration Manager 对象  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 数据库对于它存储的大部分对象都支持 Unicode，而且，它会尽可能使用与计算机的区域设置匹配的操作系统语言来显示此信息。 若要使客户端界面或 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台以计算机的操作系统语言来显示信息，计算机的区域设置必须匹配你在站点中安装的客户端或服务器语言。  
  
 但是，有几个 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 对象不支持 Unicode，而且它们使用 ASCII 存储在数据库中，或者它们具有其他语言限制。 此信息始终使用 ASCII 字符集或者在创建对象时使用的语言来显示。  
  
## 请参阅  
 [System Center Configuration Manager 的站点和层级结构基础结构技术参考](../LocTest/Site-and-hierarchy-infrastructure-technical-reference-for-System-Center-Configuration-Manager.md)
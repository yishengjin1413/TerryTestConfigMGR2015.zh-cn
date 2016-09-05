---
title: "对 System Center Configuration Manager 的 Active Directory 域的支持"
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
ms.assetid: 8c5a13f8-42d5-4898-b7b6-e594dae8b335
caps.latest.revision: 7
caps.handback.revision: 4
translationtype: Human Translation
---
# 对 System Center Configuration Manager 的 Active Directory 域的支持
所有 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 站点系统必须均为受支持的 Windows Active Directory 域的成员。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端计算机可以是域成员，也可以是工作组成员。  
  
 **要求和限制：**  
  
-   域成员关系适用于在外围网络（也称为 DMZ、外围安全区域和外围子网）中支持基于 Internet 的客户端管理的站点系统。  
  
-   不支持对承载站点系统角色的计算机进行以下更改：  
  
    -   域成员身份  
  
    -   域名  
  
    -   计算机名称  
  
 进行这些更改之前，必须卸载站点系统角色（若为站点服务器，则包括站点）。  
  
 **支持具有以下域功能级别的域：**  
  
-   Windows Server 2008 R2  
  
-   Windows Server 2012  
  
-   Windows Server 2012 R2  
  
##  <a name="bkmk_Disjoint"></a> 非连续命名空间  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 支持在具有非连续命名空间的域中安装站点系统和客户端。  
  
 在非连续命名空间方案中，一台计算机的主域名系统 \(DNS\) 后缀与该计算机所在的 Active Directory DNS 域名不匹配。 使用不匹配的主 DNS 后缀的计算机是非连续的。 如果域控制器的 NetBIOS 域名与 Active Directory DNS 域名不匹配，则会产生另一种非连续命名空间方案。  
  
 下表标识了非连续命名空间受支持的方案。  
  
|方案|更多信息|  
|--------|----------|  
|**方案 1：**<br /><br /> 域控制器的主 DNS 后缀与 Active Directory DNS 域名不同。 是域成员的计算机可以是非连续的或连续的。|在此方案中，域控制器的主 DNS 后缀与 Active Directory DNS 域名不同。 在此方案中，域控制器是非连续的。 是域成员的计算机（例如站点服务器和计算机），可以具有与域控制器的主 DNS 后缀匹配或与 Active Directory DNS 域名匹配的主 DNS 后缀。|  
|**方案 2：**<br /><br /> Active Directory 域中的成员计算机是非连续的，即使域控制器是连续的。|在此方案中，安装站点系统的成员计算机的主 DNS 后缀与 Active Directory DNS 域名不同，即使域控制器的主 DNS 后缀与 Active Directory DNS 域名相同。 在此方案中，你有一个连续的域控制器，和一台非连续的成员计算机。 正在运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端的成员计算机可以具有与非连续站点系统服务器的主 DNS 后缀匹配或与 Active Directory DNS 域名匹配的主 DNS 后缀。|  
  
 若要允许计算机访问非连续域控制器，则必须更改域对象容器上的 **msDS\-AllowedDNSSuffixes** Active Directory 属性。 你必须将两个 DNS 后缀都添加到该属性。  
  
 此外，若要确保 DNS 后缀搜索列表包含在组织内部署的所有 DNS 命名空间，必须在非连续域中配置每台计算机的搜索列表。 包括命名空间列表、域控制器的主 DNS 后缀、DNS 域名以及 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 可能与其进行互操作的其他服务器的任何其他命名空间。 可以使用组策略管理控制台来配置“域名系统 \(DNS\) 后缀搜索”列表。  
  
> [!IMPORTANT]  
>  引用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的计算机时，使用其主 DNS 后缀输入该计算机。 此后缀应与在 Active Directory 域中注册为 **dnsHostName** 属性的完全限定域名相匹配和与该系统关联的服务主体名称相匹配。  
  
##  <a name="bkmk_SLD"></a> 单标签域  
 在满足以下条件时，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 支持单标签域中的站点系统和客户端：  
  
-   Active Directory 域服务中的单标签域必须使用具有有效顶级域的非连续 DNS 命名空间配置。  
  
     **例如：**Contoso 的单标签域配置为在 contoso.com 的 DNS 中具有非连续命名空间。 因此，当你在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中为 Contoso 域中的计算机指定 DNS 后缀时，你指定 Contoso.com 而不是 Contoso。  
  
-   系统上下文中的站点服务器之间的 DCOM 连接必须使用 Kerberos 身份验证成功完成。  
  
## 请参阅  
 [System Center Configuration Manager 支持的配置](../LocTest/Supported-configurations-for-System-Center-Configuration-Manager.md)
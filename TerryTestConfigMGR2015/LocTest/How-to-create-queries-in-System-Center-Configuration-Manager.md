---
title: "如何在 System Center Configuration Manager 中创建查询"
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
ms.assetid: 868049d3-3209-47ec-b34a-9cc26941893a
caps.latest.revision: 5
caps.handback.revision: 4
---
# 如何在 System Center Configuration Manager 中创建查询
使用本主题中的下列部分来帮助你在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中创建或导入查询。  
  
-   [如何创建查询](#BKMK_Create)  
  
-   [如何导入查询](#BKMK_Import)  
  
-   [WQL 查询示例](#BKMK_Example)  
  
##  <a name="BKMK_Create"></a> 如何创建查询  
 使用此过程可帮助你在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中创建查询。  
  
#### 若要创建查询  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“监视”。  
  
2.  在“监视”工作区中，单击“查询”，然后，在“主页”选项卡中，在“创建”组中单击“创建查询”。  
  
3.  在“创建查询向导”的“常规”选项卡中，为查询指定一个唯一的名称和可选备注。  
  
4.  如果想要将现有查询导入为新查询的基础，请单击“导入查询语句”，然后在“浏览查询”对话框中，选择要导入的现有查询，然后单击“确定”。  
  
5.  在“对象类型”列表中选择希望查询返回的对象类型。 下表描述了可以搜索的一些对象类型的示例：  
  
    |对象类型|描述|  
    |----------|--------|  
    |**系统资源**|用于搜索典型的系统属性，例如设备的 NetBIOS 名称、客户端版本、客户端 IP 地址和 Active Directory 域服务信息。|  
    |**用户资源**|用于搜索典型的用户信息，例如用户名、用户组名称和安全组名称。|  
    |**部署**|用于搜索部署的典型属性，例如部署名称、计划和部署到的集合。|  
  
6.  单击“编辑查询语句”以打开 *\<Query Name\>*“语句属性”对话框。  
  
7.  在 *\<Query Name\>*“语句属性”对话框的“常规”选项卡中，指定此查询返回的属性和显示方式。 单击“新建”图标以添加新属性。 还可以单击“显示查询语言”直接以 WMI 查询语言 \(WQL\) 输入或编辑查询。 有关 WMI 查询的示例，请参阅本主题中的 [WQL 查询示例](#BKMK_Example) 部分。  
  
    > [!TIP]  
    >  可以使用下列 MSDN 参考文档，以帮助构造自己的 WQL 查询：  
    >   
    >  -   [WQL \(SQL for WMI\)](http://go.microsoft.com/fwlink/p/?LinkId=256653)  
    > -   [WHERE 子句](http://go.microsoft.com/fwlink/p/?LinkId=256654)  
    > -   [WQL 运算符：](http://go.microsoft.com/fwlink/p/?LinkId=256655)  
  
8.  在 *\<Query Name\>*“语句属性”对话框框中的“条件”选项卡中，指定用于优化查询结果的条件。 例如，可以只返回查询结果中包含 **XYZ** 站点代码的资源。 可以配置多个查询条件。  
  
    > [!IMPORTANT]  
    >  如果创建的查询中未包含任何条件，查询将在“所有系统”集合中返回所有设备。  
  
9. 在 *\<Query Name\>*“语句属性”对话框中的“联接”选项卡中，可以将两个不同属性的数据组合到查询结果中。 虽然在为查询结果选择不同的属性时，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 会自动创建查询联接，但“联接”选项卡提供了更多高级选项。 下表中列出了 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] 支持的属性类：  
  
    |联接类型|描述|  
    |----------|--------|  
    |内部|只显示匹配的结果 – 始终由自动创建的联接使用。|  
    |左|显示基属性的所有结果，同时，只显示联接属性的匹配结果。|  
    |右|对于联接属性显示所有结果，而对于基属性只显示匹配结果。|  
    |完整|对于基属性和联接属性均显示所有结果。|  
  
     有关联接运算使用方法的详细信息，请参阅 SQL Server 文档。  
  
10. 单击“确定”关闭 *\<Query Name\>*“语句属性”对话框。  
  
11. 在“创建查询向导”中的“常规”选项卡中，指定是否将此查询的结果不限制于一个集合成员，而限制于指定集合的成员，或每次运行查询时提示输入集合。  
  
12. 完成向导以创建查询。 新查询显示在“监视”工作区中的“查询”节点中。  
  
##  <a name="BKMK_Import"></a> 如何导入查询  
 使用此过程来帮助你将查询导入到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中。 有关查询导出方法的信息，请参阅 [如何在 System Center Configuration Manager 中管理查询](../LocTest/How-to-manage-queries-in-System-Center-Configuration-Manager.md)。  
  
#### 若要导入查询  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“监视”。  
  
2.  在“监视”工作区中，单击“查询”，然后，在“主页”选项卡中，在“创建”组中单击“导入对象”。  
  
3.  在“导入对象向导”中的“MOF 文件名”页面中，请单击“浏览”以选择包含要导入的查询的托管对象格式 \(MOF\) 文件。  
  
4.  查看关于要导入的查询的信息，然后完向导。 新查询显示在“监视”工作区中的“查询”节点中。  
  
##  <a name="BKMK_Example"></a> WQL 查询示例  
 本部分包含可在你的层次结构中使用或因其他目的修改的 WMI 查询示例。 要使用这些查询，请单击“查询语句属性”对话框中的“显示查询语言”，然后复制查询并将其粘贴到“查询语句”字段中。  
  
> [!TIP]  
>  使用 **%** 通配符来表示任何字符串。 例如，**%Visio%** 返回 Microsoft Office Visio 2010。  
  
### 运行 Windows 7 的计算机  
 使用以下查询返回运行 Windows 7 的所有计算机的 NetBIOS 名称和操作系统版本。  
  
> [!TIP]  
>  若要返回运行 Windows Server 2008 R2 的计算机，请将 **%Workstation 6.1%** 改为 **%Server 6.1%**。  
  
```  
select SMS_R_System.NetbiosName, SMS_R_System.OperatingSystemNameandVersion from SMS_R_System where SMS_R_System.OperatingSystemNameandVersion like "%Workstation 6.1%"  
```  
  
### 安装特定软件包的计算机  
 使用以下查询来返回安装了特定软件包的所有计算机的 NetBIOS 名称和软件包名称。 本示例显示了已安装某个版本的 Microsoft Visio 的所有计算机。 用想要查询的软件包代替 **%Visio%**。  
  
> [!TIP]  
>  此查询通过使用 Windows 控制面板中程序列表中显示的名称来搜索软件包。  
  
```  
select SMS_R_System.NetbiosName, SMS_G_System_ADD_REMOVE_PROGRAMS.DisplayName from SMS_R_System inner join SMS_G_System_ADD_REMOVE_PROGRAMS on SMS_G_System_ADD_REMOVE_PROGRAMS.ResourceId = SMS_R_System.ResourceId where SMS_G_System_ADD_REMOVE_PROGRAMS.DisplayName like "%Visio%"  
```  
  
### 特定 Active Directory 域服务组织单位 \(OU\) 中的计算机  
 使用以下查询来返回指定 OU 中所有计算机的 NetBIOS 名称和 OU 名称。 用想要查询的 OU 的名称代替文本 **OU Name**。  
  
```  
select SMS_R_System.NetbiosName, SMS_R_System.SystemOUName from SMS_R_System where SMS_R_System.SystemOUName = "OU Name"  
```  
  
### 具有特定 NetBIOS 名称的计算机  
 使用以下查询来返回以指定字符串开头的所有计算机的 NetBIOS 名称。 在本例中，查询会返回 NetBIOS 名称以 **ABC** 开头的所有计算机。  
  
```  
select SMS_R_System.NetbiosName from SMS_R_System where SMS_R_System.NetbiosName like "ABC%"  
```  
  
###  <a name="BKMK_DeviceType"></a> 特定类型的设备  
 设备类型存储在资源类 **sms\_r\_system** 和属性名称 **AgentEdition** 下的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 数据库中。 使用以下查询来检索与指定设备类型的代理版本匹配的设备：  
  
```  
Select SMS_R_System.ClientEdition from SMS_R_System where SMS_R_System.ClientEdition = <Device ID>  
```  
  
 为 *\<Device ID\>* 选择下列值之一：  
  
|设备类型|AgentEdition 的值|  
|----------|---------------------|  
|Windows 台式机或便携式计算机|0|  
|Windows 基于 ARM 的设备（运行 Windows RT）|1|  
|Windows Mobile 6.5|2|  
|Nokia Symbian|3|  
|Windows Phone|4|  
|Mac 计算机|5|  
|Windows CE|6|  
|Windows Embedded|7|  
|iOS|8|  
|iPad|9|  
|iPod Touch|10|  
|Android|11|  
|Intel 片上系统|12|  
|UNIX 和 Linux 服务器|13|  
  
 例如，如果想要查询只返回 Mac 计算机，请使用以下查询：  
  
```  
Select SMS_R_System.ClientEdition from SMS_R_System where SMS_R_System.ClientEdition = 5  
```  
  
## 请参阅  
 [System Center Configuration Manager 中查询的操作和维护](../LocTest/Operations-and-maintenance-for-queries-in-System-Center-Configuration-Manager.md)
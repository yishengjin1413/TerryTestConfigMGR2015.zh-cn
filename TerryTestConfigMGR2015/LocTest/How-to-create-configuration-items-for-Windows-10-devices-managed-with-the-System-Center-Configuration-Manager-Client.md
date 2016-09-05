---
title: "如何为使用 System Center Configuration Manager 客户端管理的 Windows 10 设备创建配置项目"
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
ms.assetid: 14226fbe-dd07-4432-910b-130790624a4e
caps.latest.revision: 17
caps.handback.revision: 11
---
# 如何为使用 System Center Configuration Manager 客户端管理的 Windows 10 设备创建配置项目
使用 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]“Windows 10”配置项目可为由 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端管理的 Windows 10 计算机管理设置。  
  
> [!IMPORTANT]  
>  在此版本中，当创建了“密码”设置作为“Windows 10”类型的配置项目的一部分（对于使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端管理的设备）时，如果该设置尚不存在，或是在 Windows 10 设备上尚未配置，则会错误地评估为符合。  
>   
>  作为解决方法，在为这些设备创建设置时，请确保在创建配置项目向导的设置页上选择“修正非符合性设置”。 此外，当部署的配置基线包括密码设置的 Windows 10 配置项目时，请在“部署配置基线”对话框中选择“在支持时修正非符合性规则”。 通过使用此解决方法，设置会受到监视，并在发现它不符合要求时进行修正。 修正之后，设置会正确报告为“符合”（除非遇到问题，在这种情况下它报告“错误”）。  
  
### 创建 Windows 10 配置项目  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”。  
  
2.  在“资产和符合性”工作区中，展开“符合性设置”，然后单击“配置项目”。  
  
3.  在“主页”选项卡上的“创建”组中，单击“创建配置项目”。  
  
4.  在“创建配置项目向导”的“常规”页面上，指定配置项目的名称和可选描述。  
  
5.  在“指定要创建的配置项目的类型”下，选择“Windows 10”。  
  
6.  如果创建并分配类别以帮助在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中搜索和筛选配置项目，请单击“类别”。  
  
7.  在向导的“支持的平台”页上，选择将评估配置项目的特定 Windows 10 平台。  
  
8.  在向导的“设备设置”页面上，选择要配置的设置组。 请参阅本主题中的 [Windows 10 配置项目设置参考](#BKMK_Ref) 以了解详细信息，然后单击“下一步”。  
  
    > [!TIP]  
    >  如果所需设置未列出，请选中“配置默认设置组以外的其他设置”复选框。  
  
9. 在每个设置页面上，配置所需设置，以及是否要在它们在设备上不符合要求时修正它们（如果支持这样做）。  
  
10. 对于每个设置组，还可以配置在发现配置项目不符合要求时将要报告的严重性：  
  
    -   **不报告** \- 对于 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 报表，不符合此符合性规则的设备不报告故障严重性。  
  
    -   **信息** \- 对于 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 报表，不符合此符合性规则的设备将报告“信息”这一故障严重性。  
  
    -   **警告** \- 对于 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 报表，不符合此符合性规则的设备将报告“警告”这一故障严重性。  
  
    -   **严重** \- 对于 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 报表，不符合此符合性规则的设备将报告“严重”这一故障严重性。  
  
    -   **事件严重** \- 对于 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 报表，不符合此符合性规则的设备将报告“严重”这一故障严重性。 应用程序事件日志中也会以 Windows 事件的形式记录此严重性级别。  
  
11. 在向导的“平台适用性”页面上，查看任何与先前选择的受支持平台不兼容的设置。 你可以返回并删除这些设置，也可以继续。  
  
    > [!TIP]  
    >  不会对不受支持的设置评估符合性。  
  
12. 完成向导。  
  
 可以在“资产和符合性”工作区的“配置项目”节点中查看新配置项目。  
  
##  <a name="BKMK_Ref"></a> Windows 10 配置项目设置参考  
  
### Password  
  
|设置|详细信息|  
|--------|----------|  
|**设备上需要密码设置**|支持的设备上需要密码。|  
|**最短密码长度（字符）**|密码的最短长度（以字符为单位）。|  
|**密码过期天数**|必须更改密码前的天数。|  
|**记住的密码数**|防止重复使用以前的密码。|  
|**擦除设备前的失败登录尝试次数**|如果登录失败达到此次数，则擦除设备。|  
|**锁定移动设备前的空闲时间**|指定设备在自动锁定之前必须处于非活动状态的分钟数。|  
|**密码复杂性**|选择是否可以指定一个如“1234”的 PIN，或是否必须提供一个强密码。|  
  
###  <a name="BKMK_Device"></a> 设备  
  
|设置名|详细信息|  
|---------|----------|  
|**蓝牙**|允许在设备上使用蓝牙功能。|  
  
### 云  
  
|设置名|详细信息|  
|---------|----------|  
|**设置同步**|允许设备之间的设置同步。|  
|**凭据同步**|允许设备之间的凭据同步。|  
|**通过按流量计费的连接进行设置同步**|允许在 Internet 连接按流量计费时进行设置同步。|  
  
### 漫游  
  
|设置名|详细信息|  
|---------|----------|  
|**数据漫游**|允许在访问数据时进行网络之间的漫游。|  
  
### 加密  
  
|设置名|详细信息|  
|---------|----------|  
|**设备上的文件加密**|要求对设备上的文件进行加密。|  
  
### 系统安全  
  
|设置名|详细信息|  
|---------|----------|  
|**用户帐户控制**|配置设备上的 Windows 用户帐户控制的工作方式。 例如，可以禁用它，或设置它通知你时所处的级别。|  
|**网络防火墙**|启用或禁用 Windows 防火墙。|  
|**SmartScreen**|启用或禁用 Windows 智能屏幕。|  
|**病毒保护**|要求必须安装并配置防病毒软件。|  
|**病毒保护签名为最新**|要求设备上的防病毒软件的签名文件必须保持最新状态。|  
  
### 企业数据保护  
 管理 Windows 10 设备时，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将能够为 Windows 10 企业数据保护 \(EDP\) 创建和部署配置项目。 EDP 可帮助限制并\/或以警报方式告知你公司数据共享操作。[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] EDP 配置项目将管理受 EDP 保护的应用、企业网络位置、保护级别和加密设置的列表。 若要选择加入以接收 Windows 的预览版本，请考虑加入 [Windows 预览体验计划](https://insider.windows.com/)。  
  
> [!NOTE]  
>  企业数据保护当前正通过大量企业客户进行测试，将很快可用于 Windows 预览体验。  
  
## 请参阅  
 [为使用 System Center Configuration Manager 客户端管理的设备配置项目](../LocTest/Configuration-items-for-devices-managed-with-the-System-Center-Configuration-Manager-client.md)
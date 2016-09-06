---
title: "System Center Configuration Manager 中的软件计数"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-app
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 8e071ea6-aba7-47be-97d7-63dcbb61d1d9
caps.latest.revision: 9
caps.handback.revision: 6
author: barlanmsft
translationtype: Human Translation
---
# System Center Configuration Manager 中的软件计数
本主题包含使用 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 软件计数时，可能执行的所有操作的参考。 有关如何使用软件计数的示例方案，请参阅[在 System Center Configuration Manager 中使用软件计数监视应用使用情况](../LocTest/Monitor-app-usage-with-software-metering-in-System-Center-Configuration-Manager.md)。  
  
 本主题包含以下各节：  
  
-   [软件计数的先决条件](#BKMK_Pre)  
  
-   [配置软件计数](#BKMK_Config)  
  
-   [创建软件计数规则](#BKMK_Create)  
  
-   [配置自动软件计数规则](#BKMK_Auto)  
  
-   [管理软件计数规则](#BKMK_Manage)  
  
-   [监视软件计数](#BKMK_Monitor)  
  
-   [软件计数的安全和隐私](#BKMK_Sec)  
  
##  <a name="BKMK_Pre"></a> 软件计数的先决条件  
 软件计数没有外部依赖关系，仅在产品内部有依赖关系。  
  
> [!IMPORTANT]  
>  软件计数用于监视文件名以“.exe”结尾的 Windows 电脑桌面应用。 软件计数不监视现代 Windows 应用（例如 Windows 8 曾使用的应用）。  
  
### Configuration Manager 依赖关系  
  
|依赖关系|更多信息|  
|----------|----------|  
|软件计数的客户端设置。|若要使用软件计数，必须启用客户端设置“在客户端上启用软件计数”，并将该设置部署到计算机。 可以将软件计数设置部署到层次结构中的所有计算机，也可以将自定义设置部署计算机组。 有关详细信息，请参阅 [配置软件计数](#BKMK_Config)。|  
|Reporting Services 点。|在查看软件计数报表前，必须先配置一个 Reporting Services 点。 有关详细信息，请参阅[System Center Configuration Manager 中的报表](../LocTest/Reporting-in-System-Center-Configuration-Manager.md)。|  
  
##  <a name="BKMK_Config"></a> 配置软件计数  
 此过程为软件计数配置默认客户端设置，并应用于层次结构中的所有计算机。 如果希望这些设置仅应用于某些计算机，请创建一个自定义设备客户端设置，并将其部署到包含要使用软件计数的计算机的集合。 有关如何创建自定义设备设置的详细信息，请参阅 [如何在 System Center Configuration Manager 中配置客户端设置](../LocTest/How-to-configure-client-settings-in-System-Center-Configuration-Manager.md)。  
  
#### 若要配置软件计数  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“管理”\>“客户端设置”\>“默认客户端设置”。  
  
2.  在“主页”选项卡上的“属性”组中，单击“属性”。  
  
3.  在“默认设置”对话框中，单击“软件计数”。  
  
4.  在“设备设置”列表中，配置以下各项：  
  
    -   “在客户端上启用软件计数”：选择“True”以启用软件计数。  
  
    -   “计划数据收集”：配置从客户端计算机收集软件计数数据的频率。 使用默认值每“7 天”或单击“计划”来指定自定义计划。  
  
5.  单击“确定”来关闭“默认设置”对话框。  
  
 当客户端计算机下一次下载客户端策略时，将使用这些设置进行配置。 要为单个客户端启动策略检索，请参阅 [如何在 System Center Configuration Manager 中管理客户端](../LocTest/How-to-manage-clients-in-System-Center-Configuration-Manager.md)。  
  
##  <a name="BKMK_Create"></a> 创建软件计数规则  
 使用“创建软件计数规则向导”为你的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点创建新的软件计数规则。  
  
#### 如何创建软件计数规则  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”。  
  
2.  在“资产和符合性”工作区中，单击“软件计数”。  
  
3.  在“主页”选项卡的“创建”组中，单击“创建软件计数规则”。  
  
4.  在“创建软件计数规则向导”的“常规”页上，指定下列信息：  
  
    -   **名称** \- 软件计数规则的名称。 名称应该唯一并且是描述性的。  
  
        > [!NOTE]  
        >  如果规则中包含的文件名不同，软件计数规则可共享相同的名称。  
  
    -   **文件名** \- 要计数的程序文件的名称。 可以单击“浏览”以显示“打开”对话框，然后从中选择要使用的程序文件。  
  
        > [!NOTE]  
        >  如果在“文件名”框中键入可执行文件名，则不会执行任何检查来确定此文件是否存在或是否包含必需的标头信息。 如果可能，请单击“浏览”，然后选择要计数的可执行文件。  
        >   
        >  不允许在文件名中使用通配符。  
        >   
        >  如果为“原始文件名”指定了值，则此框是可选的。  
  
    -   **原始文件名** \- 要计数的可执行文件的名称。  此名称与文件头中的信息（而不是文件名本身）相匹配，这在已重命名可执行文件但是你要按原始名称计数时非常有用。  
  
        > [!NOTE]  
        >  不允许在原始文件名中使用通配符。  
        >   
        >  如果为“文件名”指定了值，则此框是可选的。  
  
    -   **版本** \- 要计数的可执行文件的版本。 您可以使用通配符 \(\*\) 表示任何字符串，也可以使用通配符 \(?\) 表示任何单个字符。 如果要计数可执行文件的所有版本，请使用默认值 \(\*\)。  
  
    -   **语言** \- 要计数的可执行文件的语言。 默认值为正在使用的操作系统的当前区域设置。 如果你通过单击“浏览”按钮来选择要计数的可执行文件，则当文件标头中存在语言信息，系统会自动填充此框。 要对文件的所有语言版本计数，请在下拉列表中选择“任何”。  
  
    -   **描述** \- 软件计数规则的可选描述。  
  
    -   “将此软件计数规则应用于以下客户端”– 选择你是要将此软件计数规则应用到层次结构中的所有客户端还是分配给“站点”列表中指定站点的客户端。  
  
5.  要继续，请单击“下一步”。  
  
6.  查看并确认设置，然后完成向导以创建软件计数规则。 新的软件计数规则将显示在“资产和符合性”工作区中的“软件计数”节点下。  
  
##  <a name="BKMK_Auto"></a> 配置自动软件计数规则  
 可在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中将软件计数配置为从站点数据库中保存的最新使用率清单数据自动生成禁用的软件计数规则。 你可以配置此清单数据，以便仅针对在指定百分比的计算机上使用的应用程序创建计数规则。 您还可以指定允许在站点上自动生成的软件计数规则的最大数量。  
  
> [!NOTE]  
>  默认情况下，自动创建的软件计数规则处于禁用状态。 在可以根据这些规则开始收集使用数据之前，必须启用这些规则。  
  
#### 配置自动软件计数规则生成  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”。  
  
2.  在“资产和符合性”工作区中，单击“软件计数”，然后在“主页”选项卡上的“设置”组中，单击“软件计数属性”。  
  
3.  在“软件计数属性”对话框中，配置以下各项：  
  
    -   **数据保留期\(天\)** \- 指定软件计数规则生成的数据保存在站点数据库中的时间长度。 默认值为 **90** 天。  
  
    -   启用“根据最新使用率清单数据自动创建禁用的计数规则”选项。  
  
    -   **指定在自动创建软件计数规则前层次结构中必须使用程序的计算机的百分比** \- 默认值为“10”%。  
  
    -   **指定在禁用自动创建规则前层次结构中必须超出的软件计数规则数** \- 默认值为 **100** 条规则。  
  
4.  单击“确定”以关闭“软件计数属性”对话框。  
  
##  <a name="BKMK_Manage"></a> 管理软件计数规则  
 在“资产和符合性”工作区中，选择“软件计数”，然后选择要管理的软件计数规则和管理任务。  
  
 使用下表以详细了解可能需要一些信息才能让你选择的管理任务。  
  
|管理任务|详细信息|更多信息|  
|----------|----------|----------|  
|**启用**<br /><br /> **禁用**|启用或禁用软件计数规则。 此设置根据客户端设置中“客户端策略”部分的“客户端策略轮询间隔”（默认值为每隔 60 分钟）下载到客户端计算机。|[如何在 System Center Configuration Manager 中配置客户端设置](../LocTest/How-to-configure-client-settings-in-System-Center-Configuration-Manager.md)|  
  
##  <a name="BKMK_Monitor"></a> 监视软件计数  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的软件计数包括多种内置报表，使用这些报表可监视有关软件计数操作的信息。 这些报表的报表类别为“软件计数”。  
  
 有关如何配置 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的报告的详细信息，请参阅 [System Center Configuration Manager 中的报表](../LocTest/Reporting-in-System-Center-Configuration-Manager.md)。  
  
 此外，你还可以根据 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 数据库中存储的数据根据软件计数创建查询和集合。  
  
 有关 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中集合的详细信息，请参阅[System Center Configuration Manager 中集合的技术参考](../LocTest/Collections-technical-reference-for-System-Center-Configuration-Manager.md)。  
  
 有关 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中查询的详细信息，请参阅 [System Center Configuration Manager 中查询的技术参考](../LocTest/Queries-technical-reference-for-System-Center-Configuration-Manager.md)。  
  
##  <a name="BKMK_Sec"></a> 软件计数的安全和隐私  
  
### 软件计数的安全问题  
 攻击者可能会向 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 发送无效的软件计数信息，即使禁用了软件计数客户端设置，管理点也会接受该信息。 这可能会导致整个层次结构中复制大量计数规则在，进而导致拒绝网络上的服务和对 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点的服务。  
  
 由于攻击者可以创建无效的软件计数数据，因此请勿认为软件计数信息具有权威性。  
  
 默认情况下，客户端设置中启用了软件计数。  
  
###  <a name="BKMK_Privacy_Metering"></a> 软件计数的隐私信息  
 软件计数监视客户端计算机上应用程序的使用情况。 默认情况下，软件计数处于启用状态。 您必须配置要计数的应用程序。 计数信息存储在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 数据库中。 该信息在传输到管理点的过程中加密，但不会存储在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 数据库的加密表单中。  
  
 在被站点维护任务“删除过期的软件计数数据”（每隔五天）和“删除过期的软件计数摘要数据”（每隔 270 天）删除之前，此信息将保留在数据库中。 可以配置删除间隔。 计数信息不会发送到 Microsoft。  
  
 在配置软件计数前，请考虑隐私要求。  
  
## 请参阅  
 [System Center Configuration Manager 中应用程序管理的技术参考](../LocTest/Application-management-technical-reference-for-System-Center-Configuration-Manager.md)
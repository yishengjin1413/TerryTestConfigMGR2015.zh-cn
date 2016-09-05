---
title: "How to extend hardware inventory in System Center Configuration Manager"
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
ms.assetid: d5bfab4f-c55e-4545-877c-5c8db8bc1891
caps.latest.revision: 10
caps.handback.revision: 10
author: barlanmsft
translationtype: Human Translation
---
# How to extend hardware inventory in System Center Configuration Manager
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 硬件清单通过使用 Windows Management Instrumentation (WMI) 从 Windows PC 读取有关设备的信息。 WMI 是基于 Web 的企业管理 (WBEM) 的 Microsoft 实现，它是用于访问企业环境中管理信息的行业标准。 在以前版本的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)], ，您可以通过修改站点服务器上的文件 sms_def.mof 扩展硬件清单。 此文件包含可以通过阅读的 WMI 类的列表 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 硬件清单。 如果编辑此文件，则你可以启用和禁用现有类，还能将新类创建到清单。  
  
 Configuration.mof 文件用于定义要通过客户端上的硬件清单列出清单的数据类，与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 2012 相比并无变化。 你可以创建数据类，以列出客户端系统上存在的现有或自定义 WMI 存储库数据类或注册表项的清单。  
  
 Configuration.mof 文件还定义并注册 WMI 提供程序用于访问在硬件清单期间的设备信息。 通过注册提供程序，可以定义要使用的提供程序类型和提供程序支持的类。  
  
 当 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端请求策略，例如，其标准的客户端策略轮询间隔期间，Configuration.mof 将被附加到的策略正文。 然后下载此文件并对其进行了编译的客户端。 当添加、 修改或删除 Configuration.mof 文件中的数据类时，客户端将自动编译对清单相关的数据类进行这些更改。 不需要执行进一步的操作来列出 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端上新数据类或已修改数据类的清单。 此文件在主站点服务器上的位置是 **<CMInstallLocation\>\Inboxes\clifiles.src\hinv\\**。  
  
 在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]中，你不再像在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 2007 中一样编辑 sms_def.mof 文件。 相反，你可以启用和禁用 WMI 类，并通过使用客户端设置来添加硬件清单将收集的新类。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 提供了以下方法来扩展硬件清单。  
  
> [!NOTE]  
>  如果你手动更改了 Configuration.mof 文件以添加自定义清单类，则在你更新到 1602 版本时，这些更改将被覆盖。 若要在更新后继续使用自定义类，你必须在更新到 1602 后将这些类添加到 Configuration.mof 文件的“已添加扩展”部分中。  
> 但是，请勿修改此部分上的任何内容，因为这些部分保留供 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 修改。 自定义 Configuration.mof 的备份位于：  
> **<CM Install dir\>\data\hinvarchive\\**。  
  
|方法|更多信息|  
|------------|----------------------|  
|启用或禁用现有的清单类|您可以启用或禁用使用的默认清单类 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 也可以创建自定义客户端设置，允许您从指定的集合的客户端收集不同的硬件清单类。 有关详细信息，请参阅本主题中的 [若要启用或禁用现有清单类](#BKMK_Enable) 过程。|  
|添加一个新的清单类|您可以从另一台设备的 WMI 命名空间添加一个新的清单类。 有关详细信息，请参阅本主题中的 [若要添加新的清单类](#BKMK_Add) 过程。|  
|导入和导出硬件清单类|你可以从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台导入和导出包含清单类的托管对象格式 (MOF) 文件。 有关详细信息，请参阅本主题中的 [若要导入硬件清单类](#BKMK_Import) 和 [若要导出硬件清单类](#BKMK_Export) 过程。|  
|创建 NOIDMIF 文件|使用 NOIDMIF 文件来收集有关不能通过已列出清单的客户端设备的信息 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]。 例如，您可能想要收集设备资产编号的信息仅作为在设备上的标签存在。 NOIDMIF 清单是自动与收集从客户端设备相关联。 有关详情，请参阅本主题中的 [若要创建 NOIDMIF 文件](#BKMK_NOIDMIF) 。|  
|创建 IDMIF 文件|使用 IDMIF 文件来收集有关您的组织中将不与关联的资产的信息 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端，例如，投影仪、 复印机和网络打印机。 有关详情，请参阅本主题中的 [若要创建 IDMIF 文件](#BKMK_IDMIF) 。|  
  
## 扩展硬件清单的过程  
 使用下列过程来扩展硬件清单，如前面的表中所述。  
  
 这些过程帮助您配置硬件清单的默认客户端设置和它们适用于层次结构中的所有客户端。 如果你希望这些设置仅应用于某些客户端，请创建自定义客户端设备设置，并将它分配给包含要列出清单的设备的集合。 有关如何创建自定义客户端设置的详细信息，请参阅 [How to configure client settings in System Center Configuration Manager](../LocTest/How-to-configure-client-settings-in-System-Center-Configuration-Manager.md)。  
  
###  <a name="BKMK_Enable"></a> 若要启用或禁用现有清单类  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击 **管理**。  
  
2.  在“管理”  工作区中，单击“客户端设置” 。  
  
3.  单击“默认客户端设置” 。  
  
4.  在“主页”  选项卡上的“属性”  组中，单击“属性” 。  
  
5.  在 **默认客户端设置** 对话框中，单击 **硬件清单**。  
  
6.  在 **设备设置** 列表中，单击 **设置类**。  
  
7.  在 **硬件清单类** 对话框框中，选中或清除的类和类属性，以按照硬件清单收集。 您可以展开以选择或清除使该类中的各个属性的类。 使用 **清单类搜索** 字段以单个类中搜索。  
  
    > [!IMPORTANT]  
    >  当您添加到的新类 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 硬件清单收集和发送到站点服务器的清单文件的大小将增加。 这可能会产生负面影响网络性能和 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点。 启用您想要收集的清单类。  
  
8.  单击 **确定** 以保存所做的更改并关闭 **硬件清单类** 对话框。  
  
###  <a name="BKMK_Add"></a> 若要添加一个新的清单类  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击 **管理**。  
  
    > [!IMPORTANT]  
    >  只能从最高级别服务器层次结构中并通过修改默认客户端设置中添加清单类。 当创建自定义设备设置此选项不可用。  
  
2.  在“管理”  工作区中，单击“客户端设置” 。  
  
3.  单击“默认客户端设置” 。  
  
4.  在“主页”  选项卡上的“属性”  组中，单击“属性” 。  
  
5.  在 **默认客户端设置** 对话框中，单击 **硬件清单**。  
  
6.  在 **设备设置** 列表中，单击 **设置类**。  
  
7.  在 **硬件清单类** 对话框中，单击 **添加**。  
  
8.  在 **添加硬件清单类** 对话框中，单击 **连接**。  
  
9. 在 **连接到 Windows Management Instrumentation (WMI)** 对话框框中，指定将用于检索 WMI 类要用于检索这些类的 WMI 命名空间的计算机的名称。 如果您想要检索您指定的 WMI 命名空间下的所有类中，单击 **递归**。 如果您要连接到计算机不是本地计算机，提供有权访问远程计算机上的 WMI 的帐户的登录凭据。  
  
10. 单击“连接” 。  
  
11. 在“添加硬件清单类”  对话框的“清单类”  列表中，选择想要添加到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 硬件清单的 WMI 类。  
  
12. 如果您想要编辑所选的 WMI 类的相关信息，请单击 **编辑**, ，然后在 **类限定符** 对话框框中，提供以下信息：  
  
    -   **显示名称** – 指定友好名称将显示在资源浏览器的类。  
  
    -   **属性** – 指定在 WMI 中的每个属性将显示类的单位。  
  
     此外可以将属性指定为键属性来帮助唯一地标识每个类的实例。 如果类未定义任何键，从客户端报告的类的多个实例只能找到的最新的实例存储在数据库中。  
  
     完成配置属性，请单击 **确定** 关闭 **类限定符** 对话框。  
  
13. 单击确定以关闭 **添加硬件清单类** 对话框。  
  
14. 单击 **确定** 关闭 **硬件清单类** 对话框。  
  
15. 单击“确定”  以关闭“默认客户端设置”  对话框。  
  
###  <a name="BKMK_Import"></a> 若要导入硬件清单类  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击 **管理**。  
  
2.  在“管理”  工作区中，单击“客户端设置” 。  
  
3.  单击“默认客户端设置” 。  
  
    > [!IMPORTANT]  
    >  当您修改默认客户端设置时，只可以导入清单类。 但是，您可以使用自定义客户端设置导入不包含架构更改，例如，更改从现有类的属性的信息 **True** 到 **False**。  
  
4.  在“主页”  选项卡上的“属性”  组中，单击“属性” 。  
  
5.  在 **默认客户端设置** 对话框中，单击 **硬件清单**。  
  
6.  在 **设备设置** 列表中，单击 **设置类**。  
  
7.  在 **硬件清单类** 对话框中，单击 **导入**。  
  
8.  在 **导入** 对话框中，选择托管对象格式 (MOF) 文件您想要导入，然后单击 **确定**。  
  
9. 在 **导入摘要** 对话框框中，检查的项，将导入，然后单击 **导入**。  
  
###  <a name="BKMK_Export"></a> 若要导出硬件清单类  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击 **管理**。  
  
2.  在“管理”  工作区中，单击“客户端设置” 。  
  
3.  单击“默认客户端设置” 。  
  
4.  在“主页”  选项卡上的“属性”  组中，单击“属性” 。  
  
5.  在 **默认客户端设置** 对话框中，单击 **硬件清单**。  
  
6.  在 **设备设置** 列表中，单击 **设置类**。  
  
7.  在 **硬件清单类** 对话框中，单击 **导出**。  
  
    > [!NOTE]  
    >  导出类时，将导出所有当前所选的类。  
  
8.  在“导出”  对话框中，指定想要将类导出到的托管对象格式 (MOF) 文件，然后单击“保存” 。  
  
## 如何使用管理信息文件（MIF 文件）扩展硬件清单  
 使用管理信息格式 (MIF) 文件扩展 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]从客户端收集的硬件清单信息。 在硬件清单过程中，存储在 MIF 文件中的信息被添加到客户端清单报表并存储在站点数据库中，使用站点数据库中数据的方式可以与使用默认客户端清单数据的方式相同。 有两种类型的 MIF 文件，文件 NOIDMIF 和 IDMIF。  
  
> [!IMPORTANT]  
>  您可以从 MIF 文件添加信息之前 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 数据库中，您必须创建或导入为它们的类信息。 有关详细信息，请参阅本主题中的 [若要添加新的清单类](#BKMK_Add) 和 [若要导入硬件清单类](#BKMK_Import) 部分。  
  
###  <a name="BKMK_NOIDMIF"></a> 若要创建 NOIDMIF 文件  
 NOIDMIF 文件可以用于将信息添加到通常不能收集的客户端硬件清单 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 并且与特定客户端设备相关联。 例如，许多公司标记具有资产号码组织中的每台计算机并手动编目这些。 当创建 NOIDMIF 文件时，可以将此信息添加到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 数据库和用于查询和报告。 有关创建 NOIDMIF 文件的信息，请参阅 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] SDK 文档。  
  
> [!IMPORTANT]  
>  当创建 NOIDMIF 文件时，这必须以 ANSI 编码格式保存。 以 utf-8 编码格式保存的 NOIDMIF 文件无法读取由 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]。  
  
 创建 NOIDMIF 文件后，将此存储在文件夹中 *%windir%***\System32\CCM\Inventory\Noidmifs** 每个客户端上的文件夹。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将信息从收集此文件夹中的 NODMIF 文件在下一步计划的硬件清单周期内。  
  
###  <a name="BKMK_IDMIF"></a> 若要创建 IDMIF 文件  
 IDMIF 文件可用于将有关资产的信息添加到通常不能被 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 列出清单并且不与特定客户端设备相关联的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 数据库。 例如，可以使用 IDMIFS 收集有关投影仪、 DVD 播放机、 复印机或不包含其他设备信息 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端。 有关创建 IDMIF 文件的信息，请参阅 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] SDK 文档。  
  
 创建 IDMIF 文件后，将此存储在文件夹中 *%windir%***\System32\CCM\Inventory\Idmifs** 客户端计算机上的文件夹。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将收集信息从该文件在下一步计划的硬件清单周期内。 您必须声明通过添加或将其导入该文件中包含的信息的新类。  
  
## 另请参阅  
 [在 System Center Configuration Manager 中配置硬件清单](../LocTest/Configuring-hardware-inventory-in-System-Center-Configuration-Manager.md)
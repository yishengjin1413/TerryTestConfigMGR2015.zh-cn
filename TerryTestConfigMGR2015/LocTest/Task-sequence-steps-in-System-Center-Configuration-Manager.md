---
title: "System Center Configuration 中的任务序列步骤"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-osd
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 7c888a6f-8e37-4be5-8edb-832b218f266d
caps.latest.revision: 26
caps.handback.revision: 25
translationtype: Human Translation
---
# System Center Configuration 中的任务序列步骤
可将以下任务序列步骤添加到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 任务序列中。 有关编辑任务序列的信息，请参阅 [Edit a task sequence](../LocTest/Manage-task-sequences-to-automate-tasks-in-System-Center-Configuration-Manager.md#BKMK_ModifyTaskSequence)。  
  
-   [应用数据映像任务序列步骤](#BKMK_ApplyDataImage)  
  
-   [应用驱动程序包](#BKMK_ApplyDriverPackage)  
  
-   [应用网络设置步骤](#BKMK_ApplyNetworkSettings)  
  
-   [应用操作系统映像](#BKMK_ApplyOperatingSystemImage)  
  
-   [应用 Windows 设置](#BKMK_ApplyWindowsSettings)  
  
-   [自动应用驱动程序](#BKMK_AutoApplyDrivers)  
  
-   [捕获网络设置](#BKMK_CaptureNetworkSettings)  
  
-   [捕获操作系统映像](#BKMK_CaptureOperatingSystemImage)  
  
-   [捕获用户状态](#BKMK_CaptureUserState)  
  
-   [捕获 Windows 设置](#BKMK_CaptureWindowsSettings)  
  
-   [检查准备情况](#BKMK_CheckReadiness)  
  
-   [连接到网络文件夹](#BKMK_ConnectToNetworkFolder)  
  
-   [将磁盘转换为动态磁盘](#BKMK_ConvertDisktoDynamic)  
  
-   [禁用 BitLocker](#BKMK_DisableBitLocker)  
  
-   [下载包内容](#BKMK_DownloadPackageContent)  
  
-   [启用 BitLocker](#BKMK_EnableBitLocker)  
  
-   [格式化磁盘并分区](#BKMK_FormatandPartitionDisk)  
  
-   [安装应用程序](#BKMK_InstallApplication)  
  
-   [安装部署工具](#BKMK_InstallDeploymentTools)  
  
-   [安装包](#BKMK_InstallPackage)  
  
-   [安装软件更新](#BKMK_InstallSoftwareUpdates)  
  
-   [加入域或工作组](#BKMK_JoinDomainorWorkgroup)  
  
-   [准备 ConfigMgr 客户端以便捕获](#BKMK_PrepareConfigMgrClientforCapture)  
  
-   [准备 Windows 以便捕获](#BKMK_PrepareWindowsforCapture)  
  
-   [预设置 BitLocker](#BKMK_PreProvisionBitLocker)  
  
-   [和“发布状态存储”](#BKMK_ReleaseStateStore)  
  
-   [任务序列步骤与“请求状态存储”](#BKMK_RequestStateStore)  
  
-   [重启计算机](#BKMK_RestartComputer)  
  
-   [还原用户状态](#BKMK_RestoreUserState)  
  
-   [运行命令行](#BKMK_RunCommandLine)  
  
-   [运行 PowerShell 脚本](#BKMK_RunPowerShellScript)  
  
-   [设置动态变量](#BKMK_SetDynamicVariables)  
  
-   [设置任务序列变量](#BKMK_SetTaskSequenceVariable)  
  
-   [安装 Windows 和 ConfigMgr](#BKMK_SetupWindowsandConfigMgr)  
  
-   [升级操作系统](#BKMK_UpgradeOS)  
  
##  <a name="BKMK_ApplyDataImage"></a> 应用数据映像任务序列步骤  
 使用“应用数据映像”  任务序列步骤将数据映像复制到指定目标分区。  
  
 此步骤仅可在 Windows PE 中运行。 不能在标准操作系统中运行。 若要深入了解此操作的任务序列变量，请参阅 [System Center Configuration Manager 中的任务序列操作变量](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md)。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 描述此步骤所采取操作的用户定义的短名。  
  
 **描述**  
 有关此步骤所采取操作的更详细信息。  
  
 **映像包**  
 单击“浏览”  ，指定将用于此任务序列步骤的“映像包” 。 在“选择包”  对话框中选择要安装的包。 每个现有映像包的关联属性信息显示在“选择包”  对话框的底部。 使用下拉列表，从所选的“映像包”  中选择要安装的“映像” 。  
  
> [!NOTE]  
>  此任务序列操作将映像视为数据文件，不会执行将映像作为操作系统启动所需的任何设置。  
  
 **目标**  
 指定现有的格式化分区和硬盘、特定逻辑驱动器号或包含逻辑驱动器号的任务序列变量的名称。  
  
-   **下一可用分区** – 使用此任务序列中此前未被“应用操作系统”或“应用数据映像”作为目标的下一个顺序分区。  
  
-   “特定磁盘和分区” – 选择“磁盘”  编号（从 0 开始）和“分区”  编号（从 1 开始）。  
  
-   “特定逻辑驱动器号” – 指定 Windows PE 分配给分区的“驱动器号”  。 注意，此驱动器号可不同于新部署的操作系统将要分配的驱动器号。  
  
-   **变量中存储的逻辑驱动器号** – 指定包含 Windows PE 分配给分区的驱动器号的任务序列变量。 对于“格式化磁盘并分区”  任务序列操作，此变量通常在“分区属性”  对话框的“高级”部分中设置。  
  
 **应用映像之前删除分区中的所有内容**  
 指定在安装映像之前目标分区上的所有文件将被删除。 如果不删除分区内容，则此步骤可用于将其他内容应用到以前的目标分区。  
  
##  <a name="BKMK_ApplyDriverPackage"></a> 应用驱动程序包  
 使用“应用驱动程序包”  任务序列步骤可下载驱动程序包中的所有驱动程序，并将其安装在 Windows 操作系统上。 
  
 “应用驱动程序包”  任务序列步骤使 Windows 可以使用驱动程序包中的所有设备驱动程序。 此步骤可以添加到“应用操作系统”   与“安装 Windows 和 ConfigMgr”  步骤之间的任务序列，使驱动程序包中的设备驱动程序可以用于 Windows。 通常，“应用驱动程序包”  步骤位于“自动应用驱动程序”  任务序列步骤之后。 “应用驱动程序包”  任务序列步骤也可以与独立媒体部署方案配合使用。  
  
 确保类似的设备驱动程序放入驱动程序包，并将其分发到合适的分发点。 分发它们后 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端计算机才能安装它们。 例如，可以将所有来自同一制造商的设备驱动程序放在一个驱动程序包中，然后将该包分发到关联计算机可以访问的分发点。 
  
 对于独立媒体和要安装特定驱动程序集的管理员，包括即插即用扫描无法检测到的设备（例如，网络打印机）的驱动程序，此步骤很有用。  
  
 此任务序列步骤仅可在 Windows PE 中运行。 不能在标准操作系统中运行。 有关此操作的任务序列变量的详细信息，请参阅 [Apply Driver Package Task Sequence Action Variables](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md#BKMK_ApplyDriverPackage)。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 描述此步骤所采取操作的用户定义的短名。  
  
 **描述**  
 有关此步骤所采取操作的更详细信息。  
  
 **驱动程序包**  
 通过单击“浏览”  并启动“选择包”  对话框，指定包含所需设备驱动程序的驱动程序包。 指定要使用的现有包。 相应的包属性显示在对话框底部。  
  
 **选择包中需要安装的大容量存储驱动程序，然后在 Windows Vista 以前的操作系统上安装**  
 指定 Windows Vista 以前的操作系统安装所需的任何大容量存储设备驱动程序。  
  
 **驱动程序**  
 选择要安装的大容量存储设备驱动程序文件，然后在 Windows Vista 以前的操作系统部署上安装。 下拉列表根据指定包填充。  
  
 **型号**  
 指定 Windows Vista 以前的操作系统部署需要的启动关键设备。  
  
 **在 Windows 版本上对未签名的驱动程序执行允许的无人参与安装**  
 选择此选项以允许 Windows 安装没有在引用计算机上签名的驱动程序。  
  
##  <a name="BKMK_ApplyNetworkSettings"></a> 应用网络设置步骤  
 使用“应用网络设置”  任务序列步骤指定目标计算机的网络或工作组配置信息。 指定值以适当的答案文件格式进行存储，以供 Windows 安装程序在运行“安装 Windows 和 ConfigMgr”  任务序列步骤时使用。  
  
 标准操作系统或 Windows PE 中均可运行此任务序列步骤。 有关此操作的任务序列变量的详细信息，请参阅 [Apply Network Settings Task Sequence Action Variables](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md#BKMK_ApplyNetworkSettings)。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 描述此步骤所采取操作的用户定义的短名。  
  
 **描述**  
 有关此步骤所采取操作的更详细信息。  
  
 **加入工作组**  
 选择此选项，使目标计算机加入指定的工作组。 在“工作组”  行中输入工作组的名称。 此值可被“捕获网络设置”  任务序列步骤所捕获的值替代。  
  
 **加入域**  
 选择此选项以将目标计算机加入指定的域。 指定或浏览到域，如 *fabricam.com*。 指定或浏览到组织单位的轻型目录访问协议 (LDAP) 路径（即 LDAP//OU=computers，DC=Fabricam.com，C=com）。  
  
 **帐户**  
 单击“设置”  以指定拥有将计算机加入域所需权限的帐户。 在“Windows 用户帐户”  对话框中，可以使用下列格式输入用户名： **Domain\User** 。  
  
 **适配器设置**  
 指定计算机中每个网络适配器的网络配置。 单击  “新建”打开  “网络设置”对话框，然后指定网络设置。 如果在之前的  “捕获网络设置”任务序列步骤中已捕获网络设置，之前的设置会应用到网络适配器，不会应用在此步骤中指定的设置。 如果先前没有捕获网络设置，在“应用网络设置”  步骤中指定的设置将以 Windows 设备枚举顺序应用到网络适配器。  
  
##  <a name="BKMK_ApplyOperatingSystemImage"></a> 应用操作系统映像  
 使用“应用操作系统映像”  任务序列步骤在目标计算机上安装操作系统。 此任务序列步骤会根据使用操作系统映像还是操作系统安装包来执行一组操作，以安装操作系统。  
  
 使用操作系统映像时，“应用操作系统映像”  步骤将执行以下操作。  
  
1.  删除目标卷上的所有内容，除了 _SMSTSUserStatePath 任务序列变量指定的文件夹中的文件之外。  
  
2.  将指定的 .wim 文件的内容提取到指定目标分区。  
  
3.  准备答案文件：  
  
    1.  为将要部署的操作系统创建新的默认 Windows 安装程序答案文件（sysprep.inf 或 unattend.xml）。  
  
    2.  从用户提供的答案文件中合并所有值。  
  
4.  将 Windows 启动加载程序复制到活动分区中。  
  
5.  设置 boot.ini 或启动配置数据库 (BCD) 来引用新安装的操作系统。  
  
 使用操作系统安装包时，“应用操作系统映像”  步骤将执行以下操作。  
  
1.  删除目标卷上的所有内容，除了 _SMSTSUserStatePath 任务序列变量指定的文件夹中的文件之外。  
  
2.  准备答案文件：  
  
    1.  使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]创建的标准值创建全新的答案文件。  
  
    2.  从用户提供的答案文件中合并所有值。  
  
> [!NOTE]  
>  Windows 的实际安装由“安装 Windows 和 ConfigMgr”  任务序列步骤启动。 在  “应用操作系统”任务序列操作运行之后，OSDTargetSystemDrive 任务序列变量设置为包含操作系统文件的分区的驱动器号。  
  
 此任务序列步骤仅可在 Windows PE 中运行。 不能在标准操作系统中运行。 有关此操作的任务序列变量的详细信息，请参阅 [Apply Operating System Image Task Sequence Action Variables](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md#BKMK_ApplyOperatingSystem)。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   **直接从分发点访问内容**：  
  
     使用此选项指定你是否希望任务序列直接从分发点访问操作系统映像。 例如，可在部署操作系统到存储容量有限的嵌入式设备时使用此选项。 选择此选项后，你还必须在包属性的“数据访问”  选项卡上配置包共享设置。  
  
    > [!NOTE]  
    >  此设置仅针对此任务序列步骤中指定的操作系统映像覆盖在“部署软件向导”  的“分发点”  页上配置的部署选项，而不是整个任务序列的所有内容。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 描述此步骤所采取操作的用户定义的短名。  
  
 **描述**  
 有关此步骤所采取操作的更详细信息。  
  
 **从捕获的映像应用操作系统**  
 安装先前已捕获的操作系统映像。 单击“浏览”  以打开“选择映像包”  对话框，然后选择你要安装的现有映像包。 如果指定的映像包 关联了多个映像，请使用下拉列表指定将用于此部署的关联映像。 你可以通过单击每个现有映像查看有关该映像的基本信息。  
  
 **从原始安装源应用操作系统映像**  
 使用原始安装源安装操作系统。 单击“浏览”  以打开“选择操作系统安装包”  对话框，然后选择你要使用的现有操作系统安装包。 可以通过单击每个现有映像源查看有关该映像源的基本信息。 关联映像源属性显示在对话框底部的结果窗格中。 如果指定的包关联了多个版本，请使用下拉列表指使用的关联“版本”  。  
  
 **使用无人参与或 Sysprep 答案文件进行自定义安装**  
 使用此选项提供 Windows 安装程序答案文件（**unattend.xml**、 **unattend.txt**或 **sysprep.inf**），取决于操作系统版本和安装方法。 你指定的文件可以包含 Windows 答案文件支持的任何标准的配置选项。 例如，可以使用它指定默认的 Internet Explorer 主页。 你必须指定包含答案文件的包以及包中文件的关联路径。  
  
> [!NOTE]  
>  你提供的 Windows 安装程序答案文件可以包含形式为 %*varname*% 的嵌入任务序列变量，其中 varname 是指变量的名称。 %*varname*% 字符串将替换为“安装 Windows 和 ConfigMgr”  任务序列操作中的实际变量值。 但是请注意，unattend.xml 答案文件的仅数字字段中不能使用此类嵌入任务序列变量。  
  
 如果你不提供 Windows 安装程序答案文件，此任务序列操作将自动生成一个答案文件。  
  
 **目标**  
 指定现有的格式化分区和硬盘、特定逻辑驱动器号或包含逻辑驱动器号的任务序列变量的名称。  
  
-   **下一可用分区** – 使用此任务序列中此前未被“应用操作系统”或“应用数据映像”作为目标的下一个顺序分区。  
  
-   “特定磁盘和分区” – 选择“磁盘”  编号（从 0 开始）和“分区”  编号（从 1 开始）。  
  
-   “特定逻辑驱动器号” – 指定 Windows PE 分配给分区的“驱动器号”  。 注意，此驱动器号可不同于新部署的操作系统将要分配的驱动器号。  
  
-   **变量中存储的逻辑驱动器号** – 指定包含 Windows PE 分配给分区的驱动器号的任务序列变量。 对于“格式化磁盘并分区”  任务序列操作，此变量通常在“分区属性”  对话框的“高级”部分中设置。  
  
##  <a name="BKMK_ApplyWindowsSettings"></a> 应用 Windows 设置  
 使用“应用 Windows 设置”  任务序列步骤配置目标计算机的 Windows 设置。 指定值以适当的答案文件格式进行存储，以供 Windows 安装程序在运行“安装 Windows 和 ConfigMgr”  任务序列步骤时使用。  
  
 此任务序列步骤仅可在 Windows PE 中运行。 不能在标准操作系统中运行。 有关此操作的任务序列变量的详细信息，请参阅 [Apply Windows Settings Task Sequence Action Variables](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md#BKMK_ApplyWindowsSettings)。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 描述在此步骤中执行的操作的用户定义的短名称  
  
 **描述**  
 有关此步骤所采取操作的更详细信息。  
  
 **用户名**  
 指定与目标计算机关联的已注册用户名。 “捕获 Windows 设置”  任务序列操作所捕获的值可以替代此值。  
  
 **组织名称**  
 指定与目标计算机关联的已注册组织名称。 “捕获 Windows 设置”  任务序列操作所捕获的值可以替代此值。  
  
 **产品密钥**  
 指定用于目标计算机上的 Windows 安装的产品密钥。  
  
 **服务器授权**  
 指定授权模式。 你可以选择“每服务器”  或“每用户”  作为授权模式。 如果选择“每服务器”作为授权模式，则还需要指定每个许可协议将允许的最大连接数。 如果目标计算机不是服务器或你不想指定授权模式，请选择“不指定”  。  
  
 **最大连接数**  
 指定许可协议中声明的可用于此计算机的最大连接数。  
  
 **随机生成本地管理员密码并在所有支持的平台上禁用帐户（推荐）**  
 选择此选项以随机生成本地管理员密码。 这将创建本地管理员密码并导致帐户在支持的平台上被禁用。  
  
 **启用帐户并指定本地管理员密码**  
 择此选项以启用本地管理员帐户并创建本地管理员密码。 在“密码”  行上输入密码，并在“确认密码”  行上确认密码。  
  
 **时区**  
 指定要在目标计算机上配置的时区。 “捕获 Windows 设置”  任务序列步骤所捕获的值可以替代此值。  
  
##  <a name="BKMK_AutoApplyDrivers"></a> 自动应用驱动程序  
 使用“自动应用驱动程序”  任务序列步骤匹配驱动程序，并将其作为操作系统部署的一部分进行安装。  
  
 “自动应用驱动程序”  任务序列步骤执行以下操作：  
  
1.  扫描硬件并为系统上存在的所有设备查找即插即用 ID。  
  
2.  将设备列表以及设备的即插即用 ID 发送到管理点。 管理点从驱动程序目录中为每个设备返回兼容的驱动程序的列表。 无论驱动程序可能位于哪个驱动程序包，管理点都将对所有驱动程序进行考虑。 只考虑标记有指定驱动程序类别和未标记为“已禁用”的驱动程序。  
  
3.  对于每个设备，客户端会挑选出适合于正在部署该设备的操作系统并位于可访问的分发点上的最佳驱动程序。  
  
4.  选定的一个或多个驱动程序将从分发点下载，并在目标操作系统上暂存。  
  
    1.  对于基于映像的安装，驱动程序放置在操作系统的驱动程序存储中。  
  
    2.  对于基于安装程序的安装，Windows 安装程序通过查找驱动程序的位置来进行配置。  
  
5.  当  “安装 Windows 和 ConfigMgr”任务序列操作运行且 Windows 首次启动时，它将查找由此操作暂存的驱动程序。  
  
> [!IMPORTANT]
>  不能将“自动应用驱动程序”  任务序列步骤与独立媒体配合使用，因为 Windows 安装程序将没有到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点的连接。
  
此任务序列步骤仅可在 Windows PE 中运行。 不能在标准操作系统中运行。 有关此操作的任务序列变量的详细信息，请参阅 [Auto Apply Drivers Task Sequence Action Variables](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md#BKMK_AutoApplyDrivers)。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 描述此步骤所采取操作的用户定义的短名。  
  
 **描述**  
 有关此步骤所采取操作的更详细信息。  
  
 **仅安装最匹配的兼容驱动程序**  
 指定任务序列步骤为检测到的每个硬件设备仅安装最匹配的驱动程序。  
  
 **安装所有兼容的驱动程序**  
 指定任务序列步骤为检测到的每个硬件设备安装所有兼容的驱动程序并允许 Windows 安装程序选择最适合的驱动程序。 因为此选项会下载更多的驱动程序，所以它会占用更多的网络带宽和磁盘空间，但可以选取到更适合的驱动程序。  
  
 **考虑所有类别的驱动程序**  
 指定任务序列操作搜索适当设备驱动程序的所有可用驱动程序类别。  
  
 **将驱动程序匹配限制为仅考虑所选类别的驱动程序**  
 指定任务序列操作在适当设备驱动程序的指定驱动程序类别中搜索设备驱动程序。  
  
 **在 Windows 版本上对未签名的驱动程序执行允许的无人参与安装**  
 允许此任务序列操作安装未签名的 Windows 设备驱动程序。  
  
> [!IMPORTANT]  
>  此选项不适用于不能配置驱动程序签名策略的操作系统。  
  
##  <a name="BKMK_CaptureNetworkSettings"></a> 捕获网络设置  
 使用“捕获网络设置”  任务序列步骤从运行该任务序列的计算机捕获 Microsoft 网络设置。 这些设置保存在任务序列变量中，将替代在“应用网络设置”  任务序列步骤中配置的默认设置。  
  
 此任务序列步骤仅可在标准操作系统中运行。 不可在 Windows PE 中运行。 有关此操作的任务序列变量的详细信息，请参阅 [Capture Network Settings Task Sequence Action Variables](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md#BKMK_CaptureNetworkSettings)。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 指定描述此步骤中执行的操作的用户定义的短名。  
  
 **描述**  
 提供有关在此步骤中执行的操作的更详细信息。  
  
 **迁移域和工作组成员身份**  
 捕获目标计算机的域和工作组成员身份信息。  
  
 **迁移网络适配器配置**  
 捕获目标计算机的网络适配器配置。 捕获的信息包括全局网络设置、适配器数量以及与每个适配器关联的网络设置。 这些设置包括与 DNS、WINS、IP 和端口筛选器关联的设置。  
  
##  <a name="BKMK_CaptureOperatingSystemImage"></a> 捕获操作系统映像  
 使用“捕获操作系统映像”  任务序列步骤可从引用计算机捕获一个或多个映像，并将它们存储在指定网络共享上的 WIM 文件中。 随后可以使用添加操作系统映像包向导将此 .WIM 文件导入 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中，以便它可用于基于映像的操作系统部署。  
  
 引用计算机上的每个卷（驱动器）是作为 .wim 文件中的单独映像捕获的。 如果引用计算机有多个卷，则生成的 WIM 文件对于每个卷将包含单独的映像。 仅捕获格式化为 NTFS 或 FAT32 的卷。 其他格式的卷和 USB 卷会被忽略。  
  
 引用计算机上安装的操作系统必须是 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 支持的 Windows 版本，并且必须是使用 SysPrep 工具进行准备的。 安装的操作系统卷和启动卷必须是相同的卷。  
  
 你还必须输入对你所选择的网络共享具有写入权限的 Windows 帐户。  
  
 此任务序列步骤仅可在 Windows PE 中运行。 不能在标准操作系统中运行。 有关此操作的任务序列变量的详细信息，请参阅 [Capture Operating System Image Task Sequence Action Variables](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md#BKMK_CaptureOperatingSystemImage)。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 描述此步骤所采取操作的用户定义的短名。  
  
 **描述**  
 有关此步骤所采取操作的更详细信息。  
  
 **目标**  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 在存储捕获的操作系统映像时使用的位置的文件系统路径名。  
  
 **描述**  
 .WIM 文件中存储的捕获的操作系统映像的用户定义的描述（可选）。  
  
 **版本**  
 向捕获的操作系统映像分配的用户定义的版本号（可选）。 此值可以是字母和数字的任意组合，存储在 .WIM 文件中。  
  
 **创建者**  
 创建操作系统映像的用户的可选名称，存储在 WIM 文件中。  
  
 **捕获操作系统映像帐户**  
 你必须输入对你指定的网络共享具有访问权限的 Windows 帐户。 单击“设置”  以指定该 Windows 帐户的名称。  
  
##  <a name="BKMK_CaptureUserState"></a> 捕获用户状态  
 使用“捕获用户状态”  任务序列步骤来通过用户状态迁移工具 (USMT) 从运行该任务序列的计算机捕获用户状态和设置。 此任务序列步骤与“还原用户状态”  任务序列步骤一起使用。 通过 USMT 3.0.1 和更高版本，此选项始终使用由 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]生成并管理的加密密钥加密 USMT 状态存储。  
  
 有关部署操作系统时管理用户状态的详细信息，请参阅[在 System Center Configuration Manager 中管理用户状态](../LocTest/Manage-user-state-in-System-Center-Configuration-Manager.md)。  
  
 如果你想要将状态设置保存到 **站点中的状态迁移点或从其还原设置，你还可以将“捕获用户状态”****任务序列步骤与“请求状态存储”****和“发布状态存储”**[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 任务序列步骤一起使用。  
  
  “捕获用户状态”任务序列步骤提供对最常用 USMT选项的受限子网的控制。 其他命令行选项可使用 OSDMigrateAdditionalCaptureOptions 任务序列变量指定。  
  
 此任务序列步骤仅可在 Windows PE 中运行。 不能在标准操作系统中运行。 有关此操作的任务序列变量的详细信息，请参阅 [Capture User State Task Sequence Action Variables](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md#BKMK_CaptureUserState)。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 描述此步骤所采取操作的用户定义的短名。  
  
 **描述**  
 有关此步骤所采取操作的更详细信息。  
  
 **用户状态迁移工具包**  
 输入包含 USMT 版本的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 包，供此任务序列步骤在捕获用户状态和设置时使用。 此包不需要程序。 当任务序列步骤运行时，任务序列将使用指定的包中的 USMT 版本。 根据你正在捕获其状态的操作系统的体系结构，指定包含 32 位或 x64 版本的 USMT 的包。  
  
 **使用标准选项捕获所有用户配置文件**  
 选择此选项以迁移所有用户配置文件信息。 默认情况下选择此选项。  
  
 如果你选择此选项，但不在“还原用户状态”任务序列步骤中选择“还原本地计算机用户配置文件”选项，则任务序列将失败，因为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不能在未向新用户帐户分配密码的情况下迁移它们。 此外，如果你使用  新建任务序列向导并创建了一个任务序列以 安装现有映像包，则结果任务序列将默认为“使用标准选项捕获所有用户配置文件”，但是不会选择“还原本地计算机用户配置文件”选项（即非域帐户）。  
  
 选择“还原本地计算机用户配置文件”  ，并为要迁移的帐户提供密码。 在手动创建的任务序列中，此设置可在“还原用户状态”步骤下找到。 在由  新建任务序列向导创建的任务序列中，可在步骤“还原用户文件和设置”  向导页面下方找到此设置。  
  
 如果没有本地用户帐户，此方法不适用。  
  
 **自定义如何捕获用户配置文件**  
 选择此选项以指定自定义配置文件迁移。 单击  “文件”以选择 USMT 要在此步骤中使用的配置文件。 你必须指定一个 custom .xml 文件，该文件包含定义要迁移的用户状态文件的规则。  
  
 **单击此处选择配置文件:**  
 选择此选项以便在想要用于捕获用户配置文件的 USMT 包中选择配置文件。 单击“文件”  按钮以启动“配置文件”  对话框。 要指定配置文件，请在“文件名”  行中输入文件名称并单击“添加”  按钮。  
  
 **启用详细日志记录**  
 启用此选项以生成更详细的日志文件信息。 当捕获状态时，将生成日志 Scanstate.log 并默认存储在 \windows\system32\ccm\logs 文件夹的任务序列日志文件夹中。  
  
 **使用加密文件系统跳过文件**  
 如果你想跳过而不捕获使用加密文件系统 (EFS) 加密的文件（包括配置文件），请启用此选项。 根据操作系统和 USMT 版本，还原后可能无法读取加密文件。 有关详细信息，请参阅 USMT 文档。  
  
 **使用文件系统访问进行复制**  
 启用此选项以指定任何以下设置：  
  
-   **在无法捕获某些文件时继续：**启用此设置以在无法捕获某些文件时继续迁移过程。 如果禁用此选项，则当无法捕获某个文件时，任务序列步骤将失败。 默认情况下会启用此选项。  
  
-   **使用链接而非复制文件的方式在本地捕获：**启用此设置以使用 NTFS 硬链接来捕获文件。  
  
     有关使用硬链接迁移数据的详细信息，请参阅 [硬链接迁移存储](http://go.microsoft.com/fwlink/p/?LinkId=240222)  
  
-   在脱机模式下捕获（仅针对 Windows PE）：启用此设置可在 Windows PE 而不是整个操作系统中捕获用户状态。  
  
 **使用卷影复制服务 (VSS) 进行捕获**  
 通过此选项，你可捕获即使锁定由其他应用程序编辑的文件。  
  
##  <a name="BKMK_CaptureWindowsSettings"></a> 捕获 Windows 设置  
 使用“捕获 Windows 设置”  任务序列步骤从运行该任务序列的计算机捕获 Windows 设置。 这些设置保存在任务序列变量中，将替代在“应用 Windows 设置”  任务序列步骤中配置的默认设置。  
  
 Windows PE 或标准操作系统中均可运行此任务序列步骤。 有关此操作的任务序列变量的详细信息，请参阅 [Capture Windows Settings Task Sequence Action Variables](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md#BKMK_CaptureWindowsSettings)。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 描述此步骤所采取操作的用户定义的短名。  
  
 **描述**  
 有关此步骤所采取操作的更详细信息。  
  
 **迁移计算机名称**  
 选择此选项以捕获计算机的 NetBIOS 计算机名称。  
  
 **迁移注册用户和组织名称**  
 选择此选项以捕获计算机中已注册的用户和组织名称。  
  
 **迁移时区**  
 选择此选项以捕获计算机上的时区设置。  
  
##  <a name="BKMK_CheckReadiness"></a> 检查准备情况  
 使用“检查准备情况”  任务序列步骤验证目标计算机是否满足指定部署必备条件。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。 对于此步骤，请勿择此设置，否则当检查失败时将只记录准备情况检查而不停止任务序列。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 描述此步骤所采取操作的用户定义的短名。  
  
 **描述**  
 有关此步骤所采取操作的更详细信息。  
  
 **确保最小内存 (MB)**  
 选择此设置，验证安装在目标计算机上的内存量（以兆字节为单位）是否达到或超出指定的量。 默认情况下选择了此设置。  
  
 **确保最低处理器速度 (MHz)**  
 选择此设置，验证安装在目标计算机上的处理器速度（以兆赫 (MHz) 为单位）是否达到或超过指定量。 默认情况下选择了此设置。  
  
 **确保最小可用磁盘空间 (MB)**  
 选择此设置，验证目标计算机上的可用磁盘空间量（以兆字节为单位）是否达到或超过指定量。  
  
 **确保要刷新的当前 OS**  
 选择此设置，验证目标计算机上安装的操作系统是否满足你指定的要求。 默认情况下，使用值 **CLIENT**选择此设置。  
  
##  <a name="BKMK_ConnectToNetworkFolder"></a> 连接到网络文件夹  
 使用“连接到网络文件夹”  任务序列操作来创建到共享网络文件夹的连接。  
  
 标准操作系统或 Windows PE 中均可运行此任务序列步骤。 有关此操作的任务序列变量的详细信息，请参阅 [Connect to Network Folder Task Sequence Action Variables](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md#BKMK_ConnecttoNetworkFolder)。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
##  <a name="BKMK_ConvertDisktoDynamic"></a> 将磁盘转换为动态磁盘  
 使用“将磁盘转换为动态磁盘”  任务序列步骤将物理磁盘从基本磁盘类型转换为动态磁盘类型。  
  
 标准操作系统或 Windows PE 中均可运行此步骤。 有关此操作的任务序列变量的详细信息，请参阅 [Convert Disk to Dynamic Task Sequence Action Variables](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md#BKMK_ConvertDisk)。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 描述此步骤所采取操作的用户定义的短名。  
  
 **描述**  
 有关此步骤所采取操作的更详细信息。  
  
 **磁盘编号**  
 将被转换的磁盘的物理磁盘编号。  
  
##  <a name="BKMK_DisableBitLocker"></a> 禁用 BitLocker  
 使用“禁用 BitLocker”  任务序列步骤可在当前操作系统驱动器或特定驱动器上禁用 BitLocker 加密。 此操作使得密钥保护程序在硬盘驱动器上以明文形式显示，但是不会解密该驱动器的内容。 因此，此操作几乎立刻完成。  
  
> [!NOTE]  
>  BitLocker 驱动器加密提供磁盘卷内容的低级加密。  
  
 如果加密了多个驱动器，你必须在任何数据驱动器上禁用 BitLocker，才能在操作系统驱动器上禁用 BitLocker。  
  
 此步骤仅可在标准操作系统中运行。 不可在 Windows PE 中运行。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 指定描述此步骤中执行的操作的用户定义的短名。  
  
 **描述**  
 提供有关在此步骤中执行的操作的更详细信息。  
  
 **当前操作系统驱动器**  
 在当前操作系统驱动器上禁用 BitLocker。  
  
 **特定驱动器**  
 在特定驱动器上禁用 BitLocker。 使用下拉列表指定禁用 BitLocker 的驱动器。  
  
##  <a name="BKMK_DownloadPackageContent"></a> 下载包内容  
 使用“下载包内容”  任务序列步骤下载以下任意一种包类型：  
  
-   操作系统映像  
  
-   操作系统升级包  
  
-   驱动程序包  
  
-   包  
  
 此步骤适用于任务序列，以在以下方案中升级操作系统：  
  
-   若要使用可同时用于 x86 平台和 x64 平台的单一升级任务序列。 为了实现这一目的，在“升级准备”  组中包括两个“下载包内容”  步骤，以及检测客户端体系结构的条件和仅下载相应操作系统升级包的条件。 将每个“下载包内容”  步骤配置为使用相同的变量，并将该变量用于“升级操作系统”  步骤的媒体路径。  
  
-   若要动态下载适用的驱动程序包，请使用两个“下载包内容”  步骤以及检测每个驱动程序包的相应硬件类型的条件。 将每个“下载包内容”  步骤配置为使用相同的变量，并将该变量用于“升级操作系统”  步骤的驱动程序部分中的“分步内容”  值。  
  
 此步骤仅可在标准操作系统中运行。 不可在 Windows PE 中运行。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 指定描述此步骤中执行的操作的用户定义的短名。  
  
 **描述**  
 提供有关在此步骤中执行的操作的更详细信息。  
  
 “选择包” 图标  
 单击图标以选择要下载的包。 选择包后，可以再次单击图标以选择另一个包。  
  
 **置于下列位置**  
 选择将包保存在下列位置之一：  
  
-   **任务序列工作目录**  
  
-   **Configuration Manager 客户端缓存：**使用此选项可在客户端缓存中存储内容。 使客户端可作为其他对等缓存客户端的对等缓存源。 有关详细信息，请参阅 [Prepare Windows PE peer cache to reduce WAN traffic in System Center Configuration Manager](../LocTest/Prepare-Windows-PE-peer-cache-to-reduce-WAN-traffic-in-System-Center-Configuration-Manager.md)。  
  
-   **自定义路径**  
  
 **将路径另存为一个变量**  
 可以将路径另存为一个可在另一任务序列步骤中使用的变量。 当有多个包时， [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 会向变量名称中添加数字后缀。 例如，如果你指定变量 %*mycontent*% 作为自定义变量，它就是用于存储所有引用内容（可以是多个包）的根目录。 当引用子序列步骤中的变量时（如升级操作系统），会为该变量添加数字后缀。 在本例中，%*mycontent01*% 或 %*mycontent02*%，其中的数字对应于包在此步骤中列出的顺序。  
  
 **如果包下载失败，继续下载列表中的其他包**  
 指定如果包下载失败，将转到列表中的下一个包并开始下载。  
  
##  <a name="BKMK_EnableBitLocker"></a> 启用 BitLocker  
 使用“启用 BitLocker”  任务序列步骤在硬盘上的至少两个分区中启用 BitLocker 加密。 第一个活动分区包含 Windows 启动代码。 另一个分区包含操作系统。 启动分区必须保持为未加密状态。  
  
 在 Windows PE 中，使用“预设置 BitLocker”  任务序列步骤可在驱动器上启用 BitLocker。 有关详细信息，请参阅本主题中的 [预设置 BitLocker](#BKMK_PreProvisionBitLocker) 部分。  
  
> [!NOTE]  
>  BitLocker 驱动器加密提供磁盘卷内容的低级加密。  
  
 “启用 BitLocker”  步骤只能在标准操作系统中运行。 不可在 Windows PE 中运行。 有关此操作的任务序列变量的详细信息，请参阅 [Enable BitLocker Task Sequence Action Variables](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md#BKMK_EnableBitLocker)。  
  
 当指定“仅 TPM” 、“USB 上的 TPM 和启动密钥”  或“TPM 和 PIN” 时，受信任的平台模块 (TPM) 必须处于以下状态，然后才能运行“启用 BitLocker”  步骤：  
  
-   Enabled  
  
-   已激活  
  
-   允许的所有权  
  
 该任务序列步骤可以完成任何剩余的 TPM 初始化，因为剩余步骤不需要物理访问或重新启动。 可以由“启用 BitLocker”  （如有必要）透明完成的剩余 TPM 初始化步骤包括：  
  
-   创建认可密钥对  
  
-   创建所有者授权值和 Active Directory 的证书，后者必须已扩展为支持此值  
  
-   取得所有权  
  
-   创建存储根密钥，或在已存在但不兼容时重置  
  
 如果希望“启用 BitLocker”  步骤等待驱动器加密过程完成再继续任务序列中的下一步，请选择“等待”  复选框。 如果你没有选择  “等待”复选框，将在后台中执行驱动器加密过程，且任务序列将立即执行下一个步骤。  
  
 BitLocker 可用于加密单个计算机系统上的多个驱动器（操作系统和数据驱动器）。 要加密数据驱动器，必须已加密操作系统，并且必须完成加密过程，因为数据驱动器的密钥保护程序存储在操作系统驱动器上。 因此，如果你在同一过程中加密操作系统驱动器和数据驱动器，则必须针对为操作系统驱动器启用 BitLocker 的步骤选择等待选项。  
  
 如果硬盘已加密，但 BitLocker 处于禁用状态，则“启用 BitLocker”会重新启用一个或多个密钥保护程序，并且将立刻完成。 在这种情况下不需要重新加密硬盘。  
  
 有关此操作的任务序列变量的详细信息，请参阅 [Enable BitLocker Task Sequence Action Variables](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md#BKMK_EnableBitLocker)。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 指定此任务序列步骤的描述性名称。  
  
 **描述**  
 允许你选择性地输入此任务序列步骤的描述。  
  
 **选择要加密的驱动器**  
 指定要加密的驱动器。 要加密当前操作系统驱动器，请选择“当前操作系统驱动器”  ，然后配置以下其中一个密钥管理选项：  
  
-   **仅 TPM：**选择此选项，以仅使用受信任的平台模块 (TPM)。  
  
-   **仅 USB 上的启动密钥：**选择此选项以使用存储在 USB 闪存驱动器上的启动密钥。 选择此选项时，BitLocker 将锁定正常启动过程，直至含有 BitLocker 启动密钥的 USB 设备连接到计算机。  
  
-   **TPM 和 USB 上的启动密钥：**选择此选项以使用 TPM 和存储在 USB 闪存驱动器上的启动密钥。 选择此选项时，BitLocker 将锁定正常启动过程，直至含有 BitLocker 启动密钥的 USB 设备连接到计算机。  
  
-   **TPM 和 PIN：**选择此选项以使用 TPM 和个人标识号 (PIN)。 当选择此选项时，BitLocker 将锁定正常启动过程，直至用户提供 PIN。  
  
 若要对特定非操作系统数据驱动器进行加密，请选择“特定驱动器” ，然后从列表中选择驱动器。  
  
 **选择要创建恢复密钥的位置**  
 要指定创建恢复密码的位置，请选择“Active Directory 中”  以在 Active Directory 中保存密码。 如果选择此选项，你必须为站点扩展 Active Directory，以便保存关联的 BitLocker 恢复信息。 你可以选择“不创建恢复密钥” 不创建密码。 但最好创建密码。  
  
 **等待 BitLocker 完成所有驱动器上的驱动器加密过程之后，继续执行任务序列**  
 选择此选项以允许在运行任务序列中的下一步骤之前完成 BitLocker 驱动器加密。 如果选择此选项，则在用户能够登录到计算机之前，将对整个磁盘卷加密。  
  
 加密大型硬盘时，加密过程可能需要数小时才能完成。 不选择此选项将允许立即处理任务序列。  
  
##  <a name="BKMK_FormatandPartitionDisk"></a> 格式化磁盘并分区  
 使用“格式化磁盘并分区”  任务序列步骤对目标计算机上的特定磁盘进行格式化和分区。  
  
> [!IMPORTANT]  
>  你为此任务序列步骤指定的所有设置均应用于单个特定磁盘。 如果要对目标计算机上的另一个磁盘进行格式化和分区，则必须将其他“格式化磁盘并分区”  任务序列步骤添加到该任务序列。  
  
 此任务序列步骤仅可在 Windows PE 中运行。 不能在标准操作系统中运行。 有关此操作的任务序列变量的详细信息，请参阅 [Format and Partition Disk Task Sequence Action Variables](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md#BKMK_FormatPartitionDisk)。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 描述此步骤所采取操作的用户定义的短名。  
  
 **描述**  
 有关此步骤所采取操作的更详细信息。  
  
 **磁盘编号**  
 要进行格式化的磁盘的物理磁盘编号。 该编号取决于 Windows 磁盘枚举排序。  
  
 **磁盘类型**  
 格式化的磁盘的类型。 可以从下拉列表中选择两个选项：  
  
-   标准 (MBR) – 主启动记录。  
  
-   GPT – GUID 分区表  
  
> [!NOTE]  
>  如果将磁盘类型从“标准 (MBR)”  更改为“GPT” ，并且分区布局包含扩展分区，则所有扩展分区和逻辑分区将从布局中删除。 系统会在更改磁盘类型前提示你确认此操作。  
  
 **Volume**  
 指定有关要创建的分区或卷的信息，包括：  
  
-   Name  
  
-   剩余磁盘空间  
  
 要创建新的分区，请单击“新建”  以启动“分区属性”  对话框。 你可以指定分区类型和大小，并指定其是否为启动分区。 要修改现有分区，请单击要修改的分区，然后单击“属性”按钮。 有关如何配置硬盘分区的详细信息，请参阅下列其中一个链接：  
  
-   [如何配置基于 UEFI/GPT 的硬盘分区](http://go.microsoft.com/fwlink/?LinkID=272104)  
  
-   [如何配置基于 BIOS/MBR 的硬盘分区](http://go.microsoft.com/fwlink/?LinkId=272105)  
  
 要删除分区，请选择要删除的分区，然后单击“删除” 。  
  
##  <a name="BKMK_InstallApplication"></a> 安装应用程序  
 使用“安装应用程序”  任务序列步骤将应用程序作为任务序列的一部分进行安装。 此步骤可以安装任务序列步骤指定或任务序列变量动态列表指定的一组应用程序。 此步骤运行时，应用程序安装会立即开始而不等待策略轮询间隔。  
  
 安装的应用程序必须满足以下条件：  
  
-   应用程序的部署类型必须是 Windows Installer 或脚本安装程序。 不支持 Windows 应用程序包（.appx 文件）部署类型。  
  
-   它必须在本地系统帐户而非用户帐户下运行。  
  
-   它不得与桌面进行交互。 该程序必须无提示运行或在无人参与模式下运行。  
  
-   它本身不能启动重新启动。 该应用程序必须使用标准的重新启动代码（3010 退出代码）请求重新启动。 此代码可确保任务序列步骤正确地处理重新启动。 如果该应用程序不返回 3010 退出代码，则基础任务序列引擎执行重新启动。 重新启动后，任务序列自动继续。  
  
 当“安装应用程序”  步骤运行时，应用程序将检查应用程序部署类型的要求规则和检测方法的适用性。 根据此检查的结果，应用程序将安装适用的部署类型。 如果部署类型包含依赖关系，则对该依赖部署类型进行评估并将其作为安装应用程序步骤的一部分进行安装。 独立媒体不支持应用程序依赖关系。  
  
> [!NOTE]  
>  要安装取代另一应用程序的应用程序，被取代的应用程序的内容文件必须可用，否则任务序列步骤将失败。 例如，在客户端或捕获的映像中安装 Microsoft Visio 2010。 当运行“安装应用程序”任务序列步骤安装 Microsoft Visio 2013 时，Microsoft Visio 2010（被取代的应用程序）的内容文件必须在分发点上可用，否则该任务序列将失败。 未安装 Microsoft Visio 的客户端或捕获映像将完成 Microsoft Visio 2013 安装，而不会检查 Microsoft Visio 2010 内容文件。  
  
 此任务序列步骤仅可在标准操作系统中运行。 不可在 Windows PE 中运行。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   ：指定计算机意外重启时重试此步骤。 还可以指定重启后重试的次数。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 描述此步骤所采取操作的用户定义的短名。  
  
 **描述**  
 有关此步骤所采取操作的更详细信息。  
  
 **安装以下应用程序**  
 此设置指定按照对其指定的顺序进行安装的应用程序。  
  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将筛选出任何禁用的或具有以下设置的应用程序。 这些应用程序不会出现在“选择要安装的应用程序”  对话框中。  
  
-   仅当用户登录时  
  
-   使用用户权限运行  
  
 **根据动态变量列表安装应用程序**  
 此设置指定为集合或为计算机定义的一组任务序列变量的基本名称。 这些变量指定将为该集合或计算机安装的应用程序。 每个变量名称都由其通用的基名称和一个数字后缀（从 01 开始）组成。 每个变量的值都必须包含应用程序的名称，且没有其他任何内容。  
  
 对于要使用动态变量列表安装的应用程序，必须在应用程序的“属性”  对话框中的“常规”  选项卡中启用以下设置：“允许通过安装应用程序任务序列操作安装此应用程序，而不是手动部署”   
  
> [!NOTE]  
>  对于独立媒体部署，无法使用动态变量列表安装应用程序。  
  
 例如，要使用名为 AA01 的任务序列变量安装单个应用程序，需指定以下变量：  
  
|变量名称|变量值：|  
|-------------------|--------------------|  
|AA01|Microsoft Office|  
  
 要安装两个应用程序，需指定以下变量：  
  
|变量名称|变量值：|  
|-------------------|--------------------|  
|AA01|Microsoft Lync|  
|AA02|Microsoft Office|  
  
 以下条件将影响安装的东西：  
  
-   如果变量的值中包含应用程序名称之外的其他任何信息。 不安装该应用程序且任务序列继续。  
  
-   如果找不到具有指定基本名称和“01”后缀的变量，则不安装应用程序。 在任务序列步骤的“选项”选项卡上选择“出错时继续”时，该任务序列将在应用程序安装失败时继续。 如果未选择该设置，则任务序列失败且不会安装剩余的应用程序。  
  
 **如果应用程序失败，继续安装列表中的其他应用程序**  
 此设置指定在单个应用程序安装失败时该步骤继续。 如果指定了此设置，任务序列将不考虑返回的任何安装错误而继续。 如果未指定此设置，则在安装失败时任务序列将立即终止。  
  
##  <a name="BKMK_InstallDeploymentTools"></a> 安装部署工具  
 使用“安装部署工具”  任务序列步骤来安装包含 Sysprep 部署工具的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 包。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 描述此步骤所采取操作的用户定义的短名。  
  
 **描述**  
 有关此步骤所采取操作的更详细信息。  
  
 **Sysprep 包**  
 此设置指定包含以下操作系统的 Sysprep 部署工具的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 包：  
  
-   Windows XP SP3  
  
-   Windows XP X64 SP2  
  
-   Windows Server 2003 SP2  
  
##  <a name="BKMK_InstallPackage"></a> 安装包  
 使用“安装包”  任务序列步骤将软件作为任务序列的一部分进行安装。 此步骤运行时，安装会立即开始而不等待策略轮询间隔。  
  
 安装的软件必须满足以下条件：  
  
-   它必须在本地系统帐户而非用户帐户下运行。  
  
-   它不应与桌面进行交互。 该程序必须无提示运行或在无人参与模式下运行。  
  
-   它本身不能启动重新启动。 该软件必须使用标准的重新启动代码（3010 退出代码）请求重新启动。 此代码可确保任务序列步骤正确地处理重新启动。 如果该软件不返回 3010 退出代码，则基础任务序列引擎将执行重新启动。 重新启动后，该任务序列会自动继续。  
  
 部署操作系统时不支持使用“首先运行其他程序”  选项安装从属程序的程序。 如果为软件启用了“首先运行其他程序”  且其从属程序已在目标计算机上运行，则将运行从属程序且任务序列将继续。 但是，如果从属程序尚未在目标计算机上运行，则任务序列步骤将失败。  
  
> [!NOTE]  
>  管理中心站点并没有在执行任务序列期间启用软件分发代理所需的必要客户端配置策略。 当你在管理中心站点为任务序列创建独立媒体，而任务序列包含“安装包”  步骤时，CreateTsMedia.log 文件可能会出现以下错误：  
>   
>  `“WMI method SMS_TaskSequencePackage.GetClientConfigPolicies failed (0x80041001)”`  
>   
>  对于包含“安装包”步骤的独立媒体，必须在启用了软件分发代理的主站点上创建独立媒体，或者，必须在“安装 Windows 和 ConfigMgr”  步骤之后和第一个“安装包”  步骤之前添加一个“运行命令行”  步骤。 “运行命令行”  步骤运行 WMIC 命令，以便在第一个安装包步骤运行之前启用软件分发代理。 可以在“运行命令行”  任务序列步骤中使用以下命令：  
>   
>  **命令行**：**WMIC /namespace:\\\root\ccm\policy\machine\requestedconfig path ccm_SoftwareDistributionClientConfig CREATE ComponentName="Enable SWDist", Enabled="true", LockSettings="TRUE", PolicySource="local", PolicyVersion="1.0", SiteSettingsKey="1" /NOINTERACTIVE**  
>   
>  有关创建独立媒体的详细信息，请参阅[使用 System Center Configuration Manager 创建独立媒体](../LocTest/Create-stand-alone-media-with-System-Center-Configuration-Manager.md)。  
  
 此任务序列步骤仅可在标准操作系统中运行。 不可在 Windows PE 中运行。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 描述此步骤所采取操作的用户定义的短名。  
  
 **描述**  
 有关此步骤所采取操作的更详细信息。  
  
 **安装单个软件包**  
 此设置指定 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 软件包。 该步骤要等到安装完成后才开始。  
  
 **根据动态变量列表安装软件包**  
 此设置指定为集合或为计算机定义的一组任务序列变量的基本名称。 这些变量指定将为该集合或计算机安装的包。 每个变量名称都由其通用的基名称和一个数字后缀（从 001 开始）组成。 每个变量的值都必须包含包 ID 和软件名称，以冒号分隔。  
  
 对于要使用动态变量列表安装的软件，必须在包的“属性”  对话框中的“高级”  选项卡上启用以下设置：“允许在未部署的情况下从安装包任务序列中安装此应用程序”   
  
> [!NOTE]  
>  对于独立媒体部署，无法使用动态变量列表安装软件包。  
  
 例如，要使用名为 AA001 的任务序列变量安装单个软件包，需指定以下变量：  
  
|变量名称|变量值：|  
|-------------------|--------------------|  
|AA001|CEN00054:Install|  
  
 要安装两三个软件包，需指定以下变量：  
  
|变量名称|变量值：|  
|-------------------|--------------------|  
|AA001|CEN00054:Install|  
|AA002|CEN00107:Install Silent|  
|AA003|CEN00031:Install|  
  
 以下条件将影响安装的东西：  
  
-   如果变量的值未以正确的格式创建，或者未指定有效的应用程序 ID 和名称，则软件安装将失败。  
  
-   如果包 ID 含有小写字符，则该软件的安装将失败。  
  
-   如果未找到具有指定基本名称和“001”后缀的变量，将不安装任何软件包而任务序列将继续。  
  
 **如果软件包安装失败，则继续安装列表中的其他包**  
 此设置指定在单个软件包安装失败时该步骤继续。 如果指定了此设置，任务序列将不考虑返回的任何安装错误而继续。 如果未指定此设置，则在安装失败时任务序列将立即终止。  
  
##  <a name="BKMK_InstallSoftwareUpdates"></a> 安装软件更新  
 使用“安装软件更新”  任务序列在目标计算机上安装软件更新。 在运行此任务序列步骤时，才会评估目标计算机是否有适用的软件更新。 那时，会与其他 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]托管客户端一样评估目标计算机是否有合适的软件更新。 特别是，此步骤只会安装目标为计算机当前所属集合的软件更新。  
>  [!IMPORTANT]
>使用安装软件更新任务序列步骤时，强烈建议安装最新版的 Windows 更新代理以实现更好的性能。
>* 有关 Windows 7 的信息，请参阅[知识库文章 3161647](https://support.microsoft.com/kb/3161647)。
>* 有关 Windows 8 的信息，请参阅[知识库文章 3163023](https://support.microsoft.com/kb/3163023)。

 此任务序列步骤仅可在标准操作系统中运行。 不可在 Windows PE 中运行。 有关此任务序列操作的任务序列变量的信息，请参阅 [Install Software Updates Task Sequence Action Variables](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md#BKMK_InstallSoftwareUpdates)。

> [!NOTE]
>在“选项”选项卡中，可以将此任务序列配置为在计算机意外重启时重试。 例如，会自动重启计算机的软件更新安装。 从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 1602 开始，可以配置 SMSTSWaitForSecondReboot 变量以指定在安装软件更新时，重启计算机之后任务序列应暂停的时间长度（以秒为单位）。 有关详细信息，请参阅 [Task sequence built-in variables in System Center Configuration Manager](../LocTest/Task-sequence-built-in-variables-in-System-Center-Configuration-Manager.md)。

### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定计算机意外重启时重试此步骤。 还可以指定重启后重试的次数。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 描述此步骤所采取操作的用户定义的短名。  
  
 **描述**  
 有关此步骤所采取操作的更详细信息。  
  
 **安装要求 - 仅必需的软件更新**  
 选择此选项以为接收任务序列的目标计算机安装在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中被标记为必需的所有软件更新。 必需的软件更新具有管理员定义的安装截止时间。  
  
 **可供安装 - 所有软件更新**  
 选择此选项可以安装以将接收任务序列的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 集合为目标的所有可用软件更新。 所有可用的软件更新都将安装在目标计算机上。  
 
 **根据缓存的扫描结果评估软件更新**  
从 Configuration Manager 版本 1606 开始，可以选择对软件更新执行完全扫描，而不是使用缓存的扫描结果。 默认情况下，任务序列使用缓存的结果。 你可以清除复选框，使客户端连接到软件更新点以处理和下载最新的软件更新目录。 当使用一个任务序列来[捕获和生成操作系统映像](../LocTest/Create-a-task-sequence-to-capture-an-operating-system-in-System-Center-Configuration-Manager.md)时，建议选择此选项。因为其中将有大量的软件更新，尤其是许多软件更新都具有依赖关系（需要安装 X 才会在适用情况下显示 Y）。 当清除此设置并将任务序列部署到大量客户端时，它们将同时连接到的软件更新点。 这可能会在目录处理和下载过程中导致性能问题。 在大多数情况下，建议使用默认设置。

Configuration Manager 版本 1606 中引入了一个新的任务序列变量 SMSTSSoftwareUpdateScanTimeout，以使你能够控制安装软件更新任务序列步骤中的软件更新扫描的超时时间。 默认值为 30 分钟。 有关详细信息，请参阅 [Task sequence built-in variables in System Center Configuration Manager](../LocTest/Task-sequence-built-in-variables-in-System-Center-Configuration-Manager.md)。 

  
##  <a name="BKMK_JoinDomainorWorkgroup"></a> 加入域或工作组  
 使用“加入域或工作组”  任务序列步骤将目标计算机添加到工作组或域中。  
  
 此任务序列步骤仅可在标准操作系统中运行。 不可在 Windows PE 中运行。 有关此任务序列操作的任务序列变量的信息，请参阅 [Join Domain or Workgroup Task Sequence Action Variables](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md#BKMK_JoinDomainWorkgroup)。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 描述此步骤所采取操作的用户定义的短名。  
  
 **描述**  
 有关此步骤所采取操作的更详细信息。  
  
 **加入工作组**  
 选择此选项，使目标计算机加入指定的工作组。 如果计算机当前是某个域的成员，选择此选项将导致计算机重新启动。  
  
 **加入域**  
 选择此选项以将目标计算机加入指定的域。  
  
 （可选）在指定的域中输入或浏览查找计算机要加入的组织单位 (OU)。 如果计算机当前是某个其他域或某个工作组的成员，此操作将导致计算机重新启动。 如果计算机已经是某个其他组织单位的成员，Active Directory 域服务不允许你更改组织单位，且此设置将被忽略。  
  
 **输入有权限加入域的帐户**  
 单击“设置”  以输入有权限加入域的帐户和密码。 帐户必须按下列格式输入：  
  
 *域\帐户*  
  
##  <a name="BKMK_PrepareConfigMgrClientforCapture"></a> 准备 ConfigMgr 客户端以便捕获  
 通过执行以下任务，使用“准备 ConfigMgr 客户端以便捕获”  步骤来获取引用计算机上的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端，并准备该客户端以便在映像进程期间进行捕获：  
  
-   从 Windows 目录的 smscfg.ini 文件中删除客户端配置属性部分。 这些属性包括客户端特定信息，如 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] GUID 及其他客户端标识符。  
  
-   删除所有 SMS 或 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 计算机证书。  
  
-   删除 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端缓存。  
  
-   清除 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端的已分配的站点变量。  
  
-   删除所有本地 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 策略。  
  
-   删除 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端的受信任根密钥。  
  
 此任务序列步骤仅可在标准操作系统中运行。 不可在 Windows PE 中运行。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 描述此步骤所采取操作的用户定义的短名。  
  
 **描述**  
 有关此步骤所采取操作的更详细信息。  
  
##  <a name="BKMK_PrepareWindowsforCapture"></a> 准备 Windows 以便捕获  
 使用“准备 Windows 以便捕获”  任务序列步骤指定在引用计算机上捕获操作系统映像时要使用的 Sysprep 选项。 此任务序列操作运行 Sysprep，然后将计算机重新启动到为该任务序列指定的 Windows PE 启动映像。 要使此操作成功完成，引用计算机不可加入域。  
  
 此任务序列步骤仅可在标准操作系统中运行。 不可在 Windows PE 中运行。 有关此任务序列操作的任务序列变量的信息，请参阅 [Prepare Windows for Capture Task Sequence Action Variables](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md#BKMK_PrepareWindowsCapture)。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 描述此步骤所采取操作的用户定义的短名。  
  
 **描述**  
 有关此步骤所采取操作的更详细信息。  
  
 **自动生成大容量存储驱动程序列表**  
 选择此选项以便 Sysprep 从引用计算机自动生成大容量存储驱动程序列表。 此选项在引用计算机上的 sysprep.inf 文件中启用“生成大容量存储驱动程序”选项。 有关此设置的详细信息，请参阅 Sysprep 文档。  
  
 **不重置激活标志**  
 选择此选项以阻止 Sysprep 重置产品激活标志。  
  
##  <a name="BKMK_PreProvisionBitLocker"></a> 预设置 BitLocker  
 在 Windows PE 中，使用“预设置 BitLocker”  任务序列步骤可在驱动器上启用 BitLocker。 由于仅加密使用的磁盘空间，因此加密时间要短得多。 安装操作系统后，使用 [启用 BitLocker](#BKMK_EnableBitLocker) 任务序列步骤应用密钥管理选项。 此步骤仅可在 Windows PE 中运行。 不能在标准操作系统中运行。  
  
> [!IMPORTANT]  
>  若要预设置 BitLocker，至少需要安装 Windows 7 操作系统，并且计算机上必须支持且启用 TPM。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 指定描述此步骤中执行的操作的用户定义的短名。  
  
 **描述**  
 指定有关此步骤所采取操作的详细信息。  
  
 **将 BitLocker 应用于指定的驱动器**  
 指定要为其启用 BitLocker 的驱动器。 仅加密驱动器上使用的空间。  
  
 **对于没有 TPM 或 未启用 TPM 的计算机跳过此步骤**  
 选择此选项以在计算机硬件不支持 TPM 或未启用 TPM 时跳过驱动器加密。 例如，可在将操作系统部署到虚拟机时使用此选项。  
  
##  <a name="BKMK_ReleaseStateStore"></a> 和“发布状态存储”  
 使用“发布状态存储”  任务序列步骤通知状态迁移点捕获或还原操作已完成。 此步骤与“请求状态存储” 、“捕获用户状态” 和“还原用户状态”  任务序列步骤一起使用，以使用状态迁移点和用户状态迁移工具 (USMT) 迁移用户状态数据。  
  
 有关部署操作系统时管理用户状态的详细信息，请参阅[在 System Center Configuration Manager 中管理用户状态](../LocTest/Manage-user-state-in-System-Center-Configuration-Manager.md)。  
  
 如果你在“请求状态存储”   任务序列步骤中请求访问状态迁移点以捕获用户状态，此步骤将通知状态迁移点捕获过程已完成，且用户状态数据可供还原。 状态迁移点设置已捕获状态的访问控制权限，以便只能通过还原计算机来只读访问此状态。  
  
 如果你在“请求状态存储”  任务序列步骤中请求访问状态迁移点以还原用户状态，此任务序列步骤通知状态迁移点还原过程已完成。 此时将激活你为状态迁移点配置的保持设置。  
  
> [!IMPORTANT]  
>  最好你在“请求状态存储”  步骤和“发布状态存储”  步骤之间的任何任务序列步骤中设置“出错时继续”  ，以使每个“请求状态存储”  任务序列操作都有一个相匹配的“发布状态存储”  任务序列操作。  
  
 此任务序列步骤仅可在标准操作系统中运行。 不可在 Windows PE 中运行。 有关此任务序列操作的任务序列变量的信息，请参阅 [Release State Store Sequence Action Variables](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md#BKMK_ReleaseStateStore)。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 描述此步骤所采取操作的用户定义的短名。  
  
 **描述**  
 有关此步骤所采取操作的更详细信息。  
  
##  <a name="BKMK_RequestStateStore"></a> 任务序列步骤与“请求状态存储”  
 使用“请求状态存储”  任务序列步骤在从计算机捕获状态或将状态还原到计算机时请求访问状态迁移点。  
  
 有关部署操作系统时管理用户状态的详细信息，请参阅[在 System Center Configuration Manager 中管理用户状态](../LocTest/Manage-user-state-in-System-Center-Configuration-Manager.md)。  
  
 可将“请求状态存储”  任务序列步骤与“发布状态存储” 、“捕获用户状态” 和“还原用户状态”  任务序列步骤结合使用，以使用状态迁移点和用户状态迁移工具 (USMT) 迁移计算机状态。  
  
> [!NOTE]  
>  如果你刚刚建立新的状态迁移点站点角色 (SMP)，最长可能一个小时之后才可用于用户状态存储。 要促进 SMP 的可用性，你可以调整任何状态迁移点属性设置以触发站点控制文件更新。  
  
 对于脱机 USMT，此任务序列步骤仅可在标准操作系统和 Windows PE 中运行。 有关此任务序列操作的任务序列变量的信息，请参阅 [Request State Store Task Sequence Action Variables](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md#BKMK_RequestState)。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 描述此步骤所采取操作的用户定义的短名。  
  
 **描述**  
 有关此步骤所采取操作的更详细信息。  
  
 **从计算机捕获状态**  
 查找满足在状态迁移点设置中配置的最低要求（最大客户端数和最小可用磁盘空间）的状态迁移点，但并不保证在状态迁移时有足够的空间可供使用。 选择此选项将请求访问状态迁移点，以便从计算机捕获用户状态和设置。  
  
 如果 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点已启用多个状态迁移点，此任务序列步骤将查找具有可用磁盘空间的状态迁移点，方法是查询该站点的管理点，获取状态迁移点列表，然后评估每个状态迁移点，直到找到满足最低要求的状态迁移点为止。  
  
 **从另一台计算机还原状态**  
 选择此选项来请求访问状态迁移点，以便将先前捕获的用户状态和设置还原到目标计算机。  
  
 如果 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点具有多个状态迁移点，此任务序列步骤将查找具有为目标计算机存储的计算机状态的状态迁移点。  
  
 **重试次数**  
 此任务序列步骤在失败之前将尝试查找适当的状态迁移点的次数。  
  
 **重试延迟（秒）**  
 任务序列步骤在重试尝试之间等待的秒数。  
  
 **如果计算机帐户无法连接到状态存储，请使用网络访问帐户。**  
 指定如果 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端无法使用计算机帐户访问 SMP 状态存储， [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 网络访问帐户凭据将用于连接到状态迁移点。 此选项的安全性较低，因为其他计算机可能使用该网络访问帐户访问你的已存储状态，但如果目标计算机不可加入域，则可能需要此选项。  
  
##  <a name="BKMK_RestartComputer"></a> 重启计算机  
 使用“重新启动计算机”  任务序列步骤重新启动运行该任务序列的计算机。 重新启动之后，计算机将自动地继续运行任务序列中的下一个步骤。  
  
 标准操作系统或 Windows PE 中均可运行此步骤。 有关此任务序列操作的任务序列变量的详细信息，请参阅 [Restart Computer Task Sequence Action Variables](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md#BKMK_RestartComputer)。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 描述此步骤所采取操作的用户定义的短名。  
  
 **描述**  
 有关此步骤所采取操作的更详细信息。  
  
 **分配给此任务序列的启动映像**  
 对目标计算机选择此选项以使用分配给该任务序列的启动映像。 启动映像将用来运行在 Windows PE 中运行的后续任务序列步骤。  
  
 **当前安装的默认操作系统**  
 对目标计算机选择此选项以重新启动到安装的操作系统。  
  
 **重新启动之前通知用户**  
 选择此选项以向用户显示目标计算机将重新启动的通知。 默认情况下选择此选项。  
  
 **通知消息**  
 输入在目标计算机重新启动之前向用户显示的通知消息。  
  
 **消息显示超时**  
 指定在目标计算机重新启动之前给定用户的时间（秒）。 默认时间为 60 秒。  
  
##  <a name="BKMK_RestoreUserState"></a> 还原用户状态  
 使用  “还原用户状态”任务序列步骤来启动用户状态迁移工具 (USMT) 将用户状态和设置还原到目标计算机。 此任务序列步骤与“捕获用户状态”  任务序列步骤配合使用。  
  
 有关部署操作系统时管理用户状态的详细信息，请参阅[在 System Center Configuration Manager 中管理用户状态](../LocTest/Manage-user-state-in-System-Center-Configuration-Manager.md)。  
  
 如果你想要将状态设置保存到 **站点中的状态迁移点或从其还原设置，你还可以将“还原用户状态”****任务序列步骤与“请求状态存储”****和“发布状态存储”**[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 任务序列步骤一起使用。 通过 USMT 3.0 和更高版本，此选项始终使用由 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]生成并管理的加密密钥解密 USMT 状态存储。  
  
  “还原用户状态”任务序列步骤提供对最常用 USMT 选项的受限子网的控制。 其他命令行选项可使用 OSDMigrateAdditionalRestoreOptions 任务序列变量指定。  
  
> [!IMPORTANT]  
>  如果使用“还原用户状态”  任务序列步骤执行与操作系统部署方案无关的任务，请在紧随“还原用户状态” [](#BKMK_RestartComputer) 任务序列步骤之后添加 **Restart Computer** 任务序列步骤。  
  
 此任务序列步骤仅可在标准操作系统中运行。 不可在 Windows PE 中运行。 有关此任务序列操作的任务序列变量的信息，请参阅 [Restore User State Task Sequence Action Variables](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md#BKMK_RestoreUserState)。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 指定描述此步骤中执行的操作的用户定义的短名。  
  
 **描述**  
 指定有关此步骤所采取操作的更详细信息。  
  
 **用户状态迁移工具包**  
 输入包含 USMT 版本的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 包，供此步骤在还原用户状态和设置时使用。 此包不需要程序。 当任务序列步骤运行时，任务序列将使用指定的包中的 USMT 版本。 根据你正在还原状态到的操作系统的体系结构，指定包含 32 位或 x64 版本的 USMT 的包。  
  
 **使用标准选项还原所有捕获的用户配置文件**  
 使用标准选项还原捕获的用户配置文件。 要自定义将还原的选项，请选择“自定义用户配置文件捕获” 。  
  
 **自定义如何还原用户配置文件**  
 允许你自定义想要还原到目标计算机的文件。 单击  “文件”以指定想要用于还原用户配置文件的 USMT 包中的配置文件。 要添加配置文件，请在“文件名”  框中输入文件的名称，然后单击“添加” 。 将用于该操作的配置文件列出在“文件”窗格中。 你指定的 .xml 文件定义将还原的用户文件。  
  
 **还原本地计算机用户配置文件**  
 还原本地计算机用户（即非域用户）配置文件。 由于不能迁移原始本地用户帐户密码，你将需要对还原的本地用户帐户分配新密码。 在“密码”  框中输入新密码，然后在“确认密码”  框中确认该密码。  
  
 **如果无法还原某些文件则继续**  
 即使无法还原某些文件，也继续还原用户状态和设置。 默认情况下会启用此选项。 如果你禁用此选项并且在还原文件时遇到错误，任务序列步骤将会立即以故障结束，并且将无法还原所有文件。  
  
 **启用详细日志记录**  
 启用此选项以生成更详细的日志文件信息。 当还原状态时，将生成日志 Loadstate.log 并默认存储在 \windows\system32\ccm\logs 文件夹的任务序列日志文件夹中。  
  
##  <a name="BKMK_RunCommandLine"></a> 运行命令行  
 使用“运行命令行”  任务序列步骤来运行指定命令行。  
  
 标准操作系统或 Windows PE 中均可运行此步骤。 有关此任务序列操作的任务序列变量的信息，请参阅 [Run Command Line Task Sequence Action Variables](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md#BKMK_RunCommand)。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 指定描述所运行命令行的用户定义的短名称。  
  
 **描述**  
 指定与所运行命令行有关的更多详细信息。  
  
 **命令行**  
 指定所运行的命令行。 此字段为必需字段。 最好包括文件扩展名，例如 .vbs 和 .exe。 包括所有必需的设置文件、命令行选项或开关。  
  
 如果文件名没有指定文件扩展名，则 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 会尝试查找 .com、.exe 和 .bat。 如果文件扩展名不是可执行文件，则 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 会尝试应用本地关联。 例如，如果命令行为 readme.gif，则 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 会启动目标计算机上指定的应用程序来打开 .gif 文件。  
  
 例如：  
  
 **setup.exe /a**  
  
 **cmd.exe /c copy Jan98.dat c:\sales\Jan98.dat**  
  
> [!NOTE]  
>  必须优先执行输出重定向、管道或复制等命令行操作（如上例所述）， **cmd.exe /c** 命令才能成功运行。  
  
 **禁用 64 位文件系统重定向**  
 默认情况下，在 64 位操作系统上运行时，使用 WOW64 文件系统重定向程序查找并运行命令行中的可执行文件，以便找到 32 位版本的操作系统可执行文件和 DLL。  选择此选项将禁用 WOW64 文件系统重定向程序，以便可以找到本机 64 位版本的操作系统可执行文件和 DLL。  在 32 位操作系统上运行时，选择此选项没有任何作用。  
  
 **开始于**  
 指定程序的可执行文件夹，最多 127 个字符。 此文件夹可以是目标计算机上的绝对路径，也可以是包含包的分发点文件夹的相对路径。 此字段是可选的。  
  
 例如：  
  
 **c:\officexp**  
  
 **i386**  
  
> [!NOTE]  
>  “浏览”  按钮浏览本地计算机上的文件和文件夹，因此你以此方式选择的任何内容还必须存储在目标计算机上的相同位置，并且具有相同的文件和文件夹名称。  
  
 **包**  
 当在命令行上指定了目标计算机上尚不存在的文件或程序时，请选择此选项以指定包含合适的文件的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 包。 此包不需要程序。 如果指定的文件在目标计算机上，则不需要此选项。  
  
 **超时**  
 指定表示 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将允许命令行运行的时间长度的值。 此值的范围为 10 分钟至 999 分钟。 默认值为 15 分钟。  
  
 默认情况下禁用此选项。  
  
> [!IMPORTANT]  
>  如果你输入的值使得“运行命令行”任务序列步骤没有足够的时间成功完成，该任务序列步骤将失败，整个任务序列也可能因为其他控制设置而失败。 如果超时过期， [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将终止命令行进程。  
  
 **作为以下帐户运行此步骤**  
 指定作为本地系统帐户之外的其他 Windows 用户帐户运行的命令行。  
  
> [!NOTE]  
>  当你在操作系统安装步骤之后为此步骤指定了另一帐户，则必须将该帐户添加到计算机后才能运行简单脚本或命令，且必须还原 Windows 用户帐户的配置文件才能运行 MSI 等更复杂的程序。  
  
 **帐户**  
 为任务序列中的命令行任务指定此操作要运行的运行方式 Windows 用户帐户。 命令行将使用指定帐户的权限运行。 单击“设置”  以指定本地用户或域帐户。  
  
> [!IMPORTANT]  
>  如果指定用户帐户的“运行命令行”  任务序列操作在 Windows PE 中执行，则该操作可能失败，因为 Windows PE 无法加入域。 该失败将记录在 smsts.log 文件中。  
  
##  <a name="BKMK_RunPowerShellScript"></a> 运行 PowerShell 脚本  
 使用“运行 PowerShell 脚本”  任务序列步骤运行指定的 PowerShell 脚本。  
  
 标准操作系统或 Windows PE 中均可运行此步骤。 若要在 Windows PE 中运行此步骤，必须在启动映像中启用 PowerShell。 你可以从启动映像属性中的“可选组件”  选项卡中启用 Windows PowerShell (WinPE-PowerShell)。 有关如何修改启动映像的详细信息，请参阅 [Manage boot images with System Center Configuration Manager](../LocTest/Manage-boot-images-with-System-Center-Configuration-Manager.md)。  
  
> [!NOTE]  
>  默认情况下，Windows Embedded 操作系统上未启用 PowerShell。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 指定描述所运行命令行的用户定义的短名称。  
  
 **描述**  
 指定与所运行命令行有关的更多详细信息。  
  
 **包**  
 指定包含 PowerShell 脚本的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 包。 一个包可以包含多个 PowerShell 脚本。  
  
 **脚本名称**  
 指定要运行的 PowerShell 脚本的名称。 此字段为必需字段。  
  
 **参数**  
 指定要传递给 Windows PowerShell 脚本的参数。 配置参数，就好像你正将它们从命令行添加到 Windows PowerShell 脚本一样。  
  
> [!IMPORTANT]  
>  提供脚本使用的参数，而不是为 Windows PowerShell 命令行。  
>   
>  以下示例包含有效的参数：  
>   
>  **-MyParameter1 MyValue1 -MyParameter2 MyValue2**  
>   
>  以下示例包含无效的参数。 粗体项是 Windows PowerShell 命令行参数 (-nologo and –executionpolicy unrestricted)，未被脚本使用。  
>   
>  **-nologo-executionpolicy unrestricted-File MyScript.ps1 -MyParameter1 MyValue1 -MyParameter2 MyValue2**  
  
 **PowerShell 执行策略**  
 选择 PowerShell 执行策略，你可确定允许哪些 Windows PowerShell 脚本（如果有）在计算机上运行。 选择以下其中一个执行策略：  
  
-   **AllSigned：**只能运行由受信任的发布者签发的脚本。  
  
-   **未定义：**未定义执行策略。 。  
  
-   **绕过：**加载所有配置文件并运行所有脚本。 如果运行从 Internet 下载的未签名脚本，在其运行前将不提示可允许。  
  
> [!IMPORTANT]  
>  PowerShell 1.0 不支持未定义和旁路执行策略。  
  
##  <a name="BKMK_SetDynamicVariables"></a> 设置动态变量  
 使用“设置动态变量”  任务序列步骤执行以下操作：  
  
1.  从计算机和它所在的环境中收集信息，然后使用该信息设置指定的任务序列变量。  
  
2.  评估定义的规则，并根据为评估结果为 true 的规则配置的变量和值设置任务序列变量。  
  
 任务序列自动设置以下只读任务序列变量：  
  
-   _SMSTSMake  
  
-   _SMSTSModel  
  
-   _SMSTSMacAddresses  
  
-   _SMSTSIPAddresses  
  
-   _SMSTSSerialNumber  
  
-   _SMSTSAssetTag  
  
-   _SMSTSUUID  
  
 标准操作系统或 Windows PE 中均可运行此步骤。 有关任务序列变量的详细信息，请参阅 [System Center Configuration Manager 中的任务序列操作变量](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md)。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 此任务序列步骤的用户定义的短名称。  
  
 **描述**  
 有关此步骤所采取操作的更详细信息。  
  
 **动态规则和变量**  
 若要设置动态变量以在任务序列中使用，可以添加一条规则，然后为你为规则指定的每个变量指定一个值，或者添加一个或多个变量进行设置，而不添加规则。 添加规则时，可以从以下规则类别中进行选择：  
  
-   **计算机：**使用此规则类别可评估资产标记、UUID、序列号或 MAC 地址的值。 你可以设置多个值，如果任何一个值为 true，则该规则将评估为 true。 例如，如果序列号是 5892087，无论 MAC 地址是否等于 26-78-13-5A-A4-22，以下规则都将评估为 true。  
  
     `IF Serial Number = 5892087 OR MAC address = 26-78-13-5A-A4-22 THEN`  
  
-   **位置：**使用此规则类别可评估默认网关的值。  
  
-   **品牌和型号：**使用此规则类别可评估计算机的品牌和型号的值。 品牌和型号均必须评估为 true，规则才能评估为 true。  
  
-   **任务序列变量：**使用此规则类别可添加要评估的任务序列变量、条件和值。 当为变量设置的值符合指定条件时，规则评估为 true。  
  
 你可以指定将为评估为 true 的规则设置的一个或多个变量，或者设置变量而不使用规则。 你可以从现有变量选择或创建自定义变量。  
  
-   **现有任务序列变量：**使用此设置可从现有任务序列变量的列表中选择一个或多个变量。 不可选择数组变量。  
  
-   **自定义任务序列变量：**使用此设置可定义自定义任务序列变量。 你也可指定现有任务序列变量。 这有助于指定现有变量数组，如 OSDAdapter，因为变量数组不在现有任务序列变量的列表中。  
  
 为规则选择变量后，必须为每个变量提供一个值。 规则评估为 true 时，则变量设置为指定的值。 对于每个变量，可以选择“机密值”  来隐藏该变量的值。 默认情况下，某些现有变量隐藏值，例如 OSDCaptureAccountPassword 任务序列变量。  
  
> [!IMPORTANT]  
>  使用“设置动态变量”步骤导入任务序列并为变量的值选择“机密值”  时，导入该任务序列时将删除该值。 因此，导入任务序列后你必须重新输入动态变量的值。  
  
##  <a name="BKMK_SetTaskSequenceVariable"></a> 设置任务序列变量  
 使用“设置任务序列变量”  任务序列步骤来设置与该任务序列配合使用的变量的值。  
  
 标准操作系统或 Windows PE 中均可运行此步骤。 任务序列变量由任务序列操作读取，并指定这些操作的行为。 有关特定任务序列变量的详细信息，请参阅 [System Center Configuration Manager 中的任务序列操作变量](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md)。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 此任务序列步骤的用户定义的短名称。  
  
 **描述**  
 有关此步骤所采取操作的更详细信息。  
  
 **任务序列变量：**  
 任务序列变量的用户定义的名称。  
  
 **值**  
 与任务序列变量相关联的值。 此值可以是 %<varname\>% 语法中的另一个任务序列变量。  
  
##  <a name="BKMK_SetupWindowsandConfigMgr"></a> 安装 Windows 和 ConfigMgr  
 使用“安装 Windows 和 ConfigMgr”  任务序列步骤执行从 Windows PE 到新操作系统的转移。 此任务序列步骤是在部署任何操作系统时都必需的部分。 该步骤会将 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端安装到新操作系统中，并为任务序列在新操作系统中继续执行做好准备。  
  
 此步骤仅可在 Windows°PE 中运行。 不能在标准操作系统中运行。 有关此任务序列操作的任务序列变量的详细信息，请参阅 [Setup Windows and ConfigMgr Task Sequence Action Variables](../LocTest/Task-sequence-action-variables-in-System-Center-Configuration-Manager.md#BKMK_SetupWindows)。  
  
 “安装 Windows 和 ConfigMgr”  任务序列操作将使用 Windows°PE 安装目录 X:\Windows 替换 sysprep.inf 或 unattend.xml 目录变量，例如 %WINDIR% 和 %ProgramFiles%。 使用这些环境变量指定的任务序列变量将被忽略。  
  
 使用此任务序列步骤来执行以下操作：  
  
1.  初步操作：Windows°PE  
  
    1.  在 unattend.xml 文件中执行任务序列变量替换。  
  
    2.  下载包含 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端的包，并将其放入部署的映像中。  
  
2.  设置 Windows  
  
    1.  基于映像的安装。  
  
        1.  禁用映像中的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端（即，禁用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端服务的自动启动功能）。  
  
        2.  更新已部署映像中的注册表，确保已部署的操作系统使用与引用计算机上相同的驱动器号启动。  
  
        3.  在已部署的操作系统中重新启动。  
  
        4.  Windows 最小化安装使用先前指定的已禁用所有最终用户交互的 sysprep.inf 或 unattend.xml 文件运行。 如果“应用网络设置”  指定为加入域，则该信息位于 sysprep.inf 或 unattend.xml 文件中，且 Windows 最小化安装执行域加入操作。  
  
    2.  基于 Setup.exe 的安装。  运行 Setup.exe 会执行典型的 Windows 安装过程：  
  
        1.  将在前面的“应用操作系统”  任务序列中指定的操作系统安装包复制到硬盘驱动器。  
  
        2.  在新部署的操作系统中重新启动。  
  
        3.  Windows 最小化安装使用先前指定的已禁用所有用户界面的 sysprep.inf 或 unattend.xml 文件运行。 如果“应用网络设置”  指定为加入域，则该信息位于 sysprep.inf 或 unattend.xml 文件中，且 Windows 最小化安装执行域加入操作。  
  
3.  安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端  
  
    1.  Windows 最小化安装结束后，任务序列将使用 setupcomplete.cmd 继续运行。  
  
    2.  根据在“应用 Windows 设置”  步骤中选择的选项，启用或禁用本地管理员帐户。  
  
    3.  使用先前下载的包 (1.b) 以及在“任务序列编辑器”中指定的安装属性，安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端。 客户端以“设置模式”进行安装，以防止它在任务序列完成之前处理新策略请求。  
  
    4.  等待客户端完全可以操作。  
  
    5.  如果计算机在启用了网络访问保护的环境中运行，客户端将检查是否存在任何所需的更新并进行安装，以便所需的全部更新在任务序列继续运行之前均已存在。  
  
4.  任务序列继续运行下一个步骤。  
  
> [!NOTE]  
>   “安装 Windows 和 ConfigMgr”任务序列操作负责运行新安装计算机上的组策略。 组策略在任务序列完成后应用。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   如果在运行该步骤时出现错误，请勿选择继续执行任务序列。 如果出现错误，无论是否选择此设置，任务序列都将失败。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 指定描述此步骤中执行的操作的用户定义的短名。  
  
 **描述**  
 指定有关在此步骤中采取的操作的其他信息。  
  
 **客户端包**  
 指定此任务序列步骤将使用的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端安装包。 单击“浏览”  ，并选择你想要用来安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端的客户端安装包。  
  
 **如果可用，使用预生产客户端包**  
 指定如有可用的预生产客户端包，则任务序列步骤将使用此包而非生产客户端包。 通常情况下，预生产客户端是在生产环境中进行测试的较新版本。 单击“浏览”  ，并选择想用于安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端的预生产客户端安装包。  
  
 **安装属性**  
 站点分配和默认配置由任务序列操作自动指定。 你可以使用此字段来指定安装客户端时使用的任何其他安装属性。 要输入多个安装属性，请使用空格分隔。  
  
 你可以指定要在客户端安装过程中使用命令行选项。 例如，你可以输入 **/skipprereq: silverlight.exe** 以通知 CCMSetup.exe 不安装 Microsoft Silverlight 必备组件。 有关 CCMSetup.exe 的可用命令行选项的详细信息，请参阅 [About client installation properties in System Center Configuration Manager](../LocTest/About-client-installation-properties-in-System-Center-Configuration-Manager.md)。  
  
##  <a name="BKMK_UpgradeOS"></a> 升级操作系统  
 使用“升级操作系统”  任务序列步骤将现有的 Windows 7、Windows 8、Windows 8.1 或 Windows 10 操作系统升级到 Windows 10。  
  
 此任务序列步骤仅可在标准操作系统中运行。 不可在 Windows PE 中运行。  
  
### 详细信息  
 在此步骤的“属性”  选项卡上，可以配置此部分描述的设置。  
  
 此外，使用“选项”  选项卡可执行以下操作：  
  
-   禁用该步骤。  
  
-   指定在运行该步骤时若出现错误，任务序列是否继续。  
  
-   指定运行步骤必须满足的条件。  
  
 **Name**  
 描述此步骤所采取操作的用户定义的短名。  
  
 **描述**  
 有关此步骤所采取操作的更详细信息。  
  
 **升级包**  
 选择此选项以指定用于升级的 Windows 10 操作系统升级包。  
  
 **源路径**  
 指定要使用的 Windows 10 媒体的本地路径或网络路径（对应于 /installFrom 命令行选项）。 还可以指定一个变量，例如 %mycontentpath% 或 %DPC01%。 将变量用作源路径时，必须在任务序列中提前指定。 例如，如果在任务序列中使用 [下载包内容](#BKMK_DownloadPackageContent) 步骤，可以为操作系统升级包的位置指定一个变量。 然后，可在此步骤中将该变量用作源路径。  
  
 **版本**  
 指定要用于升级的操作系统媒体的版本。  
  
 **产品密钥**  
 指定要用于升级过程的产品密钥  
  
 **在升级过程中向 Windows 安装程序提供以下驱动程序内容**  
 选择此设置在升级过程中将驱动程序添加到目标计算机中（对应于 /InstallDriver 命令行选项）。 驱动程序必须与 Windows 10 兼容。 指定下列选项之一：  
  
-   **驱动程序包：**单击“浏览”  并从列表中选择现有的驱动程序包。  
  
-   **暂存内容：**选择此选项以指定驱动程序包的位置。 可以指定本地文件夹、网络路径或任务序列变量。 将变量用作源路径时，必须在任务序列中提前指定。 例如，通过使用 [Download Package Content](../LocTest/Task-sequence-steps-in-System-Center-Configuration-Manager.md#BKMK_DownloadPackageContent) 步骤。  
  
 **超时（分钟）**  
 指定在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 使任务序列步骤失败之前，安装程序必须运行的分钟数。  
  
 **不启动升级而执行 Windows 安装程序兼容性扫描**  
 指定不启动升级过程而执行 Windows 安装程序兼容性扫描（对应于 Compat ScanOnly 命令行选项）。 使用此选项时，仍必须部署整个安装源。 安装程序将退出代码作为扫描结果返回。 下表提供了一些常见的退出代码。  
  
|||  
|-|-|  
|MOSETUP_E_COMPAT_SCANONLY (0xC1900210)|不存在兼容性问题（“成功”）。|  
|MOSETUP_E_COMPAT_INSTALLREQ_BLOCK (0xC1900208)|可操作的兼容性问题。|  
|MOSETUP_E_COMPAT_MIGCHOICE_BLOCK (0xC1900204)|所选的迁移选项不可用。 例如，从 Enterprise 升级到 Professional。|  
|MOSETUP_E_COMPAT_SYSREQ_BLOCK (0xC1900200)|不适合 Windows 10。|  
|MOSETUP_E_COMPAT_INSTALLDISKSPACE_BLOCK (0xC190020E)|可用磁盘空间不足。|  
  
 有关此参数的详细信息，请参阅 [Windows 安装程序命令行选项](https://msdn.microsoft.com/library/windows/hardware/dn938368\(v=vs.85\).aspx)  
  
 **忽略任何不重要的兼容性消息**  
 指定安装程序完成安装，忽略任何不重要的兼容性消息（对应于 /Compat IgnoreWarning 命令行选项）。  
  
 **通过 Windows Update 动态更新 Windows 安装程序**  
 指定安装程序是否执行动态更新操作，如搜索、下载和安装更新（对应于 /DynamicUpdate 命令行选项）。 此设置与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 软件更新不兼容，但使用 WSUS（独立）或 Windows Update 来处理更新时可启用它。  
  
 **替代策略并使用默认的 Microsoft Update：**选择此设置以实时临时替代本地策略，运行动态更新操作，并让计算机从 Windows Update 中获取更新。  
  
## 另请参阅  
 [System Center Configuration Manager 的操作系统部署技术参考](../LocTest/Operating-system-deployment-technical-reference-for-System-Center-Configuration-Manager.md)
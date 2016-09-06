---
title: "创建任务序列来升级 System Center Configuration Manager 中的操作系统"
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
ms.assetid: 7591e386-a9ab-4640-8643-332dce5aa006
caps.latest.revision: 12
caps.handback.revision: 7
translationtype: Human Translation
---
# 创建任务序列来升级 System Center Configuration Manager 中的操作系统
在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中使用任务序列将目标计算机上的操作系统从 Windows 7 或更高版本升级到 Windows 10。 你创建一个任务序列，该任务序列引用要安装在目标计算机上的操作系统映像，以及要安装的任何其他附加内容（例如应用程序或软件更新）。 用于升级操作系统的任务序列属于[使用 System Center Configuration Manager 将 Windows 升级到最新版本](../LocTest/Upgrade-Windows-to-the-latest-version-with-System-Center-Configuration-Manager.md)方案的一部分。  
  
##  <a name="BKMK_UpgradeOS"></a> 创建用于升级操作系统的任务序列  
 若要将计算机上的操作系统升级到 Windows 10，你可以创建一个任务序列，并在“创建任务序列向导”中选择**从升级包升级操作系统**。 该向导将添加一些步骤，用于升级操作系统、应用软件更新和安装应用程序。 在创建任务序列之前，必须部署以下内容：  
  
-   **必需**  
  
     Windows 10 [操作系统升级包](https://technet.microsoft.com/library/mt627916\(TechNet.10\).aspx)必须在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中可用。  
  
-   **必需（若使用）**  
  
     在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，[软件更新](https://technet.microsoft.com/library/mt612804\(TechNet.10\).aspx)必须同步。  
  
     [应用程序](https://technet.microsoft.com/library/mt595707\(TechNet.10\).aspx)必须添加到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台。  
  
#### 创建可升级操作系统的任务序列  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“软件库”。  
  
2.  在“软件库”工作区中，展开“操作系统”，然后单击“任务序列”。  
  
3.  在“主页”选项卡上的“创建”组中，单击“创建任务序列”以启动创建任务序列向导。  
  
4.  在“创建新的任务序列”页上，单击“从升级包升级操作系统”，然后单击“下一步”。  
  
5.  在“任务序列信息”页上，指定以下设置，然后单击“下一步”。  
  
    -   “任务序列名称”：指定用于标识任务序列的名称。  
  
    -   “说明”：指定任务序列所执行的任务的描述。  
  
6.  在“升级 Windows 操作系统”页上，指定以下设置，然后单击“下一步”。  
  
    -   “升级包”：指定包含操作系统升级源文件的升级包。 你可以通过查看“属性”窗格中的信息来验证你是否选择了正确的升级包。 有关详细信息，请参阅[使用 System Center Configuration Manager 管理操作系统升级包](../LocTest/Manage-operating-system-upgrade-packages-with-System-Center-Configuration-Manager.md)。  
  
    -   “版本索引”：如果包中有多个操作系统版本索引可用，请选择所需的版本索引。 默认情况下，选择第一项。  
  
    -   “产品秘钥”：指定要安装的 Windows 操作系统的产品密钥。 你可以指定编码的批量许可证密钥和标准产品密钥。 如果使用非编码的产品密钥，则必须通过短划线 \(\-\) 分隔每组 5 个字符。 例如：*XXXXX\-XXXXX\-XXXXX\-XXXXX\-XXXXX*。 当对批量许可证版本进行升级时，不需要产品密钥。 仅对零售 Windows 版本进行升级时，才需要产品密钥。  
  
7.  在“包括更新”页上，指定是安装必需的软件更新、所有软件更新还是不安装软件更新，然后单击“下一步”。 如果指定要安装软件更新，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将只会安装以包含目标计算机的集合为目标的那些软件更新。  
  
8.  在“安装应用程序”页上，指定要安装在目标计算机上的应用程序，然后单击“下一步”。 如果指定多个应用程序，你也可以指定任务序列在特定应用程序的安装失败时继续进行。  
  
9. 完成向导。  
  
## 下载包内容的任务序列步骤  
 在以下方案中，可先使用 [下载包内容](../LocTest/Task-sequence-steps-in-System-Center-Configuration-Manager.md#BKMK_DownloadPackageContent) 步骤，再使用**升级操作系统**步骤：  
  
-   你想要使用可用于 x86 和 x64 平台的单一升级任务序列。 为了实现这一目的，在“升级准备”组中包括两个“下载包内容”步骤，以及检测客户端体系结构的条件和仅下载相应操作系统升级包的条件。 将每个“下载包内容”步骤配置为使用相同的变量，并将该变量用于“升级操作系统”步骤的媒体路径。  
  
-   若要动态下载适用的驱动程序包，请使用两个“下载包内容”步骤以及检测每个驱动程序包的相应硬件类型的条件。 将每个“下载包内容”步骤配置为使用相同的变量，并将该变量用于“升级操作系统”步骤的驱动程序部分中的“分步内容”值。  
  
## 可选的后续处理任务序列步骤  
 创建任务序列后，你可以添加其他步骤以卸载具有已知兼容性问题的应用程序，也可以添加要在重启电脑并成功升级到 Windows 10 后运行的后续处理操作。 在任务序列的后续处理组中添加这些附加步骤。  
  
> [!NOTE]  
>  由于此任务序列不是线性的，因此，针对步骤的某些条件可能对任务序列的结果产生影响，具体取决于是否成功升级客户端计算机，或者是否必须将客户端计算机回滚到开始升级的操作系统版本。  
  
## 可选的回滚任务序列步骤  
 当重启计算机后升级过程出现问题时，安装程序会此升级回滚到以前的操作系统，并且任务序列将继续执行回滚组中的任何步骤。 创建任务序列后，你可以将可选步骤添加到回滚组。  
  
## 请参阅  
 [管理任务序列以在 System Center Configuration Manager 中自动执行任务](../LocTest/Manage-task-sequences-to-automate-tasks-in-System-Center-Configuration-Manager.md)
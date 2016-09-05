---
title: "对 System Center Configuration Manager 站点数据库使用非默认的 SQL Server 配置"
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
ms.assetid: d09a82c6-bbd1-49ca-8ffe-e3ce87b85d33
caps.latest.revision: 10
caps.handback.revision: 8
---
# 对 System Center Configuration Manager 站点数据库使用非默认的 SQL Server 配置
当你安装 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 站点，并选择对站点数据库使用 SQL Server 的非默认实例或配置时，可从以下选项中进行选择：  
  
-   [使用 SQL Server 群集](#BKMK_SQLCluster)  
  
-   [将自定义文件位置用于数据库文件](#BKMK_DBFiles)  
  
 此外，当 SQL Server 不使用该计算机的本地系统帐户运行 SQL Server 服务时，必须配置帐户的服务主体名称 \(SPN\)，该帐户在 Active Directory 域服务中运行 SQL Server 服务。 （当使用系统帐户时，将为你自动注册 SPN）。 有关站点数据库的 SPN 的信息，请参阅 [修改你的 System Center Configuration Manager 基础结构](../LocTest/Modify-your-System-Center-Configuration-Manager-infrastructure.md) 主题中的 [管理站点数据库服务器的 SPN](../LocTest/Modify-your-System-Center-Configuration-Manager-infrastructure.md#bkmk_SPN)。  
  
##  <a name="BKMK_SQLCluster"></a> 使用 SQL Server 群集  
 可以使用 SQL Server 群集承载站点数据库。 站点数据库是 Server 群集支持的唯一站点系统角色。  
  
> [!NOTE]  
>  成功的配置和 SQL Server 群集要求你适应配置 SQL Server 群集，并且依赖于 SQL Server 文档库中提供的文档和过程。  
  
 使用群集可以提供故障转移支持，并提高站点数据库的可靠性。 但是，使用群集的站点数据库并不提供额外的处理或负载平衡优点。 事实上，由于站点服务器必须查找 SQL Server 群集的活动节点之后才会连接到站点数据库，因此可能出现性能下降。  
  
 在安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 之前，你必须准备 SQL Server 群集，使其支持 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]。 （请参阅本节后面的先决条件）。  
  
 在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 安装过程中，在 Microsoft Windows Server 群集的每个物理计算机节点上安装卷影复制服务 \(VSS\) 编写器，以支持“备份站点服务器”维护任务。  
  
 安装站点后，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 每小时检查群集节点的更改并自动管理发现的影响 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 组件安装的任何更改（如节点故障转移或向 SQL Server 群集添加新节点）。  
  
 **使用 SQL Server 故障转移群集的支持选项：**  
  
-   单个实例群集  
  
-   多个实例配置  
  
-   多个活动节点  
  
-   命名或默认实例都受支持  
  
 **先决条件：**  
  
-   站点数据库必须远离站点服务器。 （群集不能包括站点系统服务器。）  
  
-   必须将站点服务器的计算机帐户添加到群集中每台 Server 的“本地管理员”组。  
  
-   若要支持 Kerberos 身份验证，必须启用 **TCP\/IP** 网络通信协议，以便每个 SQL Server 群集节点进行网络连接。 不需要**命名管道**，但可以将其用于排除 Kerberos 身份验证问题。 在“SQL Server 网络配置”下的“SQL Server 配置管理器”中配置网络协议设置。  
  
-   如果你使用 PKI，当你将 SQL Server 群集用于站点数据库时，请参阅 \<[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的 PKI 证书要求\> 以了解特定证书要求。  
  
 **要考虑的限制：**  
  
-   **安装和配置：**  
  
    -   辅助站点不能使用 SQL Server 群集。  
  
    -   当你指定 SQL Server 群集时，用于指定站点数据库的非默认文件位置的选项不可用。  
  
-   **SMS 提供程序：**  
  
    -   不支持在 SQL Server 群集或作为群集 SQL Server 节点运行的计算机上安装 SMS 提供程序的实例。  
  
-   **数据复制选项：**  
  
    -   如果将使用“分布式视图”，则不能使用 SQL Server 群集承载站点数据库。  
  
-   **备份和恢复：**  
  
    -   [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 不支持对使用命名实例的 SQL Server 群集进行 DPM 备份，但支持对使用默认 SQL Server 实例的 SQL Server 群集进行 DPM 备份。  
  
### 若要为站点数据库准备群集 SQL Server 实例  
  
-   创建虚拟 SQL Server 群集以在现有 Windows Server 群集环境上承载站点数据库。 有关安装和配置 SQL Server 群集的具体步骤，请参阅特定于 SQL Server 版本的文档。 例如，你在使用 SQL Server 2008 R2，请参阅[安装 SQL Server 2008 R2 故障转移群集](http://go.microsoft.com/fwlink/p/?LinkId=240231)。 如果你在使用 SQL Server 2014，请参阅 [SQL Server 故障转移群集安装](https://technet.microsoft.com/library/hh231721\(v=sql.120\).aspx)。  
  
-   在 SQL Server 群集中的每台计算机上，可以在你不希望 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 在其上安装站点组件的各驱动器的根文件夹中放置名为“NO\_SMS\_ON\_DRIVE.SMS”的文件。 默认情况下，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 将在每个物理节点上安装某些组件以支持诸如备份等操作。  
  
-   将站点服务器的计算机帐户添加到每台 Windows Server 群集节点计算机的“本地管理员”组。  
  
-   在虚拟 SQL Server 实例中，将 **sysadmin** SQL Server 角色分配给运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 安装程序的用户帐户。  
  
### 若要安装使用群集 SQL Server 的新站点  
 若要安装使用群集站点数据库的站点，则按照安装站点的通常过程并执行以下变更来运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 安装程序：  
  
-   在“数据库信息”页上，指定要承载站点数据库的虚拟 SQL Server 群集实例的名称。  虚拟实例将替换运行 SQL Server 的计算机的名称。  
  
    > [!IMPORTANT]  
    >  当输入虚拟 SQL Server 群集实例的名称时，请勿输入 Windows Server 群集创建的虚拟 Windows Server 名称。 如果使用虚拟 Windows Server 名称，则站点数据库在活动 Windows Server 群集节点的本地硬盘驱动器上安装。 这会在该节点故障时阻止成功进行故障转移。  
  
##  <a name="BKMK_DBFiles"></a> 将自定义文件位置用于数据库文件  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 支持 SQL Server 数据库文件的自定义位置。  
  
> [!NOTE]  
>  当你使用 SQL Server 群集时，用于指定非默认文件位置的选项不可用。  
  
 在新的主站点或管理中心站点的**安装过程中**，你可以：  
  
-   指定站点数据库的非默认文件位置：然后 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 安装程序会创建使用这些位置的站点数据库。  
  
-   指定使用预创建的 SQL Server 数据库，该库使用自定义文件位置：然后 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 安装程序使用该预创建的数据库及其预配置的文件位置。  
  
 **安装之后**，可以更改站点数据库文件的位置。 这需要你停止该站点并在 SQL Server 中编辑文件位置：  
  
-   在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点服务器上，停止**SMS\_Executive** 服务。  
  
-   请根据你所使用的 SQL Server 版本的文档，指导你如何移动用户数据库。 例如，如果使用 SQL Server 2014，请参阅 TechNet 上的[移动用户数据库](https://technet.microsoft.com/library/ms345483\(v=sql.120\).aspx)。  
  
-   完成数据库文件移动后，在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点服务器上重启 SMS\_Executive 服务。  
  
## 请参阅  
 [为 System Center Configuration Manager 准备网络环境](../LocTest/Prepare-your-network-environment-for-System-Center-Configuration-Manager.md)
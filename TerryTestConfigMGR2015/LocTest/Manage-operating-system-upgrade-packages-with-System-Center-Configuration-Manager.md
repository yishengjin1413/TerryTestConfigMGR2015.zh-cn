---
title: "使用 System Center Configuration Manager 管理操作系统升级包"
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
ms.assetid: b9b22655-b8c1-461f-8047-3a7e906f647a
caps.latest.revision: 12
caps.handback.revision: 12
---
# 使用 System Center Configuration Manager 管理操作系统升级包
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的升级包包含用于在计算机上升级现有操作系统的 Windows 安装程序源文件。 使用以下部分在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中管理操作系统升级包：  
  
-   [将操作系统升级包添加到 Configuration Manager](#BKMK_AddOSUpgradePkgs)  
  
-   [将操作系统映像分发到分发点](#BKMK_DistributeBootImages)  
  
-   [将软件更新应用于操作系统升级包](#BKMK_OSUpgradePkgApplyUpdates)  
  
##  <a name="BKMK_AddOSUpgradePkgs"></a> 将操作系统升级包添加到 Configuration Manager  
 在使用操作系统升级包之前，必须先将该包添加到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点。 使用以下过程将操作系统升级包添加的站点：  
  
#### 若要添加操作系统升级包  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“软件库” 。  
  
2.  在“软件库”  工作区中，展开“操作系统” ，然后单击“操作系统升级包” 。  
  
3.  在“主页”  选项卡上的“创建”  组中，单击“添加操作系统升级包”  以启动“添加操作系统升级向导”。  
  
4.  在“数据源”  页上，指定操作系统升级包的安装源文件的网络路径。 例如，指定安装源文件所在位置的 UNC **\\\server\path**。  
  
    > [!NOTE]  
    >  安装源文件包含 Setup.exe 和其他文件以及用于安装操作系统的文件夹。  
  
    > [!IMPORTANT]  
    >  限制对安装源文件的访问，以防止受到恶意篡改。  
  
5.  在“常规”  页上，指定以下信息，然后单击“下一步” 。 当你有多个操作系统安装程序时，此信息在用于标识时非常有用。  
  
    -   **名称**：指定操作系统安装程序的名称。  
  
    -   **版本**：指定操作系统安装程序的版本。  
  
    -   **备注**：指定操作系统安装程序的简要描述。  
  
6.  完成向导。  
  
 你现在可以将操作系统安装程序分发到部署任务序列访问的分发点。  
  
##  <a name="BKMK_DistributeBootImages"></a> 将操作系统映像分发到分发点  
 将采用与分发其他内容相同的方式将操作系统映像分发到分发点。 大多数情况下，部署操作系统之前必须将操作系统映像分发到至少一个分发点。 关于分发操作系统映像的步骤，请参阅 [Distribute content](../LocTest/Manage-content-and-content-infrastructure-for-System-Center-Configuration-Manager.md#bkmk_dist)。  
  
##  <a name="BKMK_OSUpgradePkgApplyUpdates"></a> 将软件更新应用于操作系统升级包  
 从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 版本 1602 开始，可以将新的软件更新应用于操作系统升级包中的操作系统映像。 当然，必须将软件更新基础结构实施到位且已成功同步软件更新后才可以将软件更新应用于升级包。 有关详细信息，请参阅[在 System Center Configuration Manager 中部署并管理软件更新](../LocTest/Deploy-and-manage-software-updates-in-System-Center-Configuration-Manager.md)。  
  
 你可以按指定计划将适用的软件更新应用于升级包。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 按指定计划将你选择的软件更新应用于操作系统升级包，然后根据需要将更新的升级包分发到分发点。 有关操作系统升级包的信息存储在站点数据库中，包括在导入时应用的软件更新。 自升级包最初添加以来已应用于升级包的软件更新也存储在站点数据库中。 当你启动向导以将软件更新应用于操作系统升级包时，向导将检索尚未应用于升级包的适用软件更新的列表供你选择。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 从站点服务器上的内容库中复制软件更新，然后将软件更新应用于操作系统升级包。  
  
 使用以下过程将软件更新应用于操作系统升级包。  
  
#### 将软件更新应用于操作系统升级包  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“软件库” 。  
  
2.  在“软件库”  工作区中，展开“操作系统” ，然后单击“操作系统升级包” 。  
  
3.  选择要向其应用软件更新的操作系统升级包。  
  
4.  在“主页”选项卡上的“操作系统升级包”组中，单击“计划更新”以启动向导。  
  
5.  在“选择更新”  页上，选择要应用于操作系统映像的软件更新，然后单击“下一步” 。  
  
6.  在“设置计划”  页上，指定以下设置，然后单击“下一步” 。  
  
    1.  **计划**：指定有关何时将软件更新应用于操作系统映像的计划。  
  
    2.  **出错时继续**：选择此选项以便即使在出错时也继续将软件更新应用于映像。  
  
    3.  **将映像分发到分发点**：选择此选项以在应用了软件更新后更新分发点上的操作系统映像。  
  
7.  在“摘要”  页上，验证以下信息，然后单击“下一步” 。  
  
8.  在“完成”  页上，验证软件更新是否已成功应用于操作系统映像。  
  
## 另请参阅  
 [准备 System Center Configuration Manager 中的操作系统部署](../LocTest/Prepare-for-operating-system-deployment-in-System-Center-Configuration-Manager.md)
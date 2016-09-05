---
title: "使用 System Center Configuration Manager 替换现有计算机和传输设置"
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
ms.assetid: d28f4363-9e8a-4c54-9cb7-0594fabfff26
caps.latest.revision: 6
caps.handback.revision: 5
---
# 使用 System Center Configuration Manager 替换现有计算机和传输设置
本主题提供了 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的常规步骤以用一台新计算机替换现有计算机。 对于此方案，可以在许多不同的部署方法中进行选择，如可启动媒体、多播或软件中心。 你还可以选择用以存储设置的状态迁移点，然后在安装后将这些设置还原到新的操作系统。 如果你不确定这是正确的操作系统部署方案，请参阅 [使用 System Center Configuration Manager 部署企业版操作系统的方案](../LocTest/Scenarios-to-deploy-enterprise-operating-systems-with-System-Center-Configuration-Manager.md)。  
  
 采用以下部分内容，使用新版本的 Windows 来刷新现有计算机。  
  
##  <a name="BKMK_Plan"></a> 计划  
  
-   **规划和实现基础结构要求**  
  
     在你可以部署操作系统前，有几个必须实施到位的基础结构要求，例如 Windows ADK、用户状态迁移工具 \(USMT\)、Windows 部署服务 \(WDS\) 以及支持的硬盘配置等。 有关详细信息，请参阅[System Center Configuration Manager 中的操作系统部署的基础架构要求](../LocTest/Infrastructure-requirements-for-operating-system-deployment-in-System-Center-Configuration-Manager.md)。  
  
-   **安装状态迁移点（仅在传输设置时需要）**  
  
     当你要从现有计算机捕获设置并将设置还原到新的操作系统时，必须安装状态迁移点。 有关详细信息，请参阅[状态迁移点](../LocTest/Prepare-site-system-roles-for-operating-system-deployments-with-System-Center-Configuration-Manager.md#BKMK_StateMigrationPoints)。  
  
##  <a name="BKMK_Configure"></a> 配置  
  
1.  **准备启动映像**  
  
     启动映像将启动 Windows PE 环境（具有有限组件和服务的最小操作系统）中的计算机，然后在该计算机上安装完整的 Windows 操作系统。   在部署操作系统时，必须选择要使用的启动映像并将其分发到分发点。 使用以下方法来准备启动映像：  
  
    -   若要了解有关启动映像的详细信息，请参阅 [使用 System Center Configuration Manager 管理启动映像](../LocTest/Manage-boot-images-with-System-Center-Configuration-Manager.md)。  
  
    -   有关如何自定义启动映像的详细信息，请参阅 [使用 System Center Configuration Manager 自定义启动映像](../LocTest/Customize-boot-images-with-System-Center-Configuration-Manager.md)。  
  
    -   将启动映像分发到分发点 有关详细信息，请参阅 [Distribute content](../LocTest/Manage-content-and-content-infrastructure-for-System-Center-Configuration-Manager.md#bkmk_dist)。  
  
2.  **准备操作系统映像**  
  
     操作系统映像包含在目标计算机上安装操作系统所必需的文件。 使用以下方法来准备操作系统映像：  
  
    -   若要了解有关如何创建操作系统映像的详细信息，请参阅 [使用 System Center Configuration Manager 管理操作系统映像](../LocTest/Manage-operating-system-images-with-System-Center-Configuration-Manager.md)。  
  
    -   将操作系统映像分发到分发点。 有关详细信息，请参阅 [Distribute content](../LocTest/Manage-content-and-content-infrastructure-for-System-Center-Configuration-Manager.md#bkmk_dist)。  
  
3.  **创建任务序列以通过网络部署操作系统**  
  
     使用任务序列以通过网络自动安装操作系统 使用 [在 System Center Configuration Manager 中创建用于安装操作系统的任务序列](../LocTest/Create-a-task-sequence-to-install-an-operating-system-in-System-Center-Configuration-Manager.md) 中的步骤创建任务序列，以部署操作系统。 可能会有有关任务序列的其他注意事项，具体取决于你所选择的部署方法。  
  
    > [!NOTE]  
    >  在此方案中，如果捕获并还原了用户设置和文件，你可以选择使用状态迁移点或本地保存这些文件。 有关详细信息，请参阅 [在 System Center Configuration Manager 中管理用户状态](../LocTest/Manage-user-state-in-System-Center-Configuration-Manager.md)。  
  
##  <a name="BKMK_Deploy"></a> 部署  
  
-   使用下列部署方法之一部署操作系统：  
  
    -   [使用软件中心与 System Center Configuration Manager 一起通过网络部署 Windows](../LocTest/Use-Software-Center-to-deploy-Windows-over-the-network-with-System-Center-Configuration-Manager.md)  
  
    -   [使用可启动媒体与 System Center Configuration Manager 一起通过网络部署 Windows](../LocTest/Use-bootable-media-to-deploy-Windows-over-the-network-with-System-Center-Configuration-Manager.md)  
  
    -   [使用多播与 System Center Configuration Manager 一起通过网络部署 Windows](../LocTest/Use-multicast-to-deploy-Windows-over-the-network-with-System-Center-Configuration-Manager.md)  
  
    -   [使用 System Center Configuration Manager 为工厂中的 OEM 或本地 depot 创建映像](../LocTest/Create-an-image-for-an-OEM-in-factory-or-a-local-depot-with-System-Center-Configuration-Manager.md)  
  
## 监视器  
  
-   **监视任务序列部署**  
  
     若要监视任务序列部署以安装操作系统，请参阅 [在 System Center Configuration Manager 中监视操作系统部署](../LocTest/Monitor-operating-system-deployments-in-System-Center-Configuration-Manager.md)。  
  
## 请参阅  
 [使用 System Center Configuration Manager 部署企业版操作系统的方案](../LocTest/Scenarios-to-deploy-enterprise-operating-systems-with-System-Center-Configuration-Manager.md)
---
title: "使用 System Center Configuration Manager 在新计算机（裸机）上安装新版本的 Windows"
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
ms.assetid: f5ad22d5-7df1-49c6-8a0f-db1c3f0cda19
caps.latest.revision: 8
caps.handback.revision: 7
translationtype: Human Translation
---
# 使用 System Center Configuration Manager 在新计算机（裸机）上安装新版本的 Windows
本主题提供了 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中在新计算机上安装操作系统的常规步骤。 对于此方案，可以从许多不同的部署方法中选择，如 PXE、OEM、或独立媒体。 如果你不确定这是正确的操作系统部署方案，请参阅 [使用 System Center Configuration Manager 部署企业版操作系统的方案](../LocTest/Scenarios-to-deploy-enterprise-operating-systems-with-System-Center-Configuration-Manager.md)。  
  
 采用以下部分内容，使用新版本的 Windows 来刷新现有计算机。  
  
##  <a name="BKMK_Plan"></a> 计划  
  
-   **规划和实现基础结构要求**  
  
     在你可以部署操作系统前，有几个必须实施到位的基础结构要求，例如 Windows ADK、Windows 部署服务 \(WDS\) 以及支持的硬盘配置等。 有关详细信息，请参阅[System Center Configuration Manager 中的操作系统部署的基础架构要求](../LocTest/Infrastructure-requirements-for-operating-system-deployment-in-System-Center-Configuration-Manager.md)。  
  
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
  
##  <a name="BKMK_Deploy"></a> 部署  
  
-   使用下列部署方法之一部署操作系统：  
  
    -   [使用 PXE 与 System Center Configuration Manager 一起通过网络部署 Windows](../LocTest/Use-PXE-to-deploy-Windows-over-the-network-with-System-Center-Configuration-Manager.md)  
  
    -   [使用多播与 System Center Configuration Manager 一起通过网络部署 Windows](../LocTest/Use-multicast-to-deploy-Windows-over-the-network-with-System-Center-Configuration-Manager.md)  
  
    -   [使用 System Center Configuration Manager 为工厂中的 OEM 或本地 depot 创建映像](../LocTest/Create-an-image-for-an-OEM-in-factory-or-a-local-depot-with-System-Center-Configuration-Manager.md)  
  
    -   [在 System Center Configuration Manager 中使用独立媒体部署 Windows，而不使用网络](../LocTest/Use-stand-alone-media-to-deploy-Windows-without-using-the-network-in-System-Center-Configuration-Manager.md)  
  
    -   [使用可启动媒体与 System Center Configuration Manager 一起通过网络部署 Windows](../LocTest/Use-bootable-media-to-deploy-Windows-over-the-network-with-System-Center-Configuration-Manager.md)  
  
## 监视器  
  
-   **监视任务序列部署**  
  
     若要监视任务序列部署以安装操作系统，请参阅 [在 System Center Configuration Manager 中监视操作系统部署](../LocTest/Monitor-operating-system-deployments-in-System-Center-Configuration-Manager.md)。  
  
## 请参阅  
 [使用 System Center Configuration Manager 部署企业版操作系统的方案](../LocTest/Scenarios-to-deploy-enterprise-operating-systems-with-System-Center-Configuration-Manager.md)
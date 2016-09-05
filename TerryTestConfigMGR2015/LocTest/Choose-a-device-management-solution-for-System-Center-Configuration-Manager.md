---
title: "选择 System Center Configuration Manager 的设备管理解决方案"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-client
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 24633725-791a-4df7-8dce-2c24c1a19a03
caps.latest.revision: 14
caps.handback.revision: 9
---
# 选择 System Center Configuration Manager 的设备管理解决方案
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 提供用于管理 PC、服务器和设备的不同解决方案。 你可以根据进行管理所需的设备平台和所需的管理功能来选择最适合的解决方案。  
  
 本文内容：  
  
-   [设备管理解决方案概述](#bkmk_overview)  
  
-   [基于受支持的移动设备平台比较设备管理解决方案](#bkmk_comp1)  
  
-   [根据管理功能比较移动设备管理解决方案](#bkmk_comp2)  
  
##  <a name="bkmk_overview"></a> 设备管理解决方案概述  
 以下选项可用于使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 管理计算机和设备：  
  
-   使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端管理设备  
  
     此选项（要求在每台要管理的设备上安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端应用程序）提供用于管理 PC、服务器和环境中的其他设备的最全面的功能。 此选项是传统方法，[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 已在产品的历史记录中提供了设备管理。  
  
     有关此解决方案的详细信息，请参阅 [使用 System Center Configuration Manager 管理计算机客户端](../LocTest/Manage-computer-clients-with-System-Center-Configuration-Manager.md)。  
  
-   [!INCLUDE[onprem_first](../LocTest/includes/onprem_first_md.md)]  
  
     此选项使用内置于特定设备平台的操作系统的设备管理功能。 尽管没有基于客户端的管理的功能全面，[!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 为使用本地 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 资源访问和管理设备的管理提供更轻的触点方法。[!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)] 目前仅支持 Windows 10 PC 和 Windows 10 移动设备。  
  
     有关此解决方案的详细信息，请参阅 [在 System Center Configuration Manager 中使用本地基础结构管理移动设备](../LocTest/Manage-mobile-devices-with-on-premises-infrastructure-in-System-Center-Configuration-Manager.md)。  
  
-   使用 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 管理设备  
  
     此选项使用 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 来注册和管理设备，而非使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 本地资源。 但是，它允许通过 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台控制管理任务。 此选项支持所有主要移动设备操作系统，包括 Windows 10 Mobile、Windows Phone、iOS 以及 Android。 它还为组织中的 Windows 8.1 和 Windows 10 计算机提供管理。  
  
     有关此解决方案的详细信息，请参阅 [使用 System Center Configuration Manager 和 Microsoft Intune 的混合移动设备管理 \(MDM\)](../LocTest/Hybrid-mobile-device-management--MDM--with-System-Center-Configuration-Manager-and-Microsoft-Intune.md)。  
  
-   使用 Exchange 管理  
  
     此选项（使用 Exchange Server 连接器将多个Exchange 服务器连接到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]）集中管理可连接到 Exchange ActiveSync 的设备。 你可从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台配置 Exchange 移动设备管理功能，例如远程设备擦除和针对多个 Exchange 服务器的设置控制。  
  
     有关此解决方案的详细信息，请参阅 [使用 System Center Configuration Manager 和 Exchange 管理移动设备](../LocTest/Manage-mobile-devices-with-System-Center-Configuration-Manager-and-Exchange.md)  
  
 可以使用这些本身相互结合的设备管理解决方案。 例如，可以使用基于客户端的管理方法来介绍管理组织中的计算机和服务器，也可以使用基于 Intune 的管理来管理移动设备。 通过这样组合方法，你可以满足所有设备管理需求并可以完全从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台对它进行控制。  
  
##  <a name="bkmk_comp1"></a> 基于受支持的移动设备平台比较设备管理解决方案  
  
|平台|通过 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端进行管理|通过 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 进行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]：|[!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)]|通过 Exchange 进行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]|  
|--------|--------------------------------------|----------------------------------------------------------|-------------------------------|------------------------------------------|  
|Android||是||是|  
|iOS||是||是|  
|Mac OS X|是|||是|  
|UNIX\/Linux|是|||是|  
|Windows 10|是|是|是|是|  
|Windows 10 移动版||是|是|是|  
|Windows（以前的版本）|是|是||是|  
|Windows CE|是（具有移动设备旧客户端）|||是|  
|Windows Embedded|是||||  
|Windows Phone||是||是|  
|Windows Server|是|||是|  
  
 关于支持平台的完整列表，请参阅[System Center Configuration Manager 支持的站点和客户端操作系统](../Topic/Supported%20operating%20systems%20for%20sites%20and%20clients%20for%20System%20Center%20Configuration%20Manager.md)中的以下部分：  
  
-   [System Center Configuration Manager 客户端支持的操作系统](../Topic/Supported%20operating%20systems%20for%20sites%20and%20clients%20for%20System%20Center%20Configuration%20Manager.md#bkmk_ClientOS)  
  
-   [Microsoft Intune 注册的移动设备](../Topic/Supported%20operating%20systems%20for%20sites%20and%20clients%20for%20System%20Center%20Configuration%20Manager.md#bkmk_IntuneOS)  
  
-   [本地移动设备管理](../Topic/Supported%20operating%20systems%20for%20sites%20and%20clients%20for%20System%20Center%20Configuration%20Manager.md#bkmk_OnpremOS)  
  
##  <a name="bkmk_comp2"></a> 根据管理功能比较移动设备管理解决方案  
  
|平台|通过 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端进行管理|通过 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 进行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]：|[!INCLUDE[onprem_next](../LocTest/includes/onprem_next_md.md)]|通过 Exchange 进行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]|  
|--------|--------------------------------------|----------------------------------------------------------|-------------------------------|------------------------------------------|  
|移动设备和 Configuration Manager 之间的公钥基础结构 \(PKI\) 安全性通过使用相互身份验证和 SSL 来加密数据传输|是|是|是||  
|客户端安装|是||||  
|通过 Internet 提供的支持|是||||  
|发现|是|||是|  
|硬件清单|是|是|是|是|  
|软件清单|是|||是|  
|设置|是|是|是|是|  
|软件部署|是|是|是||  
|利用回退状态点进行监视|是||||  
|连接到管理点|是||是||  
|连接到分发点|是|是|是||  
|通过 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 进行阻止|是|是|是||  
|通过 Exchange Server 和 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 进行隔离和阻止||||是|  
|远程擦除|是|是|是|是|  
  
## 请参阅  
 [使用 System Center Configuration Manager 管理计算机和设备](../LocTest/Manage-computers-and-devices-with-System-Center-Configuration-Manager.md)
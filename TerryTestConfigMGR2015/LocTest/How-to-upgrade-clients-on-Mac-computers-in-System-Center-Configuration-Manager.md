---
title: "如何在 System Center Configuration Manager 中升级 Mac 计算机的客户端"
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
ms.assetid: 74c60941-5eae-4905-9e58-252bdb39df96
caps.latest.revision: 10
caps.handback.revision: 6
translationtype: Human Translation
---
# 如何在 System Center Configuration Manager 中升级 Mac 计算机的客户端
使用下表来了解有关如何使用 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 应用程序为 Mac 计算机升级客户端的步骤、详情及更多信息。 或者，你也可以下载 Mac 客户端安装文件，将其复制到 Mac 计算机上的共享网络位置或本地文件夹，然后指示用户手动运行安装。  
  
##  <a name="BKMK_StepsToUpgradeMacComputers"></a>   
> [!NOTE]  
>  在执行这些步骤之前，请确保 Mac 计算机满足 [System Center Configuration Manager 支持的站点和客户端操作系统](../Topic/Supported%20operating%20systems%20for%20sites%20and%20clients%20for%20System%20Center%20Configuration%20Manager.md) 中的 [本地移动设备管理](../Topic/Supported%20operating%20systems%20for%20sites%20and%20clients%20for%20System%20Center%20Configuration%20Manager.md#bkmk_OnpremOS) 部分列出的先决条件。  
  
|步骤|详细信息|更多信息|  
|--------|----------|----------|  
|**步骤 1：**从 Microsoft 下载中心下载最新的 Mac 客户端安装文件|[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 安装媒体上未提供 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的 Mac 客户端，必须从 Microsoft 下载中心下载。 Mac 客户端安装文件包含在名为 ConfigmgrMacClient.msi 的 Windows Installer 文件中。|可以从 [Microsoft Download Center（Microsoft 下载中心）](http://go.microsoft.com/fwlink/p/?LinkId=525184)下载此文件。|  
|**步骤 2：**运行下载的安装文件以创建 Mac 客户端安装文件。|在运行 Windows 的计算机上，运行下载的“ConfigmgrMacClient.msi”以解压缩名为“Macclient.dmg”的 Mac 客户端安装文件。 默认情况下，在你解压缩文件之后，此文件可在 Windows 计算机上的“C:\\Program Files \(x86\)\\Microsoft\\System Center 2012 Configuration Manager Mac Client”文件夹中找到。||  
|**步骤 3：**提取客户端安装文件。|将 Macclient.dmg 文件复制到网络共享或 Mac 计算机上的本地文件夹。 然后，从 Mac 计算机中装载并随后打开 Macclient.dmg 文件，并将文件复制到 Mac 计算机上的某个文件夹。||  
|**步骤 4：**创建可用于创建应用程序的 .cmmac 文件。|使用“CMAppUtil”工具（位于 Mac 客户端安装文件的“Tools”文件夹中）通过客户端安装包创建 .cmmac 文件。 此文件将用于创建 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 应用程序。<br /><br /> 将新文件“CMClient.pkg.cmmac”复制到可供运行 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台的计算机使用的位置。|有关详细信息，请参阅 [使用 System Center Configuration Manager 创建 Mac 计算机应用程序](../LocTest/Creating-Mac-computer-applications-with-System-Center-Configuration-Manager.md)中的[Step 1: Prepare Mac applications for Configuration Manager](../LocTest/Creating-Mac-computer-applications-with-System-Center-Configuration-Manager.md#BKMK_Step1)部分。|  
|**步骤 5：**创建并部署包含 Mac 客户端文件的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 应用程序。|在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，从包含客户端安装文件的“CMClient.pkg.cmmac”文件创建应用程序。<br /><br /> 将此应用程序部署到层次结构中的 Mac 计算机。|有关详细信息，请参阅 [使用 System Center Configuration Manager 创建 Mac 计算机应用程序](../LocTest/Creating-Mac-computer-applications-with-System-Center-Configuration-Manager.md)。|  
|**步骤 6：**用户安装最新的客户端。|将向 Mac 客户端的用户发出提示，指出 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端的更新可用并且必须安装。 用户安装客户端后，他们必须重启其 Mac 计算机。|计算机重启后，“计算机注册向导”将自动运行以请求新用户证书。<br /><br /> 如果不想使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 注册，而想从 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 独立安装客户端证书，请参阅 [将升级后的客户端配置为使用现有证书](#BKMK_UpgradingClient_MachineEnrollment)。|  
  
##  <a name="BKMK_UpgradingClient_MachineEnrollment"></a> 将升级后的客户端配置为使用现有证书  
 运行下列过程以防止“计算机注册向导”运行，并将升级后的客户端配置为使用现有客户端证书。  
  
-   在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，创建“Mac OS X”类型的配置项目。  
  
-   使用设置类型“脚本”将设置添加到此配置项。  
  
-   将下列脚本添加到设置：  
  
    ```  
    #!/bin/sh  
    echo "Starting script\n"  
    echo "Changing directory to MAC Client\n"  
    cd /Users/Administrator/Desktop/'MAC Client'/  
    echo "Import root cert\n"  
    /usr/bin/sudo /usr/bin/security import /Users/Administrator/Desktop/'MAC Client'/Root.pfx -A -k /Library/Keychains/System.Keychain -P ROOT  
    echo "Using openssl to convert pfx to a crt\n"  
    /usr/bin/sudo openssl pkcs12 -in /Users/Administrator/Desktop/'MAC Client'/Root.pfx -out Root1.crt -nokeys -clcerts -passin pass:ROOT  
    echo "Adding trust to root cert\n"  
    /usr/bin/sudo /usr/bin/security add-trusted-cert -d -r trustRoot -k /Library/Keychains/System.Keychain Root1.crt  
    echo "Import client cert\n"  
    /usr/bin/sudo /usr/bin/security import /Users/Administrator/Desktop/'MAC Client'/MacClient.pfx -A -k /Library/Keychains/System.Keychain -P MAC  
    echo "Executing ccmclient with MP\n"  
    sudo ./ccmsetup -MP https://SCCM34387.SCCM34387DOM.NET/omadm/cimhandler.ashx  
    echo "Editing Plist file\n"  
    sudo /usr/libexec/Plistbuddy -c 'Add:SubjectName string CMMAC003L' /Library/'Application Support'/Microsoft/CCM/ccmclient.plist  
    echo "Changing directory to CCM\n"  
    cd /Library/'Application Support'/Microsoft/CCM/  
    echo "Making connection to the server\n"  
    sudo open ./CCMClient  
    echo "Ending Script\n"  
    exit  
  
    ```  
  
-   将配置项添加到配置基线，然后将该配置基线部署到独立于 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 安装证书的所有 Mac 计算机。  
  
 有关如何为 Mac 计算机创建和部署配置项的详细信息，请参阅[如何为使用 System Center Configuration Manager 客户端管理的 Mac OS X设备创建配置项目](../LocTest/How-to-create-configuration-items-for-Mac-OS-X-devices-managed-with-the-System-Center-Configuration-Manager-client.md)和[如何在 System Center Configuration Manager 中部署配置基线](../LocTest/How-to-deploy-configuration-baselines-in-System-Center-Configuration-Manager.md)。  
  
## 请参阅  
 [在 System Center Configuration Manager 中升级客户端](../LocTest/Upgrade-clients-in-System-Center-Configuration-Manager.md)
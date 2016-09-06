---
title: "How to upgrade clients for Windows computers in System Center Configuration Manager"
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
ms.assetid: 6143fd47-48ec-4bca-b53b-5b9b9f067bc3
caps.latest.revision: 11
caps.handback.revision: 10
translationtype: Human Translation
---
# How to upgrade clients for Windows computers in System Center Configuration Manager
You can upgrade the client on Windows computers using client installation methods or the automatic client upgrade features in [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)]. The following client installation methods are valid ways to upgrade client software on Windows computers:  
  
-   Group policy installation  
  
-   Logon script installation  
  
-   Manual installation  
  
-   Upgrade installation  
  
 If you are interested in upgrading the client using a client installation methods, learn more about using those methods in [How to deploy clients to Windows computers in System Center Configuration Manager](../LocTest/How-to-deploy-clients-to-Windows-computers-in-System-Center-Configuration-Manager.md)  
  
> [!TIP]  
>  [!INCLUDE[cm-client-upgrade-tip](../LocTest/includes/cm-client-upgrade-tip_md.md)]  
  
## Use automatic client upgrade  
 You can also configure [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] to automatically upgrade the client software to the latest [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] client version when [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] identifies that a client that is assigned to the [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] hierarchy is lower than the version used in the hierarchy. This scenario includes upgrading the client to the latest version when it attempts to assign to a [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] site.  
  
 A client can be automatically upgraded in the following scenarios:  
  
-   The client version is lower that the version being used in the hierarchy.  
  
-   The client on the central administration site has a language pack installed and the existing client does not.  
  
-   A client prerequisite in the hierarchy is a different version than the one installed on the client.  
  
-   One or more of the client installation files are a different version.  
  
> [!NOTE]  
>  You can run the report **Count of Configuration Manager clients by client versions** in the report folder **Site – Client Information** to identify the different versions of the [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] client in your hierarchy.  
  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] creates an upgrade package by default that is automatically sent to all distribution points in the hierarchy. If you make changes to the client package on the central administration site, for example, add a client language pack, [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] automatically updates the package, and distributes it to all distribution points in the hierarchy. If automatic client upgrade is enabled, every client will install the new client language package automatically.  
  
> [!NOTE]  
>  [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] does not automatically send the client upgrade package to [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] cloud-based distribution points.  
  
 Automatic client upgrades are useful when you want to upgrade a small number of client computers that might have been missed by your main client installation method. For example, you have completed an initial client upgrade, but some clients were offline during the upgrade deployment. You then use this method to upgrade the client on these computers when they are next active.  
  
 Use the following procedure to configure automatic client upgrade. Automatic client upgrade must be configured at a central administration site and this configuration applies to all clients in your hierarchy.  
  
#### To configure automatic client upgrades  
  
1.  In the [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] console, click **Administration**.  
  
2.  In the **Administration** workspace, expand **Site Configuration**, and then click **Sites**.  
  
3.  On the **Home** tab, in the **Sites** group, click **Hierarchy Settings**.  
  
4.  In the **Client Upgrade** tab of the **Hierarchy Settings Properties** dialog box, review the version and date of the production client, and make sure it's the version you want to use for upgrading Windows computers.  If it's not the client version you were expecting to see, you may need to promote the pre-production client to production. For more information, see [How to test client upgrades in a preproduction collection in System Center Configuration Manager](../LocTest/How-to-test-client-upgrades-in-a-preproduction-collection-in-System-Center-Configuration-Manager.md).  
  
5.  Click **Upgrade all clients in the hierarchy using the production client** and click **OK** in the confirmation dialog box.  
  
6.  If you don't want client upgrades to apply to servers, click **Do not upgrade servers**.  
  
7.  Specify the number of days in which computers must upgrade the client after they receive client policy. The client will be upgraded at a random interval within this number of days. This prevents scenarios where a large number of client computers are upgraded simultaneously.  
  
8.  If you want the client installation package to be copied to distribution points that have been enabled for prestaged content, click **Automatically distribute client installation package to distribution points that are enabled for prestaged content**.  
  
9. Click **OK** to save the settings and close the **Hierarchy Settings Properties** dialog box. Clients receive these settings when they next download policy.  
  
## See Also  
 [Upgrade clients in System Center Configuration Manager](../LocTest/Upgrade-clients-in-System-Center-Configuration-Manager.md)
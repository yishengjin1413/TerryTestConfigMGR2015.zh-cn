---
title: "Security and privacy for hardware inventory in System Center Configuration Manager"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-other
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 62e20d86-db6d-4a1f-b14a-905a9de31698
caps.latest.revision: 6
caps.handback.revision: 6
author: barlanmsft
translationtype: Human Translation
---
# Security and privacy for hardware inventory in System Center Configuration Manager
This topic contains security and privacy information for hardware inventory in [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)].  
  
##  <a name="BKMK_Security_HardwareInventory"></a> Security best practices for hardware inventory  
 Use the following security best practices for when you collect hardware inventory data from clients:  
  
|Security best practice|More information|  
|----------------------------|----------------------|  
|Sign and encrypt inventory data|When clients communicate with management points by using HTTPS, all data that they send is encrypted by using SSL. However, when client computers use HTTP to communicate with management points on the intranet, client inventory data and collected files can be sent unsigned and unencrypted. Make sure that the site is configured to require signing and use encryption. In addition, if clients can support the SHA-256 algorithm, select the option to require SHA-256.|  
|Do not collect IDMIF and NOIDMIF files in high-security environments|You can use IDMIF and NOIDMIF file collection to extend hardware inventory collection. When necessary, [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] creates new tables or modifies existing tables in the [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] database to accommodate the properties in IDMIF and NOIDMIF files. However, [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] does not validate IDMIF and NOIDMIF files, so these files could be used to alter tables that you do not want altered. Valid data could be overwritten by invalid data. In addition, large amounts of data could be added and the processing of this data might cause delays in all [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] functions. To mitigate these risks, configure the hardware inventory client setting **Collect MIF files** as **None**.|  
  
### Security issues for hardware inventory  
 Collecting inventory exposes potential vulnerabilities. Attackers can perform the following:  
  
-   Send invalid data, which will be accepted by the management point even when the software inventory client setting is disabled and file collection is not enabled.  
  
-   Send excessively large amounts of data in a single file and in lots of files, which might cause a denial of service.  
  
-   Access inventory information as it is transferred to [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)].  
  
 Because a user with local administrative privileges can send any information as inventory data, do not consider inventory data that is collected by [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] to be authoritative.  
  
 Hardware inventory is enabled by default as a client setting.  
  
##  <a name="BKMK_Privacy_HardwareInventory"></a> Privacy information for hardware inventory  
 Hardware inventory allows you to retrieve any information that is stored in the registry and in WMI on [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] clients. Software inventory allows you to discover all files of a specified type or to collect any specified files from clients. Asset Intelligence enhances the inventory capabilities by extending hardware and software inventory and adding new license management functionality.  
  
 Hardware inventory is enabled by default as a client setting and the WMI information collected is determined by options that you select. Software inventory is enabled by default but files are not collected by default. Asset Intelligence data collection is automatically enabled, although you can select the hardware inventory reporting classes to enable.  
  
 Inventory information is not sent to Microsoft. Inventory information is stored in the [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] database. When clients use HTTPS to connect to management points, the inventory data that they send to the site is encrypted during the transfer. If clients use HTTP to connect to management points, you have the option to enable inventory encryption. The inventory data is not stored in encrypted format in the database. Information is retained in the database until it is deleted by the site maintenance tasks **Delete Aged Inventory History** or **Delete Aged Collected Files** every 90 days. You can configure the deletion interval.  
  
 Before you configure hardware inventory, software inventory, file collection, or Asset Intelligence data collection, consider your privacy requirements.  
  
## See Also  
 [Hardware inventory in System Center Configuration Manager](../LocTest/Hardware-inventory-in-System-Center-Configuration-Manager.md)
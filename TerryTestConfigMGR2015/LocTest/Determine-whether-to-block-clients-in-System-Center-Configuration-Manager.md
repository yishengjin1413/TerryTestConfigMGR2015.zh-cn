---
title: "Determine whether to block clients in System Center Configuration Manager"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-client
ms.tgt_pltfrm: na
ms.topic: get-started-article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 54ef5fbb-521d-4ca5-a1c5-61e6f538d71e
caps.latest.revision: 8
caps.handback.revision: 8
translationtype: Human Translation
---
# Determine whether to block clients in System Center Configuration Manager
If a client computer or client mobile device is no longer trusted, you can block the client in the [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)] console. Blocked clients are rejected by the [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] infrastructure so that they cannot communicate with site systems to download policy, upload inventory data, or send state or status messages.  
  
 You must block and unblock a client from its assigned site rather than from a secondary site or a central administration site.  
  
> [!IMPORTANT]  
>  Although blocking in [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] can help to secure the [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] site, do not rely on this feature to protect the site from untrusted computers or mobile devices if you allow clients to communicate with site systems by using HTTP, because a blocked client could rejoin the site with a new self-signed certificate and hardware ID. Instead, use the blocking feature to block lost or compromised boot media that you use to deploy operating systems, and when site systems accept HTTPS client connections.  
  
 Clients that access the site by using the ISV Proxy certificate cannot be blocked. For more information about the ISV Proxy certificate, see the [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] Software Development Kit (SDK).  
  
 If your site systems accept HTTPS client connections and your public key infrastructure (PKI) supports a certificate revocation list (CRL), always consider certificate revocation to be the primary line of defense against potentially compromised certificates. Blocking clients in [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] offers a second line of defense to protect your hierarchy.  
  
##  <a name="BKMK_Block_vs_CRL"></a> Considerations for blocking clients  
  
-   This option is available for HTTP and HTTPS client connections, but has limited security when clients connect to site systems by using HTTP.  
  
-   [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] administrative users have the authority to block a client, and the action is taken in the [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] console.  
  
-   Client communication is rejected from the [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] hierarchy only.  
  
    > [!NOTE]  
    >  The same client could register with a different [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] hierarchy.  
  
-   The client is immediately blocked from the [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] site.  
  
-   Helps to protect site systems from potentially compromised computers and mobile devices.  
  
## Considerations for using certificate revocation  
  
-   This option is available for HTTPS Windows client connections if the public key infrastructure supports a certificate revocation list (CRL).  
  
     Mac clients always perform CRL checking and this functionality cannot be disabled.  
  
     Although mobile device clients do not use certificate revocation lists to check the certificates for site systems, their certificates can be revoked and checked by [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)].  
  
-   Public key infrastructure administrators have the authority to revoke a certificate, and the action is taken outside the [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] console.  
  
-   Client communication can be rejected from any computer or mobile device that requires this client certificate.  
  
-   There is likely to be a delay between revoking a certificate and site systems downloading the modified certificate revocation list (CRL).  
  
-   For many PKI deployments, this delay can be a day or longer. For example, in Active Directory Certificate Services, the default expiration period is one week for a full CRL, and one day for a delta CRL.  
  
-   Helps to protect site systems and clients from potentially compromised computers and mobile devices.  
  
    > [!NOTE]  
    >  You can further protect site systems that run IIS from unknown clients by configuring a certificate trust list (CTL) in IIS.  
  
## See Also  
 [Planning considerations for deploying clients in System Center Configuration Manager](../LocTest/Planning-considerations-for-deploying-clients-in-System-Center-Configuration-Manager.md)
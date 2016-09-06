---
title: "在 System Center Configuration Manager 中规划 Linux 和 UNIX 计算机的客户端部署"
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
ms.assetid: 44153689-70e8-42ad-9ae8-17ae35f6a2e3
caps.latest.revision: 9
caps.handback.revision: 9
translationtype: Human Translation
---
# 在 System Center Configuration Manager 中规划 Linux 和 UNIX 计算机的客户端部署
你可以在运行 Linux 或 UNIX 的计算机上安装 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 客户端。 此客户端适用于作为工作组计算机运行的服务器，并且不支持与登录用户交互。 安装客户端软件后，客户端将与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点建立通信，你可以使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台和报表管理客户端。  
  
> [!NOTE]  
>  Linux 和 UNIX 计算机的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端不支持以下管理功能：  
>   
>  -   客户端请求安装  
> -   操作系统部署  
> -   应用程序部署；改用包和程序来部署软件。  
> -   软件清单  
> -   软件更新  
> -   符合性设置  
> -   远程控制  
> -   电源管理  
> -   客户端状态客户端检查和修正  
> -   基于 Internet 的客户端管理  
  
 有关受支持的 Linux 和 UNIX 分发版和支持适用于 Linux 和 UNIX 的客户端所需的硬件的信息，请参阅[用于 System Center Configuration Manager 的推荐硬件](../LocTest/Recommended-hardware-for-System-Center-Configuration-Manager.md)。  
  
 使用下列部分中的信息来帮助你规划要部署 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 适用于 Linux 和 UNIX 的客户端。  
  
-   [客户端部署到 Linux 和 UNIX 服务器的必备条件](#BKMK_ClientDeployPrereqforLnU)  
  
-   [向 Configuration Manager 外部依赖关系：](#BKMK_ClientDeployExternalforLnU)  
  
-   [适用于 Linux 和 UNIX 服务器规划跨林通信信任](#BKMK_PlanningforCommunicationsforLnU)  
  
-   [适用于 Linux 和 UNIX 客户端的服务位置](#BKMK_ServiceLocationforLnU)  
  
-   [适用于 Linux 和 UNIX 服务器规划安全性和证书](#BKMK_SecurityforLnU)  
  
-   [有关以供 Linux 和 UNIX 服务器的证书](#BKMK_AboutCertsforLnU)  
  
-   [适用于 Linux 和 UNIX 服务器配置证书](#BKMK_ConfigCertsforLnU)  
  
-   [有关 Linux 和 UNIX 的操作系统，请执行不支持 sha-256](#BKMK_NoSHA-256)  
  
##  <a name="BKMK_ClientDeployPrereqforLnU"></a> 客户端部署到 Linux 和 UNIX 服务器的必备条件  
 使用以下信息来确定您必须具有到成功的必备组件安装适用于 Linux 和 UNIX 的客户端。  
  
###  <a name="BKMK_ClientDeployExternalforLnU"></a> 向 Configuration Manager 外部依赖关系：  
 下表描述了所需的 UNIX 和 Linux 操作系统和程序包依赖关系。  
  
 **Red Hat Enterprise Linux ES 版本 4**  
  
|所需的程序包|描述|最低版本|  
|----------------------|-----------------|---------------------|  
|glibc|C 标准库|2.3.4-2|  
|Openssl|OpenSSL 库；安全网络通信协议|0.9.7a-43.1|  
|PAM|可插入身份验证模块|0.77-65.1|  
  
 **Red Hat Enterprise Linux Server release 5.1 (Tikanga)**  
  
|所需的程序包|描述|最低版本|  
|----------------------|-----------------|---------------------|  
|glibc|C 标准库|2.5-12|  
|Openssl|OpenSSL 库；安全网络通信协议|0.9.8b-8.3.el5|  
|PAM|可插入身份验证模块|0.99.6.2-3.14.el5|  
  
 **Red Hat Enterprise Linux Server 版本 6**  
  
|所需的程序包|描述|最低版本|  
|----------------------|-----------------|---------------------|  
|glibc|C 标准库|2.12-1.7|  
|Openssl|OpenSSL 库；安全网络通信协议|1.0.0-4|  
|PAM|可插入身份验证模块|1.1.1-4|  
  
 **Solaris 9 SPARC**  
  
|所需的程序包|描述|最低版本|  
|----------------------|-----------------|---------------------|  
|所需的操作系统修补程序|PAM 内存泄漏|112960-48|  
|SUNWlibC|Sun Workshop Compilers Bundled libC (sparc)|5.9,REV=2002.03.18|  
|SUNWlibms|Forte 开发人员捆绑在一起共享 libm (sparc)|5.9,REV=2001.12.10|  
|Openssl|SMCosslg (sparc)<br /><br /> Sun 未提供适用于 Solaris 9 SPARC 的 OpenSSL 版本。 可以从 Sunfreeware 中获得某个版本。|0.9.7g|  
|PAM|可插入身份验证模块<br /><br /> SUNWcsl，Core Solaris (共享的 Libs) (sparc)|11.9.0,REV=2002.04.06.15.27|  
  
 **Solaris 10 SPARC**  
  
|所需的程序包|描述|最低版本|  
|----------------------|-----------------|---------------------|  
|所需的操作系统修补程序|PAM 内存泄漏|117463-05|  
|SUNWlibC|Sun Workshop Compilers Bundled libC (sparc)|5.10, REV=2004.12.22|  
|SUNWlibms|Math & Microtasking Libraries (Usr) (sparc)|5.10, REV=2004.11.23|  
|SUNWlibmsr|Math & Microtasking Libraries (Root) (sparc)|5.10, REV=2004.11.23|  
|SUNWcslr|Core Solaris Libraries (Root) (sparc)|11.10.0, REV=2005.01.21.15.53|  
|SUNWcsl|Core Solaris Libraries (Root) (sparc)|11.10.0, REV=2005.01.21.15.53|  
|Openssl|SUNopenssl-librararies (Usr)<br /><br /> Sun 为 Solaris 10 SPARC 提供了 OpenSSL 库。 它们与操作系统捆绑在一起。|11.10.0,REV=2005.01.21.15.53|  
|PAM|可插入身份验证模块<br /><br /> SUNWcsr、Core Solaris，(Root) (sparc)|11.10.0, REV=2005.01.21.15.53|  
  
 **Solaris 10 x86**  
  
|所需的程序包|描述|最低版本|  
|----------------------|-----------------|---------------------|  
|所需的操作系统修补程序|PAM 内存泄漏|117464-04|  
|SUNWlibC|Sun 研讨会编译器捆绑 libC (i386)|5.10,REV=2004.12.20|  
|SUNWlibmsr|Math & Microtasking Libraries (Root) (i386)|5.10, REV=2004.12.18|  
|SUNWcsl|核心 Solaris，(共享 Libs) (i386)|11.10.0,REV=2005.01.21.16.34|  
|SUNWcslr|Core Solaris 库 (根) (i386)|11.10.0, REV=2005.01.21.16.34|  
|Openssl|SUNWopenssl 库 ；OpenSSL 库 (用户) (i386)|11.10.0, REV=2005.01.21.16.34|  
|PAM|可插入身份验证模块<br /><br /> SUNWcsr 核心 Solaris，(Root)(i386)|11.10.0,REV=2005.01.21.16.34|  
  
 **Solaris 11 SPARC**  
  
|所需的程序包|描述|最低版本|  
|----------------------|-----------------|---------------------|  
|SUNWlibC|Sun Workshop Compilers Bundled libC|5.11, REV=2011.04.11|  
|SUNWlibmsr|Math & Microtasking Libraries (Root)|5.11, REV=2011.04.11|  
|SUNWcslr|Core Solaris Libraries (Root)|11.11, REV=2009.11.11|  
|SUNWcsl|Core Solaris（共享库）|11.11, REV=2009.11.11|  
|SUNWcsr|Core Solaris, (Root)|11.11, REV=2009.11.11|  
|SUNWopenssl-libraries|OpenSSL Libraries (Usr)|11.11.0,REV=2010.05.25.01.00|  
  
 **Solaris 11 x86**  
  
||||  
|-|-|-|  
|所需的程序包|描述|最低版本|  
|SUNWlibC|Sun Workshop Compilers Bundled libC|5.11, REV=2011.04.11|  
|SUNWlibmsr|Math & Microtasking Libraries (Root)|5.11, REV=2011.04.11|  
|SUNWcslr|Core Solaris Libraries (Root)|11.11, REV=2009.11.11|  
|SUNWcsl|Core Solaris（共享库）|11.11, REV=2009.11.11|  
|SUNWcsr|Core Solaris, (Root)|11.11, REV=2009.11.11|  
|SUNWopenssl-libraries|OpenSSL Libraries (Usr)|11.11.0,REV=2010.05.25.01.00|  
  
 **SUSE Linux Enterprise Server 9 (i586)**  
  
|所需的程序包|描述|最低版本|  
|----------------------|-----------------|---------------------|  
|Service Pack 4|SUSE Linux Enterprise Server 9||  
|OS Patch lib gcc-41.rpm|标准共享库|41-4.1.2_20070115-0.6|  
|OS Patch lib stdc++-41.rpm|标准共享库|41-4.1.2_20070115-0.6|  
|Openssl|OpenSSL 库；安全网络通信协议|0.9.7d-15.35|  
|PAM|可插入身份验证模块|0.77-221-11|  
  
 **SUSE Linux Enterprise Server 10 SP1 (i586)**  
  
|所需的程序包|描述|最低版本|  
|----------------------|-----------------|---------------------|  
|glibc-2.4-31.30|C 标准共享库|2.4-31.30|  
|Openssl|OpenSSL 库；安全网络通信协议|0.9.8a-18.15|  
|PAM|可插入身份验证模块|0.99.6.3-28.8|  
  
 **SUSE Linux Enterprise Server 11 (i586)**  
  
|所需的程序包|描述|最低版本|  
|----------------------|-----------------|---------------------|  
|glibc-2.9-13.2|C 标准共享库|2.9-13.2|  
|PAM|可插入身份验证模块|pam-1.0.2-20.1|  
  
 **通用 Linux（Debian 包）Debian，Ubuntu Server**  
  
|所需的程序包|描述|最低版本|  
|----------------------|-----------------|---------------------|  
|libc6|C 标准共享库|2.3.6|  
|Openssl|OpenSSL 库；安全网络通信协议|0.9.8 或 1.0|  
|PAM|可插入身份验证模块|0.79-3|  
  
 **通用 Linux（RPM 包）CentOS，Oracle Linux**  
  
|所需的程序包|描述|最低版本|  
|----------------------|-----------------|---------------------|  
|glibc|C 标准共享库|2.5-12|  
|Openssl|OpenSSL 库；安全网络通信协议|0.9.8 或 1.0|  
|PAM|可插入身份验证模块|0.99.6.2-3.14|  
  
 **IBM AIX 5L 5.3**  
  
|所需的程序包|描述|最低版本|  
|----------------------|-----------------|---------------------|  
|操作系统版本|操作系统的版本|AIX 5.3，Technology Level 6，Service Pack 5|  
|xlC.rte|XL C/C++ Runtime|9.0.0.2|  
|openssl.base|OpenSSL 库；安全网络通信协议|0.9.8.4|  
  
 **IBM AIX 6.1**  
  
|所需的程序包|描述|最低版本|  
|----------------------|-----------------|---------------------|  
|操作系统版本|操作系统的版本|AIX 6.1、任何 Technology Level 和 Service Pack|  
|xlC.rte|XL C/C++ Runtime|9.0.0.5|  
|OpenSSL/openssl.base|OpenSSL 库；安全网络通信协议|0.9.8.4|  
  
 **IBM AIX 7.1 (Power)**  
  
|所需的程序包|描述|最低版本|  
|----------------------|-----------------|---------------------|  
|操作系统版本|操作系统的版本|AIX 7.1、任何 Technology Level 和 Service Pack|  
|xlC.rte|XL C/C++ Runtime||  
|OpenSSL/openssl.base|OpenSSL 库；安全网络通信协议||  
  
 **HP-UX 11i v2 IA 64**  
  
|所需的程序包|描述|最低版本|  
|----------------------|-----------------|---------------------|  
|HPUXBaseOS|基操作系统|B.11.23|  
|HPUXBaseAux|HP-UX 基操作系统辅助|B.11.23.0706|  
|HPUXBaseAux.openssl|OpenSSL 库；安全网络通信协议|A.00.09.07l.003|  
|PAM|可插入身份验证模块|在 HP-UX 上，PAM 是核心操作系统组件的一部分。 没有其它依赖关系。|  
  
 **HP-UX 11i v2 PA-RISC**  
  
|所需的程序包|描述|最低版本|  
|----------------------|-----------------|---------------------|  
|HPUX11i-OE|HP-UX 基础操作环境|B.11.23.0706|  
|OS-Core.MinimumRuntime.CORE-SHLIBS|兼容开发工具库|B.11.23|  
|HPUXBaseAux|HP-UX 基操作系统辅助|B.11.23.0706|  
|HPUXBaseAux.openssl|OpenSSL 库；安全网络通信协议|A.00.09.071.003|  
|PAM|可插入身份验证模块|在 HP-UX 上，PAM 是核心操作系统组件的一部分。 没有其它依赖关系。|  
  
 **HP-UX 11i v3 PA-RISC**  
  
|所需的程序包|描述|最低版本|  
|----------------------|-----------------|---------------------|  
|HPUX11i-OE|HP-UX 基础操作环境|B.11.31.0709|  
|OS-Core.MinimumRuntime.CORE2-SHLIBS|特定 IA 仿真器库|B.11.31|  
|openssl/Openssl.openssl|OpenSSL 库；安全网络通信协议|A.00.09.08d.002|  
|PAM|可插入身份验证模块|在 HP-UX 上，PAM 是核心操作系统组件的一部分。 没有其它依赖关系。|  
  
 **HP-UX 11i v3 IA64**  
  
|所需的程序包|描述|最低版本|  
|----------------------|-----------------|---------------------|  
|HPUX11i-OE|HP-UX 基础操作环境|B.11.31.0709|  
|OS-Core.MinimumRuntime.CORE-SHLIBS|特定 IA 开发库|B.11.31|  
|SysMgmtMin|最低软件部署工具|B.11.31.0709|  
|SysMgmtMin.openssl|OpenSSL 库；安全网络通信协议|A.00.09.08d.002|  
|PAM|可插入身份验证模块|在 HP-UX 上，PAM 是核心操作系统组件的一部分。 没有其它依赖关系。|  
  
 **[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 依赖项:** 下表列出了支持 Linux 和 UNIX 的客户端的站点系统角色。 有关这些站点系统角色的详细信息，请参阅[为 System Center Configuration Manager 客户端确定站点系统角色](../LocTest/Determine-the-site-system-roles-for-System-Center-Configuration-Manager-clients.md)。  
  
|[!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点系统|更多信息|  
|---------------------------------------|----------------------|  
|管理点|尽管管理点不需要安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 适用于 Linux 和 UNIX 的客户端，必须具有客户端计算机之间传输信息的管理点和 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 服务器。 没有管理点，就无法管理客户端计算机。|  
|分发点|分发点不需要安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 适用于 Linux 和 UNIX 的客户端。 但是，站点系统角色时的要求在将软件部署到 Linux 和 UNIX 服务器。<br /><br /> 因为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 适用于 Linux 和 UNIX 的客户端不支持使用 SMB 的通信、 与客户一起使用的分发点必须支持 HTTP 或 HTTPS 通信。|  
|回退状态点|回退状态点不需要安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 适用于 Linux 和 UNIX 的客户端。 但是，回退状态点中的计算机可以 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点不能与管理点通信时发送状况消息。 客户端还可以向回退状态点发送其安装状态。|  
  
 **防火墙要求**:确保防火墙不会在您指定为客户端请求端口的端口中阻止通信。 适用于 Linux 和 UNIX 的客户端直接与管理点、分发点以及回退状态点进行通信。  
  
 有关客户端通信和请求端口的详细信息，请参阅  [Configure the Client for Linux and UNIX to Locate Management Points](../LocTest/How-to-deploy-clients-to-UNIX-and-Linux-servers-in-System-Center-Configuration-Manager.md#BKMK_ConfigClientMP)。  
  
##  <a name="BKMK_PlanningforCommunicationsforLnU"></a> 为 Linux 和 UNIX 服务器规划跨林信任的通信  
 使用管理 Linux 和 UNIX 服务器 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 作为工作组客户端运行和为位于一个工作组中基于 Windows 的客户端需要类似的配置。 有关来自工作组中的计算机的通信的信息，请参阅 [System Center Configuration Manager 中终结点之间的通信](../LocTest/Communications-between-endpoints-in-System-Center-Configuration-Manager.md)主题中的[跨 Active Directory 林的通信](../LocTest/Communications-between-endpoints-in-System-Center-Configuration-Manager.md#Plan_Com_X-Forest)部分。  
  
###  <a name="BKMK_ServiceLocationforLnU"></a> 适用于 Linux 和 UNIX 客户端的服务位置  
 查找为客户端提供服务的站点系统服务器的任务称为服务位置。 与不同的是基于 Windows 的客户端，适用于 Linux 和 UNIX 客户端不使用 Active Directory 用于服务定位。 此外， [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 适用于 Linux 和 UNIX 的客户端不支持指定的管理点的域后缀的客户端属性。 相反，客户端了解到关于从已知的管理点时安装客户端软件分配给客户端提供服务的其他站点系统服务器。  
  
 有关服务定位的详细信息，请参阅[了解客户端如何查找 System Center Configuration Manager 的站点资源和服务](../LocTest/Understand-how-clients-find-site-resources-and-services-for-System-Center-Configuration-Manager.md)中的[服务定位和客户端如何确定向其分配的管理点](../LocTest/Understand-how-clients-find-site-resources-and-services-for-System-Center-Configuration-Manager.md#BKMK_Plan_Service_Location)。  
  
##  <a name="BKMK_SecurityforLnU"></a> 适用于 Linux 和 UNIX 服务器规划安全性和证书  
 对于与安全且经过身份验证的通信 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点， [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 适用于 Linux 和 UNIX 的客户端使用相同的模型作为通信 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] Windows 的客户端。  
  
 在安装 Linux 和 UNIX 的客户端时，您可以将客户端分配使它能够使用 HTTPS 与进行通信的 PKI 证书 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点。 如果未分配的 PKI 证书，客户端创建自签名的证书和仅通过 HTTP 进行通信。  
  
 在安装时提供的 PKI 证书的客户端使用 HTTPS 与管理点进行通信。 客户端找不到支持 HTTPS 的管理点时，它会回退到 HTTP 使用所提供的 PKI 证书。  
  
 在 Linux 或 UNIX 的客户端使用 PKI 证书时您不需要批准它们。 当客户端使用自签名的证书时，查看在客户端批准的层次结构设置 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台。 如果客户端批准方法不是 **自动批准所有计算机 (不推荐)**, ，您必须手动都批准客户端。  
  
 有关如何手动批准客户端的详细信息，请参阅[如何在 System Center Configuration Manager 中管理客户端](../LocTest/How-to-manage-clients-in-System-Center-Configuration-Manager.md)主题中的[从设备节点管理客户端](../LocTest/How-to-manage-clients-in-System-Center-Configuration-Manager.md#BKMK_ManagingClients_DevicesNode)部分。  
  
 有关如何在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 使用证书的信息，请参阅 [System Center Configuration Manager 的 PKI 证书要求](../LocTest/PKI-certificate-requirements-for-System-Center-Configuration-Manager.md)。  
  
###  <a name="BKMK_AboutCertsforLnU"></a> 有关以供 Linux 和 UNIX 服务器的证书  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 适用于 Linux 和 UNIX 的客户端使用自签名的证书或就像基于 Windows 的客户端的 X.509 PKI 证书。 没有任何变化的 PKI 要求 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 管理 Linux 和 UNIX 的客户端时站点系统。  
  
 对于与通信的 Linux 和 UNIX 的客户端使用证书 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点系统必须采用公钥证书标准 (PKCS #12) 格式，并且密码必须已知，以便指定 PKI 证书时可以指定它向客户端。  
  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 适用于 Linux 和 UNIX 的客户端支持单一的 PKI 证书，并不支持多个证书。 因此，证书选择条件配置为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点不适用。  
  
###  <a name="BKMK_ConfigCertsforLnU"></a> 适用于 Linux 和 UNIX 服务器配置证书  
 若要配置 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 用于 HTTPS 通信 Linux 和 UNIX 服务器的客户端，必须配置客户端在安装客户端时使用 PKI 证书。 无法设置之前的客户端软件安装的证书。  
  
 在安装时使用 PKI 证书的客户端，您使用命令行参数 **-UsePKICert** 指定位置和包含 PKI 证书的 PKCS #12 文件的名称。 此外，您必须使用命令行参数 **-certpw** 来指定证书的密码。  
  
 如果未指定 **-UsePKICert**, ，客户端生成自签名的证书并尝试通过仅使用 HTTP 与站点系统服务器进行通信。  
  
##  <a name="BKMK_NoSHA-256"></a> 有关 Linux 和 UNIX 的操作系统，请执行不支持 sha-256  
 以下 Linux 和 UNIX 操作系统支持为客户端为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 与不支持 sha-256 的版本的 OpenSSL 发布：  
  
-   Red Hat Enterprise Linux 版本 4 (x86/x64)  
  
-   Solaris 版本 9 (SPARC) 和 Solaris 版本 10 (SPARC/x86)  
  
-   SUSE Linux Enterprise Server 版本 9 (x86)  
  
-   版本 HP-UX 11iv2 (PA-RISH/IA64)  
  
 若要管理使用这些操作系统的系统 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)], ，必须安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 具有定向客户端要跳过验证 SHA 256 个字节的命令行开关适用于 Linux 和 UNIX 的客户端。 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 在这些操作系统版本运行的客户端在比支持 sha-256 的客户端不太安全模式下运行。 这种运行较不安全的模式具有以下行为：  
  
-   客户端不会验证与它们从管理点请求的策略关联的站点服务器签名。  
  
-   客户端不会验证它们从分发点下载的包的哈希值。  
  
> [!IMPORTANT]  
>  **IgnoreSHA256validation** 选项允许您在较不安全模式下运行 Linux 和 UNIX 计算机的客户端。 这旨在用于在不包括支持 sha-256 的较旧平台上使用。 这是安全覆盖并不建议使用由 Microsoft，但支持在安全和受信任的数据中心环境中使用。  
  
 当 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 适用于 Linux 和 UNIX 的客户端安装，安装脚本将检查操作系统版本。 默认情况下，如果操作系统版本标识为具有发布不支持 sha-256 的安装 OpenSSL 具有版本 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端将失败。  
  
 若要安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端 Linux 和 UNIX 操作系统在系统上未释放版支持 sha-256 的 OpenSSL，必须使用安装命令行开关 **IgnoreSHA256validation**。 当您使用的适用 Linux 或 UNIX 操作系统上，此命令行选项 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端将跳过 sha-256 验证并安装完成后，客户端将不使用 sha-256 对其提交给站点系统使用 HTTP 的符号数据。 有关将 Linux 和 UNIX 客户端配置为使用证书的详细信息，请参阅本主题中的 [Planning for Security and Certificates for Linux and UNIX Servers](#BKMK_SecurityforLnU) 。 有关需要 SHA-256 的信息，请参阅[配置 System Center Configuration Manager 中的安全](../LocTest/Configure-security-in-System-Center-Configuration-Manager.md)主题中的[配置签名和加密](../LocTest/Configure-security-in-System-Center-Configuration-Manager.md#BKMK_ConfigureSigningEncryption)。  
  
> [!NOTE]  
>  命令行选项 **ignoreSHA256validation** 忽略使用支持 sha-256 的 OpenSSL 版本运行 Linux 和 UNIX 发布的版本的计算机上。  
  
## 另请参阅  
 [在 System Center Configuration Manager 中部署客户端的规划注意事项](../LocTest/Planning-considerations-for-deploying-clients-in-System-Center-Configuration-Manager.md)
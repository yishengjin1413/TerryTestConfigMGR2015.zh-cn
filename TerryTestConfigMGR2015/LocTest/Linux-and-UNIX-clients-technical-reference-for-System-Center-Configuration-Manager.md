---
title: "System Center Configuration Manager 的 Linux 和 UNIX 客户端技术参考 "
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
ms.assetid: e5a8c79f-5791-49c5-8055-086d742e5559
caps.latest.revision: 6
caps.handback.revision: 5
translationtype: Human Translation
---
# System Center Configuration Manager 的 Linux 和 UNIX 客户端技术参考 
此主题包含适用于 Linux 和 UNIX 的 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 客户端的技术信息。  
  
##  <a name="BKMK_ComponentsofClientforLnU"></a> 适用于 Linux 和 UNIX 的 Configuration Manager 客户端组件服务  
 下表标识了适用于 Linux 和 UNIX 的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 客户端的客户端组件服务。  
  
|文件名|更多信息|  
|---------|----------|  
|ccmexec.bin|此服务等效于基于 Windows 的客户端上的 ccmexc 服务。 它负责与 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点系统角色的所有通信，并且还可与 omiserver.bin 服务通信，以从本地计算机收集硬件清单。<br /><br /> 有关支持的命令行参数列表，请运行 **ccmexec \-h**|  
|omiserver.bin|此服务是 CIM 服务器。 CIM 服务器为被称为提供程序的可插拔软件模块提供框架。 提供程序与 Linux 和 UNIX 计算机资源进行交互，并且收集硬件清单数据。 例如，适用于 Linux 计算机的“进程内提供程序”收集与 Linux 操作系统进程关联的数据。|  
  
## 适用于 Linux 和 UNIX 的 Configuration Manager 客户端的命令  
 以下列表列出了在每种版本的 Linux 或 UNIX 上可用于启动、停止或重启客户端服务的命令 \(ccmexec.bin and omiserver.bin\)。 在启动或停止 ccmexec 服务时，omiserver 服务也会启动或停止。  
  
|操作系统|命令|  
|----------|--------|  
|通用代理<br /><br /> RHEL 4 和 SLES 9|启动：**\/etc\/init d\/ccmexecd start**<br /><br /> 停止：**\/etc\/init d\/ccmexecd stop**<br /><br /> 重启：**\/etc\/init d\/ccmexecd restart**|  
|Solaris 9|启动：**\/etc\/init d\/ccmexecd start**<br /><br /> 停止：**\/etc\/init d\/ccmexecd stop**<br /><br /> 重启：**\/etc\/init d\/ccmexecd restart**|  
|Solaris 10|启动：<br /><br /> **svcadm enable –s svc:\/application\/management\/omiserver**<br /><br /> **svcadm enable –s svc:\/application\/management\/ccmexecd**<br /><br /> 停止：<br /><br /> **svcadm disable –s svc:\/application\/management\/ccmexecd**<br /><br /> **svcadm disable –s svc:\/application\/management\/omiserver**|  
|Solaris 11|启动：<br /><br /> **svcadm enable –s svc:\/application\/management\/omiserver**<br /><br /> **svcadm enable –s svc:\/application\/management\/ccmexecd**<br /><br /> 停止：<br /><br /> **svcadm disable –s svc:\/application\/management\/ccmexecd**<br /><br /> **svcadm disable –s svc:\/application\/management\/omiserver**|  
|AIX|启动：<br /><br /> **startsrc –s omiserver**<br /><br /> **startsrc –s ccmexec**<br /><br /> 停止：<br /><br /> **stopsrc –s ccmexec**<br /><br /> **stopsrc –s omiserver**|  
|HP\-UX|启动：**\/sbin\/init.d\/ccmexecd start**<br /><br /> 停止：**\/sbin\/init.d\/ccmexecd stop**<br /><br /> 重启：**\/sbin\/init.d\/ccmexecd restart**|  
  
## 请参阅  
 [System Center Configuration Manager 中客户端管理的技术参考](../LocTest/Client-management-technical-reference-for-System-Center-Configuration-Manager.md)
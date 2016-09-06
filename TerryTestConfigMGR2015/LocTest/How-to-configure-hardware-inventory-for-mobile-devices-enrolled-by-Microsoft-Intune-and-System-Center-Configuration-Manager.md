---
title: "如何配置通过 Microsoft Intune 和 System Center Configuration Manager 注册的移动设备的硬件清单"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-other
ms.tgt_pltfrm: na
ms.topic: get-started-article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 78a0aecc-f775-451e-aa05-56377ec91b1f
caps.latest.revision: 7
caps.handback.revision: 4
author: barlanmsft
translationtype: Human Translation
---
# 如何配置通过 Microsoft Intune 和 System Center Configuration Manager 注册的移动设备的硬件清单
在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中，可以使用 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 连接器收集 iOS、Android 和 Windows 设备上的硬件清单。 有关如何配置硬件清单的信息，请参阅 [如何在 System Center Configuration Manager 中扩展硬件清单](../LocTest/How-to-extend-hardware-inventory-in-System-Center-Configuration-Manager.md)。  
  
 若要了解如何向 [!INCLUDE[mit_first](../LocTest/includes/mit_first_md.md)] 注册设备，请参阅 [使用 Microsoft Intune 管理移动设备](https://technet.microsoft.com/en-us/library/dn646962.aspx)。  
  
## 移动设备的硬件清单  
 下表列出了可用于硬件清单的清单类。  
  
|硬件清单类|Windows Phone 8 和 Windows Phone 8.1|Windows RT|iOS|Android（使用 Android 公司门户应用时可用）|  
|-----------|-----------------------------------------|----------------|---------|-----------------------------------|  
|Name|Device\_ComputerSystem.DeviceName|Device\_ComputerSystem.DeviceName|Device\_ComputerSystem.DeviceName|不适用|  
|唯一的设备 ID|Device\_ComputerSystem.DeviceClientID|Device\_ComputerSystem.DeviceName|Device\_ComputerSystem.UDID|不适用|  
|序列号|不适用|不适用|Device\_ComputerSystem.SerialNumber|Device\_ComputerSystem.SerialNumber|  
|电子邮件地址|Device\_Email.OwnerEmailAddress|Device\_Email.OwnerEmailAddress|Device\_Email.OwnerEmailAddress|不适用|  
|操作系统类型|Device\_OSInformation.Platform|CCM\_OperatingSystem .SystemType|不适用|Device\_OSInformation.Platform|  
|操作系统版本|Device\_ComputerSystem.SoftwareVersion|Win32\_OperatingSystem.Version|Device\_OSInformation.OSVersion|Device\_OSInformation.Version|  
|内部版本|不适用|Win32\_OperatingSystem.BuildNumber|不适用|不适用|  
|Service Pack 主要版本|不适用|Win32\_OperatingSystem.ServicePackMajorVersion|不适用|不适用|  
|Service Pack 次要版本|不适用|Win32\_OperatingSystem.ServicePackMinorVersion|不适用|不适用|  
|操作系统语言|Device\_OSInformation.Language|不适用|不适用|不适用|  
|总存储空间|不适用|Win32\_PhysicalMemory.Capacity|Device\_Memory.DeviceCapacity|Device\_Memory.StorageTotal|  
|可用存储空间|不适用|Win32\_OperatingSystem.FreePhysicalMemory|Device\_Memory.AvailableDeviceCapacity|Device\_Memory.StorageFree|  
|国际移动设备标识或 IMEI \(IMEI\)|不适用|不适用|Device\_ComputerSystem.IMEI|Device\_ComputerSystem.IMEI|  
|移动设备标识符 \(MEID\)|不适用|不适用|Device\_ComputerSystem.MEID|不适用|  
|制造商|Device\_ComputerSystem.DeviceManufacturer|Win32\_ComputerSystem.Manufacturer|不适用|Device\_Info.Manufacturer|  
|型号|Device\_ComputerSystem.DeviceModel|Win32\_ComputerSystem.Model|型号名称|Device\_Info.Model|  
|电话号码 <sup>1</sup>|不适用|不适用|Device\_ComputerSystem.PhoneNumber|Device\_ComputerSystem.PhoneNumber|  
|用户载波|不适用|不适用|Device\_ComputerSystem.SubscriberCarrierNetwork|Device\_ComputerSystem.SubscriberCarrierNetwork|  
|移动电话技术|不适用|不适用|Device\_ComputerSystem.CellularTechnology|Device\_ComputerSystem.CellularTechnology|  
|Wi\-Fi MAC|不适用|Win32\_NetworkAdapter.MACAddress|Device\_WLAN.WiFiMAC|Device\_WLAN.WiFiMAC|  
  
 <sup>1</sup> 除了最后 4 位数字之外，其余电话号码用 \* 屏蔽了。  
  
 若要让清单收集电话号码，设备必须插入 SIM 卡并有该 SIM 的运营商预配的电话号码。  
  
## 请参阅  
 [在 System Center Configuration Manager 中配置硬件清单](../LocTest/Configuring-hardware-inventory-in-System-Center-Configuration-Manager.md)
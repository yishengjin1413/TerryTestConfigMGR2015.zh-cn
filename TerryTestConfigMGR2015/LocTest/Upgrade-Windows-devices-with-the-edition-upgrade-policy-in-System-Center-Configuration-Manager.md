---
title: "在 System Center Configuration Manager 中使用版本升级策略升级 Windows 设备"
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
ms.assetid: 45f20c53-2571-4dea-826d-d1d12d3b5aa0
caps.latest.revision: 11
caps.handback.revision: 8
translationtype: Human Translation
---
# 在 System Center Configuration Manager 中使用版本升级策略升级 Windows 设备
[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]“版本升级策略”可以将运行以下任一 Windows 10 版本的设备自动升级至较新的版本：  
  
-   Windows 10 桌面版  
  
-   Windows 10 移动版  
  
-   Windows 10 全息版  
  
 设备必须在 Microsoft Intune 中进行注册或由 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 进行本地管理。  
  
## 开始之前  
 在开始将设备升级至最新版本之前，你将需要以下内容之一：  
  
-   在该策略针对的所有设备上安装 Windows 新版本使用的有效产品密钥（针对于桌面操作系统）  
  
-   在该策略针对的所有设备上安装 Windows 新版本使用的包含许可信息的 Microsoft 许可证文件（针对于 Windows 10 移动版和 Windows 10 全息版）。  
  
## 配置版本升级策略  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”。  
  
2.  在“资产和符合性”工作区中，展开“符合性设置”，然后单击“Windows 10 版本升级”。  
  
3.  在“主页”选项卡上的“创建”组中，单击“创建版本升级策略”。  
  
4.  单击“创建策略”。  
  
5.  在“创建版本升级策略向导”的“常规”页上，指定以下信息：  
  
    -   **名称** \- 输入版本升级策略的名称。  
  
    -   **描述**（可选）\- 根据需要，输入有助于在 Intune 控制台中识别该策略的描述。  
  
    -   **将设备升级到的 SKU 版本** – 从下拉列表中，选择你想将目标设备升级到的版本：Windows 10 桌面版、Windows 10 全息版或 Windows 10 移动版。  
  
    -   **许可证信息** \- 选择以下之一：  
  
        -   **产品密钥** \- 输入有效的 Windows 10 产品密钥，该密钥将用于升级运行 Windows 10 桌面版操作系统的目标设备。  
  
            > [!NOTE]  
            >  在创建包含产品密钥的策略后，将无法对产品密钥进行编辑。 这是因为出于安全考虑，密钥将被遮盖。 若要更改产品密钥，必须重新输入完整的密钥。  
  
        -   **许可证文件** \- 单击“浏览”以选择有效的 XML 格式的许可证文件，该文件将用于升级运行 Windows 10 全息版和 Windows 10 移动版操作系统的目标设备。  
  
6.  完成向导。  
  
 新策略会显示在“资产和符合性”工作区的“Windows 10 版本升级”节点中。  
  
## 部署版本升级策略  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“资产和符合性”。  
  
2.  在“资产和符合性”工作区中，展开“符合性设置”，然后单击“Windows 10 版本升级”。  
  
3.  选择你想部署的 Windows 10 版本升级策略，然后在“主页”选项卡上的“部署”组中，单击“部署”。  
  
4.  在“部署 Windows 10 版本升级”对话框中，选择你想要为其部署策略以及评估该策略的计划的用户或设备集合，然后单击“确定”。  
  
 可从“监视”工作区的“部署”节点监视才创建的部署。  
  
 一旦该策略应用到目标 Windows 电脑，该电脑将在两小时内重启以应用该升级。 请确保通知将为其部署该策略的任何用户。  
  
## 请参阅  
 [使用 System Center Configuration Manager 确保设备的合规性](../LocTest/Ensure-device-compliance-with-System-Center-Configuration-Manager.md)
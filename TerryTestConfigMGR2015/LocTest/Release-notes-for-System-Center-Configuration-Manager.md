---
title: "System Center Configuration Manager 的发行说明"
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
ms.assetid: 030947fd-f5e0-4185-8513-2397fb2ec96f
caps.latest.revision: 41
caps.handback.revision: 36
---
# System Center Configuration Manager 的发行说明
在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]中，产品发行说明限于尚未在产品（通过在控制台中更新可用）中解决的或者未在 Microsoft 知识库文章中详细介绍的紧急问题。  
  
 有关影响核心方案的已知问题，此信息在 System Center Configuration Manager 文档库中的在线产品文档中传达。  
  
> [!TIP]  
>  本主题包含 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 当前分支的发行说明。 有关 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] Technical Preview 的信息，请参阅 [System Center Configuration Manager Technical Preview](../LocTest/Technical-Preview-for-System-Center-Configuration-Manager.md)  
  
## 安装和升级  

### <a name="bkmk_1606install"></a> 在运行版本 1511 的站点上对 1602 更新运行了先决条件检查且在没有警告的情况下通过后，则更新 1606 安装失败
当你使用版本 1511，只对更新 1602 运行先决条件检查，且在没有警告的情况下通过了该检查，但没有安装 1602 时，将无法成功从 1511 更新至版本 1606。 

此问题仅在你运行 [PowerShell 脚本](https://gallery.technet.microsoft.com/ConfigMgr-1606-Enable-043a8c50)选择加入第一波客户获取此更新且已在 2016 年 7 月 27 日星期三之前下载了该脚本时适用。 如果使用更新的脚本（截至 7 月 27 日可用），在此条件下你将不能加入第一波客户。 而必须等待此更新的通用正式版。 

此问题在以下情况不适用：
 -  更新 1602 的先决条件检查通过，但存在一个或多个警告时
 - 安装版本 1602 后
 - 如果你未选择加入第一波客户以接收更新 1606
 
 当更新 1606 安装失败时，将在 **cmupdate.log** 中出现下列项： 
> - 找不到具有哈希 SHA256:D3EC1B62BE7429D29850E4BA4EEFAD9BA7E6B7782ACBB2BED1318EF3AA660AED 的 SQL 对象 StateSysSqlClr。 将创建该对象。 
>  -  ***  SELECT HashMatch = COUNT(*),         ClrExists = (SELECT COUNT(*) FROM sys.assemblies WHERE name = N'StateSysSqlClr')  FROM DBSchema  WHERE ObjectName=N'StateSysSqlClr' AND ObjectHashAlg=N'SHA256' AND ObjectHash=0xD3EC1B62BE7429D29850E4BA4EEFAD9BA7E6B7782ACBB2BED1318EF3AA660AED AND SiteNumber = dbo.fnGetSiteNumber() 
> -  *** [42000][6270][Microsoft][SQL Server Native Client 11.0][SQL Server]ALTER ASSEMBLY 失败，因为找不到与更新的程序集中具有同一签名的类型 "Microsoft.SystemsManagementServer.SQLCLR.StateSys.VPPMessageParsing" 中要求的方法。 
> -  错误：创建程序集 StateSysSqlClr 失败。
> -  错误：更新 CLR 程序集失败。

**解决方法**：在站点服务器上： 
1.  从管理命令提示符运行以下命令：**net stop CONFIGURATION_MANAGER_UPDATE**
2.  手动复制 **cmupdate.exe**（具有 5.0.8412.1200 版） 
    -  复制于：*\<服务连接点上的 CM 安装目录\>\\EasySetupPayload\\705820EF-6982-4417-8E54-307454C9A17A\\SMSSETUP\\BIN\\X64\\CMUpdate.exe*     
    - **复制到**：*\<站点服务器上的 CM 安装目录\>\\bin\\x64\\CMUpdate.exe*
3.  在站点服务器上从管理命令提示符运行以下命令：**net stop CONFIGURATION_MANAGER_UPDATE**
4.  在 Configuration Manager 控制台中，转到“管理” > “概述” > “云服务” > “更新与服务”，右键单击“1606 更新”并选择“重试安装”。






### Configuration Manager 使用中的 SQL Server 备份模型可以从完整模型更改为简单模型  
 当你升级到 System Center Configuration Manager 版本 1511 时，Configuration Manager 使用的 SQL Server 备份模型可以从完整更改为简单。  
  
-   如果你使用具有完整备份模型自定义 SQL Server 备份任务（而不是 Configuration Manager 的内置备份任务）时，升级可以将你的备份模型从完整更改为简单。  
  
 **解决方法**：升级到版本 1511 后，查看你的 SQL Server 配置，并将其还原为完整（如果必要）。  
  
### 向新站点服务器添加服务时段时，将删除为另一个站点服务器配置的服务时段  
 当你使用 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 1511 版的服务时段时，只能为层次结构中的单个站点服务器配置服务时段。 在一个服务器上配置服务时段之后，当你随后在第二个站点服务器上配置服务时段时，将静默删除第一个站点服务器上的服务时段，而不会出现警告和错误。  
  
 **解决方法**：从 [Microsoft 知识库文章 3142341](http://support.microsoft.com/kb/3142341) 安装修补程序。 为 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 安装 1602 更新时此问题也得到了解决。  
  
### 在 Configuration Manager 控制台的更新和服务节点内，更新停滞在正在下载的状态  
 在通过联机服务连接点自动下载更新时，更新可能会停滞在正在下载的状态。 当更新的下载处于停滞状态时，与下列内容类似的条目将会出现在指示的日志文件中：  
  
 DMPdownloader 日志：  
  
-   ERROR: Failed to download redist for 037cd17e-4d7b-40e1-802b-14bb682364c7 with command  /RedistUrl http://go.microsoft.com/fwlink/?LinkID=724436 /LnManifestUrl http://go.microsoft.com/fwlink/?LinkID=724434 /RedistVersion 112015 /NoUI  "D:\ConfigMgr\EasySetupPayload\037cd17e-4d7b-40e1-802b-14bb682364c7\redist"  
  
 ConfigMgrSetup.log  
  
-   Error: failed to verify 'd:\ConfigMgr\EasySetupPayload\037cd17e-4d7b-40e1-802b-14bb682364c7\redist\sqlncli.msi' authenticode signature.  
  
-   Error: file signature check failed for 'd:\ConfigMgr\EasySetupPayload\037cd17e-4d7b-40e1-802b-14bb682364c7\redist\sqlncli.msi  
  
 **解决方法**：在站点服务器上，修改下列注册表项以匹配以下内容，然后重启 SMS_Executive 服务，或等待（最多 24 小时）下一个自动下载周期。  
  
-   **需要编辑的项**：HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\WinTrust\Trust Providers\Software Publishing  
  
-   **状态值**：设为 **146944** 十进制或者 **0x00023e00** 十六进制  
  
### System Center Configuration Manager 1602 中的预发行功能  
 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 版本 1602 引入了两项预发行功能：  
  
-   对由 System Center Configuration Manager 管理的电脑进行条件访问。 有关详细信息，请参阅[管理对由 System Center Configuration Manager 管理的电脑的 O365 服务的访问](../LocTest/Manage-access-to-O365-services-for-PCs-managed-by-System-Center-Configuration-Manager.md)  
  
-   维护群集感知集合。 有关详细信息，请参阅 [Technical Preview 1605 for System Center Configuration Manager 中的功能](../Topic/Capabilities%20in%20Technical%20Preview%201605%20for%20System%20Center%20Configuration%20Manager.md)中的[为服务器组提供服务](../Topic/Capabilities%20in%20Technical%20Preview%201605%20for%20System%20Center%20Configuration%20Manager.md#BKMK_ServerGroups)。  
  
 预发行功能包含在产品中，用于在生产环境中进行早期测试，但不应将其视为生产就绪。  
 
从更新 1606 开始，在可以使用预发行功能前必须表示许可。 有关详细信息，请参阅[使用更新中的预发行功能](../LocTest/Install-in-console-updates-for-System-Center-Configuration-Manager.md)。

  
### 辅助站点的恢复选项在控制台中不可用  
 恢复辅助站点失败后，“恢复辅助站点”选项可能在 Configuration Manager 控制台中不再可用。  
  
 此问题对 System Center Configuration Manager 版本 1511 和 1602 有所影响，预计会在将来的更新中得到解决。  
  
 **解决方法**：使用以下方法之一来恢复（重新安装）辅助站点：  
  
-   使用 **Preinst.exe** 和 **/delsite** 命令删除辅助站点，然后重新安装辅助站点。 有关 Preinst.exe 的信息，请参阅 [System Center Configuration Manager 的层次结构维护工具 (Preinst.exe)](../LocTest/Hierarchy-Maintenance-Tool--Preinst.exe--for-System-Center-Configuration-Manager.md)  
  
-   运行以下脚本以启动辅助站点恢复。 在要恢复的辅助站点的主父站点的数据库上运行此脚本：  
  
    ```  
    declare @SiteCode NVARCHAR(3)=N'<replace with secondary site code>'   
  
    UPDATE Sites SET Status = 9  
                    , DetailedStatus = 3  
    FROM Sites WHERE SiteCode = @SiteCode  
  
    UPDATE SCP SET SCP.Value1 = 9  
                    , SCP.Value2 = N'3'  
    FROM SC_SiteDefinition_Property SCP INNER JOIN SC_SiteDefinition SC ON SC.SiteNumber = SCP.SiteNumber  
    WHERE SC.SiteCode = @SiteCode AND SCP.[Name] = N'Requested Status'  
    ```  
  
## 备份和恢复
### 预生产客户端在站点还原后不可用
有了版本 1602，在你使用预生产客户端并从备份中还原层次结构的顶层站点时，预生产客户端版本将在站点还原后不可用。  

**解决方法：**还原层次结构中的顶层站点后，必须手动复制预生产客户端文件，以便 Configuration Manager 可对其进行处理和还原以供使用：
1. 在顶层站点服务器计算机上，将 \<CM_Install_Location\>\\Client 文件夹的内容复制到 \<CM_Install_Location\>\\StagingClient 文件夹。
  2. 创建一个名为 **client.acu** 的空文件并将此文件复制或粘贴到站点服务器上的 \<CM_Install_Location\>\\Inboxes\\hman.box 文件夹中。 （此文件可以是已重命名的文本文件，只要它不再具有 txt 扩展名）。 将此文件置于 hman.box 文件夹后，站点服务器上的层次结构管理器将启动并处理客户端文件以及还原预生产客户端文件以供使用。 

此问题已在版本 1606 中解决。
   

## 客户端部署和升级  
  
### 扩展到管理中心站点会停止自动客户端升级  
 仅在 1511 版本中，不能为从主站点扩展到中心管理站点的任意站点运行自动客户端升级。 站点扩展后，客户端升级包上的权威站点未正确设置为新的中心管理站点，这会阻止自动客户端升级的成功运行。 此问题仅存在于在 1511 版本中。 在 1602 及更高版本中，此问题已得到解决。  
  
 **解决方法：**在管理中心站点数据库上运行以下 SQL 脚本。 运行该脚本后，自动客户端升级应该会开始正常运行。  
  
```  
DECLARE @RootSite AS NVARCHAR(3)  
DECLARE @SourceServer AS NVARCHAR(255)  
DECLARE @FullClientPkgSource AS NVARCHAR(255)  
DECLARE @UpgradePkgSource AS NVARCHAR(255)  
  
SELECT @RootSite = SiteCode, @SourceServer = SiteServer  
FROM sites  
WHERE ISNULL(ReportToSite, N'') = N''  
  
SELECT @FullClientPkgSource = N'\\' + @SourceServer + N'\SMS_' + @RootSite + N'\Client'  
SELECT @UpgradePkgSource = N'\\' + @SourceServer + N'\SMS_' + @RootSite + N'\ClientUpgrade'  
  
UPDATE SMSPackages_G  
SET Source = @FullClientPkgSource, SourceSite = @RootSite  
WHERE PkgID IN  
    (SELECT FullPackageID FROM ClientDeploymentSettings)  
  
UPDATE SMSPackages_G  
SET Source = @UpgradePkgSource, SourceSite = @RootSite  
WHERE PkgID IN  
    (SELECT UpgradePackageID FROM ClientDeploymentSettings)  
  
UPDATE ProgramOffers_G  
SET SourceSite = @RootSite  
WHERE OfferID IN  
    (SELECT UpgradeAdvertisementID FROM ClientDeploymentSettings)  
```  
  
## 操作系统部署  
  
### 关于适用于 Windows 10 的 Windows ADK 1511 版的问题  
 如果你从使用 Windows ADK 10 1511 版中 Windows PE v.10.0.10586 启动映像的软件中心中运行任务序列，则计算机重启进入 Windows PE 时将在“初始化硬件设备”阶段失败，并出现错误： **Windows PE 初始化失败，错误代码 0x80220014**  
  
 **解决方法**：使用原始的 Window 10 ADK。 有关详细信息，请参阅以下 System Center Configuration Manager 团队博客： [关于适用于 Windows 10 的 Windows ADK 的问题](http://blogs.technet.com/b/configmgrteam/archive/2015/11/20/issue-with-the-windows-adk-for-windows-10-version-1511.aspx)  
  
### 任务序列成功完成，而在此期间进行的动态应用程序安装失败  
 当你部署使用“根据动态变量列表安装应用程序” 选项的任务序列，而应用程序之一由于任意原因而安装失败时，该任务序列将报告成功。 无论你如何配置以下选项，都将出现这种情况：  
  
-   **出错时继续** （在“安装应用程序”步骤的“选项”选项卡上）  
  
-   **如果应用程序安装失败，则继续安装列表中的其他应用程序** （在“安装应用程序”步骤的“属性”选项卡上）  
  
 你可以查看 smsts.log 以确定应用程序是否安装失败。  
  
 **解决方法**：使用 **_TSAppInstallStatus** 变量作为一个任务序列后续步骤的条件，该条件是如果动态应用程序中的某一个存在错误，那么将使该任务序列失败。  
  
### 在使用任务序列安装 Windows 10 后，SMB 可能无法正常工作  
 当使用任务序列安装 Windows 10 映像时，在 Configuration Manager 客户端安装之后，SMB 可能无法正常工作。 例如，下列任务序列步骤可能会失败：  
  
-   当与状态迁移点一起使用时，还原用户状态  
  
-   连接到网络文件夹  
  
 从 F8 管理员命令提示符中，例如，你仍可以对计算机进行 PING 操作，但任何 SMB 网络流量（如命令提示符中的 NET USE）都可能会失败，错误为 1231 - 无法访问网络位置。  
  
 **解决方法**：  
在安装 Windows 和 ConfigMgr 这一任务序列步骤停止后添加运行命令行这一任务序列步骤，然后如下启动工作站服务：    
**net stop workstation /y & net start workstation**  
  
### 默认情况下，维护计划会创建大量重复的软件更新组和部署  
 默认情况下，创建维护计划向导目前会在每个软件更新同步之后运行。 每次运行向导时，都会创建新的软件更新组和部署。 例如，如果你有每天多次运行的软件更新同步计划，创建维护计划向导每天都会创建多个并且可能相同的软件更新组和部署。  
  
 **解决方法**：    
创建维护计划后，打开维护计划的属性，转到“评估计划”选项卡，选择“按计划运行此规则”，单击“自定义”，然后创建自定义计划。 例如，你可以将维护计划设置为每 60 天运行一次。  
  
## 移动设备管理  
  
### 无法在主站点上创建注册配置文件  
 管理员不能在连接到主站点的 System Center Configuration Manager 管理控制台中创建注册配置文件。 在尝试注册时，管理员将在注册配置文件向导中看到“DEP 令牌未更新。 请上传 DEP 令牌”错误。 即使向管理中心站点上传了有效的 DEP 令牌，仍将发生此错误。  
  
 **解决方法**：在连接到管理中心站点的 System Center Configuration Manager 控制台中创建注册配置文件。  
  
### 在注册配置文件中，DEP 不能使用非字母数字字符  
 当启用 DEP 时，与 Apple 的设备注册配置文件 (DEP) 关联的注册配置文件不能在注册配置文件的“名称” 、“描述” 、“部门”  和“电话号码”  字段中使用非字母数字字符。 在这些字段中使用非字母数字字符将创建注册配置文件，但该配置文件无法上传至 Apple。 Apple 服务器将不提供错误消息或警告，配置文件将不部署至 DEP 管理的设备。  
 
  **解决方法**：无。
  
### 完全擦除会禁用 RAM 小于 4 GB 的 Windows 10 设备
 
在 RAM 小于 4 GB 的 Windows 10 RTM 设备（早于版本 1511 的版本）上执行完全擦除可能会使该设备不可用。 尝试擦除该设备后，设备无法启动且无响应。 

 **解决方法**：在设备上执行完全擦除前，确保 Windows 10 RTM 电脑至少具有 4 GB 的可用 RAM。 若要查看 Windows 10 设备的版本号，请在命令提示符处输入 ＂winver＂。 如果已擦除设备，且它不再响应，则使用可启动的 Windows 10 USB 驱动器启动并恢复对该设备的访问。
  
### 如果用户属于部署了同一条款和条件策略的两个或更多用户集合，则该用户将看到多组相同条款  
 当管理员将一组条款部署至多个用户集合，而用户是这些集合中多个集合的成员时，该用户打开公司门户时将看到相同条款的多个副本。  例如，如果名为“SampleUser”的用户是两个不同的用户集合的成员，两个集合分别称为“CompanyEmployeesFTE”和“CompanyEmployeesNA”，并且向 CompanyEmployeesFTE 和 CompanyEmployeesNA 均部署了名为“CompanyTerms”的条件和条款，那么 SampleUser 将在条款接受页面看到两组相同的 CompanyTerms。 由于用户只可接受或拒绝所有条款，因此不存在接受状态不明确的风险（即用户同时接受和拒绝条款）。 对于每位用户的每组条款，条款和条件接受报表将仅包括一行，因此报表中没有错误。 唯一的影响是用户会在接受页面看到两组条款。  
  
 **解决方法**：确保每个用户只包含在条款部署到的一个集合中。  
  
## 报告和监视  
  
### 运行状况认证报告为空，即使之前收集过运行状况认证数据  
 当具有安全角色（包括对“运行状况认证”权限组有“读取”权限）的管理用户查看运行状况认证报告时，报告为空并且无法显示数据。 这是因为查看运行状况认证报告中数据的权限链接到了“用户设备相关性”权限组，而不是“运行状况认证”权限组。  
  
 此问题影响 1602 更新的 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]，预计会在将来的更新中得到解决。  
  
 **解决方法**：为管理用户分配包括对“用户设备相关性”权限组有“读取”权限的安全组。  
  
### 条件性访问  
  
#### 同一用户集合添加到免除和目标集合不受阻止。  
 这仅发生在将同一“用户集合”添加到“目标集合”页前，将其添加到“免除集合”页。  如果首先将“用户集合”添加到“目标集合”页，然后尝试将同一“用户集合”添加到“免除集合”页，你会看到正常的拦截消息。  
  
 此问题影响 1602 更新中对 **Exchange 本地**进行 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 条件性访问，预计会在将来的更新中得到解决。  
  
 **解决方法：**在“免除集合”页上选择“用户集合”之前，将“用户集合”添加到“目标集合”页，或者确保不会将同一“用户集合”添加到“目标集合”和“免除集合”中。
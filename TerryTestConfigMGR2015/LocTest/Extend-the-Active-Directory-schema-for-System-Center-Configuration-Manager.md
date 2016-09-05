---
title: "扩展 System Center Configuration Manager 的 Active Directory 架构"
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
ms.assetid: bc15ee7e-4d0a-4463-ae2c-f72d8d45d65d
caps.latest.revision: 17
caps.handback.revision: 16
translationtype: Human Translation
---
# 扩展 System Center Configuration Manager 的 Active Directory 架构
为 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 扩展 Active Directory 架构时，向 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点所使用的 Active Directory 引入新结构，以便将关键信息发布在客户端可以轻松访问的安全位置。  
  
 当你管理本地客户端时，建议使用 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 和扩展的 Active Directory 架构。 扩展的架构可以简化部署和配置客户端的过程，并让客户端能够有效地查找资源（如内容服务器）和各种 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 站点系统角色提供的其他服务。  
  
-   如果你不熟悉提供 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 部署的扩展架构，可参阅 [System Center Configuration Manager 的架构扩展](../LocTest/Schema-extensions-for-System-Center-Configuration-Manager.md)以帮助你做出这一决定。  
  
-   当不使用扩展的架构时，你可以配置其他方法（例如 DNS 和 WINS）来查找服务和站点系统服务器。 这些服务定位方法需要附加配置，不是客户端进行服务定位的首选方法。 若要了解详细信息，请阅读[了解客户端如何查找 System Center Configuration Manager 的站点资源和服务](../LocTest/Understand-how-clients-find-site-resources-and-services-for-System-Center-Configuration-Manager.md)，  
  
-   如果已为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 2007 或 [!INCLUDE[cm5short](../LocTest/includes/cm5short_md.md)]扩展 Active Directory 架构，则不需要执行更多操作。 架构扩展不变，并已就位。  
  
 扩展架构是用于任何林的一次性操作。 若要扩展并利用扩展的 Active Directory 架构涉及以下步骤：  
  
## 步骤 1。 扩展架构  
 为 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 扩展架构需要进行以下操作：  
  
-   使用属于“架构管理员”安全组成员的帐户  
  
-   登录到架构主机域控制器  
  
-   运行 **Extadsch.exe** 工具，或将 LDIFDE 命令行实用程序用于 **ConfigMgr\_ad\_schema.ldf** 文件。 工具和文件均位于 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 安装媒体上的 **SMSSETUP\\BIN\\X64** 文件夹中。  
  
#### 选项 A：使用 Extadsch.exe  
  
1.  运行 **extadsch.exe** ，将新类和属性添加到 Active Directory 架构。  
  
    > [!TIP]  
    >  从命令行运行此工具，以便在它运行时查看反馈。  
  
2.  通过查看位于系统驱动器根目录中的 extadsch.log，验证架构扩展是否成功。  
  
#### 选项 B：使用 LDIF 文件  
  
1.  编辑 **ConfigMgr\_ad\_schema.ldf** 文件以定义你希望扩展的 Active Directory 根域：  
  
    -   必须将该文件中文本 **DC\=x** 的所有实例替换为要扩展的域的完整名称  
  
    -   例如，要扩展的域的完整名称为 widgets.microsoft.com，则将文件中 DC\=x 的所有实例更改为“DC\=widgets, DC\=microsoft, DC\=com”。  
  
2.  使用 LDIFDE 命令行实用工具将 **ConfigMgr\_ad\_schema.ldf** 文件的内容导入 Active Directory 域服务：  
  
    -   例如，下列命令行会将架构扩展导入 Active Directory 域服务，启用详细日志记录，并在导入过程中创建一个日志文件：**ldifde \-i \-f ConfigMgr\_ad\_schema.ldf \-v \-j \<location to store log file\>**  
  
3.  通过查看上一步中使用的命令行所创建的日志文件，可以验证架构扩展是否成功。  
  
## 步骤 2。  创建系统管理容器，并向该容器授予站点权限  
 扩展架构之后，必须在 Active Directory 域服务 \(AD DS\) 中创建名为“系统管理”的容器：  
  
-   在具有将向 Active Directory 发布数据的主站点或辅助站点的每个域中创建一次此容器  
  
-   对于每个容器，向发布该域数据的每个主站点和辅助站点服务器的计算机帐户授予权限。 每个帐户都需要对容器具有“完全控制”权限，并且高级权限“应用到”等于“这个对象及全部后代”  
  
#### 若要添加容器  
  
1.  使用对 Active Directory 域服务中“系统”容器具有“创建所有子对象”权限的帐户。  
  
2.  运行“ADSI 编辑器”\(adsiedit.msc\)，并连接到站点服务器的域。  
  
3.  创建容器：  
  
    -   展开“域”\<计算机完全限定的域名\>，展开\<可分辨名称\>，右键单击“CN\=System”，再单击“新建”，然后单击“对象”。  
  
    -   在  “创建对象”对话框中，选择“容器” ，然后单击“下一步” 。  
  
    -   在“值”  框中，键入“系统管理” ，然后单击“下一步” 。  
  
4.  分配权限：  
  
    > [!NOTE]  
    >  如果有需要，可以使用 Active Directory 用户和计算机管理工具 \(dsa.msc\) 等其他工具向容器添加权限。  
  
    -   右键单击“CN\=System Management”，然后单击“属性”。  
  
    -   选择“安全”选项卡，单击“添加”，然后添加具有  
        “完全控制”权限的站点服务器计算机帐户。  
  
    -   单击“高级” ，选择站点服务器的计算机帐户，然后单击“编辑” 。  
  
    -   在“应用到”  列表中，选择“这个对象及全部后代” 。  
  
5.  单击“确定”关闭控制台并保存配置。  
  
## 步骤 3。 配置站点以发布到 Active Directory 域服务  
 配置容器并授予权限，并且安装 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 主站点后，你可以配置该站点以将数据发布到 Active Directory。  
  
 有关发布的信息，请参阅 [Publish site data for System Center Configuration Manager](../LocTest/Publish-site-data-for-System-Center-Configuration-Manager.md)。  
  
## 另请参阅  
 [为 System Center Configuration Manager 准备网络环境](../LocTest/Prepare-your-network-environment-for-System-Center-Configuration-Manager.md)
---
title: "如何在 System Center Configuration Manager 中监视证书配置文件"
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
ms.assetid: 98feaa06-64b1-4e86-a122-93017c97cd4f
caps.latest.revision: 7
caps.handback.revision: 6
---
# 如何在 System Center Configuration Manager 中监视证书配置文件
将 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 证书配置文件部署到层次结构中的用户后，你可以使用下列过程来监视证书配置文件的符合性状态：  
  
-   [如何在 Configuration Manager 控制台中查看符合性结果](#BKMK_console)  
  
-   [如何使用报表来查看符合性结果](#BKMK_Reports)  
  
##  <a name="BKMK_console"></a> 如何在 Configuration Manager 控制台中查看符合性结果  
 使用此过程在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 控制台中查看有关所部署的证书配置文件的符合性的详细信息。  
  
> [!NOTE]  
>  要监视 SCEP 证书符合性，请勿使用 Configuration Manager 控制台，而应按 [如何使用报表来查看符合性结果](#BKMK_Reports) 中说明使用报表。 具体而言，使用位于报表节点“公司资源访问”下的这些证书报表：  
>   
>  -   证书颁发历史记录  
> -   证书即将到期的资产列表  
> -   按证书颁发状态列出的资产的列表  
  
#### 在 Configuration Manager 控制台查看符合性结果  
  
1.  在[!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)]控制台中，单击“监视”。  
  
2.  在“监视”工作区中，单击“部署”。  
  
3.  在“部署”列表中，选择要查看其符合性信息的证书配置文件部署。  
  
4.  你可以在主页上查看有关证书配置文件符合性的摘要信息。 若要查看更详细的信息，请选择证书配置文件，然后在“主页”选项卡上的“部署”组中，单击“查看状态”以打开“部署状态”页。  
  
     “部署状态”页包含下列选项卡：  
  
    -   **符合**：显示基于受影响资产数量的证书配置文件的符合性。 你可以双击规则以在“资产和符合性”工作区中的“用户”节点下创建一个临时节点。 此节点包含符合此证书配置文件的所有用户。 “资产详细信息”窗格也显示符合此配置文件的用户。 双击列表中的用户以显示其他信息。  
  
        > [!IMPORTANT]  
        >  如果某个证书配置文件在客户端设备上不适用，则不会评估该配置文件。 但是，它返回的状态为符合。  
  
    -   **错误**：显示基于受影响资产数量的所选证书配置文件部署的所有错误的列表。 你可以双击规则以在“资产和符合性”工作区的“用户”节点下创建一个临时节点。 此节点包含对于此配置文件生成了错误的所有用户。 当你选择某个用户时，“资产详细信息”窗格将显示受所选问题影响的用户。 双击列表中的用户以显示有关问题的其他信息。  
  
    -   **不符合**：显示基于受影响资产数量的证书配置文件内所有不符合规则的列表。 你可以双击规则以在“资产和符合性”工作区的“用户”节点下创建一个临时节点。 此节点包含不符合此配置文件的所有用户。 当你选择某个用户时，“资产详细信息”窗格将显示受所选问题影响的用户。 双击列表中的用户以显示有关问题的进一步信息。  
  
    -   **未知**：显示没有为所选证书配置文件部署报告符合性的所有用户的列表，以及设备的当前客户端状态。  
  
5.  在“部署状态”页上，你可以查看有关所部署的证书配置文件的符合性的详细信息。 将在“部署”节点下创建一个临时节点，该节点可帮助你快速再次找到此信息。  
  
     证书的注册状态显示为数字。 使用下表了解每个数字的含意：  
  
    |注册状态|描述|  
    |----------|--------|  
    |0x00000001|注册成功，并已颁发证书。|  
    |0x00000002|已提交请求并且正在等待注册，或者已在带外发出请求。|  
    |0x00000004|注册必须被推迟。|  
    |0x00000010|出现了错误。|  
    |0x00000020|注册状态未知。|  
    |0x00000040|已跳过状态信息。 如果 HYPERLINK "http:\/\/msdn.microsoft.com\/en\-us\/windows\/ms721572" \\l "\_security\_certification\_authority\_gly" 证书颁发机构无效或者尚未选中进行监视，便会出现此问题。|  
    |0x00000100|注册被拒绝。|  
  
##  <a name="BKMK_Reports"></a> 如何使用报表来查看符合性结果  
 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的符合性设置包括内置报表，你可以使用这些报表监视有关证书配置文件的信息。 这些报表的报表类别为“符合性和设置管理”。  
  
> [!IMPORTANT]  
>  在符合性设置报表中使用参数“设备筛选器”和“用户筛选器”时，你必须使用通配符 \(%\) 字符。  
  
 有关如何配置 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中的报告的详细信息，请参阅 [System Center Configuration Manager 中的报表](../LocTest/Reporting-in-System-Center-Configuration-Manager.md)。  
  
## 请参阅  
 [System Center Configuration Manager 中证书配置文件的操作和维护](../LocTest/Operations-and-maintenance-for-certificate-profiles-in-System-Center-Configuration-Manager.md)
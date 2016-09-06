---
title: "使用 System Center Configuration Manager 创建和部署应用程序"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-app
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 3bd1e487-ea18-43c1-b7c3-acbd9b86d429
caps.latest.revision: 15
caps.handback.revision: 12
author: barlanmsft
translationtype: Human Translation
---
# 使用 System Center Configuration Manager 创建和部署应用程序
在本主题中，你将直接开始使用 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 创建应用程序。 在此示例中，你将为 Windows PC 创建并部署一个包含业务线应用的应用程序，该应用程序名为“Contoso.msi”且必须安装在你公司中运行 Windows 10 的所有 PC 上。 与此同时，你将了解许多有关你可以执行哪些操作以帮助有效管理应用程序的内容。  
  
> [!TIP]  
>  此过程旨在为你提供有关如何创建和部署 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 应用程序的概述。 但是，它并未涵盖你可以配置的每个选项，也未涵盖如何为其他平台创建和配置应用程序的内容。  
>   
>  有关为其他平台安装应用程序时的区别的详细信息，请参阅以下其中一个主题：  
>   
>  -   [使用 System Center Configuration Manager 创建 Windows 应用程序](../LocTest/Creating-Windows-applications-with-System-Center-Configuration-Manager.md)  
> -   [使用 System Center Configuration Manager 创建 iOS 应用程序](../LocTest/Creating-iOS-applications-with-System-Center-Configuration-Manager.md)  
> -   [使用 System Center Configuration Manager 创建 Android 应用程序](../LocTest/Creating-Android-applications-with-System-Center-Configuration-Manager.md)  
> -   [使用 System Center Configuration Manager 创建 Windows Phone 应用程序](../LocTest/Creating-Windows-Phone-applications-with-System-Center-Configuration-Manager.md)  
> -   [使用 System Center Configuration Manager 创建 Mac 计算机应用程序](../LocTest/Creating-Mac-computer-applications-with-System-Center-Configuration-Manager.md)  
> -   [使用 System Center Configuration Manager 创建 Linux 和 UNIX 服务器应用程序](../LocTest/Creating-Linux-and-UNIX-server-applications-with-System-Center-Configuration-Manager.md)  
  
 如果你已经熟悉 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 应用程序，则可以跳过本主题。 然而，在你创建和部署应用程序前，你可能需要查看 [如何使用 System Center Configuration Manager 创建应用程序](../LocTest/How-to-create-applications-with-System-Center-Configuration-Manager.md) 以了解所有可用的选项。  
  
## 创建和部署应用程序  
 使用以下部分中的信息为你站点中的所有 Windows 10 PC 创建、部署和监视“Contoso.msi”应用程序。  
  
### 开始之前  
 确保你已经查看了[System Center Configuration Manager 中的应用程序管理入门](../LocTest/Get-started-with-application-management-in-System-Center-Configuration-Manager.md)中的信息，以确保已经准备好站点以安装应用程序并确保你已了解本主题中使用的术语。  
  
 此外，请确保“Contoso.msi”应用的安装文件位于网络上的可访问位置。  
  
### 创建 Configuration Manager 应用程序  
  
##### 如何启动创建应用程序向导并创建应用程序  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“软件库”。  
  
2.  在“软件库”工作区中，展开“应用程序管理”，然后单击“应用程序”。  
  
3.  在“主页”选项卡上的“创建”组中，单击“创建应用程序”。  
  
4.  在“创建应用程序向导”的“常规”页上，选择“自动检测安装文件中有关此应用程序的信息”。 这将使用从 .msi 安装文件中提取出来的信息预设向导中的某些信息，然后指定以下信息：  
  
    -   “类型”\- 选择“Windows Installer \(\*.msi 文件\)”  
  
    -   **位置** \- 输入安装文件“Contoso.msi”的位置（或单击“浏览”以选择位置）。 注意，必须以 *\\\\Server\\Share\\File* 格式指定位置，以便 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 找到安装文件。  
  
         此时的屏幕截图如下：  
  
         ![App management wizard general page](../LocTest/media/App-management-wizard-general-page.png "App)  
  
5.  单击“下一步”。 在向导的“导入信息”页上，你将看到一些有关该应用以及被导入 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的任何相关文件的信息。 完成后，再次单击“下一步”。  
  
6.  在向导的“一般信息”页上，可以提供有关该应用程序的进一步信息，以帮助你在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中进行排序和查找。  
  
     此外，“安装”程序字段允许你指定将用于在 PC 上安装该应用程序的完整命令行。 你可以编辑此字段以添加自己的属性（例如添加“\/q”以进行无人参与的安装）。  
  
    > [!TIP]  
    >  导入应用程序安装文件后，向导的此页上的某些字段可能已自动填充。  
  
     此时的屏幕截图如下：  
  
     ![App management wizard general information page](../LocTest/media/App-management-wizard-general-information-page.png "App)  
  
7.  单击“下一步”。 在向导的“摘要”页上，你可以确认应用程序的设置，然后完成向导。  
  
 应用创建结束。 若要找到它，请在“软件库”工作区中，展开“应用程序管理”，然后单击“应用程序”。 对于此示例，你将看到：  
  
 ![Final app graphic](../LocTest/media/Final-app-graphic.png "Final)  
  
### 检查应用文件的属性及其部署类型  
 你已经创建了应用程序，现在可以优化应用程序设置（如果需要）。 若要查看应用程序属性，请选择应用，然后在“主页”选项卡的“属性”组中，单击“属性”。  
  
 在“\<Contoso\> 应用程序属性”对话框中，你将看到许多项，你可以配置这些项以对应用程序的行为进行微调。 有关可配置的所有设置的详细信息，请参阅[如何使用 System Center Configuration Manager 创建应用程序](../LocTest/How-to-create-applications-with-System-Center-Configuration-Manager.md)。 就本示例而言，你只是改变应用程序部署类型的某些属性。  
  
 单击“部署类型”选项卡，选择“Contoso 应用程序”部署类型，然后单击“编辑”。 此时将看到如下所示的对话框：  
  
 ![App management app properties page](../LocTest/media/App-management-app-properties-page.png "App)  
  
### 将要求添加到部署类型  
 这些要求指定必须满足什么条件才能将应用程序安装到设备上。  你可以从内置要求中选择或创建自己的要求。 在此示例中，你将添加指定仅在运行 Windows 10 的 PC 上安装应用程序的要求。  
  
##### 添加要求  
  
1.  在你刚打开的部署类型属性页中，单击“要求”选项卡。  
  
2.  单击“添加”以打开“创建要求”对话框。  
  
3.  在“创建要求”对话框中，指定以下信息：  
  
    -   “类别”\-“设备”  
  
    -   “条件”\-“操作系统”  
  
    -   “规则类型”\-“值”  
  
    -   “运算符”\-“其中一个”  
  
    -   从操作系统列表中，选择“Windows 10”。  
  
     将显示如下对话框：  
  
     ![App management requirements page](../LocTest/media/App-management-requirements-page.png "App)  
  
4.  单击“确定”以关闭打开的每个属性页，并返回到 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中的“应用程序”列表。  
  
> [!TIP]  
>  这些要求可以帮助减少你所需的 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 集合的数量。 由于你指定了只能在运行 Windows 10 的 PC 上安装该应用程序，因此稍后你可以将它部署到包含运行各种不同操作系统的 PC 的集合，应用程序将仅安装在 Windows 10 PC 上。  
  
### 将应用程序内容添加到分发点  
 若想成功将应用程序部署到 PC，下一步则必须确保将应用程序内容复制到分发点。 PC 将访问分发点以安装应用程序。  
  
> [!TIP]  
>  若要了解有关 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 中的分发点和内容管理的详细信息，请参阅 [为 System Center Configuration Manager 管理内容和内容基础结构](../LocTest/Manage-content-and-content-infrastructure-for-System-Center-Configuration-Manager.md)。  
  
##### 若要将应用程序内容复制到分发点  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“软件库”。  
  
2.  在“软件库”工作区中，展开“应用程序”，然后在应用程序列表中，选择你所创建的“Contoso 应用程序”。  
  
3.  在“主页”选项卡上的“部署”组中，单击“分发内容”。  
  
4.  在“分发内容向导”的“常规”页上，检查应用程序名称是否正确，然后单击“下一步”。  
  
5.  在“内容”页上，查看将被复制到分发点的信息，然后单击“下一步”。  
  
6.  在“内容目标”页上，单击“添加”以选择一个或多个分发点或要在其上安装应用程序内容的分发点组。  
  
7.  完成向导。  
  
 你可以从“分发状态”\>“内容状态”下的“监视”工作区检查是否已将应用程序内容成功复制到了分发点。  
  
### 部署应用程序  
 接下来，将应用程序部署到层次结构中的设备集合。 对于此示例，你需要将应用程序部署到“所有系统”设备集合。  
  
> [!TIP]  
>  请记住，根据你之前选定的要求，只有 Windows 10 计算机将安装应用程序。  
  
##### 若要部署应用程序  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“软件库”。  
  
2.  在“软件库”工作区中，展开“应用程序管理”，然后单击“应用程序”。  
  
3.  从应用程序列表中，选择之前创建的应用程序“Contoso 应用程序”，然后在“主页”选项卡上的“部署”组中，单击“部署”。  
  
4.  在“部署软件向导”的“常规”页，单击“浏览”以选择“所有系统”设备集合。  
  
5.  在向导的“内容”页，检查是否选中你想让 PC 安装应用程序的分发点。  
  
6.  在向导的“部署设置”页中，确保将部署操作设置为“安装”，将部署目的设置为“必需”。  
  
    > [!TIP]  
    >  通过将部署目的设置为“必需”，确保在满足你设定要求的 PC 上安装应用程序。 如果将该值设置为“可用”，则用户可以根据软件中心的要求安装应用程序。  
  
7.  在“计划”页上，你可以配置安装应用程序的时间。 对于此示例，选择“在可用时间之后尽快”。  
  
8.  在向导的“用户体验”页中，单击“下一步”以接受默认值。  
  
9. 完成向导。  
  
 使用下面的“监视应用程序”部分中的信息，查看应用程序部署的状态。  
  
### 监视应用程序  
 在本部分中，你将快速查看你刚才部署的应用程序的部署状态。  
  
##### 若要查看部署状态  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“监视”。  
  
2.  在“监视”工作区中，单击“部署”。  
  
3.  从部署列表中选择“Contoso 应用程序”。  
  
4.  在“主页”选项卡上的“部署”组中，单击“查看状态”。  
  
5.  选择以下选项卡之一，以查看有关应用程序部署更多状态：  
  
    -   **成功** \- 应用程序已成功安装在了指定的 PC 上。  
  
    -   **正在进行** \- 应用程序尚未完成安装。  
  
    -   **错误** \- 在指定的 PC 上安装应用程序时出现了错误。 此外还会显示有关错误的更多信息。  
  
    -   **不符合要求** \- 应用程序没有在指定的设备上尝试安装，因为它们不符合你配置的要求（在此示例中，因为它们未运行 Windows 10）。  
  
    -   **未知** \- [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 无法报告部署状态。 稍后重新检查。  
  
> [!TIP]  
>  监视应用程序部署可以采用多种方式。 有关完整的详细信息，请参阅 [使用 System Center Configuration Manager 监视应用程序](../LocTest/Monitor-applications-with-System-Center-Configuration-Manager.md)。  
  
### 结束用户体验  
 具有通过 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 管理的运行 Windows 10 的 PC 的用户很快将看到一条消息，告知必须安装 Contoso 应用程序。 用户接受安装后，将安装应用程序。  
  
## 请参阅  
 [使用 System Center Configuration Manager 部署并管理应用程序](../LocTest/Deploy-and-manage-applications-with-System-Center-Configuration-Manager.md)
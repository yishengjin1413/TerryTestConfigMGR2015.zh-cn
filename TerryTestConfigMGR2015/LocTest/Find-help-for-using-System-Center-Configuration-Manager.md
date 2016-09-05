---
title: "查找使用 System Center Configuration Manager 的帮助"
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
ms.assetid: 86810629-cf2a-43e8-86a2-847444119fc1
caps.latest.revision: 19
caps.handback.revision: 15
---
# 查找使用 System Center Configuration Manager 的帮助
使用下列资源来了解有关 [!INCLUDE[cmshortname](../LocTest/includes/cmshortname_md.md)] 的其他信息：  
  
-   [信息和支持](#bkmk_Info)  
  
    -   [搜索文档库](#BKMK_SearchTips)  
  
    -   [System Center Configuration Manager 团队博客](#BKMK_ProductGroupBlog)  
  
    -   [支持选项和社区资源](#BKMK_SupportOptions)  
  
-   [Configuration Manager 控制台的辅助功能](#bkmk_aconsole)  
  
-   [Configuration Manager 帮助的辅助功能](#bkmk_ahelp)  
  
##  <a name="bkmk_Info"></a> 信息和支持  
 使用下列资源来了解有关 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的其他信息。  
  
|若要执行此操作...|... 执行此操作：|  
|----------------|----------------|  
|访问最新的 [!INCLUDE[cmshortname](../LocTest/includes/cmshortname_md.md)] 产品文档|使用 TechNet [Documentation Library for System Center Configuration Manager（System Center Configuration Manager 的文档库）](http://go.microsoft.com/fwlink/p/?LinkId=691974)|  
|若要提供有关文档的反馈|使用位于 [System Center Configuration Manager 反馈（文档）](https://configurationmanager.uservoice.com/forums/300492-ideas/category/112371-documentation)的 User Voice 提交反馈|  
|若要接收来自文档团队的 Twitter 源（例如，文档更新通知）|请参阅 [Configuration Manager Documentation Team Twitter feed（Configuration Manager 文档团队 Twitter 源）](http://go.microsoft.com/fwlink/p/?LinkId=191940)|  
|通过 Facebook 联系我们|请参阅[我们的 Facebook 页面。](https://www.facebook.com/ConfigMgriX)|  
  
###  <a name="BKMK_SearchTips"></a> 搜索文档库  
 [使用此查询](http://go.microsoft.com/fwlink/?LinkId=691975)在 TechNet 库中查找 [!INCLUDE[cmshortname](../LocTest/includes/cmshortname_md.md)] 联机文档。  
  
 此自定义 Bing 搜索查询将搜索范围确定在 TechNet 上，以便仅查看 [!INCLUDE[cmshortname](../LocTest/includes/cmshortname_md.md)] 的文档库中的结果。 例如，搜索结果不会包括社区资源中的主题。 它使用占位符搜索文本 **System Center Configuration Manager**，你可以在搜索栏中将其替换为自己的一个或多个搜索字符串和所选的搜索运算符，以帮助你缩小搜索结果范围。  
  
#### 示例搜索  
 使用[查找联机信息](http://go.microsoft.com/fwlink/?LinkId=691975)链接并使用以下示例自定义搜索。  
  
-   单个搜索字符串：要搜索包含搜索字符串 **Endpoint Protection** 的主题，请使用 **Endpoint Protection** 替换 **Configuration Manager**：  
  
    ```  
    ("Endpoint Protection") site:technet.microsoft.com/library meta:search.MSCategory(bb126093)  
    ```  
  
-   组合搜索字符串：要搜索包含搜索字符串 **Endpoint Protection** 和 **monitoring** 的主题，请使用 **AND** 运算符：  
  
    ```  
    ("Endpoint Protection") AND ("monitoring") site:technet.microsoft.com/library meta:search.MSCategory(bb126093)  
    ```  
  
-   替换搜索字符串：要搜索包含搜索字符串 **Endpoint Protection** 或 **monitoring** 的主题，请使用 **OR** 运算符：  
  
    ```  
    ("Endpoint Protection" OR "monitoring") site:technet.microsoft.com/library meta:search.MSCategory(bb126093)  
    ```  
  
-   排除搜索字符串：要搜索包含搜索字符串 **Endpoint Protection** 的主题并排除有关 **monitoring** 的主题，请使用 **NOT** 运算符：  
  
    ```  
    ("Endpoint Protection)" NOT ("monitoring") site:technet.microsoft.com/library meta:search.MSCategory(bb126093)  
    ```  
  
#### 搜索提示  
 使用下列搜索提示来帮助你查找所需信息：  
  
-   使用与你在用户界面 \(UI\) 和 TechNet 文档中所看到的词条匹配的搜索词，而不是你可能会在社区内容中看到的非正式词条或缩写。 例如，搜索“management point”（管理点）而不是“MP”、搜索“deployment type”（部署类型）而不是“DT”，以及搜索“software updates”（软件更新）而不是“SUM”。  
  
-   在 TechNet 或帮助文件中的页面上搜索时（例如，按 Ctrl\-F1，并在“查找”框中输入搜索词），结果不包括折叠的部分中的文本。 要搜索折叠部分中的文本，请在搜索页面之前展开这些部分。 要执行此操作，你可以单击页面顶部的“全部展开”按钮，或者双击任何折叠部分。 展开所有部分后，则可以通过在页面上进行搜索来搜索该页面上的所有部分。  
  
-   要搜索帮助文件中的主题，请按 F1，并在“查找”对话框中输入搜索词。 帮助文件不支持“全部展开”选项，你必须先手动展开各个折叠部分，然后才能在页面上进行搜索来查找那些部分中的文本。  
  
-   请尽可能使用 TechNet 在线库，而不是下载的文档。 TechNet 包含最新信息，并且你搜索的信息可能不在下载的文档中，或者可能有修正或额外的在线信息。  
  
-   如果你发现搜索本地存储的文档更快捷轻松，你可以选择 TechNet 上的多个主题并将它们保存在本地。**登录到 TechNet** ，然后，在想要保存在本地的页面顶部，单击“导出”（位于“打印”旁）。 然后你会看到“导出多组页面”横幅，你可以添加和删除要保存的页面。 然后单击“管理页面”以将其导出。 有关详细信息，请单击横幅中的“帮助”。  
  
###  <a name="BKMK_ProductGroupBlog"></a> System Center Configuration Manager 团队博客  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 工程和合作伙伴团队使用 [System Center Configuration Manager Team Blog（System Center Configuration Manager 团队博客）](http://go.microsoft.com/fwlink/?LinkId=191941)向你提供有关 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 和相关技术的技术信息和其他新闻。 我们的博客文章补充了产品文档和支持信息。  
  
###  <a name="BKMK_SupportOptions"></a> 支持选项和社区资源  
 下列链接提供有关支持选项和社区资源的信息：  
  
-   [Microsoft 帮助和支持](http://go.microsoft.com/fwlink/?LinkId=243064)  
  
-   [Configuration Manager 社区页面](http://go.microsoft.com/fwlink/p/?LinkId=243065)  
  
-   [Configuration Manager 论坛页面](https://social.technet.microsoft.com/Forums/en-US/home?category=ConfigMgrCB)  
  
##  <a name="bkmk_aconsole"></a> Configuration Manager 控制台的辅助功能  
 除了 Windows 中的辅助功能和工具之外，以下功能也可以使残障人士对 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 的访问更加简单：  
  
-   要访问工作区，请使用以下键盘快捷方式：  
  
    |工作区|键盘快捷方式|  
    |---------|------------|  
    |资产和符合性|Ctrl\+1|  
    |软件库|Ctrl\+2|  
    |监视|Ctrl\+3|  
    |管理|Ctrl\+4|  
  
-   要访问工作区菜单，请按 Tab 键，直到焦点位于“展开\/折叠”图标上为止。 然后，按向下箭头键以访问工作区菜单。  
  
-   要在工作区菜单中导航，请使用箭头键。  
  
-   要访问工作区中的其他区域，请使用 Tab 键和 Shift\+Tab 键。 要在工作区区域（如功能区）内导航，请使用箭头键。  
  
-   当焦点在树节点中时，若要访问地址栏，请按 3 次 Shift\+Tab。  
  
-   在向导或属性页上，可以使用键盘快捷方式在方框之间移动。 按 Alt 键加带下划线的字符 \(Alt\+\_\) 可以选择特定方框。  
  
> [!NOTE]  
>  [!INCLUDE[accessibility6](../LocTest/includes/accessibility6_md.md)]  
  
##  <a name="bkmk_ahelp"></a> Configuration Manager 帮助的辅助功能  
 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 帮助中包括的功能使其能够被更广大的用户使用，包括行动不方便、视力低下的人士或其他残障人士。  
  
|若要执行此操作|使用此键盘快捷方式|  
|-------------|---------------|  
|显示“帮助”窗口。|F1|  
|在帮助主题窗格与导航窗格（“内容”、“搜索”和“索引”选项卡）之间移动光标。|F6|  
|处于导航窗格中时，在选项卡（例如，“内容”、“搜索”和“索引”）之间切换。|Alt \+ 选项卡的带下划线的字母|  
|选择下一个隐藏的文本或超链接。|选项卡|  
|选择上一个隐藏的文本或超链接。|Shift\+Tab|  
|为所选的“全部显示”、“全部隐藏”、隐藏文本或超链接执行操作。|Enter|  
|显示“选项”菜单以访问任何帮助工具栏命令。|Alt\+O|  
|隐藏或显示包含“内容”、“搜索”和“索引”选项卡的窗格。|Alt\+O，再按 T|  
|显示以前查看过的主题。|Alt\+O，再按 B|  
|显示以前显示的主题序列中的下一主题。|Alt\+O，再按 F|  
|返回指定的主页。|Alt\+O，再按 H|  
|阻止“帮助”窗口打开帮助主题，例如阻止网页下载。|Alt\+O，再按 S|  
|打开 Windows Internet Explorer 的“Internet 选项”对话框，您可以在其中更改辅助功能设置。|Alt\+O，再按 I|  
|刷新主题，例如链接的网页。|Alt\+O，再按 R|  
|打印书中的所有主题或仅打印选定的主题。|Alt\+O，再按 P|  
|关闭“帮助”窗口。|Alt\+F4|  
  
#### 更改帮助主题的外观  
  
1.  若要准备自定义“帮助”中的颜色、字形和字号，请打开“帮助”窗口。  
  
2.  单击“选项”，然后单击“Internet 选项”。  
  
3.  在“常规”选项卡上，单击“辅助功能”。 选择“不使用网页中指定的颜色”、“不使用网页中指定的字体样式”和“不使用网页中指定的字体大小”。 您也可以选择使用自己的样式表中指定的设置。  
  
#### 更改“帮助”中的背景或文本的颜色  
  
1.  打开“帮助”窗口。  
  
2.  单击“选项”，然后单击“Internet 选项”。  
  
3.  在“常规”选项卡上，单击“辅助功能”。 然后，选择“不使用网页中指定的颜色”。 您也可以选择使用自己的样式表中指定的设置。  
  
4.  要自定义“帮助”中使用的颜色，请在“常规”选项卡上单击“颜色”。 清除“使用 Windows 颜色”复选框，然后选择要使用的字体颜色和背景颜色。  
  
    > [!NOTE]  
    >  如果在“帮助”窗口中更改帮助主题的背景颜色，则更改还会影响 Windows Internet Explorer 中的网页的背景颜色。  
  
#### 更改“帮助”中的字体  
  
1.  打开“帮助”窗口。  
  
2.  单击“选项”，然后单击“Internet 选项”。  
  
3.  在“常规”选项卡上，单击“辅助功能”。 要使用与 Windows Internet Explorer 实例中使用的设置相同的设置，请选择“不使用网页中指定的字体样式”和“不使用网页中指定的字体大小”。 您也可以选择使用自己的样式表中指定的设置。  
  
4.  要自定义“帮助”中使用的字形，请在“常规”选项卡上单击“字体”，然后单击所需的字形。  
  
    > [!NOTE]  
    >  如果在“帮助”窗口中更改帮助主题的字体，则更改还会影响 Windows Internet Explorer 中的网页的字体。  
  
## 请参阅  
 [System Center Configuration Manager 简介](../LocTest/Introduction-to-System-Center-Configuration-Manager.md)
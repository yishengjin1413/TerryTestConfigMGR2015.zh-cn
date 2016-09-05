---
title: "如何使用 System Center Configuration Manager 创建应用程序"
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
ms.assetid: cc230ff4-7056-4339-a0a6-6a44cdbb2857
caps.latest.revision: 14
caps.handback.revision: 12
author: barlanmsft
translationtype: Human Translation
---
# 如何使用 System Center Configuration Manager 创建应用程序
<?xml version="1.0" encoding="UTF-8"?>
<developerConceptualDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns:xlink="http://www.w3.org/1999/xlink">
    <introduction>
        <para><token>cm6long</token> 应用程序包含将软件部署到设备所需的文件和信息。 应用程序包含一个或多个构成安装文件的部署类型以及安装软件所需的信息。 部署类型还包含用于指定软件部署时间和方法的规则。</para>
    <para>可以使用以下方法创建应用程序：</para><list class="bullet"><listItem><para>通过读取应用程序安装文件来自动创建应用程序和部署类型。

</para></listItem><listItem><para>

手动创建应用程序并稍后添加部署类型。

</para></listItem><listItem><para>从文件中导入应用程序。</para></listItem></list><para>按照本节中的步骤，使用 <token>cmshort</token> 创建应用程序和部署类型。 </para></introduction>
    <section>
        <title>创建应用程序的步骤</title>
        <content>
            <para>按照以下步骤来学习如何创建 <token>cmshort</token> 应用程序。</para>
        </content>
        <sections>
            <section>
                <title>启动“创建应用程序向导”</title>
                <content>
                    <procedure>
<title>若要启动“创建应用程序向导”</title>
 <steps class="ordered">
        <step><content><para>请在 <token>cmshort</token> 控制台中，单击“软件库”<ui></ui>。</para></content></step>
        <step><content><para>


在“软件库”<ui></ui>工作区中，展开“应用程序管理”<ui></ui>，然后单击“应用程序”<ui></ui>。

</para></content></step>
      <step><content><para>


在“主页”<ui></ui>选项卡上的“创建”<ui></ui>组中，单击“创建应用程序”<ui></ui>。

</para></content></step></steps>
</procedure>
                </content>
            </section>
        <section>
                <title>指定要自动检测应用程序信息还是手动定义该信息</title>
                <content>
                    <list class="bullet"><listItem><para>
<ui>自动检测应用程序信息</ui>要创建具有单一部署类型（例如没有依赖关系或要求的 Windows Installer 文件）的简单应用程序时，使用此信息。 使用此过程创建了应用程序后，你可以根据需要对其进行编辑，以便添加或更改部署类型以及添加检测方法、依赖关系或要求。

</para></listItem><listItem><para><ui>手动指定应用程序信息</ui>来创建具有多个部署类型、依赖关系、检测方法或要求的更复杂的应用程序</para></listItem></list>
                <procedure>
<title>自动检测应用程序信息</title>
 <steps class="ordered">
        <step><content><para>


在“创建应用程序向导”的“常规”<ui></ui>页，选择“自动检测安装文件中有关此应用程序的信息”<ui></ui>复选框。</para></content></step>
        <step><content><para>在“类型”<ui></ui>下拉列表中，选择要用于检测应用程序信息的应用程序安装文件类型。 有关可用安装类型的信息，请参阅本主题中的 <link xlink:href="#BKMK_Dtypes">Configuration Manager 支持的部署类型</link>。</para></content></step>
      <step><content><para>



在“位置”<ui></ui>字段中，以 <placeholder>\\&lt;server&gt;\&lt;share&gt;\&lt;filename&gt;</placeholder> 格式或以你想要用来检测应用程序信息的应用程序安装文件的存储链接来指定 UNC 路径。 或者，单击“浏览”<ui></ui>以浏览到安装文件。

</para><alert class="important">
<para>如果选择“Windows Installer(*.msi 文件)”<ui></ui>作为应用程序类型，则指定文件夹中的所有文件都将随应用程序导入，并将发送到分发点。 请确保你指定的文件夹中只有安装应用程序所必需的文件。 <token>cmshort</token> 经测试可支持应用程序包中多达 20,000 个应用程序文件。 如果你的应用程序包含更多文件，请考虑创建具有较少数量文件的多个应用程序。
</para>
<para>对于包含应用程序的 UNC 路径以及包含应用程序内容的任何子文件夹，你必须具有访问权限。
</para></alert></content></step><step><content><para>


在“创建应用程序向导”的“导入信息”<ui></ui>页上，查看已导入的信息，然后单击“下一步”<ui></ui>。 如有必要，可以单击“上一步”<ui></ui>以返回并更正任何错误。

</para></content></step><step><content><para>


在“创建应用程序向导”的“常规信息”<ui></ui>页上，指定以下信息：

</para><alert class="note">
<para>如果已从应用程序安装文件中自动获取了其中的一些信息，这些信息可能已填充。 此外，显示的选项可能会因创建的应用程序类型而异。
</para>
</alert><list class="bullet"><listItem><para> 

提供有关应用程序的常规信息，例如应用程序名称、备注、版本，以及可选的引用来帮助你在 <token>cmshort</token> 控制台中引用应用程序。

</para></listItem><listItem><para><ui>安装程序</ui> - 指定安装程序和安装应用程序部署类型所需的所有属性</para><alert class="tip">
<para>如果未显示安装程序，请单击“浏览”<ui></ui>，然后浏览到安装程序的位置。
</para>
</alert></listItem><listItem><para><ui>安装行为</ui> - 指定是仅为当前已登录用户还是为所有用户安装应用程序部署类型。 你也可以指定为所有用户安装部署类型（如果部署到设备）或仅安装到指定用户（如果部署到用户）。</para></listItem><listItem><para><ui>使用自动 VPN 连接（如果已配置）</ui> - 如果在启动应用之后将 VPN 配置文件部署到设备，当应用启动时（仅 Windows 8.1 和 Windows Phone 8.1），启动 VPN 连接。</para><para>在 Windows Phone 8.1 设备上，如果有多个 VPN 配置文件部署到设备，则不支持自动 VPN 连接。</para><para>有关 VPN 配置文件的详细信息，请参阅 <link xlink:href="c0f094f1-852e-4606-91db-97846d8f0772">System Center Configuration Manager 中的 VPN 配置文件</link>。</para></listItem></list></content></step><step><content><para>



单击“下一步”<ui></ui>，查看“摘要”<ui></ui>页上的应用程序信息，然后完成“创建应用程序向导”。

</para></content></step></steps>
<conclusion><content><para>


新的应用程序显示在 <token>cmshort</token> 控制台的“应用程序”<ui></ui>节点中，而你已完成创建一个应用程序的过程。 如果想要将更多部署类型添加到应用程序，请参阅本主题中的<link xlink:href="#BKMK_Dept1">为应用程序创建部署类型</link>。

</para></content></conclusion></procedure><procedure>
<title>若要手动指定应用程序信息</title>
 <steps class="ordered">
        <step><content><para>


在“创建应用程序向导”的“常规”<ui></ui>页上，选择“手动指定应用程序信息”<ui></ui>，然后单击“下一步”<ui></ui>。

</para></content></step>
        <step><content><para>指定有关应用程序的常规信息，例如应用程序名称、备注、版本，以及可选的引用来帮助你在 <token>cmshort</token> 控制台中查找应用程序。</para></content></step>
      <step><content><para>


在“创建应用程序向导”的<?Comment Rob:Isn&apos;t this going to change? 11/2/2015 12:33:52 AM Id='ee2d6c9f51d1adf7'?><ui>应用程序目录</ui><?CommentEnd Id='ee2d6c9f51d1adf7'?>页上，指定以下信息：

</para><list class="bullet"><listItem><para><ui>所选语言</ui> - 在下拉列表中，选择要配置的应用程序的语言版本。 单击“添加/删除”<ui></ui>为此应用程序配置更多语言。</para></listItem><listItem><para><ui>本地化的应用程序名称</ui> - 以在“所选语言”<ui></ui>下拉列表中选择的语言指定应用程序名称。</para><alert class="important">
<para>必须为配置的每个语言版本指定一个本地化的应用程序名称。
</para>
</alert></listItem><listItem><para><ui>用户类别</ui> - 单击“编辑”<ui></ui>以在“所选语言”<ui></ui>下拉列表中选择的语言指定应用程序类别。 软件中心的用户可以使用这些所选类别来帮助对可用的应用程序进行筛选和排序。</para></listItem><listItem><para><ui>用户文档</ui> - 单击“浏览”<ui></ui>来指定文件的 URL 或 UNC 路径和文件名，软件中心的用户可阅读该文件来获取有关此应用程序的详细信息。</para></listItem><listItem><para><ui>链接文本</ui> - 指定将取代应用程序 URL 显示的文本。</para></listItem><listItem><para><ui>应用程序隐私 URL</ui> - 指定链接到应用程序隐私声明的 URL。</para></listItem><listItem><para><ui>本地化的说明</ui> - 以在“所选语言”<ui></ui>下拉列表中选择的语言为此应用程序输入说明。</para></listItem><listItem><para><ui>关键字</ui> - 以在“所选语言”<ui></ui>下拉列表中选择的语言输入关键字的列表。 这些关键字将帮助软件中心的用户搜索应用程序。</para></listItem><listItem><para><ui>图标</ui> - 单击“浏览”<ui></ui>从可用图标中为此应用程序选择一个图标。 如果不指定图标，则会为此应用程序使用默认图标。</para></listItem><listItem><para><ui>将此应用显示为特色应用并在公司门户中突出显示</ui> - 选择此选项以在公司门户中突出显示该应用。</para></listItem></list></content></step><step><content><para>


在“创建应用程序向导”的“部署类型”<ui></ui>页上，单击“添加”<ui></ui>创建一个新部署类型。

有关详细信息，请参阅本主题中的<link xlink:href="#BKMK_Dept1">为应用程序创建部署类型</link>。</para></content></step><step><content><para> 



单击“下一步”<ui></ui>，查看“摘要”<ui></ui>页上的应用程序信息，然后完成“创建应用程序向导”。

</para></content></step></steps>
<conclusion><content><para>


新应用程序会出现在 <token>cmshort</token> 控制台的“应用程序”<ui></ui>节点中。</para></content></conclusion></procedure></content>
            </section></sections>
    </section>
    <section address="BKMK_Dept1">
<title>为应用程序创建部署类型</title><content><para>如果在“创建部署类型向导”的“常规”<ui></ui>页上选择“从安装文件中自动识别有关此部署类型的信息”<ui></ui>复选框，则你可能无需完成下列过程中的某些步骤。
</para></content>
<sections><section>
<title>启动创建部署类型向导</title><content><procedure>
<title></title>
 <steps class="ordered">
        <step><content><para>


在 <token>cmshort</token> 控制台中，单击“软件库”<ui></ui>。

</para></content></step>
        <step><content><para>


在<unmanagedCodeEntityReference>软件库</unmanagedCodeEntityReference>工作区中，展开“应用程序管理”<ui></ui>，然后单击“应用程序”<ui></ui>。

</para></content></step>
      <step><content><para>


选择应用程序，然后在“主页”<ui></ui>选项卡上的“应用程序”<ui></ui>组中，单击“创建部署类型”<ui></ui>。

</para></content></step></steps>
</procedure><alert class="tip">
<para>你还可以从“创建应用程序向导”和 <placeholder>&lt;应用程序名称&gt;</placeholder>“属性”<ui></ui>对话框的“部署类型”<ui></ui>选项卡中启动创建部署类型向导。
</para>
</alert></content>
</section><section>
<title>指定是要自动检测部署类型信息还是手动配置该信息</title><content><para>使用下列过程之一来自动检测或手动配置部署类型信息。</para><procedure>
<title>自动检测部署类型信息</title>
 <steps class="ordered">
        <step><content><para>


在“创建部署类型向导”的“常规”<ui></ui>页上，选择“从安装文件中自动识别有关此部署类型的信息”<ui></ui>复选框。

</para></content></step>
        <step><content><para> 



在“类型”<ui></ui>字段中，选择要用于检测部署类型信息的应用程序安装文件类型。

</para></content></step>
      <step><content><para>



在“位置”<ui></ui>字段中，以 <placeholder>\\&lt;server&gt;\&lt;share&gt;\&lt;file_name&gt;</placeholder> 格式或以指向应用程序安装文件的存储链接和你想用于检测部署类型信息的内容来指定 UNC 路径。 还可以单击“浏览”<ui></ui>以找到安装文件。

</para><alert class="note">
<para>对于包含应用程序的 UNC 路径以及包含应用程序内容的任何子文件夹，你必须具有访问权限。
</para>
</alert></content></step><step><content><para>


在“创建部署类型向导”的“导入信息”<ui></ui>页上，查看已导入的信息，然后单击“下一步”<ui></ui>。 你也可以单击“上一步”<ui></ui>返回并更正任何错误。

</para></content></step><step><content><para>


在“创建部署类型向导”的“常规信息”<ui></ui>页上，指定以下信息：

</para><alert class="note">
<para>如果从应用程序安装文件中读取了某些部署类型信息，则可能已经存在这些信息。 此外，显示的选项可能会因你创建的部署类型而异。</para>
</alert><list class="bullet"><listItem><para> 

指定有关部署类型的常规信息，例如名称、管理员备注和可用语言。

</para></listItem><listItem><para><ui>安装程序</ui> - 指定安装部署类型所需的安装程序和任何属性。</para></listItem><listItem><para><ui>安装行为</ui> - 指定是为当前已登录用户还是为所有用户安装部署类型。 你也可以指定是为所有用户安装部署类型（如果部署到设备），还是仅为某个用户安装部署类型（如果部署到用户）。</para></listItem><listItem><para><ui>使用自动 VPN 连接（如果已配置）</ui> - 如果在启动应用后将 VPN 配置文件部署到设备，当应用启动时（仅 Windows 8.1 和 Windows Phone 8.1），启动 VPN 连接。 如果已将多个 VPN 配置文件部署到 Windows 8.1 设备，则默认情况下使用第一个部署的 VPN 配置文件。</para><para>在 Windows Phone 8.1 设备上，如果有多个 VPN 配置文件部署到设备，则不支持自动 VPN 连接。</para><para>有关 VPN 配置文件的详细信息，请参阅 <link xlink:href="c0f094f1-852e-4606-91db-97846d8f0772">System Center Configuration Manager 中的 VPN 配置文件</link>。</para></listItem></list></content></step><step><content><para>单击“下一步”<ui></ui>，然后转至<link xlink:href="#BKMK_Content">为部署类型指定内容选项</link>。</para></content></step></steps>
</procedure><procedure>
<title>手动配置部署类型信息</title>
 <steps class="ordered">
        <step><content><para>在“创建部署类型向导”的“常规”<ui></ui>页上，选择“手动指定部署类型信息”<ui></ui>。</para></content></step>
        <step><content><para> 



在“类型”<ui></ui>字段中，选择要用于检测部署类型信息的应用程序安装文件类型。 你可以选择将在自动检测部署类型信息时使用的相同安装类型，此外还可以指定用于安装部署类型的脚本。

</para></content></step>
      <step><content><para>


在“创建部署类型向导”的“常规信息”<ui></ui>页上，指定部署类型的名称、可选描述、提供此部署类型所要采用的语言，然后单击“下一步”<ui></ui>。

</para></content></step><step><content><para>转至<link xlink:href="#BKMK_Content">为部署类型指定内容选项</link>。</para></content></step></steps>
</procedure></content>
</section><section address="BKMK_Content">
<title>为部署类型指定内容选项</title><content><procedure>
<title>为部署类型指定内容选项</title>
 <steps class="ordered">
        <step><content><para>


在“创建部署类型向导”的“内容”<ui></ui>页上，指定以下信息：

</para><list class="bullet"><listItem><para>内容位置 - 指定此部署类型的内容的位置，或单击“浏览”选择部署类型内容文件夹。</para><alert class="important">
<para>站点服务器计算机的系统帐户必须具有所指定内容位置的权限。
</para>
</alert></listItem><listItem><para><ui>保留客户端缓存中的内容</ui> - 选择此选项以指定是否应该在客户端计算机的缓存中永久保留内容，即使已运行了客户端计算机。 尽管此选项对于某些部署（例如基于 Windows Installer 的软件，该软件需要有本地源副本才能应用更新）可能很有用，但它会减少可用缓存空间。 如果选择此选项，在缓存没有足够的可用空间的情况下，将可能会导致以后的大型部署失败。</para></listItem><listItem><para><ui>允许客户端与同一子网上的其他客户端共享内容</ui> - 选择此选项，以允许客户端从网络上已经下载和缓存内容的其他本地客户端中下载内容，从而减小网络负荷。 此选项使用 Windows BranchCache 技术。</para></listItem><listItem><para><ui>安装程序</ui> - 指定安装程序的名称和任何所需的安装参数，或单击“浏览”<ui></ui>以找到安装文件。</para></listItem><listItem><para><ui>安装开始于</ui> -（可选）指定包含部署类型的安装程序的文件夹。 此文件夹可以是客户端上的绝对路径，或包含安装文件的分发点文件夹的路径。 </para></listItem><listItem><para><ui>卸载程序</ui> -（可选）指定卸载程序的名称和任何所需参数，或单击“浏览”<ui></ui>以找到它。</para></listItem><listItem><para><ui>卸载开始于</ui> -（可选）指定包含部署类型的卸载程序的文件夹。 此文件夹可以是客户端上的绝对路径，或者是相对于包含包的分发点文件夹的路径。</para></listItem><listItem><para><ui>在 64 位客户端上以 32 位进程形式运行安装程序和卸载程序</ui> - 使用基于 Windows 的计算机上的 32 位文件和注册表位置来运行部署类型的安装程序。</para></listItem></list></content></step>
        <step><content><para>单击“下一步”<ui></ui>。</para></content></step>
      </steps>
</procedure></content>
</section><section>
<title>将检测方法配置为指示部署类型的状态（仅适用于 Windows PC）</title><content><para>此过程配置用于指示部署类型是否已安装的检测方法。</para><procedure>
<title>配置检测方法</title>
 <steps class="ordered">
        <step><content><para>


在“创建部署类型向导”的“检测方法”<ui></ui>页上，选择“配置对此部署类型的状态进行检测的规则”<ui></ui>，然后单击“添加子句”<ui></ui>。

</para><alert class="note">
<para>你也可以选择“使用自定义脚本检测此部署类型的状态”<ui></ui>。 有关详细信息，请参阅本主题中的<link xlink:href="#BKMK_Script">使用自定义脚本确定部署类型的状态</link>部分。
</para>
</alert></content></step>
        <step><content><para> 



在“检测规则”<ui></ui>对话框的“设置类型”<ui></ui>下拉列表中，选择要用于检测部署类型的状态的方法。 你可以从下列可用的方法中选择：

</para><list class="bullet"><listItem><para><ui>文件系统</ui> - 使用此方法检测客户端设备上是否存在指定的文件或文件夹，从而指明已经安装了应用程序。</para><alert class="note">
<para>“文件系统”<ui></ui>设置类型不支持在“路径”字段中指定网络共享的 UNC 路径。 你只能指定客户端设备上的本地路径。
</para>
<para>选择“此文件或文件夹与 64 位系统中的 32 位应用程序相关联”<ui></ui>选项，以首先检查 32 位文件位置中是否有指定的文件或文件夹。 如果未找到此文件或文件夹，则将搜索 64 位位置。
</para></alert></listItem><listItem><para><ui>注册表</ui> - 你可以使用此方法检测客户端设备上是否存在指定的注册表项或注册表值，从而指明已经安装了应用程序。</para><alert class="note">
<para>选择“此注册表项与 64 位系统上的 32 位应用程序相关联”<ui></ui>选项，以首先检查 32 位注册表位置中是否有指定的注册表项。 如果未找到此注册表项，则将搜索 64 位位置。
</para>
</alert></listItem><listItem><para><ui>Windows Installer</ui> - 使用此方法检测客户端设备上是否存在指定的 Windows Installer 文件，从而指明已经安装了应用程序。</para></listItem></list></content></step>
      <step><content><para>指定想要用于检测是否安装了此部署类型的项目的详细信息。 例如，可以使用文件、文件夹、注册表项、注册表值或者 Windows Installer 产品代码。</para></content></step><step><content><para>


指定想要按照项目（用于检测是否安装了此部署类型）评估的值的详细信息。 例如，你使用文件来确定是否安装了部署类型，则可以选择“为了指明此应用程序的状态，目标系统上必须存在文件系统设置”<ui></ui>复选框。

</para></content></step><step><content><para>


单击“下一步”<ui></ui>以关闭“检测规则”<ui></ui>对话框。

</para></content></step></steps>
</procedure><procedure address="BKMK_Script">
<title>使用自定义脚本确定部署类型的状态</title>
 <steps class="ordered">
        <step><content><para>


在“创建部署类型向导”的“检测方法”<ui></ui>页上，选择“使用自定义脚本检测此部署类型的状态”<ui></ui>复选框，然后单击“编辑”<ui></ui>。

</para></content></step>
        <step><content><para>


在“脚本编辑器”<ui></ui>对话框的“脚本类型”<ui></ui>下拉列表中，选择要用于检测部署类型的脚本语言。

</para></content></step>
      <step><content><para>


在“脚本内容”<ui></ui>字段中，输入要使用的脚本。 你还可以将现有脚本的内容粘贴在此字段中，或单击“打开”<ui></ui>以浏览到现有的已保存脚本。 Configuration Manager 通过读取写入到“标准输出 (STDOUT)”输出流、“标准错误 (STDERR)”输出流和来自脚本的退出代码的值来确定从脚本得到的结果。 如果退出代码为非零值，则脚本已经失败，并且应用程序检测状态为未知。 如果退出代码为零，并且 STDOUT 包含数据，则应用程序检测状态为“已安装”。

</para><para>使用下表确定如何使用脚本输出来确定是否安装了应用程序。</para><table border="1"><tbody><tr><TD><para>脚本退出代码</para></TD><TD><para>详细信息</para></TD></tr><tr><TD><para>0</para></TD><TD><para><ui>从 STDOUT 中读取的数据</ui> - 空</para><para><ui>从 STDERR 中读取的数据</ui> - 空</para><para><ui>脚本结果</ui> - 成功</para><para><ui>应用程序检测状态</ui> - 未安装</para></TD></tr><tr><TD><para>0</para></TD><TD><para><ui>从 STDOUT 中读取的数据</ui> - 空</para><para><ui>从 STDERR 中读取的数据</ui> - 不为空</para><para><ui>脚本结果</ui> - 失败</para><para><ui>应用程序检测状态</ui> - 未知</para></TD></tr><tr><TD><para>0</para></TD><TD><para><ui>从 STDOUT 中读取的数据</ui> - 不为空</para><para><ui>从 STDERR 中读取的数据</ui> - 空</para><para><ui>脚本结果</ui> - 成功</para><para><ui>应用程序检测状态</ui> - 已安装</para></TD></tr><tr><TD><para>0</para></TD><TD><para><ui>从 STDOUT 中读取的数据</ui> - 不为空</para><para><ui>从 STDERR 中读取的数据</ui> - 不为空</para><para><ui>脚本结果</ui> - 成功</para><para><ui>应用程序检测状态</ui> - 已安装</para></TD></tr><tr><TD><para>非零值
</para></TD><TD><para><ui>从 STDOUT 中读取的数据</ui> - 空</para><para><ui>从 STDERR 中读取的数据</ui> - 空</para><para><ui>脚本结果</ui> - 失败</para><para><ui>应用程序检测状态</ui> - 未知</para></TD></tr><tr><TD><para>非零值
</para></TD><TD><para><ui>从 STDOUT 中读取的数据</ui> - 空</para><para><ui>从 STDERR 中读取的数据</ui> - 不为空</para><para><ui>脚本结果</ui> - 失败</para><para><ui>应用程序检测状态</ui> - 未知</para></TD></tr><tr><TD><para>非零值
</para></TD><TD><para><ui>从 STDOUT 中读取的数据</ui> - 不为空</para><para><ui>从 STDERR 中读取的数据</ui> - 空</para><para><ui>脚本结果</ui> - 失败</para><para><ui>应用程序检测状态</ui> - 未知</para></TD></tr><tr><TD><para>非零值
</para></TD><TD><para><ui>从 STDOUT 中读取的数据</ui> - 不为空</para><para><ui>从 STDERR 中读取的数据</ui> - 不为空</para><para><ui>脚本结果</ui> - 失败</para><para><ui>应用程序检测状态</ui> - 未知</para></TD></tr></tbody></table><para>下表包含可用于编写自己的应用程序检测脚本的 Microsoft Visual Basic (VB) 示例脚本。</para><table border="1"><thead><tr><TD><para>Visual Basic 示例脚本</para></TD><TD><para>描述</para></TD></tr></thead><tbody><tr><TD><para><ui>WScript.Quit (1)</ui>
</para></TD><TD><para>此脚本返回不为零的退出代码，这表示它未成功运行。 在这种情况下，应用程序检测状态为未知。
</para></TD></tr><tr><TD><para><ui>WScript.StdErr.Write“脚本失败”</ui></para><para><ui>WScript.Quit(0)
</ui></para></TD><TD><para>此脚本返回零退出代码，但是 STDERR 的值不为空，这表示脚本未成功运行。 在这种情况下，应用程序检测状态为未知。
</para></TD></tr><tr><TD><para><ui>WScript.Quit(0)</ui>
</para></TD><TD><para>此脚本返回零退出代码，这表示它已成功运行。 但是，STDOUT 的值为空，这表示未安装应用程序。
</para></TD></tr><tr><TD><para><ui>WScript.StdOut.Write“已安装应用程序”</ui></para><para><ui>WScript.Quit(0)</ui>
</para></TD><TD><para>此脚本返回零退出代码，这表示它已成功运行。 STDOUT 的值不为空，这表示安装了应用程序。
</para></TD></tr><tr><TD><para><ui>WScript.StdOut.Write“已安装应用程序”</ui></para><para><ui>WScript.StdErr.Write“已完成”</ui></para><para><ui>WScript.Quit(0)</ui>
</para></TD><TD><para>此脚本返回零退出代码，这表示它已成功运行。 STDOUT 和 STDERR 的值不为空，这表示安装了应用程序。
</para></TD></tr></tbody></table><alert class="note">
<para>可用于脚本的最大大小为 32 KB。
</para>
</alert></content></step><step><content><para> 



单击“确定”<ui></ui>以关闭“脚本编辑器”<ui></ui>对话框。

</para></content></step></steps>
</procedure></content>
</section><section>
<title>指定部署类型的用户体验选项</title><content><para>这些设置指定将应用程序安装到设备上的方式和用户将看到的内容。</para><procedure>
<title>指定用户体验选项</title>
 <steps class="ordered">
        <step><content><para>


在“创建部署类型向导”的“用户体验”<ui></ui>页上，指定下列信息：

</para><list class="bullet"><listItem><para><ui>安装行为</ui> - 在下拉列表中，选择下列选项之一：</para><list class="bullet"><listItem><para><ui>针对用户安装</ui> - 仅针对应用程序所部署到的用户安装应用程序。</para></listItem><listItem><para><ui>针对系统安装</ui> - 应用程序仅安装一次，可供所有用户使用。</para></listItem><listItem><para><ui>如果资源是设备，则针对系统安装；否则针对用户安装</ui> - 如果将应用程序部署到设备，则将为所有用户安装应用程序。 如果将应用程序部署到用户，则将仅为该用户安装应用程序。</para></listItem></list></listItem><listItem><para><ui>登录要求</ui> - 从以下选项中指定此部署类型的登录要求：</para><list class="bullet"><listItem><para><ui>仅当用户登录时</ui></para></listItem><listItem><para><ui>无论用户是否登录</ui></para></listItem><listItem><para><ui>仅当无用户登录时</ui></para></listItem></list><alert class="note">
<para>此选项默认为“仅当用户登录时”<ui></ui>，如果在“安装行为”<ui></ui>下拉列表中选择了“针对用户安装”<ui></ui>，则无法更改它。
</para>
</alert></listItem><listItem><para><ui>安装程序可见性</ui> - 指定部署类型在客户端设备上运行将处于的模式。 可用选项如下：</para><list class="bullet"><listItem><para><ui>最大化</ui> - 部署类型在客户端设备上以最大化模式运行。 用户将看到所有安装活动。</para></listItem><listItem><para><ui>正常</ui> - 部署类型基于系统和程序默认值在正常模式下运行。 此为默认模式。</para></listItem><listItem><para><ui>最小化</ui> - 部署类型在客户端设备上以最小化模式运行。 用户可能会在通知区域或任务栏中看到安装活动。</para></listItem><listItem><para><ui>隐藏</ui> - 部署类型在客户端设备上以隐藏模式运行，用户将看不到安装活动。</para></listItem></list></listItem><listItem><para><ui>允许用户查看程序安装并与其交互。</ui> - 指定用户是否可以与部署类型安装交互以配置安装选项。</para><alert class="note">
<para>如果在“安装行为”<ui></ui>下拉列表中选择了“针对用户安装”<ui></ui>选项，则默认情况下启用此选项。
</para>
</alert></listItem><listItem><para><ui>最大允许运行时间(分钟)</ui> - 指定预计程序在客户端计算机上运行的最长时间。 你可以将此设置指定为一个大于零的整数。 默认设置为 120 分钟。</para><para>此值用于：</para><list class="bullet"><listItem><para>监视部署类型中的结果。</para></listItem><listItem><para>确定在客户端设备上定义维护时段时是否将安装部署类型。 当处于维护时段时，只有在维护时段中有足够的可用时间来适应“最大允许运行时间”<ui></ui>设置时，程序才会运行。</para></listItem></list><alert class="important">
<para>如果“最大允许运行时间”<ui></ui>比预定维护时段长，则可能会发生冲突。 如果用户设置的最大运行时间超过了任何可用维护时段，该部署类型将不会运行。
</para>
</alert></listItem></list></content></step>
        <step><content><para><ui>估计安装时间（分钟）</ui> - 指定安装部署类型将需要的估计时间。 将向软件中心的用户显示此项。</para></content></step>
      </steps>
</procedure></content>
</section><section>
<title>指定部署类型的要求</title><content><procedure>
<title>指定要求</title>
 <steps class="ordered">
        <step><content><para>在“创建部署类型向导”的“要求”<ui></ui>页上，单击“添加”<ui></ui>以打开“创建要求”<ui></ui>对话框并添加新要求。</para><alert class="note">
<para>还可以在<placeholder>&lt;部署类型名称“属性”&gt;</placeholder> <ui></ui>对话框的“要求”<ui></ui>选项卡上添加新要求。
</para>
</alert></content></step>
        <step><content><para>在“类别”<ui></ui>下拉列表中，选择此要求是用于设备还是用于用户，或者选择“自定义”<ui></ui>以使用以前创建的全局条件。 选择“自定义”<ui></ui>时，也可以单击“创建”<ui></ui>以创建新全局条件。 有关全局条件的详细信息，请参阅<link xlink:href="2d5f871a-19dc-4bd3-a3ad-4230c7a69f1b">如何在 Configuration Manager 中创建全局条件</link>。</para><alert class="important">
<para>如果创建“用户”<ui></ui>类别和“主要设备”<ui></ui>条件的要求，然后将应用程序部署到设备集合，则会忽略要求。
</para>
<para>如果你已创建 Windows 程序包和程序或任务序列（其将 Windows 10 作为使用 System Center 2012 R2 Configuration Manager SP1 的要求），然后升级至 System Center Configuration Manager，则针对于 Windows 10 的要求可能会被删除。 若要解决此问题，请再次指定要求。 请注意，从要求列表中删除要求后，仍可在设备上正确处理。</para></alert></content></step>
      <step><content><para>在“条件”<ui></ui>下拉列表中，选择想要用于评估用户或设备是否满足安装要求的条件。 根据所选类别，此列表的内容会有所不同。</para></content></step><step><content><para>在“运算符”<ui></ui>下拉列表中，选择运算符，此运算符用于将所选条件与指定值进行比较以评估用户或设备是否满足安装要求。 可用运算符将因所选条件而异。</para><alert class="important">
<para>根据部署类型所适用的设备类型的不同，可用要求将不同。
</para>
</alert></content></step><step><content><para>在“值”<ui></ui>字段中，指定值，这些值将与所选条件和运算符一起用于评估用户或设备是否满足安装要求。 可用值将因所选条件和所选运算符而异。</para></content></step><step><content><para>单击“确定”<ui></ui>以保存要求并关闭“创建要求”<ui></ui>对话框。</para></content></step></steps>
</procedure></content>
</section><section>
<title>指定部署类型的依赖关系</title><content><para>依赖关系定义在安装部署类型之前必须先安装的另一应用程序中的一个或多个部署类型。 你可以将相关部署类型配置为在安装部署类型之前自动安装。 </para><alert class="important">
<para>在某些情况下，部署类型依赖于同时包含依赖关系的部署类型。 在存在依赖关系链的这种情况下，链中支持的依赖关系的最大数量为 <ui>5</ui>。
</para>
</alert><procedure>
<title>指定部署类型依赖关系</title>
 <steps class="ordered">
        <step><content><para>在“创建部署类型向导”的“依赖关系”<ui></ui>页上，如果要指定在安装此部署类型之前必须安装的部署类型，请单击“添加”<ui></ui>。</para><alert class="important">
<para>还可以在<placeholder>&lt;部署类型名称&gt;</placeholder> <ui></ui>“属性”对话框的“依赖关系”<ui></ui>选项卡上添加新依赖关系。
</para>
</alert></content></step>
        <step><content><para>在“添加依赖关系”<ui></ui>对话框中，单击“添加”<ui></ui>。</para></content></step>
      <step><content><para>在“指定所需的应用程序”<ui></ui>对话框中，选择要用作依赖关系的现有应用程序和应用程序部署类型之一。</para><alert class="tip">
<para>你可以单击“查看”<ui></ui>以显示所选应用程序或部署类型的属性。
</para>
</alert></content></step><step><content><para>单击“确定”<ui></ui>关闭“指定所需的应用程序”<ui></ui>对话框。</para></content></step><step><content><para>如果想要自动安装相关的应用程序，请选择相关应用程序旁边的“自动安装”<ui></ui>。</para><alert class="note">
<para>若要自动安装，则不需要部署相关应用程序。
</para>
</alert></content></step><step><content><para>在“添加依赖关系”<ui></ui>对话框内的“依赖关系组名称”<ui></ui>字段中，输入名称以引用此应用程序依赖关系组。</para></content></step><step><content><para>根据需要，使用“提高优先级”<ui></ui>和“降低优先级”<ui></ui>按钮，以更改每个依赖关系的评估顺序。</para></content></step><step><content><para>单击“确定”<ui></ui>以关闭“添加依赖关系”<ui></ui>对话框。</para></content></step></steps>
</procedure></content>
</section><section>
<title>确认部署类型设置并完成该向导</title><content><procedure>
<title>完成该向导</title>
 <steps class="ordered">
        <step><content><para>在“创建部署类型向导”的“摘要”<ui></ui>页上，查看向导将采取的操作。 单击“下一步”<ui></ui>以创建部署类型，或者单击“上一步”<ui></ui>以返回并更改部署类型设置。</para></content></step>
        <step><content><para>在向导的“进度”<ui></ui>页面完成之后，查看向导已采取的操作，然后单击“关闭”<ui></ui>以完成向导。</para></content></step>
      <step><content><para>如果从“创建应用程序向导”中启动了“创建部署类型向导”，将返回到“创建应用程序向导”的“部署类型”<ui></ui>页。</para></content></step></steps>
</procedure></content>
</section><section>
<title>配置包含虚拟应用程序的部署类型的其他选项</title><content><para>使用以下过程配置包含虚拟应用程序的部署类型的其他选项。</para><procedure>
<title>配置 Application Virtualization (App-V) 部署类型的内容选项</title>
 <steps class="ordered">
        <step><content><para>在 <token>cmshort</token> 控制台中，单击“软件库”<ui></ui>。</para></content></step>
        <step><content><para>在“软件库”<ui></ui>工作区中，单击“应用程序”<ui></ui>。</para></content></step>
      <step><content><para>在“应用程序”<ui></ui>列表中，选择包含 App-V 部署类型的应用程序。 然后，在“主页”<ui></ui>选项卡上的“属性”<ui></ui>组中，单击“属性”<ui></ui>。</para></content></step><step><content><para>在 <placeholder>&lt;应用程序名称&gt;</placeholder> <ui></ui>“属性”对话框中的“部署类型”<ui></ui>选项卡上，选择 App-V 部署类型，然后单击“编辑”<ui></ui>。</para></content></step><step><content><para>在 <placeholder>&lt;部署类型名称&gt;</placeholder> <ui></ui>“属性”对话框中的“内容”<ui></ui>选项卡上配置以下选项（如有需要）：</para><list class="bullet"><listItem><para><ui>保留客户端缓存中的内容</ui> -选择此选项以确保不从 <token>cmshort</token> 客户端缓存中删除此部署类型的内容。</para></listItem><listItem><para><ui>启动前将内容加载到 App-V 缓存中</ui> - 选择此选项以确保在启动应用程序之前将虚拟应用程序的所有内容都加载到 App-V 缓存中。 选择此选项还可以确保不在缓存中固定应用程序内容，并且可以根据需要对其进行删除。</para></listItem></list></content></step><step><content><para>单击“确定”<ui></ui>以关闭<placeholder>&lt;部署类型名称&gt;</placeholder> <ui></ui>“属性”对话框。</para></content></step><step><content><para>单击“确定”<ui></ui>以关闭<placeholder>&lt;应用程序名称&gt;</placeholder> <ui></ui>“属性”对话框。</para></content></step></steps>
</procedure><procedure>
<title>配置 App-V 部署类型的发布选项</title>
 <steps class="ordered">
        <step><content><para>在 <token>cmshort</token> 控制台中，单击“软件库”<ui></ui>。</para></content></step>
        <step><content><para>在“软件库”<ui></ui>工作区中，单击“应用程序”<ui></ui>。</para></content></step>
      <step><content><para>在“应用程序”<ui></ui>列表中，选择包含 App-V 部署类型的应用程序。 然后，在“主页”<ui></ui>选项卡上的“属性”<ui></ui>组中，单击“属性”<ui></ui>。</para></content></step><step><content><para>在<placeholder>&lt;应用程序名称&gt;</placeholder> <ui>“属性”</ui>对话框中的“部署类型”<ui></ui>选项卡上，选择 App-V 部署类型，然后单击“编辑”<ui></ui>。</para></content></step><step><content><para>在<placeholder>&lt;部署类型名称&gt;</placeholder> <ui>“属性”</ui>对话框中的“发布”<ui></ui>选项卡上，选择想要发布的虚拟应用程序中的项目。</para></content></step><step><content><para>单击“确定”<ui></ui>以关闭<placeholder>&lt;部署类型名称&gt;</placeholder> <ui>“属性”</ui>对话框。</para></content></step><step><content><para>单击“确定”<ui></ui>以关闭<placeholder>&lt;应用程序名称&gt;</placeholder> <ui>“属性”</ui>对话框。</para></content></step></steps>
</procedure></content>
</section></sections></section><section>
<title>如何导入应用程序</title><content><para>使用下列过程将应用程序导入 Configuration Manager。 有关如何导出应用程序的信息，请参阅 <link xlink:href="c4041e21-21ff-4d95-ab05-14007e0047cf">Configuration Manager 应用程序的管理任务</link>。</para><procedure>
<title>导入应用程序</title>
 <steps class="ordered">
        <step><content><para>在 <token>cmshort</token> 控制台中，单击“软件库”<ui></ui>。</para></content></step>
        <step><content><para>


在“软件库”<ui></ui>工作区中，展开“应用程序管理”<ui></ui>，然后单击“应用程序”<ui></ui>。

</para></content></step>
      <step><content><para>


在“主页”<ui></ui>选项卡上的“创建”<ui></ui>组中，单击“导入应用程序”<ui></ui>。

</para></content></step><step><content><para>在“导入应用程序向导”<ui></ui>的“常规”<ui></ui>页上，单击“浏览”<ui></ui>，然后指定 zip 文件的 UNC 路径，该路径包含要导入的应用程序。</para></content></step><step><content><para>


在向导的“文件内容”<ui></ui>页上，选择在你尝试导入的应用程序与现有应用程序重复的情况下将进行的操作。 你可以指定创建新应用程序，或忽略重复项并将新的修订添加到现有应用程序。

</para></content></step><step><content><para>


在向导的“摘要”<ui></ui>页上，查看要执行的操作，然后完成向导。 </para></content></step></steps>
<conclusion><content><para>新应用程序会出现在“应用程序”<ui></ui>节点中。

</para></content></conclusion></procedure><alert class="tip">
<para>Windows PowerShell cmdlet <ui>Import-CMApplication</ui> 执行与此过程相同的功能。 有关详细信息，请参阅 Microsoft System Center 2012 <token>cmshort</token> SP1 Cmdlet 参考文档中的 <externalLink><linkText>Import-CMApplication</linkText><linkUri>https://technet.microsoft.com/library/jj821738.aspx</linkUri></externalLink>。
</para>
</alert></content>
</section><section address="BKMK_Dtypes">
<title>Configuration Manager 支持的部署类型</title><content><?Comment robstack:Use the Intune docs to help fill this in. 11/6/2015 8:19:14 PM Id='bd7e2ed8db95c7f1'?><table border="1"><thead><tr><TD><para>部署类型名称</para></TD><TD><para>更多信息</para></TD></tr></thead><tbody><tr><TD><para><ui>Windows Installer（*.msi 文件）</ui></para></TD><TD><para>通过 Windows Installer 文件创建部署类型。</para></TD></tr><tr><TD><para><ui>Windows 应用包（*.appx*、.appxbundle）</ui></para></TD><TD><para>通过 Windows 应用包文件或 Windows 应用捆绑包为 Windows 8、Windows RT 或更高版本创建部署类型。</para></TD></tr><tr><TD><para><ui>Windows 应用包（在 Windows 应用商店中）</ui></para></TD><TD><para>通过指定指向 Windows 应用商店中应用的链接，或通过浏览应用商店选择你需要的应用，为 Windows 8、Windows RT 或更高版本创建部署类型。</para><para>如果要以指向 Windows 应用商店的链接的形式部署应用，请确保组策略设置“关闭应用商店应用程序”<ui></ui>设置为“禁用”<ui></ui>或“未配置”<ui></ui>。 如果启用此设置，客户端将无法连接到 Windows 应用商店来下载和安装应用程序。
</para><para>使用存储链接的 Windows 8 部署类型始终在其他部署类型之前进行评估（不考虑其优先级）。</para></TD></tr><tr><TD><para><ui>脚本安装程序</ui></para></TD><TD><para>创建一个部署类型，该部署类型指定在客户端设备上运行以安装内容或执行操作的脚本。</para></TD></tr><tr><TD><para><ui>Microsoft Application Virtualization 4</ui></para></TD><TD><para>通过 Microsoft Application Virtualization 4 清单创建部署类型
</para></TD></tr><tr><TD><para><ui>Microsoft Application Virtualization 5</ui></para></TD><TD><para>通过 Microsoft Application Virtualization 5 包文件创建部署类型。
</para></TD></tr><tr><TD><para><ui>Windows Phone 应用包（*.xap 文件）</ui></para></TD><TD><para>通过 Windows Phone 应用包文件创建部署类型。
</para></TD></tr><tr><TD><para><ui>Windows Phone 应用包（在 Windows Phone 应用商店中）</ui></para></TD><TD><para>通过指定指向 Windows Phone 应用商店中的应用的链接来创建部署类型。
</para></TD></tr><tr><TD><para><ui>Windows Mobile Cabinet</ui></para></TD><TD><para>通过 Windows Mobile Cabinet (CAB) 文件为 Windows Mobile 设备创建部署类型。 
</para></TD></tr><tr><TD><para><ui>iOS 应用包（*.ipa 文件）</ui></para></TD><TD><para>通过 iOS 应用包文件创建部署类型。
</para></TD></tr><tr><TD><para><ui>“应用商店中的 iOS 应用包”</ui></para></TD><TD><para>通过指定指向应用商店中的 iOS 应用的链接来创建部署类型。
</para></TD></tr><tr><TD><para><ui>Android 应用包（*.apk 文件）</ui></para></TD><TD><para>通过 Android 应用包文件创建部署类型。
</para></TD></tr><tr><TD><para><ui>“Google Play 上的 Android 应用包”</ui></para></TD><TD><para>通过指定指向 Google Play 上的应用的链接来创建部署类型。</para></TD></tr><tr><TD><para><ui>Mac OS X</ui></para></TD><TD><para>通过你使用 CMAppUtil 工具创建的 .cmmac 文件为 Mac 计算机创建部署类型。
</para><para>仅适用于运行 <token>cmshort</token> 客户端的 Mac 计算机。</para></TD></tr><tr><TD><para><ui>Web 应用程序</ui></para></TD><TD><para>创建一个部署类型，该部署类型指定指向 Web 应用程序的链接。 该部署类型在用户的设备上安装 Web 应用程序的快捷方式。</para><para></para><para>如果已在你管理的 iOS 或 Android 设备上安装了 Intune 托管浏览器，则可以确保用户只能使用托管浏览器打开应用。 为此，请在通过替换来指定应用的链接时，使用以下格式之一，替换为：将 <ui>http:</ui> 替换为 <ui>http intunemam:</ui> 或将 <ui>https:</ui> 替换为 <ui>https-intunemam:</ui></para><para>- <userInput>http-intunemam://&lt;到Web 应用的路径&gt;</userInput></para><para>- <userInput>https-intunemam://&lt;到Web 应用的路径&gt;</userInput></para><para></para><para>可以使用 <token>cmshort</token> 应用程序要求以确保将要与托管浏览器关联的应用仅安装到 iOS 和 Android 设备。
aspx)。</para><para>有关 Intune managed browser 的详细信息，请参阅<link xlink:href="735c45b8-a545-4805-84e5-46204fabd1a6">使用 System Center Configuration Manager 的托管浏览器策略管理 Internet 访问</link>。</para></TD></tr><tr><TD><?Comment Rob:This needs checking and reviewing carefully. 11/19/2015 4:12:20 AM Id='7e4291cc0281074b'?><para><ui>通过 MDM 的 Windows 安装程序 (*.msi)</ui></para><?CommentEnd Id='7e4291cc0281074b'?></TD><TD><para>此安装程序类型允许你创建基于 Windows Installer 的应用，并将其部署到运行 Windows 10 的 PC。</para><para>使用此安装程序类型时，需要考虑下列注意事项：</para><para></para><para>
-只能上传扩展名为 .msi 的单个文件。

</para><para>- 

该文件的产品代码和产品版本将用于应用检测。

</para><para>- 

将使用该应用的默认重启行为。 <token>cmshort</token> 不对此进行控制。

</para><para>- 

将为单个用户安装每个用户 MSI 包。

</para><para>- 将为设备上的所有用户安装每个计算机 MSI 包。</para><para>- 当前仅为设备上的所有用户安装双模式 MSI 包。</para><para>- 

当每个版本的 MSI 产品代码相同时，支持应用更新。

</para></TD></tr></tbody></table><?CommentEnd Id='bd7e2ed8db95c7f1'?></content>
</section><relatedTopics><link xlink:href="4c3cc80c-7ed8-43d8-950b-4544184e1dce">应用程序管理技术参考</link></relatedTopics>
</developerConceptualDocument>

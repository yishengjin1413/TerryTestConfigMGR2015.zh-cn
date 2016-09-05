---
title: "System Center Configuration Manager 中软件更新的先决条件"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-sum
ms.tgt_pltfrm: na
ms.topic: get-started-article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: fdf05118-162a-411e-b72e-386b9dc9a5e1
caps.latest.revision: 18
caps.handback.revision: 15
---
# System Center Configuration Manager 中软件更新的先决条件
<?xml version="1.0" encoding="utf-8"?>
<developerConceptualDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd">
  <introduction>
    <para>本主题列出了 <token>cm6long</token> 中的软件更新的先决条件。 对于这些先决条件中的每一个，在不同的表格中列出了外部依赖关系和内部依赖关系。</para>
  </introduction>
  <section expanded="true">
        <title>Configuration Manager 软件更新的外部依赖关系</title>
        <content>
          <para>下表列出了软件更新的外部依赖关系。</para>
          <table xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
            <thead>
              <tr>
                <TD colspan="1">
                  <para>要求</para>
                </TD>
                <TD colspan="1">
                  <para>更多信息</para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>安装在站点系统服务器上的 Internet Information Services (IIS)，以便运行软件更新点、管理点和分发点</para>
                  <para/>
                </TD>
                <TD>
                  <para>请参阅<link xlink:href="17905b4c-3895-4ad4-a69c-5e0d0fc5a8c3#bkmk_Prrequisites">站点系统角色的先决条件</link>。</para>
                  <para/>
                </TD>
              </tr>
              <tr>
                <TD colspan="1">
                  <para>Windows Server Update Services (WSUS)</para>
                </TD>
                <TD colspan="1">
                  <para>软件更新同步和在客户端上进行的软件更新符合性评估扫描都需要使用 WSUS。 在创建软件更新点站点系统角色之前，必须安装 WSUS 服务器。 软件更新点支持以下版本的 WSUS：</para>
                  <list class="bullet"><listItem><para>WSUS 4（Windows Server 2012 和 Windows Server 2012 R2 中的角色）</para></listItem><listItem><para>WSUS 3.2（Windows Server 2008 R2 中的角色）</para></listItem></list>
                    
                    <para>如果在一个站点上有多个软件更新点，请确保它们全都运行相同版本的 WSUS。</para>
                  
                <alert class="warning">
 <para><embeddedLabel>升级</embeddedLabel>软件更新分类仅在 WSUS 4.0 中开始受支持。 在同步此新分类，并且能够对 Windows 10 维护服务计划中的 Windows 10 计算机进行评估之前，在你的软件更新点和站点服务器上为 WSUS 安装<externalLink><linkText>修补程序 3095113</linkText><linkUri>https://support.microsoft.com/kb/3095113</linkUri></externalLink> 很重要。 此修补程序使基于 Windows Server 2012 或基于 Windows Server 2012 R2 的服务器上的 WSUS 能够同步和分发 Windows 10 的功能升级。 有关详细信息，请参阅<link xlink:href="da1e687b-28f6-43c4-b14a-ff2b76e60d24">使用 System Center Configuration Manager 将 Windows 作为服务进行管理</link>。</para><para><br/>如果在安装<externalLink><linkText>修补程序 3095113</linkText><linkUri>https://support.microsoft.com/kb/3095113</linkUri></externalLink>之前同步具有<embeddedLabel>升级</embeddedLabel>分类的软件更新，请参阅<link xlink:href="#BKMK_RecoverUpgrades">在安装 KB 3095113 之前从同步升级分类中恢复</link>。</para>
</alert></TD>
              </tr>
              <tr>
                <TD colspan="1">
                  <para>WSUS 管理控制台</para>
                </TD>
                <TD colspan="1">
                  <para>在软件更新点位于远程站点系统服务器上，且该站点服务器并未安装 WSUS 时，<token>cmshort</token> 站点服务器上需要安装 WSUS 管理控制台。 </para>
                  <alert class="important">
                    <para>站点服务器上的 WSUS 版本必须与在软件更新点上运行的 WSUS 版本相同。</para>
                  </alert>
                  <alert class="important">
                    <para>不要使用 WSUS 管理控制台来配置 WSUS 设置。 <token>cmshort</token> 连接到在软件更新点上运行的 WSUS，并配置适当的设置。</para>
                  </alert>
                </TD>
              </tr>
              <tr>
                <TD colspan="1">
                  <para>Windows 更新代理 (WUA)</para>
                </TD>
                <TD colspan="1">
                  <para>客户端上需要安装 WUA 客户端才能连接到 WSUS 服务器，以及检索那些必须接受符合性扫描的软件更新的列表。 </para>
                  <para>在安装 <token>cmshort</token> 时，会下载 WUA 的最新版本。 之后，在安装 <token>cmshort</token> 客户端时，如有必要将会升级 WUA。 但是，如果安装失败，你必须使用另一种方法来升级 WUA。</para>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
      </section>
  
  <section expanded="true">
        <title>Configuration Manager 软件更新的内部依赖关系</title>
        <content>
          <para>下表列出了 <token>cmshort</token> 中软件更新的外部依赖关系。</para>
          <table xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
            <thead>
              <tr>
                <TD colspan="1">
                  <para>要求</para>
                </TD>
                <TD colspan="1">
                  <para>更多信息</para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>管理点</para>
                </TD>
                <TD>
                  <para>管理点在客户端计算机和 <token>cmshort</token> 站点之间传输信息。 它们对于软件更新是必需的。</para>
                  <para/>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>软件更新点</para>
                </TD>
                <TD>
                  <para>必须在 WSUS 服务器上安装软件更新点，才能在 <token>cmshort</token> 中部署软件更新。 </para>
                  <para>有关详细信息，请参阅 <link xlink:href="40380e25-f563-40f8-b5ad-01c9a9698754">在 Configuration Manager 中配置软件更新</link></para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>分发点</para>
                </TD>
                <TD>
                  <para>需要使用分发点来存储软件更新的内容。</para>
                  <para>有关如何安装分发点和管理内容的详细信息，请参阅<link xlink:href="ceff72f5-f19d-43a0-a8c0-72f1c09b9bf5">部署和管理内容管理基础结构</link>。</para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>软件更新的客户端设置</para>
                </TD>
                <TD>
                  <para>默认情况下，会为客户端启用软件更新。 但是，可以使用其他一些设置来控制客户端如何和何时评估软件更新的符合性，以及对如何安装软件更新进行控制。</para>
                  <para>有关详细信息，请参阅以下：</para>
                  <list class="bullet">
                    <listItem>
                      <para><link xlink:href="40380e25-f563-40f8-b5ad-01c9a9698754">在 Configuration Manager 中配置软件更新</link>主题中的<?xm-deletion_mark author="Brent" time="20160129T100456-0800" data="&lt;maml:link xlink:href=&quot;40380e25-f563-40f8-b5ad-01c9a9698754#BKMK_ClientSettings&quot; xmlns:maml=&quot;http://ddue.schemas.microsoft.com/authoring/2003/5&quot; xmlns:xlink=&quot;http://www.w3.org/1999/xlink&quot;&gt;Client Settings for Software Updates&lt;/maml:link&gt;"?><?xm-insertion_mark_start author="Brent" time="20160129T100500-0800"?>软件更新客户端设置<?xm-insertion_mark_end?>部分。</para>
                    </listItem>
                    <listItem>
                      <para><link xlink:href="f7560876-8084-4570-aeab-7fd44f4ba737"> System Center Configuration Manager 中的客户端设置</link>主题中的<?xm-deletion_mark author="Brent" time="20160129T100510-0800" data="&lt;maml:link xlink:href=&quot;f7560876-8084-4570-aeab-7fd44f4ba737#BKMK_SoftwareUpdatesDeviceSetting&quot; xmlns:maml=&quot;http://ddue.schemas.microsoft.com/authoring/2003/5&quot; xmlns:xlink=&quot;http://www.w3.org/1999/xlink&quot;&gt;Software Updates&lt;/maml:link&gt;"?> <?xm-insertion_mark_start author="Brent" time="20160129T100516-0800"?>软件更新<?xm-insertion_mark_end?>部分。</para>
                    </listItem>
                  </list>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>Reporting Services 点</para>
                </TD>
                <TD>
                  <para>Reporting Services 点站点系统角色可以显示软件更新的报表。 此角色是可选的，但建议使用它。 有关如何创建 Reporting Services 点的详细信息，请参阅<link xlink:href="55ae86a7-f0ab-4c09-b4da-89cd0e7fa0e0">在 Configuration Manager 中配置报表</link>。</para>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
      </section><section address="BKMK_RecoverUpgrades">
<title>在安装 KB 3095113 之前从同步升级分类中恢复</title><content><para>必须在你的软件更新点和站点服务器上为 WSUS 安装<externalLink><linkText>修补程序 3095113</linkText><linkUri>https://support.microsoft.com/kb/3095113</linkUri></externalLink>，然后再同步<embeddedLabel>升级</embeddedLabel>分类。 如果在启用<embeddedLabel>升级</embeddedLabel>分类后未安装此修补程序，即使 WSUS 无法正确下载并部署 Windows 10 内部版本 1511 功能升级包，也能看见此功能升级选项。 如果你未先安装<externalLink><linkText>修补程序 3095113</linkText><linkUri>https://support.microsoft.com/kb/3095113</linkUri></externalLink> 就同步任何升级，则会使用不可用数据填充 WSUS 数据库 (SUSDB)，必须清除这些数据才能正确部署升级。  使用以下步骤从该问题中恢复。</para><procedure>
<title>在安装 KB 3095113 之前从同步升级分类中恢复</title>
 <steps class="ordered">
        <step><content><para>使用升级分类删除软件更新。 你可以使用类似于下面的示例脚本的 PowerShell 脚本：</para><code>$Server = Get-WSUSServer
$Config = $Server.GetConfiguration()
$Update10563 = “df4e45a3-946d-4467-b3fd-8621174bb666”
$UpdateGUID = New-Object Guid($Update10563)
$Server.DeleteUpdate($UpdateGUID)</code><alert class="important">
 <para>必须在 <token>cmshort</token> 层次结构中的所有软件更新点上运行该脚本，然后再转到下一步。 </para>
</alert><para>要使用升级分类批量删除软件更新，你可以修改此 PowerShell 脚本从一个 txt 文件读取多个 GUID。 </para></content></step>
        <step><content><para>取消选中<externalLink><linkText>软件更新点组件属性</linkText><linkUri>https://technet.microsoft.com/library/mt612804.aspx</linkUri></externalLink>中的<embeddedLabel>升级</embeddedLabel>分类，然后启动<externalLink><linkText>软件更新同步</linkText><linkUri>https://technet.microsoft.com/library/mt612804.aspx</linkUri></externalLink>。 </para></content></step>
      <step><content><para> 在你的软件更新点和站点服务器上为 WSUS 安装<externalLink><linkText>修补程序 3095113</linkText><linkUri>https://support.microsoft.com/kb/3095113</linkUri></externalLink>。 </para></content></step>
        <step><content><para>选择<externalLink><linkText>软件更新点组件属性</linkText><linkUri>https://technet.microsoft.com/library/mt612804.aspx</linkUri></externalLink>中的<embeddedLabel>升级</embeddedLabel>分类，然后启动<externalLink><linkText>软件更新同步</linkText><linkUri>https://technet.microsoft.com/library/mt612804.aspx</linkUri></externalLink>。 </para></content></step>
      </steps>
</procedure></content>
</section><relatedTopics>
    <link xlink:href="d071b0ec-e070-40a9-b7d4-564b92a5465f">规划软件更新</link>
  </relatedTopics>
</developerConceptualDocument>

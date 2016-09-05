---
title: "在 System Center Configuration Manager 中规划操作系统部署互操作性"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-osd
ms.tgt_pltfrm: na
ms.topic: get-started-article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: e327ce38-6c07-4a27-b6eb-7e5bf74ed04b
caps.latest.revision: 10
caps.handback.revision: 7
translationtype: Human Translation
---
# 在 System Center Configuration Manager 中规划操作系统部署互操作性
<?xml version="1.0" encoding="utf-8"?>
<developerConceptualDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd">
  <introduction>
    <para>当单一层次结构中不同的 <token>cm6long</token> 站点使用不同版本时，某些 <token>cmshort</token> 功能不可用。 通常，无法在站点上或通过运行较低版本的客户端访问 <token>cmshort</token> 的较新版本中的功能。 有关详细信息，请参阅 <link xlink:href="9b0a7859-747f-4495-a2f4-13fd5991f897">System Center Configuration Manager 不同版本之间的互操作性</link>。</para>
    <para>在升级层次结构中的顶层站点和升级层次结构中运行较低版本的 <token>cmshort</token> 的其他站点时，请考虑以下事项：</para>
    <list class="bullet">
      <listItem>
        <para>客户端安装包</para>
        <list class="bullet">
          <listItem>
            <para>会自动升级默认客户端安装包的来源，并使用新的客户端安装包更新层次结构中的所有分发点，即使在层次结构具有较低版本的站点处的分发点上也是如此。</para>
          </listItem>
          <listItem>
            <para>无法将运行新版本的客户端分配给尚未升级到新版本的站点。 将在管理点阻止分配。</para>
          </listItem>
        </list>
      </listItem>
      <listItem>
        <para>启动映像</para>
        <list class="bullet">
          <listItem>
            <para>将顶层站点升级到 <token>cmshort</token> 的最新版本时，默认启动映像（x86 和 x64）会自动更新为使用 Windows PE 10 且基于适用于 Windows 10 的 Windows ADK 的启动映像。 与默认启动映像关联的文件会使用这些文件的最新 <token>cmshort</token> 版本进行更新。 自定义启动映像不会自动更新。 将需要手动更新自定义启动映像，其中包括旧版 Windows PE。</para>
          </listItem>
          <?xm-deletion_mark author="Doug Eby" time="20151206T135205-0800" data="&lt;maml:listItem xmlns:maml=&quot;http://ddue.schemas.microsoft.com/authoring/2003/5&quot;&gt;
            &lt;maml:para&gt;To prevent task sequences from failing, make sure that the version of the boot image corresponds to the version of the &lt;maml:token&gt;cmshort&lt;/maml:token&gt; client installation package that you configure in the task sequence. For example, a Windows AIK-based boot image that uses Windows PE 3 must correspond to the &lt;maml:token&gt;cmshort&lt;/maml:token&gt; with no service pack client installation package version. A Windows ADK-based boot image must correspond to the &lt;maml:token&gt;cmshort&lt;/maml:token&gt; SP1 client installation package version.&lt;/maml:para&gt;
          &lt;/maml:listItem&gt;"?>
          <listItem>
            <para>如果站点层次结构包含具有不同 <token>cmshort</token> 版本的站点时，则避免使用动态媒体。 相反，使用基于站点的媒体来联系特定的管理点，直至所有站点均升级到 <token>cmshort</token> 的相同版本。</para>
          </listItem>
          <listItem><para>验证最新的 <token>cmshort</token> 启动映像是否包含所需的自定义，然后使用新的启动映像更新具有最新版 <token>cmshort</token> 的站点上的所有分发点。</para></listItem><?xm-deletion_mark author="Doug Eby" time="20151206T135234-0800" data="&lt;maml:listItem xmlns:maml=&quot;http://ddue.schemas.microsoft.com/authoring/2003/5&quot;&gt;
            &lt;maml:para&gt;You can import and use Windows AIK-based boot images only in a &lt;maml:token&gt;cmshort&lt;/maml:token&gt; site that does not have Service Pack 1 installed.&lt;/maml:para&gt;
          &lt;/maml:listItem&gt;
          &lt;maml:listItem xmlns:maml=&quot;http://ddue.schemas.microsoft.com/authoring/2003/5&quot;&gt;
            &lt;maml:para&gt;You can import and use Windows ADK-based boot images only in a &lt;maml:token&gt;cmshort&lt;/maml:token&gt; site that has Service Pack 1 installed.&lt;/maml:para&gt;
          &lt;/maml:listItem&gt;
        "?></list>
      </listItem>
    <listItem><para>用户状态迁移工具 (USMT)</para><list class="bullet"><listItem><para>将顶层站点升级到 <token>cmshort</token> 最新版本时，默认 USMT 包将自动更新为最新版本。 自定义 USMT 包不会自动更新。 将需要手动更新这些包。</para></listItem></list></listItem><listItem><para>新建任务序列步骤</para><list class="bullet"><listItem><para>将随 <token>cmshort</token> 的新版本定期引入新的任务序列步骤 。 将具有新步骤的任务序列部署到较旧的客户端时，任务序列步骤将失败。 在部署具有新步骤的任务序列之前，请确保目标集合中的客户端都更新到最新版本。</para></listItem></list></listItem><listItem><para>操作系统部署媒体</para><list class="bullet"><listItem><para>将站点更新到新版本时，必须使用新的 <token>cmshort</token> 客户端包更新所有媒体（可启动媒体、捕获媒体、预留媒体和独立媒体）。 </para></listItem></list></listItem><listItem><para>操作系统部署的第三方扩展</para><list class="bullet"><listItem><para>当具有操作系统部署的第三方扩展且拥有不同版本的 <token>cmshort</token> 站点或 <token>cmshort</token> 客户端（即混合层次结构）时，扩展可能存在问题。  </para></listItem></list></listItem></list>
    
    <para>在主动升级层次结构中的站点时，请使用下列部分来帮助你进行操作系统部署。</para>
  </introduction>
  <section>
    <title><?xm-insertion_mark_start author="Doug Eby" time="20151206T135337-0800"?>混合层次结构中 <?xm-insertion_mark_end?>Configuration Manager 站点的最新版本</title>
    <content>
      <para>将站点升级到 <token>cmshort</token> 的最新版本时，引用默认客户端安装包的任务序列将自动启动以部署最新的 <token>cmshort</token> 客户端版本。 引用自定义客户端安装包的任务序列将继续部署该自定义包中包含的客户端的版本（可能是以前的 <token>cmshort</token> 客户端版本），并且必须更新以避免任务序列部署失败。 如果有配置为使用自定义客户端安装包的任务序列，则必须更新任务序列步骤以使用客户端安装包的最新 <token>cmshort</token> 版本，或更新自定义包以使用最新 <token>cmshort</token> 客户端安装源。 </para>
      <alert class="important">
        <para>不要将引用最新 <token>cmshort</token> 客户端安装包的任务序列部署到较旧的 <token>cmshort</token> 站点中的客户端。 当将分配到较旧的 <token>cmshort</token> 站点的客户端升级到最新 <token>cmshort</token> 客户端版本时，<token>cmshort</token> 将阻止向较旧 <token>cmshort</token> 站点进行分配。 因此，在你将客户端手动分配给最新的 <token>cmshort</token> 站点或在计算机上重新安装客户端较旧的 <token>cmshort</token> 版本之前，客户端将不再分配给任何站点，并处于不受管理状态。</para>
      </alert>
      
    </content>
  </section>
  <section>
    <title>混合层次结构中 Configuration Manager 的较旧版本</title>
    <content>
      <para>如果已将管理中心站点升级到 <token>cmshort</token> 的最新版本，必须执行以下步骤，以确保你部署到客户端（分配给较旧的 <token>cmshort</token> 站点（尚未升级到 <token>cmshort</token> 的最新版本））的操作系统部署任务序列未将这些客户端置于不受管理状态。 </para>
      <list class="bullet">
        <listItem>
          <para>创建一个将仅用于在 <token>cmshort</token> 站点中部署到客户端的任务序列。 同样，你将建立用于在 <token>cmshort</token> 站点的最新版本中部署到客户端的任务序列的副本，然后修改该任务序列，以便能够在较旧的 <token>cmshort</token> 站点中将其部署到客户端。 然后，配置任务序列以引用使用较旧的 <token>cmshort</token> 客户端安装源的自定义客户端安装包。 如果还没有一个引用较旧的 <token>cmshort</token> 客户端安装源的自定义安装包，则必须手动创建该安装包。</para>
        </listItem>
        
        
      </list>
    </content>
  </section>
  <relatedTopics><link xlink:href="e327ce38-6c07-4a27-b6eb-7e5bf74ed04b">在 System Center Configuration Manager 中规划操作系统部署互操作性</link></relatedTopics>
</developerConceptualDocument>

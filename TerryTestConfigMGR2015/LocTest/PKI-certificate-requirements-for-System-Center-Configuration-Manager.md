---
title: "System Center Configuration Manager 的 PKI 证书要求"
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
ms.assetid: d6a73e68-57d8-4786-842b-36669541d8ff
caps.latest.revision: 17
caps.handback.revision: 15
---
# System Center Configuration Manager 的 PKI 证书要求
<?xml version="1.0" encoding="UTF-8"?>
<developerConceptualDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns:xlink="http://www.w3.org/1999/xlink">
    
  <summary/>
  <introduction>
    <para>以下各个表中列出了你可能需要为 <token>cm6long</token> 使用的公钥基础结构 (PKI) 证书。 此信息假定用户对 PKI 证书有着基本了解。 有关逐步<?xm-insertion_mark_start author="Nathan Bigman" time="20151108T152350+0200"?>部署<?xm-insertion_mark_end?>指南<?xm-deletion_mark author="Nathan Bigman" time="20151108T152400+0200" data="for an example deployment of these certificates,"?>的信息，请参阅 <link xlink:href="3417ff88-7177-4a0d-8967-ab21fe7eba17">Configuration Manager 的 PKI 证书的分步部署示例：Windows Server 2008 证书颁发机构</link><?xm-deletion_mark author="Nathan Bigman" time="20151108T152441+0200" data=" "?>。 有关 Active Directory 证书服务的详细信息，请参阅以下文档：</para>
    <list class="bullet">
      <listItem>
        <para>关于 Windows Server 2012：<externalLink><linkText>Active Directory 证书服务概述</linkText><linkUri>http://go.microsoft.com/fwlink/p/?LinkId=286744</linkUri></externalLink></para>
      </listItem>
      <listItem>
        <para>关于 Windows Server 2008：<externalLink><linkText>Windows Server 2008 中的 Active Directory 证书服务</linkText><linkUri>http://go.microsoft.com/fwlink/p/?LinkId=115018</linkUri></externalLink></para>
      </listItem>
    </list>
    <alert class="important">
<para>自 2017 年 1 月 1 日起生效， Windows 将不再信任使用 SHA-1 签名的证书。  建议颁发使用 SHA-2 签名的新服务器和客户端身份验证证书。</para>
<para>有关此更改以及对截止时间的可能的更新的详细信息，请关注这篇博客文章：<externalLink><linkText>Windows 强制执行的验证码签名和加盖时间戳</linkText><linkUri>http://social.technet.microsoft.com/wiki/contents/articles/32288.windows-enforcement-of-authenticode-code-signing-and-timestamping.aspx</linkUri></externalLink></para></alert><para>
      <?Comment CB: 329822 2013-03-13T14:15:00Z  Id='0?>除了 <token><?xm-deletion_mark author="Nathan Bigman" time="20151108T145935+0200" data="cmshort"?><?xm-insertion_mark_start author="Nathan Bigman" time="20151108T145935+0200"?>cm6long<?xm-insertion_mark_end?></token> 在移动设备和 Mac 计算机上注册的客户端证书之外，<token>mit_first</token> 为管理移动设备自动创建的证书以及 <token><?xm-deletion_mark author="Nathan Bigman" time="20151108T145935+0200" data="cmshort"?><?xm-insertion_mark_start author="Nathan Bigman" time="20151108T145935+0200"?>cm6long<?xm-insertion_mark_end?></token> 在基于 AMT 的计算机上安装的证书，你可以使用任何 PKI 来创建、部署和管理以下证书。 <?CommentEnd Id='0'
    ?>但是，当你使用 Active Directory 证书服务和证书模板时，可以使用此 Microsoft PKI 解决方案轻松地管理证书。 使用以下各表中的<ui>要使用的 Microsoft 证书模板</ui>列来确定最符合证书要求的证书模板。 基于模板的证书只能由运行于服务器操作系统的企业版或数据中心版（例如 <?Comment CAB: Bug165479 2013-03-13T14:15:00Z  Id='1?>Windows Server 2008<?CommentEnd Id='1'
    ?> Enterprise 和 Windows Server 2008 Datacenter）上的企业证书颁发机构颁发。 </para>
    <alert class="important">
      <para>当使用企业证书颁发机构和证书模板时，请不要使用版本 3 模板。 这些证书模板创建的证书与 <token><?xm-deletion_mark author="Nathan Bigman" time="20151108T145935+0200" data="cmshort"?><?xm-insertion_mark_start author="Nathan Bigman" time="20151108T145935+0200"?>cm6long<?xm-insertion_mark_end?></token> 不兼容。 请按照下列说明改为使用版本 2 模板：</para>
      <list class="bullet">
        <?Comment CB: 384984 2013-03-13T14:15:00Z  Id='3?>
        <listItem>
          <para>对于 Windows Server 2012 上的 CA：在证书模板属性的“兼容性”<ui></ui>选项卡上，为“证书颁发机构”<ui></ui>选项指定“Windows Server 2003”<ui></ui>，并为“证书接收人”<ui></ui>选项指定“Windows XP/Server 2003”<ui></ui>。<?CommentEnd Id='3'
    ?></para>
        </listItem>
        <listItem>
          <para>对于 Windows Server 2008 上的 CA：在复制证书模板时，请在“复制模板”<ui></ui>弹出式对话框提示你时保留默认选择的“Windows Server 2003 Enterprise”<ui></ui>。 不要选择“Windows Server 2008，Enterprise Edition”<ui></ui>。</para>
        </listItem>
      </list>
    </alert>
    <para>使用下列部分来查看证书要求。</para>
  </introduction>
  <section address="BKMK_PKIcertificates_for_servers" expanded="false">
    <title>服务器的 PKI 证书</title>
    <content>
      <table>
        <thead>
          <tr>
            <TD>
              <para>
                <token><?xm-deletion_mark author="Nathan Bigman" time="20151108T145935+0200" data="cmshort"?><?xm-insertion_mark_start author="Nathan Bigman" time="20151108T145935+0200"?>cm6long<?xm-insertion_mark_end?></token> 组件</para>
            </TD>
            <TD>
              <para>证书用途</para>
            </TD>
            <TD>
              <para>要使用的 Microsoft 证书模板</para>
            </TD>
            <TD>
              <para>证书中的特定信息</para>
            </TD>
            <TD colspan="1">
              <para><token><?xm-deletion_mark author="Nathan Bigman" time="20151108T145935+0200" data="cmshort"?><?xm-insertion_mark_start author="Nathan Bigman" time="20151108T145935+0200"?>cm6long 中证书的使用方式<?xm-insertion_mark_end?></token></para>
            </TD>
          </tr>
        </thead>
        <tbody>
          <tr>
            <TD>
              <para>运行 Internet Information Services (IIS) 并针对 HTTPS 客户端连接进行配置的站点系统：</para>
              <para>-管理点</para>
                <para>-分发点</para>
                <para>-软件更新点</para><para>-状态迁移点</para><para>-注册点</para><para>-注册代理点</para><para>-应用程序目录 Web 服务点</para><para>-应用程序目录网站点</para><para>-证书注册点  </para>
            </TD>
            <TD colspan="1">
              <para>服务器身份验证</para>
            </TD>
            <TD colspan="1">
              <para>
                <ui>Web 服务器</ui>
              </para>
            </TD>
            <TD colspan="1">
              <para>
                <ui></ui>“增强型密钥用法”值必须包含“服务器身份验证 (1.3.6.1.5.5.7.3.1)”<ui></ui>。</para>
              <para>如果站点系统接受来自 Internet 的连接，则“使用者名称”或“使用者可选名称”必须包含 Internet 完全限定的域名 (FQDN)。</para>
              <para>如果站点系统接受来自 Intranet 的连接，则“使用者名称”或“使用者可选名称”必须包含 Intranet FQDN（建议）或计算机的名称，视站点系统的配置方式而定。</para>
              <para>如果站点系统接受来自 Internet 和 Intranet 的连接，则必须在 Internet FQDN 和 Intranet FQDN（或计算机名）之间使用和号 (&amp;) 分隔符来指定这两个名称。</para>
              <para><legacyBold>注意：</legacyBold>当软件更新点仅接受来自 Internet 的客户端连接时，该证书必须包含 Internet FQDN 和 Intranet FQDN。</para>
              <para>支持 SHA-2 哈希算法。</para>
              <para>
                <?Comment CAB: Bug165306 2013-03-13T14:15:00Z  Id='4?>
                <token><?xm-deletion_mark author="Nathan Bigman" time="20151108T145935+0200" data="cmshort"?><?xm-insertion_mark_start author="Nathan Bigman" time="20151108T145935+0200"?>cm6long<?xm-insertion_mark_end?></token> 不指定此证书支持的最大密钥长度。 有关此证书的任何密钥大小的相关问题，请参阅 PKI 和 IIS 文档<?CommentEnd Id='4'
    ?>。</para>
            </TD>
            <TD colspan="1">
              <para>此证书必须位于计算机证书存储中的个人存储中。</para>
              <para>此 Web 服务器证书用于向客户端对这些服务器进行身份验证，并通过使用安全套接字层 (SSL) 对它们之间传输的所有数据进行加密。</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>基于云的分发点 </para>
            </TD>
            <TD colspan="1">
              <para>服务器身份验证</para>
            </TD>
            <TD colspan="1">
              <para>
                <ui>Web 服务器</ui>
              </para>
            </TD>
            <TD colspan="1">
              <para>
                <ui></ui>“增强型密钥用法”值必须包含“服务器身份验证 (1.3.6.1.5.5.7.3.1)”<ui></ui>。</para>
              <para>“使用者名称”必须包含客户定义的服务名称和 FQDN 格式的域名作为基于云的分发点的特定实例的公用名。 </para>
              <para>私钥必须是可导出的。</para>
              <para>支持 SHA-2 哈希算法。</para>
              <para>支持的密钥长度：2048 位。 </para>
            </TD>
            <TD colspan="1">
              <para><?xm-deletion_mark author="Nathan Bigman" time="20151108T150326+0200" data="                &lt;maml:token xmlns:maml=&quot;http://ddue.schemas.microsoft.com/authoring/2003/5&quot;&gt;sccm2012sp1note&lt;/maml:token&gt;"?>
              </para>
              <?xm-deletion_mark author="Nathan Bigman" time="20151108T150707+0200" data="&lt;maml:para xmlns:maml=&quot;http://ddue.schemas.microsoft.com/authoring/2003/5&quot;&gt;This service certificate is used to authenticate the cloud-based distribution point service to &lt;maml:token&gt;cmshort&lt;/maml:token&gt; clients and to encrypt all data transferred between them by using Secure Sockets Layer (SSL).&lt;/maml:para&gt;
              "?><para>此服务证书用于向 Configuration Manager 客户端验证基于云的分发点服务，并通过使用安全套接字层 (SSL) 对它们之间传输的所有数据进行加密。必须采用公钥证书标准 (PKCS #12) 格式导出此证书，并且密码必须已知，以便在创建基于云的分发点时可以导入该证书。</para>
              <para><legacyBold>注意：</legacyBold>该证书与 Windows Azure 管理证书结合使用。 有关此证书的详细信息，请参阅 MSDN 库 的“Windows Azure”平台部分中的 <externalLink><linkText>How to Create a Management Certificate</linkText><linkUri>http://go.microsoft.com/fwlink/p/?LinkId=220281</linkUri></externalLink>（如何创建管理证书）以及 <externalLink><linkText>How to Add a Management Certificate to a Windows Azure Subscription</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=241722</linkUri></externalLink>（如何将管理证书添加到 Windows Azure 订阅）。</para>
            </TD>
          </tr>
          
          <tr>
            <TD>
              <para>运行 Microsoft SQL Server 的站点系统服务器</para>
            </TD>
            <TD>
              <para>服务器身份验证</para>
            </TD>
            <TD>
              <para>
                <ui>Web 服务器</ui>
              </para>
            </TD>
            <TD colspan="1">
              <para>
                <ui></ui>“增强型密钥用法”值必须包含“服务器身份验证 (1.3.6.1.5.5.7.3.1)”<ui></ui>。</para>
              <para>“使用者名称”必须包含 Intranet 完全限定的域名 (FQDN)。</para>
              <para>支持 SHA-2 哈希算法。</para>
              <para>支持的最大密钥长度为 2048 位。</para>
            </TD>
            <TD>
              <para>此证书必须位于计算机证书存储中的个人存储中，并且 <token><?xm-deletion_mark author="Nathan Bigman" time="20151108T145935+0200" data="cmshort"?><?xm-insertion_mark_start author="Nathan Bigman" time="20151108T145935+0200"?>cm6long<?xm-insertion_mark_end?></token> 会自动将其复制到 <token><?xm-deletion_mark author="Nathan Bigman" time="20151108T145935+0200" data="cmshort"?><?xm-insertion_mark_start author="Nathan Bigman" time="20151108T145935+0200"?>cm6long<?xm-insertion_mark_end?></token> 层次结构中可能必须与服务器建立信任的“受信任人”存储。</para>
              <para>这些证书用于服务器到服务器的身份验证。</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <?Comment CB: 337761 2013-03-13T14:15:00Z  Id='5?>
              <para>SQL Server 群集：运行 Microsoft SQL Server 的站点系统服务器<?CommentEnd Id='5'
    ?></para>
            </TD>
            <TD>
              <para>服务器身份验证</para>
            </TD>
            <TD>
              <para>
                <ui>Web 服务器</ui>
              </para>
            </TD>
            <TD colspan="1">
              <para>
                <ui></ui>“增强型密钥用法”值必须包含“服务器身份验证 (1.3.6.1.5.5.7.3.1)”<ui></ui>。</para>
              <para>“使用者名称”必须包含群集的 Intranet 完全限定的域名 (FQDN)。</para>
              <para>私钥必须是可导出的。</para>
              <para>当你配置 <token><?xm-deletion_mark author="Nathan Bigman" time="20151108T145935+0200" data="cmshort"?><?xm-insertion_mark_start author="Nathan Bigman" time="20151108T145935+0200"?>cm6long<?xm-insertion_mark_end?></token> 以使用 SQL Server 群集时，证书必须包含至少两年的有效期。</para>
              <para>支持 SHA-2 哈希算法。</para>
              <para>支持的最大密钥长度为 2048 位。</para>
            </TD>
            <TD>
              <para>在群集中的一个节点上请求并安装了此证书后，请导出证书并将其导入到 SQL Server 群集中的每个其他节点。</para>
              <para>此证书必须位于“计算机”证书存储的“个人”存储中，<token><?xm-deletion_mark author="Nathan Bigman" time="20151108T145935+0200" data="cmshort"?><?xm-insertion_mark_start author="Nathan Bigman" time="20151108T145935+0200"?>cm6long<?xm-insertion_mark_end?></token> 会将其自动复制到 <token><?xm-deletion_mark author="Nathan Bigman" time="20151108T145935+0200" data="cmshort"?><?xm-insertion_mark_start author="Nathan Bigman" time="20151108T145935+0200"?>cm6long<?xm-insertion_mark_end?></token> 层次结构中可能必须与服务器建立信任的服务器的“受信任人”存储。</para>
              <para>这些证书用于服务器间身份验证。</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>下列站点系统角色的站点系统监视：</para>
              <para>管理点</para><para>状态迁移点</para>
            </TD>
            <TD>
              <para>客户端身份验证</para>
            </TD>
            <TD>
              <para>
                <ui>工作站身份验证</ui>
              </para>
            </TD>
            <TD colspan="1">
              <para>
                <ui></ui>“增强型密钥用法”值必须包含“客户端身份验证 (1.3.6.1.5.5.7.3.2)”<ui></ui>。</para>
              <para>计算机必须在“使用者名称”字段或“使用者可选名称”字段中有唯一的值。</para>
              <para><legacyBold>注意：</legacyBold>如果将多个值用于“使用者可选名称”，则只会使用第一个值。</para>
              <para>支持 SHA-2 哈希算法。</para>
              <para>支持的最大密钥长度为 2048 位。<?Comment A: Bug 146901 2013-03-13T14:15:00Z?></para>
            </TD>
            <TD colspan="1">
              <para>此证书在列出的站点系统服务器上是必需的（即使未安装 <token>cm6long</token> 客户端），因此可以监视这些站点系统角色的运行状况并向站点报告。</para>
              <para>这些站点系统的证书必须位于“计算机”证书存储的“个人”存储中。</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>将 <token><?xm-deletion_mark author="Nathan Bigman" time="20151108T145935+0200" data="cmshort"?><?xm-insertion_mark_start author="Nathan Bigman" time="20151108T145935+0200"?>cm6long<?xm-insertion_mark_end?></token> 策略模块与网络设备注册服务角色服务一起运行的服务器。 </para>
            </TD>
            <TD>
              <para>客户端身份验证</para>
            </TD>
            <TD>
              <para>工作站身份验证</para>
            </TD>
            <TD>
              <para>
                <ui></ui>“增强型密钥用法”值必须包含“客户端身份验证 (1.3.6.1.5.5.7.3.2)”<ui></ui>。</para>
              <para>没有针对证书“使用者”或“使用者可选名称” (SAN) 的特定要求，并且你可以为运行网络设备注册服务的多个服务器使用同一证书。</para>
              <para>支持 SHA-2 和 SHA-3 哈希算法。</para>
              <para>支持的密钥长度：1024 位和 2048 位。</para>
            </TD>
            <TD>
              <?xm-deletion_mark author="Nathan Bigman" time="20151108T150719+0200" data="&lt;maml:para xmlns:maml=&quot;http://ddue.schemas.microsoft.com/authoring/2003/5&quot;&gt;
                &lt;maml:token&gt;sccm2012r2notetopic&lt;/maml:token&gt;
              &lt;/maml:para&gt;
              &lt;maml:para xmlns:maml=&quot;http://ddue.schemas.microsoft.com/authoring/2003/5&quot;&gt;This certificate authenticates the &lt;maml:token&gt;cmshort&lt;/maml:token&gt; Policy Module to the certificate registration point site system server so that &lt;maml:token&gt;cmshort&lt;/maml:token&gt; can enroll certificates for users and devices.&lt;/maml:para&gt;
            "?></TD>
          </tr>
          <tr>
            <TD>
              <para>
                <?Comment CB: 246354,246356 2013-03-13T14:15:00Z  Id='8?>安装了分发点的站点系统<?CommentEnd Id='8'
    ?></para>
            </TD>
            <TD>
              <para>客户端身份验证</para>
            </TD>
            <TD>
              <para>
                <ui>工作站身份验证</ui>
              </para>
            </TD>
            <TD colspan="1">
              <para>
                <ui></ui>“增强型密钥用法”值必须包含“客户端身份验证 (1.3.6.1.5.5.7.3.2)”<ui></ui>。</para>
              <para>没有针对证书“使用者”或“使用者可选名称” (SAN) 的特定要求，并且你可以为多个分发点使用同一证书。 但是，我们建议为每个分发点使用不同证书。</para>
              <para>私钥必须是可导出的。</para>
              <para>支持 SHA-2 哈希算法。</para>
              <para>支持的最大密钥长度为 2048 位。<?Comment A: Bug 146901 2013-03-13T14:15:00Z?></para>
            </TD>
            <TD colspan="1">
              <para>此证书有两个用途：</para>
              <para>-在分发点发送状态消息之前，向启用 HTTPS 的管理点验证分发点。</para><para>- 如果选择了“为客户端启用 PXE 支持”<ui></ui>分发点选项，则将证书发送到计算机，以便在操作系统部署过程中的任务序列包括客户端操作（例如，客户端策略检索或发送清单信息）的情况下，客户端计算机可在操作系统部署过程中连接到启用 HTTPS 的管理点。</para><para>此证书仅在操作系统部署过程中使用，不会安装在客户端上。 由于这种暂时使用，如果你不想使用多个客户端证书，则可将同一个证书用于每个操作系统部署。</para>
              <para>必须采用公钥证书标准 (PKCS #12) 格式导出此证书，并且密码必须已知，以便可将其导入分发点属性中。</para>
              <para><legacyBold>注意：</legacyBold>此证书的要求与用于部署操作系统的启动映像的客户端证书相同。 由于要求相同，因此你可以使用同一证书文件。</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>带外服务点</para>
            </TD>
            <TD>
              <para>AMT 设置</para>
            </TD>
            <TD colspan="1">
              <para>
                <ui>Web 服务器</ui>（已修改）</para>
            </TD>
            <TD colspan="1">
              <para>
                <ui></ui>“增强型密钥用法”值必须包含“服务器身份验证 (1.3.6.1.5.5.7.3.1)”<ui></ui>和以下对象标识符：<ui>2.16.840.1.113741.1.2.3</ui>。</para>
              <para>使用者名称字段必须包含承载带外服务点的服务器的 FQDN。 </para>
              <para><legacyBold>
注意：</legacyBold>如果从外部 CA（而不是你自己的内部 CA）请求 AMT 设置证书，并且该证书不支持 AMT 设置对象标识符 2.16.840.1.113741.1.2.3，则你可以用另一种方式指定下列文本字符串作为证书使用者名称中的组织单位 (OU) 属性：<userInput>Intel(R) Client Setup Certificate</userInput>。 必须完全按原样使用这一英文文本字符串（大小写相同，不带后面的句号），另外再加上承载带外服务点的服务器的 FQDN。<?CommentEnd Id='12'
    ?></para>
              <para>支持的密钥长度：1024 和 2048。 对于 AMT 6.0 及更高版本，还支持 4096 位的密钥长度。</para>
            </TD>
            <TD colspan="1">
              <para>此证书位于带外服务点站点系统服务器的“计算机”证书存储的“个人”存储中。</para>
              <para>此 AMT 设置证书用于为带外管理准备计算机。 </para>
              <para>你必须从提供 AMT 设置证书的 CA 请求此证书，并且必须配置基于 Intel AMT 的计算机的 BIOS 扩展以便为此设置证书使用根证书指纹（也称为证书哈希）。</para>
              <para>VeriSign 是提供 AMT 设置证书的外部 CA 的典型示例，但你也可以使用自己的内部 CA。</para>
              <para>将证书安装在承载带外服务点的服务器上，该服务器必须能够成功地链接到证书的根 CA。 （默认情况下，在 Windows 安装时会安装 VeriSign 的根 CA 证书和中间 CA 证书。）</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>运行 <token>mit_first</token> 连接器的站点系统服务器</para>
            </TD>
            <TD>
              <para>客户端身份验证</para>
            </TD>
            <TD>
              <para>不适用：<token>mit_next</token> 会自动创建此证书。</para>
            </TD>
            <TD>
              <para>“增强型密钥用法”值包含“客户端身份验证 (1.3.6.1.5.5.7.3.2)”。</para>
              <para>3 个自定义扩展唯一地标识客户 <token>mit_next</token> 订阅。</para>
              <para>密钥大小为 2048 位，并且使用 SHA-1 哈希算法。</para>
              <para><legacyBold>注意：</legacyBold>无法更改这些设置：此信息仅供参考。</para>
            </TD>
            <TD>
              <para>当你订阅 <token>mit_first</token> 时，会自动请求此证书并将其安装到 Configuration Manager 数据库。 当你安装 <token>mit_first</token> 连接器时，此证书随后安装到运行 <token>mit_first</token> 连接器的站点系统服务器上。 它将安装到“计算机”证书存储中。</para>
              <para>此证书用于通过 <token>mit_first</token> 连接器向 <token>mit_first</token> 验证 Configuration Manager 层次结构。 在它们之间传输的所有数据都使用安全套接字层 (SSL)。</para>
            </TD>
          </tr>
        </tbody>
      </table>
    </content>
    <sections>
      <section address="BKMK_PKIcertificates_for_proxyservers" expanded="false">
        <title>基于 Internet 的客户端管理的代理 Web 服务器。</title>
        <content>
          <para>如果站点支持基于 Internet 的客户端管理，并且通过为传入 Internet 连接使用 SSL 终端（桥接）来使用代理 Web 服务器，则代理 Web 服务器具有下表所列的证书要求。</para>
          <alert class="note">
            <para>如果你使用代理 Web 服务器但不使用 SSL 终端（隧道），则代理 Web 服务器不需要其他证书。</para>
          </alert>
          <table>
            <thead>
              <tr>
                <TD colspan="1">
                  <para>网络基础结构组件</para>
                </TD>
                <TD colspan="1">
                  <para>证书用途</para>
                </TD>
                <TD colspan="1">
                  <para>要使用的 Microsoft 证书模板</para>
                </TD>
                <TD colspan="1">
                  <para>证书中的特定信息</para>
                </TD>
                <TD colspan="1">
                  <para><token><?xm-deletion_mark author="Nathan Bigman" time="20151108T145935+0200" data="cmshort"?><?xm-insertion_mark_start author="Nathan Bigman" time="20151108T145935+0200"?>cm6long 中证书的使用方式<?xm-insertion_mark_end?></token> </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD colspan="1">
                  <para>接受通过 Internet 的客户端连接的代理 Web 服务器</para>
                </TD>
                <TD colspan="1">
                  <para>服务器身份验证和客户端身份验证</para>
                </TD>
                <TD colspan="1">
                  <para>1. 
                        <ui>Web 服务器</ui>
                      </para><para>2. 
                        <ui>工作站身份验证</ui>
                      </para>
                </TD>
                <TD colspan="1">
                  <para>“使用者名称”字段或“使用者可选名称”字段中（如果使用的是 Microsoft 证书模板，“使用者可选名称”只能与工作站模板配合使用）的 Internet FQDN。</para>
                  <para>支持 SHA-2 哈希算法。</para>
                </TD>
                <TD colspan="1">
                  <para>此证书用于向 Internet 客户端对以下服务器进行验证，以及通过使用 SSL 对客户端和此服务器之间传输的所有数据进行加密：</para>
                  <para>-基于 Internet 的管理点</para><para>-基于 Internet 的分发点</para><para>-基于 Internet 的软件更新点</para>
                  <para>客户端身份验证用于在 <token>cm6long</token> 客户端与基于 Internet 的站点系统之间桥接客户端连接。</para>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
      </section>
    </sections>
  </section>
  <section address="BKMK_PKIcertificates_for_clients" expanded="false">
    <title>客户端的 PKI 证书</title>
    <content>
      <table>
        <thead>
          <tr>
            <TD colspan="1">
              <para>
                <token><?xm-deletion_mark author="Nathan Bigman" time="20151108T145935+0200" data="cmshort"?><?xm-insertion_mark_start author="Nathan Bigman" time="20151108T145935+0200"?>cm6long<?xm-insertion_mark_end?></token> 组件</para>
            </TD>
            <TD>
              <para>证书用途</para>
            </TD>
            <TD>
              <para>要使用的 Microsoft 证书模板</para>
            </TD>
            <TD>
              <para>证书中的特定信息</para>
            </TD>
            <TD>
              <para><token><?xm-deletion_mark author="Nathan Bigman" time="20151108T145935+0200" data="cmshort"?><?xm-insertion_mark_start author="Nathan Bigman" time="20151108T145935+0200"?>cm6long 中证书的使用方式<?xm-insertion_mark_end?></token> </para>
            </TD>
          </tr>
        </thead>
        <tbody>
          <tr>
            <TD>
              <para>Windows 客户端计算机</para>
            </TD>
            <TD>
              <para>客户端身份验证</para>
            </TD>
            <TD>
              <para>
                <ui>工作站身份验证</ui>
              </para>
            </TD>
            <TD colspan="1">
              <para>
                <ui></ui>“增强型密钥用法”值必须包含“客户端身份验证 (1.3.6.1.5.5.7.3.2)”<ui></ui>。</para>
              <para>客户端计算机必须在“使用者名称”字段或“使用者可选名称”字段中有唯一的值。</para>
              <para><legacyBold>注意：</legacyBold>如果将多个值用于“使用者可选名称”，则只会使用第一个值。</para>
              <para>支持 SHA-2 哈希算法。</para>
              <para>支持的最大密钥长度为 2048 位。</para>
            </TD>
            <TD colspan="1">
              <para>默认情况下，<token><?xm-deletion_mark author="Nathan Bigman" time="20151108T145935+0200" data="cmshort"?><?xm-insertion_mark_start author="Nathan Bigman" time="20151108T145935+0200"?>cm6long<?xm-insertion_mark_end?></token> 将在“计算机”证书存储的“个人”存储中查找计算机证书。</para>
              <para>除了软件更新点和应用程序目录网站点以外，此证书向运行 IIS 并且配置为使用 HTTPS 的站点系统服务器<?Comment CB: bug187730 2013-03-13T14:15:00Z  Id='34?>验证客户端<?CommentEnd Id='34'
    ?>。</para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>移动设备客户端</para>
            </TD>
            <TD>
              <para>客户端身份验证</para>
            </TD>
            <TD>
              <para>
                <ui>经过验证的会话</ui>
              </para>
            </TD>
            <TD colspan="1">
              <para>
                <ui></ui>“增强型密钥用法”值必须包含“客户端身份验证 (1.3.6.1.5.5.7.3.2)”<ui></ui>。</para>
              <para>SHA-1</para>
              <para>支持的最大密钥长度为 2048 位。<?Comment A: Bug 146901 2013-03-13T14:15:00Z?></para>
              <para><legacyBold>注意：</legacyBold></para><para>-这些证书必须采用可分辨编码规则 (DER) 编码的二进制 X.509 格式。 </para><para>- 不支持 Base64 编码的 X.509 格式。</para>
            </TD>
            <TD colspan="1">
              <para>此证书向它与之通信的站点系统服务器（例如管理点和分发点）验证移动设备客户端。</para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>用于部署操作系统的启动映像 </para>
            </TD>
            <TD>
              <para>客户端身份验证</para>
            </TD>
            <TD colspan="1">
              <para>
                <ui>工作站身份验证</ui>
              </para>
            </TD>
            <TD colspan="1">
              <para>
                <ui></ui>“增强型密钥用法”值必须包含<ui>客户端身份验证 (1.3.6.1.5.5.7.3.2)</ui>。</para>
              <para>没有针对证书“使用者名称”字段或<?Comment CB: 202846 2013-03-13T14:15:00Z  Id='36?>“使用者可选名称”(SAN) 的特定要求，<?CommentEnd Id='36'
    ?>并且你可以为所有启动映像使用同一证书。</para>
              <para>私钥必须是可导出的。</para>
              <para>支持 SHA-2 哈希算法。</para>
              <para>支持的最大密钥长度为 2048 位。<?Comment A: Bug 146901 2013-03-13T14:15:00Z?></para>
            </TD>
            <TD colspan="1">
              <para>如果操作系统部署过程中的任务序列包括客户端操作（例如客户端策略检索或发送清单信息），则会使用该证书。</para>
              <para>此证书仅在操作系统部署过程中使用，不会安装在客户端上。 由于这种暂时使用，如果你不想使用多个客户端证书，则可将同一个证书用于每个操作系统部署。</para>
              <para>必须采用公钥证书标准 (PKCS #12) 格式导出此证书，并且密码必须已知，以便可将其导入 <token><?xm-deletion_mark author="Nathan Bigman" time="20151108T145935+0200" data="cmshort"?><?xm-insertion_mark_start author="Nathan Bigman" time="20151108T145935+0200"?>cm6long<?xm-insertion_mark_end?></token> 启动映像中。</para>
              <para>此证书临时用于任务序列，不可用于安装客户端。 如果你的环境中仅包含 HTTPS，则客户端必须具有有效证书才能与站点通信并继续部署。 客户端加入 Active Directory 时会自动生成客户端证书，或者你也可以通过其他方法安装客户端证书。 </para><para><legacyBold>注意：</legacyBold>此证书的要求与安装了分发点的站点系统的服务器证书的要求相同。 由于要求相同，因此你可以使用同一证书文件。</para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>Mac 客户端计算机</para>
            </TD>
            <TD>
              <para>客户端身份验证</para>
            </TD>
            <TD>
              <para>对于 <token><?xm-deletion_mark author="Nathan Bigman" time="20151108T145935+0200" data="cmshort"?><?xm-insertion_mark_start author="Nathan Bigman" time="20151108T145935+0200"?>cm6long<?xm-insertion_mark_end?></token> 注册：<ui>经过验证的会话</ui></para>
              <para>对于独立于 <token><?xm-deletion_mark author="Nathan Bigman" time="20151108T145935+0200" data="cmshort"?><?xm-insertion_mark_start author="Nathan Bigman" time="20151108T145935+0200"?>cm6long<?xm-insertion_mark_end?></token> 的证书安装：<ui>工作站身份验证</ui></para>
            </TD>
            <TD colspan="1">
              <para>
                <ui></ui>“增强型密钥用法”值必须包含“客户端身份验证 (1.3.6.1.5.5.7.3.2)”<ui></ui>。</para>
              <para>对于创建用户证书的 <token><?xm-deletion_mark author="Nathan Bigman" time="20151108T145935+0200" data="cmshort"?><?xm-insertion_mark_start author="Nathan Bigman" time="20151108T145935+0200"?>cm6long<?xm-insertion_mark_end?></token>，会使用注册 Mac 计算机的人员的用户名自动填充证书使用者值。</para>
              <para>在安装证书时，如果不使用 <token><?xm-deletion_mark author="Nathan Bigman" time="20151108T145935+0200" data="cmshort"?><?xm-insertion_mark_start author="Nathan Bigman" time="20151108T145935+0200"?>cm6long<?xm-insertion_mark_end?></token> 注册，但独立于 <token><?xm-deletion_mark author="Nathan Bigman" time="20151108T145935+0200" data="cmshort"?><?xm-insertion_mark_start author="Nathan Bigman" time="20151108T145935+0200"?>cm6long<?xm-insertion_mark_end?></token> 部署计算机证书，则证书使用者值必须唯一。 例如，指定计算机的 FQDN。</para>
              <para>不支持“使用者可选名称”字段。</para>
              <para>支持 SHA-2 哈希算法。</para>
              <para>支持的最大密钥长度为 2048 位。<?Comment A: Bug 146901 2013-03-13T14:15:00Z?></para>
            </TD>
            <TD colspan="1">
              <para>此证书向它与之通信的站点系统服务器（例如管理点和分发点）验证 Mac 客户端计算机。</para>
              </TD>
          </tr>
          <tr>
            <TD>
              <para>Linux 和 UNIX 客户端计算机</para>
            </TD>
            <TD>
              <para>客户端身份验证</para>
            </TD>
            <TD>
              <para>
                <ui>工作站身份验证</ui>
              </para>
            </TD>
            <TD>
              <para>
                <ui></ui>“增强型密钥用法”值必须包含“客户端身份验证 (1.3.6.1.5.5.7.3.2)”<ui></ui>。</para>
              <para>不支持“使用者可选名称”字段。</para>
              <para>私钥必须是可导出的。</para>
              <?xm-deletion_mark author="Nathan Bigman" time="20151108T153134+0200" data="&lt;maml:para xmlns:maml=&quot;http://ddue.schemas.microsoft.com/authoring/2003/5&quot;&gt;SHA-1 hash algorithm is supported.&lt;/maml:para&gt;
              "?><para>如果客户端操作系统支持 SHA-2，则支持 SHA-2 哈希算法。 有关详细信息，请参阅<?xm-deletion_mark author="Nathan Bigman" time="20151108T152725+0200" data="the"?> <link xlink:href="44153689-70e8-42ad-9ae8-17ae35f6a2e3">规划将客户端部署到 Linux 和 UNIX 计算机</link><?xm-deletion_mark author="Nathan Bigman" time="20151108T152727+0200" data=" topic"?>中的<link xlink:href="44153689-70e8-42ad-9ae8-17ae35f6a2e3#BKMK_NoSHA-256">关于不支持 SHA-256 的 Linux 和 UNIX 操作系统</link>部分。</para>
              <para>支持的密钥长度：2048 位。</para>
              <para><legacyBold>注意：</legacyBold>这些证书必须采用可分辨编码规则 (DER) 编码的二进制 X.509 格式。 不支持 Base64 编码的 X.509 格式。</para>
            </TD>
            <TD>
              <?xm-deletion_mark author="Nathan Bigman" time="20151108T150749+0200" data="&lt;maml:para xmlns:maml=&quot;http://ddue.schemas.microsoft.com/authoring/2003/5&quot;&gt;
                &lt;maml:token&gt;sccm2012sp1note&lt;/maml:token&gt;
              &lt;/maml:para&gt;
              &lt;maml:para xmlns:maml=&quot;http://ddue.schemas.microsoft.com/authoring/2003/5&quot;&gt;This certificate authenticates the client for Linux and UNIX to the site system servers that it communicates with, such as management points and distribution points.&lt;/maml:para&gt;
              "?><para>此证书向它与之通信的站点系统服务器（例如管理点和分发点）验证 Mac 客户端计算机。 必须采用公钥证书标准 (PKCS #12) 格式导出此证书，并且密码必须已知，以便可以在指定 PKI 证书时将它指定到客户端。</para>
              <para>有关其他信息，请参阅<link xlink:href="44153689-70e8-42ad-9ae8-17ae35f6a2e3">规划将客户端部署到 Linux 和 UNIX 计算机</link>中的<link xlink:href="44153689-70e8-42ad-9ae8-17ae35f6a2e3#BKMK_SecurityforLnU">为 Linux 和 UNIX 服务器规划安全性和证书</link>部分。</para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>- 下列情况下的根证书颁发机构 (CA) 证书：</para>
              <para>-操作系统部署</para><para>-移动设备注册</para><para>-基于 Intel AMT 的计算机的 RADIUS 服务器身份验证</para><para>-客户端证书身份验证</para>
            </TD>
            <TD>
              <para>到受信任来源的证书链</para>
            </TD>
            <TD colspan="1">
              <para>不适用。</para>
            </TD>
            <TD colspan="1">
              <para>标准的根 CA 证书。</para>
            </TD>
            <TD colspan="1">
              <para>在客户端必须将通信服务器的证书链接到受信任的来源时，必须提供根 CA 证书。 这适用于下列情况：</para>
              <para>-部署操作系统，而且运行该操作系统的任务序列将客户端计算机连接到配置为使用 HTTPS 的管理点时。 </para><para>- 注册将由 <token>cm6long</token> 托管的移动设备时。</para><para>- 在使用 802.1X 对基于 AMT 的计算机进行身份验证，而且想为 RADIUS 服务器的根证书指定文件时。</para>
              <para>此外，如果颁发客户端证书的 CA 层次结构与颁发管理点证书的 CA 层次结构不同，则必须提供客户端的根 CA 证书。 </para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>基于 Intel AMT 的计算机</para>
            </TD>
            <TD colspan="1">
              <para>服务器身份验证。</para>
            </TD>
            <TD colspan="1">
              <para>
                <ui>Web 服务器</ui>（已修改）</para>
              <para>你必须对“使用 Active Directory 中的信息生成”<ui></ui>配置使用者名称，然后为“使用者名称格式”<ui></ui>选择“公用名”<ui></ui>。</para>
              <para>对于你在带外管理组件属性中指定的通用安全组，必须向其授予“读取”<ui></ui>和“注册”<ui></ui>权限。</para>
            </TD>
            <TD colspan="1">
              <para>
                <ui></ui>“增强型密钥用法”值必须包含“服务器身份验证 (1.3.6.1.5.5.7.3.1)”<ui></ui>。</para>
              <para>使用者名称必须包含基于 AMT 的计算机的 FQDN，它是自动通过 Active Directory 域服务提供的。</para>
              <?xm-deletion_mark author="Nathan Bigman" time="20151108T153354+0200" data="&lt;maml:para xmlns:maml=&quot;http://ddue.schemas.microsoft.com/authoring/2003/5&quot;&gt;
                &lt;?Comment CRB: Bug 179814 2013-03-13T14:15:00Z  Id=&apos;39?&gt;
                &lt;maml:token&gt;SHA-1&lt;/maml:token&gt;
                &lt;?CommentEnd Id=&apos;39&apos;
    ?&gt;
              &lt;/maml:para&gt;
              &lt;maml:para xmlns:maml=&quot;http://ddue.schemas.microsoft.com/authoring/2003/5&quot;&gt;Maximum supported key length: 2048 bits.&lt;/maml:para&gt;
            "?></TD>
            <TD colspan="1">
              <para>此证书驻留在计算机中的管理控制器的永久性随机存取内存中，而且在 Windows 用户界面中不可见。</para>
              <para>每台基于 Intel AMT 的计算机都会在 AMT 设置期间以及后续更新时请求此证书。 如果从这些计算机中删除 AMT 设置信息，则它们会吊销此证书。</para>
              <para>在基于 Intel AMT 的计算机上安装此证书时，也会安装到根 CA 的证书链。 基于 AMT 的计算机不能支持密钥长度大于 2048 位的 CA 证书。</para>
              <para>在基于 Intel AMT 的计算机上安装此证书之后，此证书将向带外服务点站点系统服务器和运行带外管理控制台的计算机验证基于 AMT 的计算机，并使用传输层安全性 (TLS) 对在它们之间传输的所有数据进行加密。</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>Intel AMT 802.1X 客户端证书</para>
            </TD>
            <TD>
              <para>客户端身份验证</para>
            </TD>
            <TD>
              <para>
                <ui>工作站身份验证</ui>
              </para>
              <para>你必须对“使用 Active Directory 中的信息生成”<ui></ui>配置使用者名称，然后为“使用者名称格式”<ui></ui>选择“公用名”<ui></ui>，清除 DNS 名称，然后为使用者可选名称选择用户主体名称 (UPN)。</para>
              <para>对于你在带外管理组件属性中指定的通用安全组，必须向其授予此证书模板的“读取”<ui></ui>和“注册”<ui></ui>权限。</para>
            </TD>
            <TD colspan="1">
              <para>
                <ui></ui>“增强型密钥用法”值必须包含“客户端身份验证 (1.3.6.1.5.5.7.3.2)”<ui></ui>。</para>
              <para>使用者名称字段必须包含基于 AMT 的计算机的 FQDN，而使用者可选名称必须包含 UPN。 </para>
              <para>支持的最大密钥长度：2048 位。</para>
            </TD>
            <TD>
              <para>此证书驻留在计算机中的管理控制器的永久性随机存取内存中，而且在 Windows 用户界面中不可见。</para>
              <para>每台基于 Intel AMT 的计算机都可以在 AMT 设置期间请求此证书，但是，在删除它们的 AMT 设置信息时，它们不会吊销此证书。</para>
              <para>在基于 AMT 的计算机上安装此证书之后，此证书将向 RADIUS 服务器验证基于 AMT 的计算机，以便它之后能获得网络访问的授权。</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para><token>mit_first 注册的移动设备：</token></para>
            </TD>
            <TD>
              <para>客户端身份验证</para>
            </TD>
            <TD>
              <para>不适用：<token>mit_next</token> 会自动创建此证书。</para>
            </TD>
            <TD>
              <para>“增强型密钥用法”值包含“客户端身份验证 (1.3.6.1.5.5.7.3.2)”。</para>
              <para>3 个自定义扩展唯一地标识客户 <token>mit_next</token> 订阅。</para>
              <para>用户可以在注册过程中提供证书使用者值。 但是，此值不使用 <token>mit_next</token> 来标识设备。</para>
              <para>密钥大小为 2048 位，并且使用 SHA-1 哈希算法。</para>
              <para><legacyBold>注意：</legacyBold>无法更改这些设置：此信息仅供参考。</para>
            </TD>
            <TD>
              <para>在经过身份验证的用户使用 <token>mit_first</token>注册他们的移动设备时，会自动请求和安装此证书。 设备上的最终证书驻留在计算机存储中，并且向 <token>mit_next</token>验证已注册的移动设备，以便之后可以管理它。 </para>
              <para>由于证书中包含自定义扩展，因此，只能向已经为组织建立的 <token>mit_next</token> 订阅进行验证。</para>
            </TD>
          </tr>
        </tbody>
      </table>
    </content>
  </section>
  <relatedTopics>
<?xm-deletion_mark author="Nathan Bigman" time="20151108T152245+0200" data="&lt;maml:link xlink:href=&quot;c251511b-da2d-411e-9a0e-787455305d8f&quot; xmlns:maml=&quot;http://ddue.schemas.microsoft.com/authoring/2003/5&quot; xmlns:xlink=&quot;http://www.w3.org/1999/xlink&quot;&gt;Planning for Configuration Manager Sites and Hierarchy&lt;/maml:link&gt;
"?></relatedTopics></developerConceptualDocument>

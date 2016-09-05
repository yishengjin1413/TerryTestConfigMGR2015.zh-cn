---
title: "如何为未使用 System Center Configuration Manager 客户端管理的 Windows Phone 设备创建配置项目"
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
ms.assetid: fae7f9e0-d5e7-422f-a6ed-6f6d73f6a617
caps.latest.revision: 13
caps.handback.revision: 10
translationtype: Human Translation
---
# 如何为未使用 System Center Configuration Manager 客户端管理的 Windows Phone 设备创建配置项目
<?xml version="1.0" encoding="UTF-8"?>
<developerConceptualDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns:xlink="http://www.w3.org/1999/xlink">
    <introduction>
        <para>使用 <token>cm6long</token>  <ui>Windows Phone</ui> 配置项目，以管理在 Microsoft Intune 中注册的或由 <token>cmshort</token> 在本地管理的 Windows Phone 设备的设置。</para>
    <procedure>
<title>创建 Windows Phone 配置项目</title>
 <steps class="ordered">
        <step><content><para>在 <token>cmshort</token> 控制台中，单击“资产和符合性”。</para></content></step>
        <step><content><para>在“资产和符合性” 工作区中，展开“符合性设置”，然后单击“配置项目”。</para></content></step>
      <step>
 <content><para>在“主页”选项卡上“创建”组中，单击“创建配置项目”。</para></content>
</step><step>
 <content><para>在“创建配置项目向导”的“常规”页上，指定配置项目的名称和可选描述。</para></content>
</step><step>
 <content><para>在“指定要创建的配置项目的类型”下，选择“Windows Phone”。</para></content>
</step><step>
 <content><para>如果创建并分配类别，以帮助搜索和筛选 <token>cmshort</token> 控制台中的配置项目，请单击“类别”。</para></content>
</step><step>
 <content><para>在向导的“支持的平台”页上，选择将评估配置项目的特定 Windows Phone 平台。</para></content>
</step><step>
 <content><para>在向导的“设备设置”页上，选择要配置的设置组<ui></ui><ui></ui><ui></ui><ui></ui><ui></ui><ui></ui><ui></ui><ui></ui><ui></ui><ui></ui><ui></ui><ui></ui><ui></ui><ui></ui>。 有关详细信息，请参阅本主题中 <link xlink:href="#BKMK_Setref">Windows Phone 配置项目设置引用</link>，然后单击“下一步”。</para><alert class="tip">
<para>如果未列出所需的设置，请选择“配置不在默认设置组中的其他设置”复选框。</para>
</alert></content>
</step><step>
 <content><para>在每个设置页上，配置所需的设置以及当它们与设备不兼容时是否要修正它们（当支持此选项时）。</para></content>
</step><step>
 <content><para>对于每个设置组，也可以配置当发现配置项目不兼容时报告的严重性：</para><list class="bullet"><listItem><para><ui>无</ui> -不符合此兼容性规则的设备不会在 <token>cmshort</token> 报告中报告故障严重性。</para></listItem><listItem><para><ui>信息</ui> -不符合此兼容性规则的设备在 <token>cmshort</token> 报告中报告“信息”的故障严重性。</para></listItem><listItem><para><ui>警告</ui> -不符合此兼容性规则的设备在 <token>cmshort</token> 报告中报告“警告”的故障严重性。</para></listItem><listItem><para><ui>严重</ui> -不符合此兼容性规则的设备在 <token>cmshort</token> 报告中报告“严重”的故障严重性。</para></listItem><listItem><para><ui>事件严重</ui>  -不符合此兼容性规则的设备在 <token>cmshort</token> 报告中报告“严重”的故障严重性<ui></ui><ui></ui><ui></ui><ui></ui><ui></ui><ui></ui>。 在应用程序事件日志中也会将此严重性级别作为 Windows 事件记录。</para></listItem></list></content>
</step><step>
 <content><para>在向导的“平台适用性”<ui></ui>页面上，查看任何与先前选择的受支持平台不兼容的设置。 你可以返回并删除这些设置，或继续。</para><alert class="tip">
<para>不会评估不受支持的设置的兼容性。</para>
</alert></content>
</step><step>
 <content><para>完成向导。</para></content>
</step></steps>
<conclusion><content><para>你可以查看“资产和符合性”工作区的“配置项目”节点中新的配置项目<ui></ui><ui></ui>。</para></content></conclusion></procedure></introduction>
    
    <section address="BKMK_Setref">
<title>Windows Phone 配置项目设置参考</title><content></content>
<sections><section>
<title>Password</title><content><table border="1"><thead><tr><TD><para>设置</para></TD><TD><para>详细信息</para></TD><TD><para>Windows Phone 8</para></TD><TD><para>Windows Phone 8.1</para></TD></tr></thead><tbody><tr><TD><para><ui>设备上需要密码设置</ui></para></TD><TD><para>支持的设备上需要密码。
</para></TD><TD><para>是</para></TD><TD><?xm-insertion_mark_start author="" time="20151114T110731-0800"?><para>是</para><?xm-insertion_mark_end?></TD></tr><tr><TD><para><ui>最短密码长度（字符）</ui></para></TD><TD><para>密码的最短长度。
</para></TD><TD><para>是</para></TD><TD><?xm-insertion_mark_start author="" time="20151114T110736-0800"?><para>是</para><?xm-insertion_mark_end?></TD></tr><tr><TD><para><ui>密码过期天数</ui></para></TD><TD><para>必须更改密码前的天数。
</para></TD><TD><para>是</para></TD><TD><?xm-insertion_mark_start author="" time="20151114T110737-0800"?><para>是</para><?xm-insertion_mark_end?></TD></tr><tr><TD><para><ui>记住的密码数</ui></para></TD><TD><para>防止重复使用以前用过的密码。
</para></TD><TD><para>是</para></TD><TD><?xm-insertion_mark_start author="" time="20151114T110738-0800"?><para>是</para><?xm-insertion_mark_end?></TD></tr><tr><TD><para><ui>擦除设备前的失败登录尝试次数</ui></para></TD><TD><para>如果此数目的登录尝试均失败，则擦除该设备。
</para></TD><TD><para>是</para></TD><TD><?xm-insertion_mark_start author="" time="20151114T110739-0800"?><para>是</para><?xm-insertion_mark_end?></TD></tr><tr><TD><para><ui>密码复杂性</ui></para></TD><TD><para>选择是否可以指定一个如“1234”的 PIN，或是否必须提供一个强密码。
</para></TD><TD><para>是</para></TD><TD><?xm-insertion_mark_start author="" time="20151114T110739-0800"?><para>是</para><?xm-insertion_mark_end?></TD></tr><tr><TD><para><ui>将密码恢复 PIN 发送到 Exchange Server</ui></para></TD><TD><para></para></TD><TD><para>是</para></TD><TD><?xm-insertion_mark_start author="" time="20151114T110740-0800"?><para>是</para><?xm-insertion_mark_end?></TD></tr></tbody></table></content>
</section><section>
<title>设备</title><content><table border="1"><thead><tr><TD><para>设置</para></TD><TD><para>详细信息</para></TD><TD><para>Windows Phone 8</para></TD><TD><para>Windows Phone 8.1</para></TD></tr></thead><tbody><tr><TD><para><ui>屏幕捕获</ui></para></TD><TD></TD><TD><?xm-insertion_mark_start author="" time="20151114T110847-0800"?><para>否</para><?xm-insertion_mark_end?></TD><TD><?xm-insertion_mark_start author="" time="20151114T110849-0800"?><para>是</para><?xm-insertion_mark_end?></TD></tr><tr><TD><para><ui>诊断数据提交</ui></para></TD><TD><para>允许提交应用日志文件。
</para></TD><TD><para>是</para></TD><TD><?xm-insertion_mark_start author="" time="20151114T110855-0800"?><para>是</para><?xm-insertion_mark_end?></TD></tr><tr><TD><para><ui>地理位置</ui></para></TD><TD><?xm-insertion_mark_start author="" time="20151114T111002-0800"?><para>允许设备使用位置服务信息。
</para><?xm-insertion_mark_end?></TD><TD><?xm-insertion_mark_start author="" time="20151114T110859-0800"?><para>否</para><?xm-insertion_mark_end?></TD><TD><?xm-insertion_mark_start author="" time="20151114T110900-0800"?><para>是</para><?xm-insertion_mark_end?></TD></tr><tr><TD><para><ui>复制和粘贴</ui></para></TD><TD><?xm-insertion_mark_start author="" time="20151114T111010-0800"?><para>使用复制和粘贴在应用之间传输数据。
</para><?xm-insertion_mark_end?></TD><TD><?xm-insertion_mark_start author="" time="20151114T110905-0800"?><para>否</para><?xm-insertion_mark_end?></TD><TD><?xm-insertion_mark_start author="" time="20151114T110906-0800"?><para>是</para><?xm-insertion_mark_end?></TD></tr><tr><TD><para><ui>蓝牙</ui></para></TD><TD><para>允许使用设备的蓝牙功能。</para></TD><TD><para>是</para></TD><TD><?xm-insertion_mark_start author="" time="20151114T110915-0800"?><para>是</para><?xm-insertion_mark_end?></TD></tr></tbody></table></content>
</section><section>
<title>电子邮件管理</title><content><table border="1"><thead><tr><TD><para>设置</para></TD><TD><para>详细信息</para></TD><TD><para>Windows Phone 8</para></TD><TD><para>Windows Phone 8.1</para></TD></tr></thead><tbody><tr><TD><para><ui>POP 和 IMAP 电子邮件</ui></para></TD><TD><para>允许连接到使用 POP 和 IMAP 标准的电子邮件帐户。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>保留电子邮件的最长时间</ui></para></TD><TD><para>电子邮件从服务器中删除之前可保留的时间长度。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>允许的消息格式</ui></para></TD><TD><para>指定用户电子邮件是否可以是 HTML 或仅是纯文本。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>（自动下载）纯文本电子邮件的最大大小</ui></para></TD><TD><para>控制自动下载的纯文本电子邮件的最大大小。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>（自动下载）HTML 电子邮件的最大大小</ui></para></TD><TD><para>控制自动下载的 HTML 电子邮件的最大大小。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>（自动下载）附件的最大大小</ui></para></TD><TD><para>配置将自动下载的最大大小的电子邮件。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>日历同步</ui></para></TD><TD></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>自定义电子邮件帐户</ui></para></TD><TD><para>允许在设备上使用非 Microsoft 帐户。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>在 Windows Mail 应用中将 Microsoft 帐户设为可选</ui></para></TD><TD></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr></tbody></table></content>
</section><section>
<title>存储</title><content><table border="1"><thead><tr><TD><para>设置</para></TD><TD><para>详细信息</para></TD><TD><para>Windows Phone 8</para></TD><TD><para>Windows Phone 8.1</para></TD></tr></thead><tbody><tr><TD><para><ui>应用商店</ui></para></TD><TD><para>允许在设备上访问应用商店。
</para></TD><TD><para>否</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>输入密码以访问应用商店</ui></para></TD><TD><para>用户必须输入密码以访问应用商店。
</para></TD><TD><para>否</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>应用内购买</ui></para></TD><TD><para>允许用户进行应用内购买。
</para></TD><TD><para>否</para></TD><TD><para>是</para></TD></tr></tbody></table></content>
</section><section>
<title>浏览器</title><content><table border="1"><thead><tr><TD><para>设置</para></TD><TD><para>详细信息</para></TD><TD><para>Windows Phone 8</para></TD><TD><para>Windows Phone 8.1</para></TD></tr></thead><tbody><tr><TD><para><ui>默认浏览器</ui></para></TD><TD><para>用户可以更改默认 Internet 浏览器。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>自动填充</ui></para></TD><TD><para>用户可以更改浏览器中的自动完成设置。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>活动脚本</ui></para></TD><TD><para>浏览器可以运行脚本，如 Active X 脚本。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>插件</ui></para></TD><TD><para>用户可以向 Internet Explorer 添加插件。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>弹出窗口阻止程序</ui></para></TD><TD><para>启用或禁用浏览器弹出窗口阻止程序。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>Cookie</ui></para></TD><TD><para>允许在设备上保存 Cookie。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>欺诈警告</ui></para></TD><TD><para>启用或禁用对潜在欺诈网站的警告。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr></tbody></table></content>
</section><section>
<title>Internet Explorer</title><content><table border="1"><thead><tr><TD><para>设置</para></TD><TD><para>详细信息</para></TD><TD><para>Windows Phone 8</para></TD><TD><para>Windows Phone 8.1</para></TD></tr></thead><tbody><tr><TD><para><ui>始终发送“不跟踪”标题</ui></para></TD><TD><para>防止浏览信息被发送到第三方站点。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>Intranet 安全区域</ui></para></TD><TD></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>Internet 区域的安全级别</ui></para></TD><TD><para>配置 Internet 区域的安全级别。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>Intranet 区域的安全级别</ui></para></TD><TD><para>配置 Intranet 区域的安全级别。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>受信任的站点区域的安全级别</ui></para></TD><TD><para>配置受信任的站点区域的安全级别。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>受限制的站点区域的安全级别</ui></para></TD><TD><para>配置受限制的站点区域的安全级别。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>Intranet 区域的命名空间</ui></para></TD><TD></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>转至 Intranet 站点以获取单字条目</ui></para></TD><TD><para>启用或禁用以下设置：如果输入的有效站点名称前没有“HTTP:”，则允许 Internet Explorer 自动转至 Intranet 站点
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>企业模式菜单选项</ui></para></TD><TD><para>允许用户从 Internet Explorer 的“工具”<ui></ui>菜单中激活和停用企业模式。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>记录报告位置 (URL)</ui></para></TD><TD><para>指定启用企业模式时将登录的受访网站的 URL。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>企业模式站点列表位置 (URL)</ui></para></TD><TD><para>指定活动状态下将使用企业模式的网站列表的位置。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr></tbody></table></content>
</section><section>
<title>云</title><content><table border="1"><thead><tr><TD><para>设置</para></TD><TD><para>详细信息</para></TD><TD><para>Windows Phone 8</para></TD><TD><para>Windows Phone 8.1</para></TD></tr></thead><tbody><tr><TD><para><ui>设置同步</ui></para></TD><TD><para>允许设备之间的设置同步。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>凭据同步</ui></para></TD><TD><para>允许设备之间的凭据同步。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>Microsoft 帐户</ui></para></TD><TD><para>允许在设备上使用 Microsoft 帐户。
</para></TD><TD><para>否</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>通过按流量计费的连接进行设置同步</ui></para></TD><TD><para>允许在 Internet 连接按流量计费时进行设置同步。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr></tbody></table></content>
</section><section>
<title>安全</title><content><table border="1"><thead><tr><TD><para>设置</para></TD><TD><para>详细信息</para></TD><TD><para>Windows Phone 8</para></TD><TD><para>Windows Phone 8.1</para></TD></tr></thead><tbody><tr><TD><para><ui>未签名的文件安装</ui></para></TD><TD><para>允许加载未签名的文件。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>未签名的应用程序</ui></para></TD><TD><para>允许加载未签名的应用。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>SMS 和 MMS 消息</ui></para></TD><TD><para>允许设备中的 SMS 和 MMS 消息。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>可移动存储</ui></para></TD><TD><para>允许在设备上使用可移动存储，如 SD 卡。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>照相机</ui></para></TD><TD><para>允许使用设备的照相机。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>近场通信 (NFC)</ui></para></TD><TD><para>允许在设备上使用 NFC 进行通信。
</para></TD><TD><para>否</para></TD><TD><para>是</para></TD></tr></tbody></table></content>
</section><section>
<title>峰值同步</title><content><table border="1"><thead><tr><TD><para>设置</para></TD><TD><para>详细信息</para></TD><TD><para>Windows Phone 8</para></TD><TD><para>Windows Phone 8.1</para></TD></tr></thead><tbody><tr><TD><para><ui>指定高峰时段</ui></para></TD><TD></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>峰值同步频率</ui></para></TD><TD></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>非峰值同步频率</ui></para></TD><TD></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr></tbody></table></content>
</section><section>
<title>漫游</title><content><table border="1"><thead><tr><TD><para>设置</para></TD><TD><para>详细信息</para></TD><TD><para>Windows Phone 8</para></TD><TD><para>Windows Phone 8.1</para></TD></tr></thead><tbody><tr><TD><para><ui>漫游时的设备管理</ui>
</para></TD><TD><para>允许设备在漫游时由 <token>cmshort</token> 管理。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>漫游时的软件下载</ui></para></TD><TD><para>允许在漫游时下载应用和软件。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>漫游时的电子邮件下载</ui></para></TD><TD><para>允许在漫游时下载电子邮件。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>数据漫游</ui></para></TD><TD><para>允许在访问数据时进行网络之间的漫游。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr></tbody></table></content>
</section><section>
<title>加密</title><content><table border="1"><thead><tr><TD><para>设置</para></TD><TD><para>详细信息</para></TD><TD><para>Windows Phone 8</para></TD><TD><para>Windows Phone 8.1</para></TD></tr></thead><tbody><tr><TD><para><ui>存储卡加密</ui></para></TD><TD><para>要求对设备使用的任何存储卡进行加密。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>设备上的文件加密</ui></para></TD><TD><para>要求对移动设备上的文件进行加密。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>需要电子邮件签名</ui></para></TD><TD><para>发送电子邮件前需签名。</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>签名算法</ui></para></TD><TD><para>选择用来签名电子邮件的算法。</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>需要电子邮件加密</ui></para></TD><TD><para>发送电子邮件前需加密。</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>加密算法</ui></para></TD><TD><para>选择用来加密电子邮件的算法。</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr></tbody></table></content>
</section><section address="BKMK_WiFI">
    <title>无线通信</title>
    <content>
      <para/>
      <table>
        <thead>
          <tr>
            <TD>
              <para>设置名</para>
            </TD>
            <TD>
              <para>详细信息</para>
            </TD><TD><para>Windows Phone 8</para></TD><TD><para>Windows Phone 8.1</para></TD>
            
            
            
            
            
            
            
            
          </tr>
        </thead>
        <tbody>
          <tr>
            <TD>
              <para>
                <ui>无线网络连接</ui>
                
              </para>
            </TD>
            <TD>
              <para>启用或禁用设备的 Wi-fi 功能。</para>
            </TD><TD><para>是</para></TD><TD><para>是</para></TD>
            
            
            
            
            
            
            
            
          </tr>
          <tr>
            <TD>
              <para>
                <ui>Wi-Fi Tethering</ui>
                
              </para>
            </TD>
            <TD>
              <para>使用户可以将自己的设备用作移动热点。</para>
            </TD><TD><para>是</para></TD><TD><para>是</para></TD>
            
            
            
            
            
            
            
            
          </tr>
          <tr>
            <TD>
              <para>
                <ui>可能时，将数据卸载到 Wi-fi</ui>
                
              </para>
            </TD>
            <TD>
              <para/>
            </TD><TD><para>是</para></TD><TD><para>是</para></TD>
            
            
            
            
            
            
            
            
          </tr>
          <tr>
            <TD>
              <para>
                <ui>Wi-Fi 热点报告</ui>
                
              </para>
            </TD>
            <TD>
              <para/>
            </TD><TD><para>是</para></TD><TD><para>是</para></TD>
            
            
            
            
            
            
            
            
          </tr>
        </tbody>
      </table>
      
      <procedure>
        <title>配置无线网络连接</title>
        <steps class="ordered">
          <step>
            <content>
              <para>在“配置移动设备无线通信设置”页上，单击“添加”。</para>
            </content>
          </step>
          <step>
            <content>
              <para>在“无线网络连接”对话框中，指定以下有关将在移动设备上预配的无线连接的信息：<ui></ui><ui></ui><ui></ui></para>
              <table>
                <thead>
                  <tr>
                    <TD>
                      <para>设置</para>
                    </TD>
                    <TD>
                      <para>更多信息</para>
                    </TD>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <TD>
                      <para>
                        <ui>网络名称 (SSID)</ui>
                      </para>
                    </TD>
                    <TD>
                      <para/>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>网络连接</ui>
                      </para>
                    </TD>
                    <TD>
                      <para/>
                      <para>从“Internet”<ui></ui>或“工作”<ui></ui>中选择。</para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>身份验证</ui>
                      </para>
                    </TD>
                    <TD>
                      <para>从以下各项选择无线连接的身份验证方法：</para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <ui>打开</ui>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <ui>共享</ui>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <ui>WPA</ui>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <ui>WPA-PSK</ui>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <ui>WPA2</ui>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <ui>WPA2-PSK</ui>
                          </para>
                        </listItem>
                      </list>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>数据加密</ui>
                      </para>
                    </TD>
                    <TD>
                      <para>选择此连接使用的加密方法。 根据所选的“身份验证”<ui></ui>方法，可选取的值将有所不同：</para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <ui>禁用</ui>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <ui>WEP</ui>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <ui>TKIP</ui>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <ui>AES</ui>
                          </para>
                        </listItem>
                      </list>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>密钥索引</ui>
                      </para>
                    </TD>
                    <TD>
                      <para>选择“1”到“4”的将与“WEP”的“数据加密”设置一起使用的密钥索引<ui></ui><ui></ui><ui></ui><ui></ui>。</para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>此网络连接到 Internet</ui>
                      </para>
                    </TD>
                    <TD>
                      <para>如果要提供使通过无线连接的移动设备连接到 Internet 的代理设置，请选择此选项。</para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>代理服务器设置</ui>
                      </para>
                    </TD>
                    <TD>
                      <para>根据需要为“HTTP”、“WAP”和“套接字”指定“服务器”和“端口”设置。<ui></ui><ui></ui><ui></ui><ui></ui><ui></ui></para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>启用 802.1X 网络访问</ui>
                      </para>
                    </TD>
                    <TD>
                      <para>如果要通过指定一种 EAP 类型来保护连接，请选择此选项。</para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>EAP 类型</ui>
                      </para>
                    </TD>
                    <TD>
                      <para>从以下各项选择要使用的 EAP 类型：</para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <ui>PEAP</ui>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <ui>智能卡或证书</ui>
                          </para>
                        </listItem>
                      </list>
                    </TD>
                  </tr>
                </tbody>
              </table>
            </content>
          </step>
          <step>
            <content>
              <para>完成后单击“确定”。<ui></ui></para>
            </content>
          </step>
        </steps>
      </procedure>
    </content>
  </section><section address="BKMK_Certs">
    <title>证书</title>
    <content>
      <para>使你能够导入证书以安装在移动设备上。</para>
      <para>单击“导入”，然后指定以下值：</para>
      <list class="bullet">
        <listItem>
          <para>
            <ui>证书文件</ui> – 单击“浏览”，然后选择要导入的扩展名为“.cer”的证书文件。</para>
        </listItem>
        <listItem>
          <para>
            <ui>目标存储区</ui> – 选择导入的证书将从其中被添加到移动设备上的一个或多个目标存储区：</para>
          <list class="bullet">
            <listItem>
              <para>
                <ui>根</ui>
              </para>
            </listItem>
            <listItem>
              <para>
                <ui>CA</ui>
              </para>
            </listItem>
            <listItem>
              <para>
                <ui>普通</ui>
              </para>
            </listItem>
            <listItem>
              <para>
                <ui>特权</ui>
              </para>
            </listItem>
            <listItem>
              <para>
                <ui>SPC</ui>
              </para>
            </listItem>
            <listItem>
              <para>
                <ui>对等</ui>
              </para>
            </listItem>
          </list>
        </listItem>
        <listItem>
          <para>
            <ui>角色</ui> – 如果将“SPC”（软件发行程序证书）选为目标存储区，则从以下选项中选择将与此证书相关联的角色：</para>
          <list class="bullet">
            <listItem>
              <para>
                <ui>移动运营商</ui>
              </para>
            </listItem>
            <listItem>
              <para>
                <ui>管理员</ui>
              </para>
            </listItem>
            <listItem>
              <para>
                <ui>通过身份验证的用户</ui>
              </para>
            </listItem>
            <listItem>
              <para>
                <ui>IT 管理员</ui>
              </para>
            </listItem>
            <listItem>
              <para>
                <ui>未通过身份验证的用户</ui>
              </para>
            </listItem>
            <listItem>
              <para>
                <ui>受信任的设置服务器<ui></ui><ui></ui><ui></ui><ui></ui></ui>
              </para>
            </listItem>
          </list>
        </listItem>
      </list>
    </content>
  </section><section>
<title>系统安全</title><content><table border="1"><thead><tr><TD><para>设置</para></TD><TD><para>详细信息</para></TD><TD><para>Windows Phone 8</para></TD><TD><para>Windows Phone 8.1</para></TD></tr></thead><tbody><tr><TD><para><ui>用户帐户控制</ui></para></TD><TD><para>启用或禁用设备上的 Windows 用户帐户控制。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>网络防火墙</ui></para></TD><TD><para>启用或禁用 Windows 防火墙。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>更新</ui></para></TD><TD><para>选择将 Windows 软件更新下载至计算机的方式。 例如，可以自动下载更新，但让用户选择何时进行安装。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>更新的最小分类</ui></para></TD><TD><para>选择要下载到 Windows 计算机的更新的最小分类：“无”、“重要”或“推荐”。<ui></ui><ui></ui><ui></ui>
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>SmartScreen</ui></para></TD><TD><para>启用或禁用 Windows 智能屏幕。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>病毒保护</ui></para></TD><TD><para>确保设备受防病毒软件保护</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr><tr><TD><para><ui>病毒保护签名为最新</ui></para></TD><TD><para>确保防病毒软件签名已是最新版本。</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr></tbody></table></content>
</section><section>
<title>Windows Server 工作文件夹</title><content><table border="1"><thead><tr><TD><para>设置</para></TD><TD><para>详细信息</para></TD><TD><para>Windows Phone 8</para></TD><TD><para>Windows Phone 8.1</para></TD></tr></thead><tbody><tr><TD><para><ui>工作文件夹 URL</ui></para></TD><TD><para>配置用户可从自己的设备连接的 Windows Server 工作文件夹的位置。
</para></TD><TD><para>是</para></TD><TD><para>是</para></TD></tr></tbody></table></content>
</section><section>
<title>Windows Phone 允许的和阻止的应用列表（仅限 Windows Phone 8.1）</title><content><para>使你能够指定公司中符合或不符合 Windows Phone 应用的列表。 用户无法安装你指定为阻止的应用。 如果指定允许的应用列表，则用户仅可安装此列表中的应用。</para><para>不能在同一配置项目中同时指定允许和阻止的应用。</para><alert class="important">
<para>如果指定允许的应用列表，则必须确保公司门户应用和已部署到 Windows Phone 8.1 设备的任何应用都在“允许的”应用列表中。<ui></ui>
</para>
</alert><procedure>
<title>指定允许的或阻止的应用列表</title>
 <steps class="ordered">
        <step><content><para>在“允许的和阻止的应用列表(Windows Phone 8.1)”页上，指定以下信息：</para><table border="1"><tbody><tr><TD><para>设置</para></TD><TD><para>更多信息</para></TD></tr><tr><TD><para><ui>阻止的应用列表</ui></para></TD><TD><para>如果想要指定不允许用户安装的应用的列表，则选择此选项。
</para></TD></tr><tr><TD><para><ui>允许的应用列表</ui></para></TD><TD><para>如果想要指定允许用户安装的应用的列表，则选择此选项。
</para></TD></tr><tr><TD><para><ui>添加</ui></para></TD><TD><para>将应用添加到选定的列表。 在应用商店中指定你选择的名称、（可选）应用发布者和应用的 URL。</para><para>若要从 Windows Phone 商店页面指定 URL，请搜索要使用的应用。</para><para><ui>示例：</ui>在应用商店中搜索“Skype”应用<ui></ui>。 你使用的 URL 将为 http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51。</para><alert class="note">
<para>对于公司门户应用或业务线应用，无需指定完整的 URL，只需指定应用 GUID 即可。
</para>
</alert></TD></tr><tr><TD><para><ui>编辑</ui></para></TD><TD><para>允许你编辑选定应用的名称、发布者和 URL。
</para></TD></tr><tr><TD><para><ui>移除</ui></para></TD><TD><para>从列表中删除选定的应用。
</para></TD></tr><tr><TD><para><ui>导入</ui></para></TD><TD><para>导入你已在逗号分隔值文件中指定的应用列表。 在文件中使用格式、应用程序名称、发布者和应用 URL。
</para></TD></tr></tbody></table></content></step>
        
      </steps>
</procedure></content>
</section></sections></section><relatedTopics><link xlink:href="5ab94b85-ac63-45b1-a4f6-17b0113920fd">不使用 Configuration Manager 客户端管理的设备配置项目</link></relatedTopics>
</developerConceptualDocument>

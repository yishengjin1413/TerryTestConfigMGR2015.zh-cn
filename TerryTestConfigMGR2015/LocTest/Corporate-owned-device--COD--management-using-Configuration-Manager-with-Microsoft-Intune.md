---
title: "使用 Configuration Manager 和 Microsoft Intune 管理企业拥有的设备 (COD)"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-hybrid
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: 2721c10a-b800-4f5c-a8a8-f9bceb21cfad
caps.latest.revision: 24
caps.handback.revision: 21
robots: noindex,nofollow
---
# 使用 Configuration Manager 和 Microsoft Intune 管理企业拥有的设备 (COD)
<?xml version="1.0" encoding="UTF-8"?>
<developerConceptualDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns:xlink="http://www.w3.org/1999/xlink">
    <introduction>
    <para>
你可以注册企业所有的 iOS 设备，以便它们可以由 <token>cm6long</token> 和 <token>mit_first</token> 进行管理。 Intune 支持注册企业所有的 iOS 设备，方法是使用 Apple 设备注册计划 (DEP)，或在 Mac 计算机上运行的 <externalLink><linkText>Apple Configurator</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=518017</linkUri></externalLink> 工具。 </para>
  <para></para>
    <para>可通过以下方式注册企业注册的 iOS 设备：</para>
    <list class="bullet">
      <listItem>
        <para>
          <externalLink><linkText>设备注册计划 (DEP) 注册</linkText><linkUri>https://technet.microsoft.com/library/mt629419.aspx#BKMK_DEPtok</linkUri></externalLink> – 以无线方式部署包括设备的设置助理选项的注册配置文件。 用户无法注销通过 DEP 注册的设备。</para>
      </listItem><listItem>
        <para>
          <externalLink><linkText>通过设置助理进行的 Apple Configurator 注册</linkText><linkUri>https://technet.microsoft.com/library/mt629419.aspx#BKMK_SAE</linkUri></externalLink> – 使用 Apple Configurator 对设备进行出厂重置、注册设备，并通过 USB 连接为其准备设置助理选项。</para>
      </listItem>
      
      
    </list><para>对企业所有的设备设置管理后，最终用户必须<externalLink><linkText>在 iOS 设备上完成设置</linkText><linkUri>https://technet.microsoft.com/library/mt629419.aspx#BKMK_iOSCP</linkUri></externalLink>。</para></introduction>
  
  
  
<section><title>适用于 iOS 设备的 Apple DEP 注册</title><content><para>要利用 Apple 设备注册计划 (DEP) 管理企业所有的 iOS 设备，公司必须完成 Apple 所要求的步骤以加入该计划并通过该计划获取设备。 该过程的详细信息，可以通过以下网站获得：<externalLink><linkText>https://deploy.apple.com</linkText><linkUri>https://deploy.apple.com</linkUri></externalLink>。 该程序的优点包括免手动设置设备，无需通过 USB 将每个设备连接到计算机。</para><para>在你可以通过 DEP 注册企业所有的 iOS 设备之前，你需要从 Apple 获得 DEP 令牌。 此令牌允许 <token>wit_nextref</token> 同步有关你的企业所拥有的且加入了 DEP 的设备的信息。 它还允许 <token>wit_nextref</token> 向 Apple 上传注册配置文件并将设备分配到这些配置文件。 </para><procedure address="BKMK_DEPtok" expanded="true"><title>使用 Intune 在 Configuration Manager 中启用 DEP 注册</title><steps class="ordered"><step><content><para><embeddedLabel>开始使用 Configuration Manager 管理 iOS 设备</embeddedLabel> <br/>在你能在设备上注册 iOS 设备注册计划 (DEP) 前，必须先完成<link xlink:href="5eae4400-58ca-4c71-804c-6a585cd3df5d">使用 System Center Configuration Manager 和 Microsoft Intune 设置混合 iOS 设备管理</link>的步骤。</para></content></step><step><content><para><embeddedLabel>创建 DEP 令牌请求</embeddedLabel> <br/>在 <token>cmshort</token> 控制台中的“管理”<ui></ui>工作区中，展开“层次结构配置”<ui></ui>，再展开“云服务”<ui></ui>，然后单击“Windows Intune 订阅”<ui></ui>。 单击“主页”<ui></ui>选项卡上的“创建 DEP 令牌请求”<ui></ui>，单击“浏览”<ui></ui>指定 DEP 令牌请求的下载位置，然后单击“下载”<ui></ui>。 将 DEP 令牌请求 (.pem) 文件保存到本地。 .pem 文件用于从 Apple 设备注册计划门户请求信任令牌 (.p7m)。</para></content></step><step><content><para><embeddedLabel>获取设备注册计划令牌</embeddedLabel> <br/>转到<externalLink><linkText>设备注册计划门户</linkText><linkUri>https://deploy.apple.com</linkUri></externalLink> (https://deploy.apple.com) 并使用你的公司 Apple ID 登录。 若要续订 DEP 令牌，必须在将来使用此 Apple ID。 </para><list class="ordered"><listItem><para>在<externalLink><linkText>设备注册计划门户</linkText><linkUri>https://deploy.apple.com</linkUri></externalLink> 中，转到“设备注册计划”<ui></ui>&gt;“管理服务器”<ui></ui>，然后单击“添加 MDM 服务器”<ui></ui>。</para></listItem><listItem><para>输入“MDM 服务器名称”<ui></ui>，然后单击“下一步”<ui></ui>。 服务器名称供参考，用于识别 MDM 服务器。 它不是 <token>wit_nextref</token> 或 <token>cmshort</token> 服务器的名称或 URL。</para></listItem><listItem><para>“添加服务器名称”<ui>&lt;&gt;</ui>对话框随即打开。 单击<ui>“选择文件...”</ui> 上传你在上一步中创建的.pem 文件，然后单击“下一步”<ui></ui>。</para></listItem><listItem><para><ui>添加&lt;“服务器名称”&gt;</ui>对话框会显示“你的服务器令牌”<ui></ui>链接。 将服务器令牌 (.p7m) 文件下载到计算机，然后单击“完成”<ui></ui>。</para></listItem></list><para>此证书 (.p7m) 文件用于建立 Intune 和 Apple 设备注册计划服务器之间的信任关系。</para></content></step><step><content><para><embeddedLabel>将 DEP 令牌添加到 Configuration Manager</embeddedLabel> <br/>在 <token>cmshort</token> 控制台的“管理”<ui></ui>工作区中，展开“层次结构配置”<ui></ui>，并单击“Windows Intune 订阅”<ui></ui>。 单击“主页”<ui></ui>选项卡上的“配置平台”<ui></ui>，然后单击“iOS”<ui></ui>。 选择“启用设备注册计划”<ui></ui>，浏览到证书 (.p7m) 文件，单击“打开”<ui></ui>，再单击“上传”<ui></ui>，然后单击“确定”<ui></ui>。 </para></content></step></steps></procedure><procedure>
<title>设置 Apple 设备注册计划 (DEP) iOS 设备的注册</title>
 <steps class="ordered">
        <maml:step xmlns:maml="http://ddue.schemas.microsoft.com/authoring/2003/5"><maml:content><maml:para><maml:embeddedLabel>添加企业设备注册策略</maml:embeddedLabel> <maml:br/>在 <maml:token>cmshort</maml:token> 控制台的“资产和合规性”<maml:ui></maml:ui>工作区中，依次展开“概述”<maml:ui></maml:ui>、“所有企业拥有的设备”<maml:ui></maml:ui>和“iOS”<maml:ui></maml:ui>，然后单击“注册配置文件”<maml:ui></maml:ui>。 单击“主页”<maml:ui></maml:ui>选项卡的“创建配置文件”<maml:ui></maml:ui>，打开创建配置文件向导。 在以下页面配置设置：</maml:para><maml:list class="ordered"><maml:listItem><maml:para>在“常规”<maml:ui></maml:ui>页上指定以下信息，然后单击“下一步”<maml:ui></maml:ui>。 </maml:para><maml:list class="bullet"><maml:listItem><maml:para><maml:ui>名称</maml:ui> - 设备注册配置文件的名称。 （对用户不可见）</maml:para></maml:listItem><maml:listItem><maml:para><maml:ui>说明</maml:ui> -设备注册配置文件的说明。 （对用户不可见）</maml:para></maml:listItem><maml:listItem><maml:para><maml:ui>用户关联</maml:ui> - 指定设备的注册方式。</maml:para><maml:list class="bullet"><maml:listItem><maml:para><maml:ui>用户关联提示</maml:ui>：必须在初始设置过程中将设备与用户相关联，然后允许该用户将其用于访问公司数据和电子邮件。  应该对属于用户且需要使用公司门户（即需要安装应用）的 DEP 托管设备配置用户关联。 请参阅<maml:externalLink><maml:linkText>注册具有用户关联的设备</maml:linkText><maml:linkUri>https://technet.microsoft.com/library/mt629419.aspx#BKMK_iOSCP</maml:linkUri></maml:externalLink>。</maml:para></maml:listItem><maml:listItem><maml:para><maml:ui>无用户关联</maml:ui>：该设备未与用户关联。 将此隶属关系用于无需访问本地用户数据即可执行任务的设备。 需要用户关联的应用无法运行。 请参阅<maml:externalLink><maml:linkText>无用户关联的设备。</maml:linkText><maml:linkUri>https://technet.microsoft.com/library/mt629419.aspx#BKMK_noUA</maml:linkUri></maml:externalLink></maml:para></maml:listItem></maml:list></maml:listItem></maml:list></maml:listItem><maml:listItem><maml:para>在“设备注册计划”<maml:ui></maml:ui>页上，指定以下信息，然后单击“下一步”<maml:ui></maml:ui>。</maml:para><maml:list class="bullet"><maml:listItem><maml:para><maml:ui>部门</maml:ui>：输入与此配置文件相关联的部门。</maml:para></maml:listItem><maml:listItem><maml:para><maml:ui>支持电话号码</maml:ui>：输入为此配置文件分配的电话号码。 </maml:para></maml:listItem><maml:listItem><maml:para><maml:ui>准备模式</maml:ui>：指定分配的设备处于监督模式下还是非监督模式下。</maml:para></maml:listItem><maml:listItem><maml:para><maml:ui>锁定设备上的注册配置文件</maml:ui>：选择是否要锁定所分配设备上的注册配置文件。 </maml:para></maml:listItem></maml:list></maml:listItem><maml:listItem><maml:para>在“设置助理”<maml:ui></maml:ui>页上，配置自定义第一次打开设备时启动的 iOS 设置助理的设置，然后单击“下一步”<maml:ui></maml:ui>。 这些设置包括：</maml:para><maml:list class="bullet"><maml:listItem><maml:para><maml:ui>密码</maml:ui></maml:para></maml:listItem><maml:listItem><maml:para><maml:ui>定位服务</maml:ui></maml:para></maml:listItem><maml:listItem><maml:para><maml:ui>还原</maml:ui></maml:para></maml:listItem><maml:listItem><maml:para><maml:ui>Apple ID</maml:ui></maml:para></maml:listItem><maml:listItem><maml:para><maml:ui>条款和条件</maml:ui></maml:para></maml:listItem><maml:listItem><maml:para><maml:ui>Siri</maml:ui></maml:para></maml:listItem><maml:listItem><maml:para><maml:ui>向 Apple 发送诊断数据</maml:ui></maml:para></maml:listItem></maml:list></maml:listItem><maml:listItem><maml:para>在“附加管理”<maml:ui></maml:ui>页上，指定设备注册过程中是否可以配置其他管理设置，然后完成向导。 当选择“需要证书”<maml:ui></maml:ui>时，必须导入 Apple Configurator 管理证书以供此配置文件使用。</maml:para></maml:listItem></maml:list></maml:content></maml:step>
        <step><content><para><embeddedLabel></embeddedLabel> <br/>转到<externalLink><linkText>设备注册计划门户</linkText><linkUri>https://deploy.apple.com</linkUri></externalLink> (https://deploy.apple.com) 并使用你的公司 Apple ID 登录。 转到“部署计划”<ui></ui>&gt;“设备注册计划”<ui></ui>&gt;“管理设备”<ui></ui>。 指定“选择设备”<ui></ui>的方式，提供设备信息，并按设备“序列号”<ui></ui>、“订单编号”<ui></ui>或“上传 CSV 文件”<ui></ui>指定详细信息。 接下来，选择“分配到服务器”<ui></ui>并选择在步骤 3 中指定的&lt;<placeholder>服务器名称</placeholder>&gt;，然后单击“确定”<ui></ui>。</para></content></step><step><content><para><embeddedLabel>同步 DEP 管理的设备</embeddedLabel> <br/>在“资产和符合性”<ui></ui>工作区中，转到“公司拥有的所有设备”<ui></ui>&gt;“iOS”<ui></ui>&gt;“设备信息”<ui></ui>。 在“主页”<ui></ui>选项卡上，单击“DEP 同步”<ui></ui>。 会向 Apple 发送同步请求。 同步完成后，将显示 DEP 管理的设备。 在打开设备并运行设置助理以注册设备之前，托管设备的“注册状态”<ui></ui>将一直显示为“未连接”<ui></ui>。</para></content></step><step><content><para><embeddedLabel>将设备分配给用户</embeddedLabel> <br/>现在可以将你的企业拥有的设备给予用户。 打开 iOS 设备时，它将注册为由 Intune 管理。</para></content></step>
      </steps>
</procedure></content></section><section expanded="true" address="BKMK_SAE">
    <title address="BKMK_SA">通过设置助理注册 Apple Configurator</title>
    <content>
      <para>可以使用 Apple Configurator 恢复 iOS 设备的出厂设置并做好准备，使新用户能够对设备进行设置。  此方法要求你通过 USB 将 iOS 设备连接到 Mac 计算机以设置企业注册，并且假定你使用的是 Apple Configurator 2.0。</para><para><embeddedLabel>先决条件</embeddedLabel></para><list class="bullet"><listItem><para> iOS 设备的物理访问</para></listItem><listItem><para>设备序列号 - <externalLink><linkText>如何获取 iOS 序列号</linkText><linkUri>https://support.apple.com/en-us/HT204308</linkUri></externalLink></para></listItem><listItem><para>USB 连接线</para></listItem><listItem><para>Mac 计算机与 <externalLink><linkText>Apple Configurator 2.0</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=518017</linkUri></externalLink></para></listItem></list><procedure>
        <title>使用 Configuration Manager 和 Intune 启用设置助理注册</title>
        <steps class="ordered">
          
          <step><content><para><embeddedLabel>添加企业设备注册配置文件</embeddedLabel> <br/>在 <token>cmshort</token> 控制台的“资产和符合性”<ui></ui>工作区中，依次展开“概述”<ui></ui>、“所有企业拥有的设备”<ui></ui>和“iOS”<ui></ui>，然后单击“注册配置文件”<ui></ui>。 单击“主页”<ui></ui>选项卡的“创建配置文件”<ui></ui>，打开创建配置文件向导。 在以下页面配置设置：</para><list class="ordered"><listItem><para>在“常规”<ui></ui>页上指定以下信息，然后单击“下一步”<ui></ui>。 </para><list class="bullet"><listItem><para><ui>名称</ui> - 设备注册配置文件的名称。 （对用户不可见）</para></listItem><listItem><para><ui>说明</ui> -设备注册配置文件的说明。 （对用户不可见）</para></listItem><listItem><para><ui>用户关联</ui> – 指定注册设备的方式。 对于大多数设置助理方案，使用<ui>用户关联提示</ui>。</para><list class="bullet"><listItem><para><ui>用户关联提示</ui>：必须在初始设置过程中将设备与用户相关联，然后允许该用户将其用于访问公司数据和电子邮件。 </para></listItem><listItem><para><ui>无用户关联</ui>：该设备不与用户关联。 将此隶属关系用于无需访问本地用户数据即可执行任务的设备。 需要用户关联的应用无法运行。</para></listItem></list></listItem></list></listItem><listItem><para>在“设备注册计划”<ui></ui>页上，保持“为此配置文件配置设备注册计划设置”<ui></ui>复选框为未选中状态，然后单击“下一步”<ui></ui>。</para></listItem><listItem><para>查看摘要，然后单击“net”。</para></listItem></list></content></step>
          <step>
            <content>
              <para>
                <embeddedLabel>添加 iOS 设备以便使用设置助理进行注册</embeddedLabel>
                <br/>在 <token>cmshort</token> 控制台的“资产和符合性”<ui></ui>工作区中，依次展开“概述”<ui></ui>、“所有企业拥有的设备”<ui></ui>和“iOS”<ui></ui>，然后单击“设备信息”<ui></ui>。 然后单击“添加设备”<ui></ui>。 你可以以两种方式添加设备：</para>
              <list class="bullet">
                <listItem>
                  <para>
                    <ui>上传包含序列号的 CSV 文件</ui> - 创建不带标头的两个列的逗号分隔值 (.csv) 列表，每个 csv 文件限 5000 台设备或 5MB。 </para>
                  <table>
                    <tbody>
                      <tr>
                        <TD>
                          <para>&lt;Serial #1&gt;</para>
                        </TD>
                        <TD>
                          <para>&lt;Device #1 Details&gt;</para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>&lt;Serial#2&gt;</para>
                        </TD>
                        <TD>
                          <para>&lt;Device #2 Details&gt;</para>
                        </TD>
                      </tr>
                    </tbody>
                  </table>
                  <para>在文本编辑器中查看该.csv 文件时，该文件显示为：</para>
                  <code>0000000,PO 1234
111111111,PO 1234</code>
                </listItem>
                <listItem>
                  <para>
                    <ui>手动添加序列号和详细信息</ui> -输入最多五台设备的序列号和设备详细信息</para>
                </listItem>
              </list>
              
              <para>然后单击“下一步”<ui></ui>。</para>
            </content>
          </step>
          <step>
            <content>
              <para>
                <embeddedLabel>选择要注册的设备</embeddedLabel>
                <br/>确认要注册的设备。 无法导入已注册或通过其他方式注册的序列号。 单击“下一步”<ui></ui>以继续。</para>
            </content>
          </step>
          <step>
            <content>
              <para>
                <embeddedLabel>分配配置文件</embeddedLabel>
                <br/>指定要从可用配置文件列表分配到已添加的设备的配置文件，查看“注册配置文件详细信息”<ui></ui>，然后单击“完成”<ui></ui>。 手动添加的设备可以分配给任何注册配置文件，但是 DEP 同步的设备必须分配给支持 DEP 的配置文件。</para>
            </content>
          </step>
          <step>
            <content>
              <para>
                <embeddedLabel>选择要部署到 iOS 设备的配置文件</embeddedLabel>
                <br/>在 <token>cmshort</token> 控制台的“资产和符合性”<ui></ui>工作区中，依次展开“概述”<ui></ui>、“公司拥有的所有设备”<ui></ui>和“iOS”<ui></ui>，单击“注册配置文件”<ui></ui>，然后选择要部署到移动设备的设备配置文件。 单击<ui>“导出...”</ui> （在任务栏中）。 复制并保存“配置文件 URL”<ui></ui>。 稍后你将在 Apple Configurator 中将其上传，以定义 iOS 设备使用的 Intune 配置文件。  注册配置文件 URL 自其导出之日起两周内有效。 两周后，必须导出新的 URL 文件以注册 iOS 设备。</para><para>要支持 Apple Configurator 2，必须编辑 2.0 配置文件 URL。 将 </para>
            <code>https://manage.microsoft.com/EnrollmentServer/Discovery.svc/iOS/ESProxy?id=
</code><para> 替换为：</para><code>https://appleconfigurator2.manage.microsoft.com/MDMServiceConfig?id=
</code></content>
          </step>
          <step>
            <content>
              <para>
                <embeddedLabel>使用 Apple Configurator 准备设备</embeddedLabel> <br/>iOS 设备已连接到 Mac 计算机并注册了移动设备管理。</para>
              <alert class="warning">
                <para>注册过程中，设备将重置为出厂配置。</para>
              </alert>
              <list class="ordered">
                <listItem>
                  <para>在 Mac 计算机上，打开“Apple Configurator 2”<ui></ui>。  在菜单栏中，单击“Apple Configurator 2”<ui></ui>，然后单击“首选项”<ui></ui>。</para>
                </listItem>
                <listItem>
                  <para>在“首选项”窗格中，选择“服务器”<ui></ui>，然后单击左窗格下方的“+”符号，以启动 MDM 服务器向导。 单击“下一步”<ui></ui>。</para>
                </listItem><listItem><para>输入上述步骤 5 中 MDM 服务器的“名称”<ui></ui>和“注册 URL”<ui></ui>。 单击“下一步”<ui></ui>。 </para><para>如果收到有关 Apple TV 的信任配置文件请求的警告，建议通过单击灰色的“X”安全取消“信任配置文件”<ui></ui>选项。 也可以安全忽略任何定位证书警告。 若要继续，请单击“下一步”<ui></ui>直到完成该向导。</para></listItem><listItem><para>在“服务器”<ui></ui>窗格中，单击位于新服务器配置文件旁的“编辑”。 确保注册 URL 与从 Intune 中导出的 URL 完全匹配。 如果不同，重新输入原始 URL 并“保存”<ui></ui>从 Intune 中导出的注册配置文件。</para></listItem><listItem>
                  <para>使用 USB 适配器将 iOS 移动设备连接到 Apple 计算机。 </para>
                <alert class="warning">
 <para>注册过程中，设备将重置为工厂配置。 最好重置设备，然后再启动。 最好在启动设置助理时，设备处于 Hello 屏幕。</para>
</alert></listItem>
                
                <listItem>
                  <para>单击“准备”<ui></ui>。 在“准备 iOS 设备”<ui></ui>窗格中，选择“手动”<ui></ui>，然后单击“下一步”<ui></ui>。</para>
                </listItem><listItem><para>在“在 MDM 服务器中注册”<ui></ui>窗格中，选择创建的服务器名称，然后单击“下一步”<ui></ui>。</para></listItem><listItem><para>在“在MDM 服务器中注册”<ui></ui>窗格中，选择创建的服务器名称，然后单击“下一步”<ui></ui>。</para></listItem><listItem><para>在“创建组织”<ui></ui>窗格中，选择“组织”<ui></ui>或“创建新组织”，然后单击“下一步”<ui></ui>。</para></listItem><listItem><para>在“配置 iOS 设置助理”<ui></ui>窗格中，选择向用户显示的步骤，然后单击“准备”<ui></ui>。 出现提示时，进行身份验证以更新信任设置。</para></listItem><listItem><para>iOS 设备准备完成后，即可断开 USB 连接线的连接。</para></listItem>
                
              </list>
            </content>
          </step>
          <step>
            <content>
              <para>
                <embeddedLabel>分发设备</embeddedLabel> <br/>设备现已准备好企业注册。 关闭设备电源，并将它们分发给用户。 启用设备后，设置助理将启动并提示用户输入其工作或学校帐户。 </para>
            </content>
          </step>
        </steps>
      </procedure>
    </content>
  </section><section address="BKMK_iOSCP">
<title>注册具有用户关联的企业拥有的 iOS 设备</title><content><para>配置了“用户关联”<ui></ui>的设备可以安装和运行公司门户应用，以下载应用和管理设备。 用户收到设备后，必须完成一些其他步骤，以便完成设置助理并安装公司门户应用。</para><procedure>
<title>如何注册具有用户关联的 iOS 设备</title>
 <steps class="ordered">
        <step><content><para>用户打开设备时，系统会提示他们完成设置助理。 安装过程中，系统会提示用户输入其凭据。 用户必须使用与其在 Intune 中的订阅相关的凭据（即唯一的个人名称或 UPN）。 </para></content></step>
        <step><content><para>安装过程中，系统会提示用户输入 Apple ID。 必须提供 Apple ID 才能允许设备安装公司门户。 也可以在设置完成后在 iOS 设置菜单中提供 Apple ID。</para></content></step><step>
 <content><para>完成后，iOS 设备必须安装 App Store 中的公司门户应用<externalLink><linkText>（例如公司门户应用）</linkText><linkUri>https://itunes.apple.com/cn/app/id719171358</linkUri></externalLink>。</para></content>
</step><step>
 <content><para>现在用户可以使用设置设备时使用的 UPN 登录公司门户。</para></content>
</step><step>
 <content><para>登录后，系统会提示用户注册其设备。 第一步是“识别其设备”<ui></ui>。 应用会提供一份已为企业拥有并已被分配到最终用户的 Intune 帐户的 iOS 设备列表。 选择匹配的设备。 </para><para>如果该设备还不是企业拥有的设备，选择“新设备”以继续标准注册流程。</para></content>
</step><step>
 <content><para>在下一个屏幕上，用户必须确认新设备的序列。 用户可以点击“确认序列号”链接以启动设置应用程序来验证序列号。 然后用户必须将序列号的最后 4 个字符输入到公司门户应用中。 </para><para>此步骤验证该设备是否是在 Intune 中注册的企业设备。 如果设备上的序列号不匹配，则选择了错误的设备。 返回到上一屏幕并选择其他设备。</para></content>
</step><step>
 <content><para>验证序列号后，公司门户应用将重定向到公司门户网站以完成注册，然后会提示用户返回到应用。 </para></content>
</step><step>
 <content><para>注册现已完成。 现在你可以使用此设备的完整功能集。</para></content>
</step>
      </steps>
</procedure></content>
<sections><section address="BKMK_noUA">
<title>有关无用户关联的企业拥有的受管理设备</title><content><para>配置为“无用户关联”<ui></ui>的设备不支持公司门户，并且不能安装应用。 公司门户适用于具有企业凭据的用户，并且需要访问个性化企业资源（例如邮件）的权限。 注册为“无用户关联”<ui></ui>的设备并不具有专用的用户登录。 展台、销售点 (POS) 或共享实用程序设备是注册为“无用户关联”的设备的典型用例。 如果需要用户关联，注册设备前请确保设备的注册配置文件选中“用户关联”<ui></ui>。 若要更改设备的关联状态，必须停用并重新注册设备。</para></content>
</section></sections></section><relatedTopics><link xlink:href="bb95154b-f63e-4491-896e-41d732c802f8">使用 System Center Configuration Manager 和 Microsoft Intune 管理移动设备</link></relatedTopics>
</developerConceptualDocument>

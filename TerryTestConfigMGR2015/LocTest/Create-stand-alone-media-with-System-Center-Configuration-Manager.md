---
title: "使用 System Center Configuration Manager 创建独立媒体"
ms.custom: na
ms.date: 09/02/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology: 
  - configmgr-osd
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - System Center Configuration Manager (current branch)
ms.assetid: c6b9ccd2-78d9-4f0e-b25a-70d0866300ba
caps.latest.revision: 21
caps.handback.revision: 18
translationtype: Human Translation
---
# 使用 System Center Configuration Manager 创建独立媒体
<?xml version="1.0" encoding="utf-8"?>
<developerWalkthroughDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd">
  <introduction>
    
    
    
    
    <para><token>cmshort</token> 中的独立媒体包含在未连接 <token>cmshort</token> 站点或未使用网络的计算机上部署操作系统所需的所有内容。 在以下操作系统部署方案使用独立媒体：</para><list class="bullet"><listItem><para><link xlink:href="b189a346-8c0d-4870-a876-0719fbb0ab04">通过 System Center Configuration Manager，使用新版本的 Windows 刷新现有的计算机</link></para></listItem><listItem><para><link xlink:href="f5ad22d5-7df1-49c6-8a0f-db1c3f0cda19">使用 System Center Configuration Manager 在新计算机（裸机）上安装新版本的 Windows</link></para></listItem><listItem><para><link xlink:href="c21eec87-ad1c-4465-8e45-5feb60b92707">使用 System Center Configuration Manager 将 Windows 升级到最新版本</link></para></listItem></list><para>独立媒体包含自动执行用于安装操作系统和所有其他所需内容的步骤的任务序列，这些内容包括启动映像、操作系统映像和设备驱动程序。 由于部署操作系统所需的所有内容均存储在独立媒体上，因此，独立媒体所需的磁盘空间将显著大于其他类型的媒体所需的磁盘空间。 在管理中心站点上创建独立媒体时，客户端会从 Active Directory 检索其分配的站点代码。 在子站点上创建的独立媒体会自动将该站点的站点代码分配给客户端。</para>
  
      
    </introduction>
  
  
  
  <section address="BKMK_CreateStandAloneMedia" expanded="true">
    <title>创建独立媒体</title>
    <content>
      <para>在使用“创建任务序列媒体”向导创建独立媒体之前，请确保满足以下条件：</para>
      
        
        <table><thead><tr><TD><para>任务</para></TD><TD><para>描述</para></TD></tr></thead>
<tbody><tr><TD><para>创建用于部署操作系统的任务序列</para></TD><TD><para>作为独立媒体的一部分，必须指定用于部署操作系统的任务序列。 有关创建新的任务序列步骤的信息，请参阅<link xlink:href="217c8a0e-5112-420e-a325-2a6d75326290">创建用于部署操作系统的任务序列</link>。</para><para>独立媒体不支持以下操作︰</para>
      <list class="bullet">
        <listItem>
          <para>任务序列中的“自动应用驱动程序”步骤。 不支持自动应用驱动程序目录的设备驱动程序，但可以选择“应用驱动程序包”步骤以使一组特定驱动程序可用于 Windows 安装程序。</para>
        </listItem>
        <listItem>
          <para>安装软件更新。</para>
        </listItem>
        <listItem>
          <para>在部署操作系统前安装软件。</para>
        </listItem>
        
        <listItem>
          <para>将用户与目标计算机关联以支持用户设备相关性。</para>
        </listItem>
        
        <listItem>
          <para>通过安装包任务安装动态包。</para>
        </listItem>
        <listItem>
          <para>通过安装应用程序任务安装动态应用程序。</para>
        </listItem>
      </list><alert class="note"><para>如果部署操作系统的任务序列包含<link xlink:href="7c888a6f-8e37-4be5-8edb-832b218f266d#BKMK_InstallPackage">安装包</link>步骤并在管理中心站点上创建独立媒体，则可能出现错误。 管理中心站点并没有在执行任务序列期间启用软件分发代理所需的必要客户端配置策略。 下列错误可能出现在 CreateTsMedia.log 文件中：</para>
          <para>
            <codeInline>“WMI method SMS_TaskSequencePackage.GetClientConfigPolicies failed (0x80041001)”</codeInline> </para>
          <para>对于包含“安装包”<ui></ui>步骤的独立媒体，必须在启用了软件分发代理的主站点上创建独立媒体，或者，必须在<link xlink:href="7c888a6f-8e37-4be5-8edb-832b218f266d#BKMK_SetupWindowsandConfigMgr">安装 Windows 和 ConfigMgr</link>步骤之后和任务序列中的第一个“安装包”<ui></ui>步骤之前添加一个<link xlink:href="7c888a6f-8e37-4be5-8edb-832b218f266d#BKMK_RunCommandLine">运行命令行</link>步骤。 “运行命令行”<ui></ui>步骤运行 WMIC 命令，以便在第一个安装包步骤运行之前启用软件分发代理。 可以在“运行命令行”<ui></ui>任务系列步骤中使用以下命令：</para>
          <para>
            <ui>Command Line</ui>: <userInput>WMIC /namespace:\\root\ccm\policy\machine\requestedconfig path ccm_SoftwareDistributionClientConfig CREATE ComponentName="Enable SWDist", Enabled="true", LockSettings="TRUE", PolicySource="local", PolicyVersion="1.0", SiteSettingsKey="1" /NOINTERACTIVE</userInput></para></alert>
          
        </TD></tr>
<tr><TD><para>分发与任务序列关联的所有内容</para></TD><TD><para>必须将任务序列所需的所有内容至少分发到一个分发点。 这包括启动映像、操作系统映像和其他相关联的文件。 向导在创建独立媒体时从分发点中收集信息。 必须具有对该分发点上的内容库的<embeddedLabel>读取</embeddedLabel>访问权限。  有关详细信息，请参阅<link xlink:href="a1f099f1-e9b5-4189-88b3-f53e3b4e4add#BKMK_DistributeTS">任务序列引用的分发内容</link>。 </para></TD></tr><tr><TD><para>准备可移动的 USB 驱动器</para></TD><TD><para>对于可移除的 USB 驱动器：</para><para>如果你要使用可移动的 USB 驱动器，该 USB 驱动器必须连接到运行向导的计算机，并且 USB 驱动器必须可被 Windows 检测为可移动设备。 向导将在创建媒体时直接写入 USB 驱动器。 独立媒体使用 FAT32 文件系统。 如果独立媒体的内容包含超过 4 GB 大小的文件，则无法在 USB 闪存驱动器上创建独立媒体。</para></TD></tr><tr><TD><para>创建一个输出文件夹</para></TD><TD><para>对于 CD/DVD 集：</para><para>在运行创建任务序列媒体向导以便为 CD 或 DVD 集创建媒体之前，必须为向导创建的输出文件创建一个文件夹。 为 CD 或 DVD 集创建的媒体将以 .iso 文件形式直接写入该文件夹。 </para></TD></tr>
</tbody></table>

<?xm-deletion_mark author="Doug Eby" time="20151027T131051-0800" data="&lt;maml:list class=&quot;bullet&quot; xmlns:maml=&quot;http://ddue.schemas.microsoft.com/authoring/2003/5&quot;&gt;
        
        
        &lt;maml:listItem&gt;
          
          &lt;maml:alert class=&quot;important&quot;&gt;
            &lt;maml:para&gt;To start USB flash drive media, you must manually run the TSMBAutorun.exe program located in the following folder: &lt;/maml:para&gt;
            
            &lt;maml:para&gt;
              &lt;maml:system&gt;\sms\bin\&amp;lt;architecture folder&amp;gt;\TSMBAutorun.exe&lt;/maml:system&gt;
            &lt;/maml:para&gt;
          &lt;/maml:alert&gt;
        &lt;/maml:listItem&gt;
        
      &lt;/maml:list&gt;"?>
      
      
      <para>使用以下过程来为可移除的 USB 驱动器或 CD/DVD 集创建独立媒体。</para>
      <procedure expanded="false">
        <title>创建独立媒体</title>
        <steps class="ordered">
          <step>
            <content>
              <para>在 <token>cmshort</token> 控制台中，单击“软件库”<ui></ui>。</para>
            </content>
          </step>
          <step>
            <content>
              <para>在“软件库”<ui></ui>工作区中，展开“操作系统”<ui></ui>，然后单击“任务序列”<ui></ui>。</para>
            </content>
          </step>
          <step>
            <content>
              <para>在“主页”<ui></ui>选项卡上，在“创建”<ui></ui>组中，单击“创建任务序列媒体”<ui></ui>以启动“创建任务序列媒体”向导。</para>
            </content>
          </step>
          <step>
            <content>
              <para>在“选择媒体类型”<ui></ui>页上，指定以下选项，然后单击“下一步”<ui></ui>。 </para>
              <list class="bullet">
                <listItem>
                  <para>选择“独立媒体”<ui></ui>。</para>
                </listItem>
                <listItem>
                  <para>（可选）如果你希望允许在不需要用户输入的情况下部署操作系统，则选择“允许无人参与的操作系统部署”<ui></ui>。 如果选择此选项，则不会提示用户输入网络配置信息或指定可选的任务序列。 但是，如果针对密码保护配置了媒体，则仍会提示用户输入密码。 </para>
                </listItem>
              </list>
            </content>
          </step>
          <step>
            <content>
              <para>在“媒体类型”<ui></ui>页上，指定媒体是 U 盘还是 CD/DVD 集，然后单击进行以下配置：</para>
              <alert class="important">
                <para>独立媒体使用 FAT32 文件系统。 如果独立媒体的内容包含超过 4 GB 大小的文件，则无法在 U 盘上创建独立媒体。</para>
              </alert>
              <list class="bullet">
                <listItem>
                  <para>如果你选择“U 盘”<ui></ui>，请指定要在其中存储内容的驱动器。</para>
                </listItem><listItem>
                  <para>如果你选择“CD/DVD 集”<ui></ui>，请指定媒体的容量及输出文件的名称和路径。 向导会将输出文件写入到此位置。 例如：<system>\\servername\folder\outputfile.iso</system></para>
                  <para>如果媒体的容量太小，无法存储整个内容，则会创建多个文件，从而必须将内容存储在多张 CD 或 DVD 上。 如果需要多个媒体，<token>cmshort</token> 会在创建的每个输出文件的名称中添加序号。 此外，如果将应用程序与操作系统一起部署，而单个媒体无法容纳应用程序，则 <token>cmshort</token> 会将应用程序存储到多个媒体中。 运行独立媒体时，<token>cmshort</token> 提示用户提供下一个存储应用程序的媒体。</para>
                  <alert class="important">
                    <para>如果你选择现有的 .iso 映像，“任务序列媒体”向导将在进入向导的下一页后立即从驱动器或共享中删除该映像。 即使随后取消该向导，也会删除现有映像。</para>
                  </alert>
                </listItem>
                
                
              </list>
            <para>单击“下一步”<ui></ui>。</para></content>
          </step>
          <step>
            <content>
              <para>在“安全”<ui></ui>页上，输入强密码来帮助保护媒体，然后单击“下一步”<ui></ui>。 如果指定密码，则必须提供密码才能使用媒体。</para>
              <alert class="important">
                <para>在独立媒体上，仅加密任务序列步骤及其变量。 不会加密媒体的其余内容，因此，请勿在任务序列脚本中包含任何敏感信息。 使用任务序列变量来存储和实施所有敏感信息。</para>
              </alert>
            </content>
          </step>
          <step>
            <content>
              <para>在“独立 CD/DVD”<ui></ui>页上，指定将部署操作系统的任务序列，然后单击“下一步”<ui></ui>。 向导允许你仅选择与启动映像关联的任务序列。</para>
            </content>
          </step>
          <step>
            <content>
              <para>在“分发点”<ui></ui>页上，指定包含任务序列所需的内容的分发点，然后单击“下一步”<ui></ui>。 </para><para><token>cmshort</token> 将仅显示具有内容的分发点。 必须先将与任务序列（启动映像、操作系统映像等）相关联的所有内容分发到至少一个分发点上，然后才能继续操作。 在分发内容后，可以重新启动向导或删除在此页上已选定的分发点，转到前一页，然后返回到“分发点”<ui></ui>页面以刷新分发点列表。 有关分发内容的详细信息，请参阅<link xlink:href="a1f099f1-e9b5-4189-88b3-f53e3b4e4add#BKMK_DistributeTS">任务序列引用的分发内容</link>。 有关分发点和内容管理的详细信息，请参阅<link xlink:href="ceff72f5-f19d-43a0-a8c0-72f1c09b9bf5">部署和管理内容管理基础结构</link>。</para>
              <alert class="note">
                
                <para>必须具有对分发点上内容库的<embeddedLabel>读取</embeddedLabel>访问权限。 </para>
              </alert>
            </content>
          </step>
          <step>
            <content>
              <para>在“自定义”<ui></ui>页上，指定以下信息，然后单击“下一步”<ui></ui>。 </para>
              <list class="bullet">
                <listItem>
                  <para>指定任务序列用于部署操作系统的变量。</para>
                </listItem>
                <listItem>
                  <para>指定你想要在任务序列之前运行的任何预启动命令。 预启动命令是一个脚本或可执行文件，它可以在任务序列运行以安装操作系统之前在 Windows PE 中与用户交互。 有关媒体的预启动命令的详细信息，请参阅<link xlink:href="ccc9f652-2953-4c38-8a90-c799484105ca">任务序列媒体的预启动命令</link>。</para>
                  <para>（可选）选择“预启动命令的文件”<ui></ui>以包括预启动命令所需的任何文件。</para>
                  <alert class="tip">
                    <para>在任务序列媒体创建过程中，任务序列将包 ID 和预启动命令行（包括任何任务序列变量的值）写入运行 <token>cmshort</token> 控制台的计算机上的 CreateTSMedia.log 日志文件中。 你可以查看此日志文件以验证任务序列变量的值。</para>
                  </alert>
                </listItem>
              </list>
            </content>
          </step>
          <step>
            <content>
              <para>完成此向导。 </para>
            </content>
          </step>
        </steps>
      <conclusion><content><para>在目标文件夹中创建独立媒体文件 (.iso)。 如果选择了“独立 CD/DVD”<ui></ui>，现在可以将输出文件复制到一组 CD 或 DVD。</para></content></conclusion></procedure>
    </content>
  </section>
  
  <section address="BKMK_StandAloneMediaTSExample" expanded="false">
    <title>独立媒体的任务序列示例</title>
    <content>
      <para>使用下表作为指导你使用独立媒体创建用于部署操作系统的任务序列。 该表将帮助您决定任务序列步骤的常规顺序，以及如何将这些任务序列步骤组织并构建成逻辑组。 你创建的任务序列可能与此示例有所不同并可以包含更多或较少的任务序列步骤和组。</para>
      <alert class="note">
        <para>必须使用任务序列媒体向导创建独立媒体。</para>
      </alert>
      <table>
        <thead>
          <tr>
            <TD colspan="1">
              <para>任务序列组或步骤</para>
            </TD>
            <TD colspan="1">
              <para>描述</para>
            </TD>
          </tr>
        </thead>
        <tbody>
          <tr>
            <TD colspan="1">
              <para>捕获文件和设置 - <ui>（新建任务序列组）</ui></para>
            </TD>
            <TD colspan="1">
              <para>创建任务序列组。 任务序列组将保留在一起以更好地组织和错误控制类似的任务序列步骤。</para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>捕获 Windows 设置</para>
            </TD>
            <TD colspan="1">
              <para>使用此任务序列步骤来确定目标计算机之前重置映像上现有的操作系统从捕获的 Microsoft Windows 设置。 您可以捕获计算机名称、 用户和组织信息和时区设置。</para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>捕获网络设置</para>
            </TD>
            <TD colspan="1">
              <para>使用此任务序列步骤来从接收任务序列的计算机捕获网络设置。 您可以捕获计算机和网络适配器的设置信息的域或工作组成员身份。</para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>捕获用户文件和设置 - <ui>（新建任务序列子组）</ui></para>
            </TD>
            <TD colspan="1">
              <para>创建任务序列组内的一个任务序列组。 此子组包含捕获用户状态数据从目标计算机之前重置映像上现有的操作系统所需的步骤。 类似于的初始组添加时，此子组操作可使类似的任务序列步骤一起为更好地组织和错误控制。</para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>设置本地状态位置</para>
            </TD>
            <TD colspan="1">
              <para>使用此任务序列步骤来指定使用受保护的路径任务序列变量的本地位置。 用户状态存储在硬盘驱动器上受保护的目录中。 </para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>捕获用户状态</para>
            </TD>
            <TD colspan="1">
              <para>使用此任务序列步骤以捕获用户文件和您想要迁移到新操作系统的设置。</para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>安装操作系统 - <ui>（新建任务序列组）</ui></para>
            </TD>
            <TD colspan="1">
              <para>创建另一个任务序列子组。 此子组包含安装操作系统所需的步骤。 </para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>重新启动到 Windows PE 或硬盘</para>
            </TD>
            <TD colspan="1">
              <para>使用此任务序列步骤来指定接收此任务序列的计算机的重新启动选项。 此步骤会向用户显示一则消息，消息指示将重新启动计算机以便继续安装。</para>
              <para>此步骤使用只读的“_SMSTSInWinPE”<ui></ui>任务序列变量。 如果关联值等于“false”<ui></ui>，该任务序列步骤将继续。</para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>应用操作系统</para>
            </TD>
            <TD colspan="1">
              <para>使用此任务序列步骤安装到目标计算机上的操作系统映像。 此步骤中删除该卷上的所有文件（除 <token>cmshort</token> -特定控制文件），然后将 WIM 文件中包含的所有卷映像应用到相应的顺序磁盘卷中。 你还可以指定“sysprep”<ui></ui>答案文件以配置要用于安装的磁盘分区。</para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>应用 Windows 设置</para>
            </TD>
            <TD colspan="1">
              <para>使用此任务序列步骤配置目标计算机的 Windows 设置配置信息。 可应用的 Windows 设置包括用户和组织信息、产品或许可密钥信息、时区，以及本地管理员密码。</para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>应用网络设置</para>
            </TD>
            <TD colspan="1">
              <para>使用此任务序列步骤来指定为目标计算机的网络或工作组配置信息。 此外可以指定计算机使用 DHCP 服务器是否可以静态地分配的 IP 地址信息。</para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>应用驱动程序包</para>
            </TD>
            <TD colspan="1">
              <para>使用此任务序列步骤以使驱动程序包中所有设备驱动程序可用于使用 Windows 安装程序。 所有必要的设备驱动程序必须包含在独立媒体中。</para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>安装操作系统 - <ui>（新建任务序列组）</ui></para>
            </TD>
            <TD colspan="1">
              <para>创建另一个任务序列子组。 此子组包含安装 <token>cmshort</token> 客户端所需的步骤。 </para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>安装 Windows 和 ConfigMgr</para>
            </TD>
            <TD colspan="1">
              <para>使用此任务序列步骤来安装 <token>cmshort</token> 客户端软件。 <token>cmshort</token> 安装并注册 <token>cmshort</token> 客户端 GUID。 你可以分配“安装属性”<ui></ui>窗口中的必要的安装参数。</para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>还原用户文件和设置 - <ui>（新建任务序列组）</ui></para>
            </TD>
            <TD colspan="1">
              <para>创建另一个任务序列子组。 此子组包含还原用户状态所需的步骤。 </para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>还原用户状态</para>
            </TD>
            <TD colspan="1">
              <para>
使用此任务序列步骤来启动用户状态迁移工具 (USMT) 到目标计算机捕获用户状态操作从还原用户状态和已捕获的设置。 </para>
            </TD>
          </tr>
        </tbody>
      </table>
    </content>
  </section><relatedTopics>
    
  <link xlink:href="a1f099f1-e9b5-4189-88b3-f53e3b4e4add">管理任务序列来自动执行任务</link></relatedTopics>
</developerWalkthroughDocument>

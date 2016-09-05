---
title: "使用修补程序安装程序来安装 System Center Configuration Manager 的更新"
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
ms.assetid: f3058277-c597-4dac-86d1-41b6f7e62b36
caps.latest.revision: 9
caps.handback.revision: 7
---
# 使用修补程序安装程序来安装 System Center Configuration Manager 的更新
<?xml version="1.0" encoding="UTF-8"?>
<developerConceptualDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xlink="http://www.w3.org/1999/xlink" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd">
    <introduction>
        <para><token>cm6long</token> 的某些更新无法从 Microsoft 云服务获取，只能在带外获取。 用于解决特定问题的受限版本修补程序是一个示例。 必须安装从 Microsoft 接收的更新（或修补程序），并且该更新的文件名是以 <embeddedLabel>.exe</embeddedLabel> 扩展名（而非 <embeddedLabel>update.exe</embeddedLabel>）结尾时，可使用该修补程序下载所随附的修补程序安装程序将更新直接安装到 <token>cmshort</token> 站点服务器。 
</para><para>如果修补程序文件有 <embeddedLabel>.update.exe</embeddedLabel> 文件扩展名，请参阅<link xlink:href="8cc13635-85d6-4b07-a3ec-c42188bc5c74">使用更新注册工具将修补程序导入 System Center Configuration Manager</link>。</para>
    <alert class="note">
      <para>本主题提供有关如何安装更新 <token>cm6long</token> 的修补程序的常规指南。 有关特定更新的详细信息，请参阅 Microsoft 支持上该更新的相应知识库 (KB) 文章。</para>
    </alert></introduction>
    <section address="bkmk_Overview">
        <title>用于 Configuration Manager 的修补程序的概述</title>
        <content>
            <para>用于 <token>cmshort</token> 的修补程序与其他 Microsoft 产品（如 SQL Server）类似，包含一个单独的修补程序或程序包（汇总的修补程序），并且 Microsoft 知识库文章对其进行了说明。</para><para>单独的更新包含针对特定版本 <token>cmshort</token> 的单个集中更新。
更新捆绑包含针对特定版本 <token>cmshort</token> 的多个更新。
不能从更新捆绑中安装单独更新。

</para><para>如果你计划创建部署以在其他计算机上安装更新，则必须在管理中心站点服务器或主站点服务器上安装更新捆绑。</para><para>运行更新捆绑时将发生以下事件：</para><list class="bullet"><listItem><para>它从更新捆绑中提取每个适用组件的更新文件。
</para></listItem><listItem><para>启动向导，指导你完成配置更新和更新部署选项的过程。
</para></listItem><listItem><para>完成该向导后，在站点服务器上安装捆绑中适用于该站点服务器的更新。
</para></listItem></list><para>向导也会创建部署，你可以使用这些部署在其他计算机上安装更新。 你可以使用诸如软件部署包或 Microsoft System Center Updates Publisher 2011 之类受支持的部署方法将更新部署到其他计算机。
</para><para>运行向导时，会在站点服务器上创建一个要与 Updates Publisher 2011 一起使用的 <embeddedLabel>.cab</embeddedLabel> 文件。 （可选）你可以将向导配置为创建一个或多个软件部署包。 你可以使用这些部署在客户端或 <token>cmshort</token> 控制台等组件上安装更新。 也可以在未运行 <token>cmshort</token> 客户端的计算机上手动安装更新。
</para><para>可以更新 <token>cmshort</token> 中的以下三个组：</para>
      <list class="bullet">
        <listItem>
          <para>
            <token>cmshort</token> 服务器角色，其中包括：</para>
          <list class="bullet">
            <listItem>
              <para>管理中心站点</para>
            </listItem>
            <listItem>
              <para>主站点</para>
            </listItem>
            <listItem>
              <para>辅助站点</para>
            </listItem>
            <listItem>
              <para>远程 SMS 提供程序</para>
            </listItem>
          </list>
          
        </listItem>
        <listItem>
          <para>
            <token>cmshort</token> 控制台</para>
        </listItem>
        <listItem>
          <para>
            <token>cmshort</token> 客户端</para>
        </listItem>
      </list><alert class="note">
            <para><embeddedLabel>站点系统角色更新</embeddedLabel>（包括站点数据库和基于云的分发点的更新）作为站点服务器和服务更新的一部分由站点组件管理器安装。</para>
            <para>但是，更新拉取分发点是由分发管理器而非站点组件管理器维护的。</para>
          </alert><para><br/><token>cmshort</token> 的每个更新捆绑都是可自提取的 .exe 文件 (SFX)，其中包含在 <token>cmshort</token> 的适用组件上安装更新所需的文件。 通常，SFX 文件可能包含下列文件：</para>
        <table border="1"><tbody><tr><TH><para>文件</para></TH><TH><para>详细信息</para></TH></tr><tr><TD><para>&lt;Product version&gt;-QFE-KB&lt;KB article ID&gt;-&lt;platform&gt;-&lt;language&gt;.exe</para></TD><TD><para>这是更新文件。 此文件的命令行由 Updatesetup.exe 进行管理。
</para><para>例如：CM1511RTM-QFE-KB123456-X64-ENU.exe
</para></TD></tr><tr><TD><para>Updatesetup.exe </para></TD><TD><para>此 .msi 包装管理更新捆绑的安装。
</para><para>运行更新时，Updatesetup.exe 会检测运行它的计算机的显示语言。 默认情况下，此更新的用户界面是英文。 但是，如果支持显示语言，则会以计算机的本地语言显示用户界面。
</para></TD></tr><tr><TD><para>License_&lt;language&gt;.rtf </para></TD><TD><para>如果适用，每个更新都会包含支持语言的一个或多个许可证文件。</para></TD></tr><tr><TD><para>&lt;Product&amp;updatetype&gt;-&lt;product version&gt;-&lt;KB article ID&gt;-&lt;platform&gt;.msp</para></TD><TD><para>如果更新适用于 <token>cmshort</token> 控制台或客户端，则更新捆绑会包括单独的 Windows Installer 修补 (.msp) 文件。
</para><para>例如：</para><para><embeddedLabel>Configuration Manager 控制台更新：</embeddedLabel>ConfigMgr1511 AdminUI KB1234567 i386.msp </para><para><embeddedLabel>客户端更新：</embeddedLabel>ConfigMgr1511-client-KB1234567-i386.msp ConfigMgr1511-client-KB1234567-x64.msp
</para></TD></tr></tbody></table><para>默认情况下，更新捆绑会将其操作记录到站点服务器上的 .log 文件中。 此日志文件与更新捆绑同名，并且会写入到 <system>%SystemRoot%/Temp</system> 文件夹中。
</para><para>运行更新捆绑时，会将与更新捆绑同名的文件提取到计算机上的临时文件夹中，然后运行 Updatesetup.exe。 Updatesetup.exe 会为 <token>cmshort</token> &lt;product version&gt; &lt;KB Number&gt; 向导启动软件更新。
</para><para>在适用的更新范围内，此向导会在站点服务器上的 <token>cm6long</token> 安装文件夹下创建一系列文件夹。 文件夹结构如下所示：<embeddedLabel>\\&lt;Server Name&gt;\SMS_&lt;Site Code&gt;\Hotfix\&lt;KB Number&gt;\&lt;Update Type&gt;\&lt;Platform&gt;</embeddedLabel>。
</para><para>下表提供了有关文件夹结构中的各个文件夹的详细信息：</para><table>
        <thead>
          <tr>
            <TD>
              <para>文件夹名称</para>
            </TD>
            <TD>
              <para>更多信息</para>
            </TD>
          </tr>
        </thead>
        <tbody>
          <tr>
            <TD>
              <para>&lt;服务器名称&gt;</para>
            </TD>
            <TD>
              <para>这是在其中运行更新捆绑的站点服务器的名称。</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>SMS_&lt;站点代码&gt;</para>
            </TD>
            <TD>
              <para>这是 <token>cmshort</token> 安装文件夹的共享名称。</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>&lt;KB 编号&gt;</para>
            </TD>
            <TD>
              <para>这是此更新捆绑的知识库文章的 ID 编号。</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>&lt;更新类型&gt;</para>
            </TD>
            <TD>
              <para>这些是 <token>cmshort</token> 的更新的类型。 向导会为更新捆绑中包含的每种更新类型创建一个单独的文件夹。 文件夹名称表示更新类型。 其中包括：</para>
              <para>
                    <embeddedLabel>服务器</embeddedLabel>：包括对站点服务器、站点数据库服务器和运行 SMS 提供程序的计算机的更新。</para><para>
                    <embeddedLabel>客户端</embeddedLabel>：包括对 <token>cmshort</token> 客户端的更新。</para><para>
                    <system>AdminConsole</system>：包括对 <token>cmshort</token> 控制台的更新</para>
              
              
              <para>除了上述更新类型外，该向导将创建名为 <system>SCUP</system> 的文件夹。 此文件夹并不表示更新类型，而是包含更新发布服务器的 .cab 文件。</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>&lt;平台&gt;</para>
            </TD>
            <TD>
              <para>这是特定于平台的文件夹。 它包含特定于处理器类型的更新文件。  这些文件夹包括：</para>
              <para>x64</para><para>I386</para>
            </TD>
          </tr>
        </tbody>
      </table></content>
        
    </section>
    <section address="bkmk_Install">
<title>如何安装更新</title><content><para>要安装更新，必须首先在站点服务器上安装更新捆绑。 安装更新捆绑时，会为该更新启动安装向导。 此向导将执行以下操作：</para><list class="bullet"><listItem><para>提取更新文件</para></listItem><listItem><para>帮助你配置部署</para></listItem><listItem><para>在本地计算机的服务器组件上安装适用的更新</para></listItem></list><para>在站点服务器上安装更新捆绑之后，可以更新 <token>cmshort</token> 的其他组件。 下表描述了适用于这些不同组件的更新操作： </para><table>
        <thead>
          <tr>
            <TD>
              <para>组件</para>
            </TD>
            <TD>
              <para>说明</para>
            </TD>
          </tr>
        </thead>
        <tbody>
          <tr>
            <TD>
              <para>站点服务器 </para>
            </TD>
            <TD>
              <para>当你未选择直接在远程站点服务器上安装更新捆绑时将更新部署到该远程站点服务器。</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para> 站点数据库</para>
            </TD>
            <TD>
              <para>对于远程站点服务器，如果未直接在该远程站点服务器上安装更新捆绑，则将包括更新的服务器更新部署到站点数据库。 </para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>
                <token>cmshort</token> 控制台</para>
            </TD>
            <TD>
              <para>初次安装 <token>cmshort</token> 控制台后，可以在运行该控制台的每台计算机上为 <token>cmshort</token> 控制台安装更新。 你无法修改 <token>cmshort</token> 控制台安装文件以在初次安装控制台过程中应用更新。 </para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>远程 SMS 提供程序</para>
            </TD>
            <TD>
              <para>为安装更新捆绑所在的非站点服务器计算机上运行的每个 SMS 提供程序实例安装更新。 </para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>
                <token>cmshort</token> 客户端 </para>
            </TD>
            <TD>
              <para>初次安装 <token>cmshort</token> 客户端后，可以在运行该客户端的每台计算机上为 <token>cmshort</token> 客户端安装更新。 </para>
            </TD>
          </tr>
        </tbody>
      </table>
      <alert class="note">
        <para>你可以只对运行 <token>cmshort</token> 客户端的计算机部署更新。</para>
      </alert>
      <para>如果重新安装客户端、<token>cmshort</token> 控制台或 SMS 提供程序，还必须重新安装这些组件的更新。 </para>
      <para>使用下列部分中的信息在 <token>cmshort</token> 的每个组件上安装更新。</para>
    </content>
<sections><section address="bkmk_servers">
<title>更新服务器</title><content><para>服务器更新可能包括对<embeddedLabel>站点</embeddedLabel>、<embeddedLabel>站点数据库</embeddedLabel>和运行 <embeddedLabel>SMS 提供程序</embeddedLabel>的实例的计算机的更新：</para></content>
<sections><section address="bkmk_site" expanded="false">
<title>更新站点</title>
<content><para>要更新 <token>cmshort</token> 站点，可以直接在站点服务器上安装更新捆绑，或者可以在其他站点上安装更新捆绑后将更新部署到站点服务器。
</para><para>在站点服务器上安装更新时，更新安装进程会管理应用更新所需的其他操作，如更新站点系统角色。 此情况的例外是站点数据库。 以下部分包含有关如何更新站点数据库的信息。 
</para></content></section><section address="bkmk_database" expanded="false">
<title>更新站点数据库</title><content>
              <para>要更新站点数据库，安装进程会在站点数据库上运行名为“update.sql”<ui></ui>的文件。 你可以将更新进程配置为自动更新站点数据库，或者可以以后手动更新站点数据库。 </para>
              <para>
                <embeddedLabel>站点数据库自动更新</embeddedLabel>
              </para>
              <para>在站点服务器上安装更新捆绑时，可以选择在安装服务器更新时自动更新站点数据库。 此决策仅适用于安装了更新捆绑的站点服务器，不适用于为在远程站点服务器上安装更新而创建的部署。</para>
              <alert class="note">
                <para>选择自动更新站点数据库时，进程会更新数据库，而不考虑数据库是位于站点服务器上还是位于远程计算机上。</para>
              </alert>
              <alert class="important">
                <para>在更新站点数据库之前，请创建站点数据库的备份。 你不能卸载站点数据库的更新。 有关如何创建 <token>cmshort</token> 的备份的信息，请参阅 <link xlink:href="f7832d83-9ae2-4530-8a77-790e0845e12f">System Center Configuration Manager 的备份和恢复</link>。</para>
              </alert>
              <para>
                <embeddedLabel>站点数据库的手动更新</embeddedLabel>
              </para>
              <para>如果选择在站点服务器上安装更新捆绑时不自动更新站点数据库，则服务器更新不会在运行更新捆绑的站点服务器上修改数据库。 但是，使用为软件部署或该安装创建的包的部署将始终更新站点数据库。</para>
              <alert class="warning">
                <para>如果更新包括对站点服务器和站点数据库两者的更新，则在为站点服务器和站点数据库完成更新之前，此更新将不能正常运行。 对站点数据库应用更新之前，站点处于不受支持状态。</para>
              </alert>
              <para><embeddedLabel>手动更新站点数据库：</embeddedLabel></para>
              
              <list class="ordered">
                <listItem>
                  <para>在站点服务器上停止 SMS_SITE_COMPONENT_MANAGER 服务，然后停止 SMS_EXECUTIVE 服务。</para>
                </listItem>
                <listItem>
                  <para>关闭 <token>cmshort</token> 控制台。</para>
                </listItem>
                <listItem>
                  <para>对该站点数据库运行名为“update.sql”<ui></ui>的更新脚本。 有关如何运行脚本来更新 SQL Server 数据库的信息，请参阅用于站点数据库服务器的 SQL Server 版本的文档。</para>
                </listItem>
                <listItem>
                  <para>重启之前的步骤中停止的服务。</para>
                </listItem>
                
              <listItem><para>安装更新捆绑时，将 <ui>update.sql</ui> 提取到站点服务器上的以下位置：<system>\\&lt;Server Name&gt;\SMS_&lt;Site Code&gt;\Hotfix\&lt;KB Number&gt;\update.sql</system></para></listItem></list>
              
              
              
            </content>
</section><section address="bkmk_provider" expanded="false">
<title>更新运行 SMS 提供程序的计算机</title><content>
              <para>安装包含 SMS 提供程序更新的更新捆绑之后，必须将更新部署到运行 SMS 提供程序的每台计算机。 唯一的例外是，你安装此更新捆绑的站点服务器上以前安装的 SMS 提供程序实例。 安装更新捆绑时，会更新站点服务器上的 SMS 提供程序的本地实例。</para>
              <para>如果删除计算机上的 SMS 提供程序，然后重新安装它，则必须在该计算机上重新安装 SMS 提供程序的更新。</para>
            </content>
</section></sections></section><section address="BKMK_clients" expanded="true">
        <title>更新客户端</title>
        <content>
          <para>如果你安装的更新中包含 <token>cmshort</token> 客户端的更新，则需选择是在更新安装过程中自动升级客户端，还是以后手动升级客户端。 有关客户端自动升级的详细信息，请参阅<externalLink><linkText>如何升级 Windows 计算机的客户端</linkText><linkUri>https://technet.microsoft.com/library/mt627885.aspx</linkUri></externalLink>。</para><para>可以将更新与 Updates Publisher 或软件部署包一起部署，也可以选择在每个客户端上手动安装更新。 有关如何使用部署来安装更新的详细信息，请参阅本主题中的<link xlink:href="#BKMK_Deploy">为 Configuration Manager 部署更新</link>部分。</para>
          <alert class="important">
            <para>在安装客户端更新且更新捆绑包含服务器更新时，请务必也在客户端分配到的主站点上安装服务器更新。</para>
          </alert>
          <para>若要在每个 <token>cmshort</token> 客户端上手动安装客户端更新，必须运行 <embeddedLabel>Msiexec.exe</embeddedLabel> 并引用特定于平台的客户端更新 .msp 文件。</para>
          <para>例如，可以使用下面的命令行更新客户端。 此命令行在客户端计算机上运行 MSIEXEC，并且引用更新捆绑在站点服务器上提取的 .msp 文件：<userInput>msiexec.exe /p \\&lt;ServerName&gt;\SMS_&lt;SiteCode&gt;\Hotfix\&lt;KB Number&gt;\Client\&lt;Platform&gt;\&lt;msp&gt; /L*v &lt;logfile&gt;REINSTALLMODE=mous REINSTALL=ALL</userInput></para>
        </content>
      </section><section address="BKMK_console" expanded="true">
        <title>更新 Configuration Manager 控制台</title>
        <content>
          <para>若要更新 <token>cmshort</token> 控制台，必须在控制台安装完成后在运行控制台的计算机上安装更新。 </para>
          <alert class="important">
            <para>在安装 <token>cmshort</token> 控制台的更新，且更新捆绑包含服务器更新时，请务必也在和 <token>cmshort</token> 控制台一起使用的站点上安装服务器更新。</para>
          </alert>
          <para>如果更新的计算机运行 <token>cmshort</token> 客户端：</para><list class="bullet"><listItem><para>可以使用部署来安装更新。 有关如何使用部署来安装更新的详细信息，请参阅本主题中的 <link xlink:href="#BKMK_Deploy">为 Configuration Manager 部署更新</link>部分。</para></listItem><listItem><para>如果你是直接登录到客户端计算机，则可通过交互方式运行安装。</para></listItem><listItem><para>你可以在每台计算机上手动安装更新。 若要手动安装 <token>cmshort</token> 控制台更新，则在运行 <token>cmshort</token> 控制台的每台计算机上运行 Msiexec.exe，并且引用 <token>cmshort</token> 控制台更新 .msp 文件。 </para></listItem></list>
          
          <para>例如，可以使用下列命令行来更新 <token>cmshort</token> 控制台。 此命令行在计算机上运行 MSIEXEC，并且引用更新捆绑在站点服务器上提取的 .msp 文件：<userInput>msiexec.exe /p \\&lt;ServerName&gt;\SMS_&lt;SiteCode&gt;\Hotfix\&lt;KB Number&gt;\AdminConsole\&lt;Platform&gt;\&lt;msp&gt; /L*v &lt;logfile&gt;REINSTALLMODE=mous REINSTALL=ALL</userInput></para>
        </content>
      </section></sections></section><section address="BKMK_Deploy" expanded="true">
    <title>部署 Configuration Manager 的更新</title>
    <content>
      <para>在站点服务器上安装更新捆绑后，可以通过以下三种方法之一将更新部署到其他计算机。 </para>
      
    </content>
    <sections>
      <section address="BKMK_DeploySCUP">
        <title>使用 Updates Publisher 2011 安装更新</title>
        <content>
          <para>在站点服务器上安装更新捆绑时，安装向导会为 Updates Publisher 创建一个目录文件，用于将更新部署到适用的计算机。 此向导始终会创建此目录，即使选择“使用包和程序来部署此更新”<ui></ui>选项，也是这样。</para>
          <para>Updates Publisher 的目录名为“SCUPCatalog.cab”<ui></ui>，其可在运行更新捆绑的计算机的以下位置找到：<system>\\&lt;ServerName&gt;\SMS_&lt;SiteCode&gt;\Hotfix\&lt;KB Number&gt;\SCUP\SCUPCatalog.cab</system></para>
          <alert class="important">
            <para>在创建 SCUPCatalog.cab 时，使用了安装更新捆绑的站点服务器的特定路径，因此无法在其他站点服务器上使用该文件。</para>
          </alert>
          <para><br/>在向导完成之后，可以将该目录导入到 Updates Publisher，然后使用 <token>cmshort</token> 软件更新来部署更新。 有关 Updates Publisher 的信息，请参阅 System Center 2012 的 TechNet 库中的 <externalLink><linkText>Updates Publisher 2011</linkText><linkUri>http://go.microsoft.com/fwlink/p/?LinkID=83449</linkUri></externalLink>。</para>
          <para>使用以下过程将 SCUPCatalog.cab 文件导入 Updates Publisher，然后发布更新。</para>
          <procedure expanded="false">
            <title>将更新导入 Updates Publisher 2011</title>
            <steps class="ordered">
              <step>
                <content>
                  <para>启动 Updates Publisher 控制台，然后单击“导入”<ui></ui>。</para>
                </content>
              </step>
              <step>
                <content>
                  <para>在“导入软件更新目录”向导的“导入类型”<ui></ui>页上，选择“指定要导入的目录路径”<ui></ui>，然后指定 SCUPCatalog.cab 文件。</para>
                </content>
              </step>
              <step>
                <content>
                  <para>单击“下一步”<ui></ui>，然后再次单击“下一步”<ui></ui>。</para>
                </content>
              </step>
              <step>
                <content>
                  <para>在“安全警告 - 目录验证”<ui></ui>对话框中，单击“接受”<ui></ui>。 完成后关闭向导。</para>
                </content>
              </step>
              <step>
                <content>
                  <para>在 Updates Publisher 控制台中，选择要部署的更新，然后单击“发布”<ui></ui>。</para>
                </content>
              </step>
              <step>
                <content>
                  <para>在“发布软件更新”向导的“发布选项”<ui></ui>页，选择“完整内容”<ui></ui>，然后单击“下一步”<ui></ui>。</para>
                </content>
              </step>
              <step>
                <content>
                  <para>完成向导以发布更新。</para>
                </content>
              </step>
            </steps>
            
          </procedure>
        </content>
      </section>
      <section address="BKMK_DeploySWDist">
        <title>使用软件部署来安装更新</title>
        <content>
          <para>在主站点或管理中心站点的站点服务器上安装更新捆绑时，可以配置安装向导以创建软件部署的更新包。 然后，可以将每个包部署到要更新的计算机集合中。</para>
          <para>若要创建软件部署包，在向导的“配置软件更新部署”<ui></ui>页上，选中要更新的每种更新包类型的复选框。 可用的类型可能包括服务器、<token>cmshort</token> 控制台和客户端。 为每种选择的更新类型创建一个单独的包。</para>
          <alert class="note">
            <para>服务器的包包含下列组件的更新：</para>
            <list class="bullet">
              <listItem>
                <para>站点服务器</para>
              </listItem>
              <listItem>
                <para>SMS 提供程序</para>
              </listItem>
              <listItem>
                <para>站点数据库</para>
              </listItem>
            </list>
          </alert>
          <para><br/>接下来，在向导的“配置软件更新部署方法”<ui></ui>页上，选择“我将使用软件分发”<ui></ui>选项。 此选项指示向导创建软件部署包。</para>
          
          <para>在向导完成之后，可以在 <token>cmshort</token> 控制台的“软件库”<ui></ui>工作区的“包”<ui></ui>节点中查看向导创建的包。 然后，可以按照标准过程将软件包部署到 <token>cmshort</token> 客户端。 在客户端运行包时，将更新安装到客户端计算机上 <token>cmshort</token> 的适用组件。</para>
          <para>有关如何将包部署到 <token>cmshort</token> 客户端的信息，请参阅 <link xlink:href="caad0507-9913-415a-b13d-d36f8f0a1b80">Configuration Manager 中的包和程序</link>。</para>
        </content>
      </section>
      <section address="BKMK_DeployCollections">
        <title>创建集合以将更新部署到 Configuration Manager</title>
        <content>
          <para>可以将特定的更新部署到适用的客户端。 下列信息可以帮助你为 <token>cmshort</token> 的不同组件创建设备集合。</para>
          <table>
            <thead>
              <tr>
                <TD>
                  <para><token>cmshort 的组件</token> </para>
                </TD>
                <TD>
                  <para>说明</para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>管理中心站点服务器</para>
                </TD>
                <TD>
                  <para>创建直接成员身份查询，并且添加管理中心站点服务器计算机。</para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>所有主站点服务器</para>
                </TD>
                <TD>
                  <para>创建直接成员身份查询，并且添加每台主站点服务器计算机。 </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>所有辅助站点服务器</para>
                </TD>
                <TD>
                  <para>创建直接成员身份查询，并且添加每台辅助站点服务器计算机。</para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>所有 x86 客户端</para>
                </TD>
                <TD>
                  <para>使用下列查询条件创建集合：</para>
                  <para>
                    <userInput>Select * from SMS_R_System inner join SMS_G_System_SYSTEM on SMS_G_System_SYSTEM.ResourceID = SMS_R_System.ResourceId where SMS_G_System_SYSTEM.SystemType = "X86-based PC"</userInput>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>所有 x64 客户端 </para>
                </TD>
                <TD>
                  <para>使用下列查询条件创建集合：</para>
                  <para>
                    <userInput>Select * from SMS_R_System inner join SMS_G_System_SYSTEM on SMS_G_System_SYSTEM.ResourceID = SMS_R_System.ResourceId where SMS_G_System_SYSTEM.SystemType = "X64-based PC"</userInput>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>所有运行 <token>cmshort</token> 控制台的计算机</para>
                </TD>
                <TD>
                  <para>创建直接成员身份查询，并且添加每台计算机。</para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>运行 SMS 提供程序实例的远程计算机</para>
                </TD>
                <TD>
                  <para>创建直接成员身份查询，并且添加每台计算机。 </para>
                </TD>
              </tr>
            </tbody>
          </table>
          <alert class="note">
            <para>若要更新站点数据库，请将更新部署到该站点的站点服务器。</para>
          </alert>
          <para><br/>有关如何创建集合的信息，请参阅<link xlink:href="1401a35e-4312-4d3b-8ceb-0abbb10d4f05">如何在 System Center Configuration Manager 中创建集合</link>。</para>
        </content>
      </section>
    </sections>
  </section><relatedTopics> <link xlink:href="8cc13635-85d6-4b07-a3ec-c42188bc5c74">使用更新注册工具将修补程序导入 System Center Configuration Manager</link><link xlink:href="3a832943-580a-4a40-b454-961d0854ac2b">安装 System Center Configuration Manager 的更新</link></relatedTopics>
</developerConceptualDocument>

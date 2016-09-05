---
title: "System Center Configuration Manager 中报告的操作和维护"
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
ms.assetid: b89bcfbf-f5b6-4fb1-bb5e-a5cc18ec0c78
caps.latest.revision: 5
caps.handback.revision: 4
---
# System Center Configuration Manager 中报告的操作和维护
<?xml version="1.0" encoding="utf-8"?>
<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  <caps:SxSTarget locale="zh-CN">
    <developerWalkthroughDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence sentenceid="8a8c21bed22e204d3aa332d3000071c0" id="tgt1" class="tgtSentence">为 <token>cm6long</token> 中的报表准备好基础结构后，你通常可以执行许多操作来管理报表和报表订阅。</caps:sentence>
        </para>
        <para>
          <caps:sentence sentenceid="94355e445f4858599211eea5d0f3d83f" id="tgt2" class="tgtSentence">使用本主题中的下列部分来帮助你管理 <token>cmshort</token> 层次结构中的报表和报表订阅操作：</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              <link xlink:href="#BKMK_ManageReports">Manage Configuration Manager Reports</link>
            </para>
            <list class="bullet">
              <listItem>
                <para>
                  <link xlink:href="#BKMK_RunReport">Run a Configuration Manager Report</link>
                </para>
              </listItem>
              <listItem>
                <para>
                  <link xlink:href="#BKMK_ModifyReportProperties">Modify the Properties for a Configuration Manager Report</link>
                </para>
              </listItem>
              <listItem>
                <para>
                  <link xlink:href="#BKMK_EditReport">Edit a Configuration Manager Report</link>
                </para>
              </listItem>
              <listItem>
                <para>
                  <link xlink:href="#BKMK_CreateModelBasedReport">Create a Model-Based Report</link>
                </para>
              </listItem>
              <listItem>
                <para>
                  <link xlink:href="#BKMK_CreateSQLBasedReport">Create a SQL-Based Report</link>
                </para>
              </listItem>
            </list>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="#BKMK_ManageReportSubscriptions">Manage Report Subscriptions</link>
            </para>
            <list class="bullet">
              <listItem>
                <para>
                  <link xlink:href="#BKMK_ReportSubscriptionFileShare">Create a Report Subscription to Deliver a Report to a File Share</link>
                </para>
              </listItem>
              <listItem>
                <para>
                  <link xlink:href="#BKMK_ReportSubscriptionEmail">Create a Report Subscription to Deliver a Report by Email</link>
                </para>
              </listItem>
            </list>
          </listItem>
        </list>
      </introduction>
      <section expanded="true" address="BKMK_ManageReports">
        <title>
          <caps:sentence sentenceid="c14f3d7af422022890220bd0693c18a9" id="tgt3" class="tgtSentence">管理 Configuration Manager 报表</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="d5aea4d7338b339b902a7219ad40eab7" id="tgt4" class="tgtSentence">
              <token>cmshort</token> 提供了超过 400 个预定义报表，可帮助你收集、组织和呈现有关用户、硬件和软件清单、软件更新、应用程序、站点状态以及组织中其他 <token>cmshort</token> 操作的信息。</caps:sentence>
            <caps:sentence sentenceid="37f27d17af2f2e33f8df16e62939b4c6" id="tgt5" class="tgtSentence"> 你可以按原样使用这些预定义报表，或者你可以修改报表来满足你的需求。</caps:sentence>
            <caps:sentence sentenceid="9556e5c59d9b85d69d342c1686bd1807" id="tgt6" class="tgtSentence"> 你也可以创建基于自定义模型和 SQL 的报表来满足你的需求。</caps:sentence>
            <caps:sentence sentenceid="a9da4458c959f58b6062af09881a4437" id="tgt7" class="tgtSentence"> 使用下列部分来帮助你管理 <token>cmshort</token> 报表。</caps:sentence>
          </para>
        </content>
        <sections>
          <section address="BKMK_RunReport" expanded="true">
            <title>
              <caps:sentence sentenceid="19a8af360312dd866fee3b59fb82d943" id="tgt8" class="tgtSentence">运行 Configuration Manager 报表</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="7adc2507a24b370dea6f91c0aed18bff" id="tgt9" class="tgtSentence">
                  <token>cmshort</token> 中的报表存储在 SQL Server Reporting Services 中，报表中呈现的数据是从 <token>cmshort</token> 站点数据库中检索的。</caps:sentence>
                <caps:sentence sentenceid="5d6f815cd751e4c7ae4b2bfe855cc6d3" id="tgt10" class="tgtSentence"> 你可以在 <token>cmshort</token> 控制台中或通过使用报表管理器（在 Web 浏览器中访问）访问报表。</caps:sentence>
                <caps:sentence sentenceid="b13909f35fc146476b0978e2baab8129" id="tgt11" class="tgtSentence"> 你可以在对运行 SQL Server Reporting Services 的计算机具有访问权限的任何计算机上打开报表，你必须具有足够的权限才能查看报表。</caps:sentence>
                <caps:sentence sentenceid="d365d48837c8e63ec7ab4dfcf097e207" id="tgt12" class="tgtSentence"> 在运行报表时，报表标题、描述和类别采用本地操作系统的语言显示。</caps:sentence>
              </para>
              <alert class="note">
                <para>
                  <caps:sentence sentenceid="b6a9c9da0a385ff1aee0929393233ea4" id="tgt13" class="tgtSentence">在某些非英语语言中，字符可能无法在报表中正确显示。</caps:sentence>
                  <caps:sentence sentenceid="15d166c90602d79e50fdcbe3fe2f1ae7" id="tgt14" class="tgtSentence">  在此情况下，可以使用基于 Web 的报表管理器或通过远程管理员控制台来查看报表。</caps:sentence>
                </para>
              </alert>
              <alert class="warning">
                <para>
                  <caps:sentence sentenceid="2c221cad0f2ad6f0a4586ae4dcb3898f" id="tgt15" class="tgtSentence">要运行报表，你必须对为特定对象配置的“站点”<ui></ui>许可和“运行报表”<ui></ui>许可具有“读取”<ui></ui>权限。</caps:sentence>
                </para>
              </alert>
              <alert class="note">
                <para>
                  <caps:sentence sentenceid="08703b1aff0542b18866dbddc2cf2977" id="tgt16" class="tgtSentence">报表管理器是一种基于 Web 的报表访问和管理工具，你可以使用该工具通过 HTTP 连接来管理远程位置上的单一报表服务器实例。</caps:sentence>
                  <caps:sentence sentenceid="a5dd251e8dd99202456c91cb353d939b" id="tgt17" class="tgtSentence"> 你可以使用报表管理器来执行操作任务，例如，查看报表、修改报表属性以及管理关联的报表订阅。</caps:sentence>
                  <caps:sentence sentenceid="7293bbc6a76f6f788e722236d2c8293f" id="tgt18" class="tgtSentence"> 本主题提供在报表管理器中查看报表和修改报表属性的步骤，但若要了解有关报表管理器提供的其他选项的详细信息，请参阅 SQL Server 2008 联机丛书中的<externalLink><linkText>报表管理器</linkText><linkUri>http://go.microsoft.com/fwlink/p/?LinkId=224916</linkUri></externalLink>。</caps:sentence>
                </para>
              </alert>
              <para>
                <caps:sentence sentenceid="97e98083c3f36742c70915429dd22184" id="tgt19" class="tgtSentence">使用以下过程来运行 <token>cmshort</token> 报表。</caps:sentence>
              </para>
              <procedure expanded="false">
                <title>
                  <caps:sentence sentenceid="1b3c1454149849e94929ee49861ba218" id="tgt20" class="tgtSentence">在 <token>cmshort</token> 控制台中运行报表</caps:sentence>
                </title>
                <steps class="ordered">
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="7d453f68b6a311b28873f5ba0a7e0fbe" id="tgt21" class="tgtSentence">在 <token>cmshort</token> 控制台中，单击“监视”<ui></ui>。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="5a5f548342562031cb42cd0d1973b681" id="tgt22" class="tgtSentence">在“监视”<ui></ui>工作区中，展开“报表”<ui></ui>，然后单击“报表”<ui></ui>以列出可用报表。</caps:sentence>
                      </para>
                      <alert class="important">
                        <para>
                          <caps:sentence sentenceid="75f6f314d777bfe54b0d892b580529b9" id="tgt23" class="tgtSentence">在此版本的 <token>cmshort</token> 中，“全部内容”<ui></ui>报表仅显示包，而不显示应用程序。</caps:sentence>
                        </para>
                      </alert>
                      <alert class="tip">
                        <para>
                          <caps:sentence sentenceid="aaf507cdcdfaa47f3b288025a45e11fb" id="tgt24" class="tgtSentence">如果没有列出报表，请验证是否安装和配置了 Reporting Services 点。</caps:sentence>
                          <caps:sentence sentenceid="558e83225b77b512ae4c5b6b76dd43ff" id="tgt25" class="tgtSentence"> 有关详细信息，请参阅 <link xlink:href="55ae86a7-f0ab-4c09-b4da-89cd0e7fa0e0">Configuring reporting in Configuration Manager</link>。</caps:sentence>
                        </para>
                      </alert>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="8ceda3068d8ca359c39215cdc317affd" id="tgt26" class="tgtSentence">选择要运行的报表，然后在“主页”<ui></ui>选项卡上的“报表组”<ui></ui>部分，单击“运行”<ui></ui>以打开报表。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="f9f5a11389eddb3126f2a4603ffac43d" id="tgt27" class="tgtSentence">如果有必需的参数，请指定这些参数，然后单击“查看报表”<ui></ui>。</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
              <procedure expanded="false">
                <title>
                  <caps:sentence sentenceid="1ba020c4c4db65517b9792774a3bbb6e" id="tgt28" class="tgtSentence">在 Web 浏览器中运行报表</caps:sentence>
                </title>
                <steps class="ordered">
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="429fea8c87f9888d11490f10ba3f479c" id="tgt29" class="tgtSentence">在 Web 浏览器中，输入报表管理器 URL，例如，<embeddedLabel>http://Server1/Reports</embeddedLabel>。</caps:sentence>
                        <caps:sentence sentenceid="9e5f7e3d466ca681359ace9d07630512" id="tgt30" class="tgtSentence"> 你可以确定 Reporting Services <token>cmshort</token> 中的“报表管理器 URL”<ui></ui>页上的报表管理器 URL。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="7cf28038cea232b95eb8225e75f24897" id="tgt31" class="tgtSentence">在报表管理器中，单击 <token>cmshort</token> 的报表文件夹，例如，<embeddedLabel>ConfigMgr_CAS</embeddedLabel>。</caps:sentence>
                      </para>
                      <alert class="tip">
                        <para>
                          <caps:sentence sentenceid="aaf507cdcdfaa47f3b288025a45e11fb" id="tgt32" class="tgtSentence">如果没有列出报表，请验证是否安装和配置了 Reporting Services 点。</caps:sentence>
                          <caps:sentence sentenceid="558e83225b77b512ae4c5b6b76dd43ff" id="tgt33" class="tgtSentence"> 有关详细信息，请参阅 <link xlink:href="55ae86a7-f0ab-4c09-b4da-89cd0e7fa0e0">Configuring reporting in Configuration Manager</link>。</caps:sentence>
                        </para>
                      </alert>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="8a544f286fed00e64d7504285b10f32a" id="tgt34" class="tgtSentence">单击要运行的报表的报表类别，然后单击报表的链接。</caps:sentence>
                        <caps:sentence sentenceid="bcb9f0b7b3b43f87d9d22087d9d5ce61" id="tgt35" class="tgtSentence"> 报表将在报表管理器中打开。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="f9f5a11389eddb3126f2a4603ffac43d" id="tgt36" class="tgtSentence">如果有必需的参数，请指定这些参数，然后单击“查看报表”<ui></ui>。</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
            </content>
          </section>
          <section address="BKMK_ModifyReportProperties" expanded="true">
            <title>
              <caps:sentence sentenceid="068be9162417a96d58356a6ad1a90a3b" id="tgt37" class="tgtSentence">修改 Configuration Manager 报表的属性</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="9e9c4b8011a8662f21cfaffa4e61fa28" id="tgt38" class="tgtSentence">在 <token>cmshort</token> 控制台中，你可以查看报表的属性（例如报表名称和描述），但若要更改属性，请使用报表管理器。</caps:sentence>
                <caps:sentence sentenceid="5c38bf7b46da7c82f1b336041095f83d" id="tgt39" class="tgtSentence"> 使用以下过程来修改 <token>cmshort</token> 报表的属性。</caps:sentence>
              </para>
              <procedure expanded="false">
                <title>
                  <caps:sentence sentenceid="927d4d04f0eaa930f15ad07919f39148" id="tgt40" class="tgtSentence">在报表管理器中修改报表属性</caps:sentence>
                </title>
                <steps class="ordered">
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="429fea8c87f9888d11490f10ba3f479c" id="tgt41" class="tgtSentence">在 Web 浏览器中，输入报表管理器 URL，例如，<embeddedLabel>http://Server1/Reports</embeddedLabel>。</caps:sentence>
                        <caps:sentence sentenceid="9e5f7e3d466ca681359ace9d07630512" id="tgt42" class="tgtSentence"> 你可以确定 Reporting Services <token>cmshort</token> 中的“报表管理器 URL”<ui></ui>页上的报表管理器 URL。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="7cf28038cea232b95eb8225e75f24897" id="tgt43" class="tgtSentence">在报表管理器中，单击 <token>cmshort</token> 的报表文件夹，例如，<embeddedLabel>ConfigMgr_CAS</embeddedLabel>。</caps:sentence>
                      </para>
                      <alert class="tip">
                        <para>
                          <caps:sentence sentenceid="aaf507cdcdfaa47f3b288025a45e11fb" id="tgt44" class="tgtSentence">如果没有列出报表，请验证是否安装和配置了 Reporting Services 点。</caps:sentence>
                          <caps:sentence sentenceid="1073ba37255861993eccdc9aed1b16a3" id="tgt45" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="55ae86a7-f0ab-4c09-b4da-89cd0e7fa0e0">Configuring reporting in Configuration Manager</link>。</caps:sentence>
                        </para>
                      </alert>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="1c5204963eef401ecce5c7f99ca29c76" id="tgt46" class="tgtSentence">单击要修改其属性的报表的报表类别，然后单击报表的链接。</caps:sentence>
                        <caps:sentence sentenceid="bcb9f0b7b3b43f87d9d22087d9d5ce61" id="tgt47" class="tgtSentence"> 报表将在报表管理器中打开。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="6b644430fdec5c02338ad7554e8cb2b4" id="tgt48" class="tgtSentence">单击“属性”<ui></ui>选项卡。</caps:sentence>
                        <caps:sentence sentenceid="73e5500ab907554bb75af11eaffee860" id="tgt49" class="tgtSentence"> 你可以修改报表名称和描述。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="a3c71d13f644d5fe75c3bb309d9c54eb" id="tgt50" class="tgtSentence">完成后，单击“应用”<ui></ui>。</caps:sentence>
                        <caps:sentence sentenceid="de9c60368bf7c62e2b8962db0d061cc9" id="tgt51" class="tgtSentence"> 报表属性保存在报表服务器上，<token>cmshort</token> 控制台将检索报表的更新报表属性。</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
            </content>
          </section>
          <section address="BKMK_EditReport" expanded="true">
            <title>
              <caps:sentence sentenceid="59bd27df527dea6b0b90c2971402eeee" id="tgt52" class="tgtSentence">编辑 Configuration Manager 报表</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="61f7af52630d04d120da3cb7bffe9c03" id="tgt53" class="tgtSentence">如果现有 <token>cmshort</token> 报表未检索你必须具有的信息或未提供所需的布局或设计，则你可以在报表生成器中编辑该报表。</caps:sentence>
              </para>
              <alert class="note">
                <para>
                  <caps:sentence sentenceid="82147e34c92d7ac403d78598f07d89e8" id="tgt54" class="tgtSentence">你也可以选择克隆现有报表，方式为：打开报表进行编辑，然后单击“另存为”<ui></ui>将其另存为新报表。</caps:sentence>
                </para>
              </alert>
              <alert class="security note">
                <para>
                  <caps:sentence sentenceid="fd10e5888bdfa8021c37db153c188c6f" id="tgt55" class="tgtSentence">对于与你要修改的报表关联的对象，用户帐户必须具有“站点修改”<ui></ui>权限和“修改报表”<ui></ui>权限。</caps:sentence>
                </para>
              </alert>
              <alert class="important">
                <para>
                  <caps:sentence sentenceid="722523c73f0ab332212cc9d3e9b2e30b" id="tgt56" class="tgtSentence">当 <token>cmshort</token> 升级到较新版本时，新报表将覆盖预定义的报表。</caps:sentence>
                  <caps:sentence sentenceid="afb7ef116f88eb323e475040912bda00" id="tgt57" class="tgtSentence"> 如果修改预定义报表，你必须在安装新版本之前备份报表，然后在 Reporting Services 中还原报表。</caps:sentence>
                  <caps:sentence sentenceid="1d026642c9785fbffd3421be1987dbf4" id="tgt58" class="tgtSentence"> 如果要对预定义报表进行大量更改，请考虑改为创建新报表。</caps:sentence>
                  <caps:sentence sentenceid="55e505aeb79314c9bcec90d05ba6a2b6" id="tgt59" class="tgtSentence"> 不会覆盖在升级站点之前创建的新报表。</caps:sentence>
                </para>
              </alert>
              <para>
                <caps:sentence sentenceid="ee530e3bb22a907f906fc884d63b17b2" id="tgt60" class="tgtSentence">使用以下过程来编辑 <token>cmshort</token> 报表的属性。</caps:sentence>
              </para>
              <procedure expanded="false">
                <title>
                  <caps:sentence sentenceid="9ca101515660afff75418a643c59c7db" id="tgt61" class="tgtSentence">编辑报表属性</caps:sentence>
                </title>
                <steps class="ordered">
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="7d453f68b6a311b28873f5ba0a7e0fbe" id="tgt62" class="tgtSentence">在 <token>cmshort</token> 控制台中，单击“监视”<ui></ui>。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="5a5f548342562031cb42cd0d1973b681" id="tgt63" class="tgtSentence">在“监视”<ui></ui>工作区中，展开“报表”<ui></ui>，然后单击“报表”<ui></ui>以列出可用报表。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="9dc21e5e9b1942364780b40ad377916c" id="tgt64" class="tgtSentence">选择要修改的报表，然后在“主页”<ui></ui>选项卡上的“报表组”<ui></ui>部分，单击“编辑”<ui></ui>。</caps:sentence>
                        <caps:sentence sentenceid="c7c1545451d2da0b1bdcb69dd2f4c649" id="tgt65" class="tgtSentence"> 如果出现提示，请输入你的用户帐户和密码，然后单击“确定”<ui></ui>。</caps:sentence>
                        <caps:sentence sentenceid="047c52667072b1876d8eb1bf21aaa3ec" id="tgt66" class="tgtSentence"> 如果计算机上未安装报表生成器，将会提示你进行安装。</caps:sentence>
                        <caps:sentence sentenceid="8ac2cba4642e7d9132448110c2ea4040" id="tgt67" class="tgtSentence"> 单击“运行”<ui></ui>安装修改和创建报表所需的报表生成器。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="b8de3419c4f4257854410980a3de91fb" id="tgt68" class="tgtSentence">在报表生成器中，修改相应的报表设置，然后单击“保存”<ui></ui>以将报表保存到报表服务器。</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
            </content>
          </section>
          <section address="BKMK_CreateModelBasedReport" expanded="true">
            <title>
              <caps:sentence sentenceid="3df0ced6d2f2d925580553c7fff22e44" id="tgt69" class="tgtSentence">创建基于模型的报表</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="4881917c551017e60e631d86e5dcd5e2" id="tgt70" class="tgtSentence">基于模型的报表使你能够以交互方式选择要包括在报表中的项目。</caps:sentence>
                <caps:sentence sentenceid="9ffe8f72d5860a060a56205196754c5d" id="tgt71" class="tgtSentence"> 有关创建自定义报表模型的详细信息，请参阅<link xlink:href="f2df88b4-c348-4dcf-854a-54fd6eedf485">Creating Custom Report Models in SQL Server Reporting Services</link>。</caps:sentence>
              </para>
              <alert class="security note">
                <para>
                  <caps:sentence sentenceid="b860380883e55e2e2311d29ccfb7e529" id="tgt72" class="tgtSentence">用户帐户必须具有“站点修改”<ui></ui>权限才能创建新报表。</caps:sentence>
                  <caps:sentence sentenceid="984c9235b01b4c90235648fca1242b81" id="tgt73" class="tgtSentence"> 用户只能在其具有“修改报表”<ui></ui>权限的文件夹中创建报表。</caps:sentence>
                </para>
              </alert>
              <para>
                <caps:sentence sentenceid="aa7dac25f1d63adb360ed86c694ac7bc" id="tgt74" class="tgtSentence">使用下列过程来创建基于模型的 <token>cmshort</token> 报表。</caps:sentence>
              </para>
              <procedure expanded="false">
                <title>
                  <caps:sentence sentenceid="3a2baf41c1920434734274152bf84304" id="tgt75" class="tgtSentence">创建基于模型的报表</caps:sentence>
                </title>
                <steps class="ordered">
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="7d453f68b6a311b28873f5ba0a7e0fbe" id="tgt76" class="tgtSentence">在 <token>cmshort</token> 控制台中，单击“监视”<ui></ui>。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="a37675996f538daeb307599f696b5d5c" id="tgt77" class="tgtSentence">在“监视”<ui></ui>工作区中，展开“报表”<ui></ui>，并单击“报表”<ui></ui>。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="1f714066a5007daf890ff7ec575ff7c7" id="tgt78" class="tgtSentence">在“主页”<ui></ui>选项卡上的“创建”<ui></ui>部分，单击“创建报表”<ui></ui>以打开“创建报表向导”<ui></ui>。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="236e2f567a59011e9619fbdaa89188d4" id="tgt79" class="tgtSentence">在“信息”<ui></ui>页上，配置下列设置： </caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="fe1938541b83bba09c69822d2e16b9ac" id="tgt80" class="tgtSentence">
                              <ui>类型</ui>：选择“基于模型的报表”<ui></ui>以使用 Reporting Services 模型在报表生成器中创建报表。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="933934f065970afc628493a03313275c" id="tgt81" class="tgtSentence">
                              <ui>名称</ui>：指定报表的名称。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="7b0afb76d4bdec35d267b9a9c6947287" id="tgt82" class="tgtSentence">
                              <ui>描述</ui>：指定报表的描述。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="8c90ff7bccd0b8b7ecbac13df937607a" id="tgt83" class="tgtSentence">
                              <ui>服务器</ui>：显示你在其上创建此报表的报表服务器的名称。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="e4e1be227f3a57822dfca13dd51fdccd" id="tgt84" class="tgtSentence">
                              <ui>路径</ui>：单击“浏览”<ui></ui>指定要在其中存储报表的文件夹。</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence sentenceid="090c8381dadd0cef02e0d08da6a5d306" id="tgt85" class="tgtSentence">单击“下一步”<ui></ui>。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="852620e830e01d4f0988665c189a757b" id="tgt86" class="tgtSentence">在“模型选择”<ui></ui>页上的列表中选择要用于创建此报表的可用模型。</caps:sentence>
                        <caps:sentence sentenceid="9a07311d672cc737d1d29bc06f2000da" id="tgt87" class="tgtSentence"> 当你选择报表模型时，“预览”<ui></ui>部分将显示所选报表模型提供的 SQL Server 视图和实体。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="15b53e54e35c019f6f31f229d9ffac5a" id="tgt88" class="tgtSentence">在“摘要”<ui></ui>页上，检查配置设置。</caps:sentence>
                        <caps:sentence sentenceid="527e9680082730f4a5a613393c61ab8c" id="tgt89" class="tgtSentence"> 单击“上一步”<ui></ui>以更改设置，或单击“下一步”<ui></ui>以在 <token>cmshort</token> 中创建报表。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="d6eab9c1dc32d62dbe06bd96ba499f6e" id="tgt90" class="tgtSentence">在“确认”<ui></ui>页上，单击“关闭”<ui></ui>退出向导，然后打开报表生成器以配置报表设置。</caps:sentence>
                        <caps:sentence sentenceid="c7c1545451d2da0b1bdcb69dd2f4c649" id="tgt91" class="tgtSentence"> 如果出现提示，请输入你的用户帐户和密码，然后单击“确定”<ui></ui>。</caps:sentence>
                        <caps:sentence sentenceid="047c52667072b1876d8eb1bf21aaa3ec" id="tgt92" class="tgtSentence"> 如果计算机上未安装报表生成器，将会提示你进行安装。</caps:sentence>
                        <caps:sentence sentenceid="8ac2cba4642e7d9132448110c2ea4040" id="tgt93" class="tgtSentence"> 单击“运行”<ui></ui>安装修改和创建报表所需的报表生成器。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="d0caf584c7a3c0522d3eb2aff426af16" id="tgt94" class="tgtSentence">在 Microsoft 报表生成器中，创建报表布局，选择可用 SQL Server 视图中的数据，向报表中添加参数，诸如此类。</caps:sentence>
                        <caps:sentence sentenceid="292641fed6e5fbb22b1eb75451524853" id="tgt95" class="tgtSentence"> 有关使用报表生成器来创建新报表的详细信息，请参阅报表生成器帮助。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="30c7f66c2bd5dd33fca091d76922f794" id="tgt96" class="tgtSentence">单击“运行”<ui></ui>以运行报表。</caps:sentence>
                        <caps:sentence sentenceid="9f5d9b5b3dffb2b61068fa8b9e1bdbcb" id="tgt97" class="tgtSentence"> 验证报表是否提供了预期信息。</caps:sentence>
                        <caps:sentence sentenceid="a02af188e19898a0a1b6ed6ad123db37" id="tgt98" class="tgtSentence"> 如果需要，单击“设计”<ui></ui>返回到“设计”视图以修改报表。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="589d5efbe1411c7c3ce739074fdc8b4b" id="tgt99" class="tgtSentence">单击“保存”<ui></ui>将报表保存到报表服务器。</caps:sentence>
                        <caps:sentence sentenceid="5a0e7a38eaf6ed423277f28039458193" id="tgt100" class="tgtSentence"> 你可以在“监视”<ui></ui>工作区的“报表”<ui></ui>节点中运行和修改新报表。</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
            </content>
          </section>
          <section address="BKMK_CreateSQLBasedReport" expanded="true">
            <title>
              <caps:sentence sentenceid="17d0e36eaab7407eb81caca4f3d13b1d" id="tgt101" class="tgtSentence">创建基于 SQL 的报表</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="29e5642fe4d75ca580b4c9435216bc72" id="tgt102" class="tgtSentence">基于 SQL 的报表使你能够检索基于报表 SQL 语句的数据。</caps:sentence>
              </para>
              <alert class="important">
                <para>
                  <caps:sentence sentenceid="2be28b8c56cb795301a2c54ddc6dadf1" id="tgt103" class="tgtSentence">在为自定义报表创建 SQL 语句时，不要直接引用 SQL Server 表，</caps:sentence>
                  <caps:sentence sentenceid="416468830497f89de1ec2c8655535ec0" id="tgt104" class="tgtSentence"> 而是从站点数据库中引用报表 SQL Server 视图（以 v_ 开头的视图名称）。</caps:sentence>
                  <caps:sentence sentenceid="390ba4211e8706a7ca743878d8adc713" id="tgt105" class="tgtSentence"> 你还可以从站点数据库中引用公共存储过程（以 sp_ 开头的存储过程名称）。</caps:sentence>
                </para>
              </alert>
              <alert class="security note">
                <para>
                  <caps:sentence sentenceid="b860380883e55e2e2311d29ccfb7e529" id="tgt106" class="tgtSentence">用户帐户必须具有“站点修改”<ui></ui>权限才能创建新报表。</caps:sentence>
                  <caps:sentence sentenceid="984c9235b01b4c90235648fca1242b81" id="tgt107" class="tgtSentence"> 用户只能在其具有“修改报表”<ui></ui>权限的文件夹中创建报表。</caps:sentence>
                </para>
              </alert>
              <para>
                <caps:sentence sentenceid="d6f60c7e594398718bbd08f7d21478dc" id="tgt108" class="tgtSentence">使用下列过程来创建基于 SQL 的 <token>cmshort</token> 报表。</caps:sentence>
              </para>
              <procedure expanded="false">
                <title>
                  <caps:sentence sentenceid="76e8dd8851d7b02c4895c18fa3671233" id="tgt109" class="tgtSentence">创建基于 SQL 的报表</caps:sentence>
                </title>
                <steps class="ordered">
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="7d453f68b6a311b28873f5ba0a7e0fbe" id="tgt110" class="tgtSentence">在 <token>cmshort</token> 控制台中，单击“监视”<ui></ui>。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="5bbf6953e5d7cf25f481f4796a2f1c0e" id="tgt111" class="tgtSentence">在“监视”<ui></ui>工作区中，展开“报表”<ui></ui>，然后单击“报表”<ui></ui>。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="1f714066a5007daf890ff7ec575ff7c7" id="tgt112" class="tgtSentence">在“主页”<ui></ui>选项卡上的“创建”<ui></ui>部分，单击“创建报表”<ui></ui>以打开“创建报表向导”<ui></ui>。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="236e2f567a59011e9619fbdaa89188d4" id="tgt113" class="tgtSentence">在“信息”<ui></ui>页上，配置下列设置： </caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="d839607fa5138d437baf6c302709adae" id="tgt114" class="tgtSentence">
                              <ui>类型</ui>：选择“基于 SQL 的报表”<ui></ui>以使用 SQL 语句在报表生成器中创建报表。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="933934f065970afc628493a03313275c" id="tgt115" class="tgtSentence">
                              <ui>名称</ui>：指定报表的名称。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="7b0afb76d4bdec35d267b9a9c6947287" id="tgt116" class="tgtSentence">
                              <ui>描述</ui>：指定报表的描述。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="8c90ff7bccd0b8b7ecbac13df937607a" id="tgt117" class="tgtSentence">
                              <ui>服务器</ui>：显示你在其上创建此报表的报表服务器的名称。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="e4e1be227f3a57822dfca13dd51fdccd" id="tgt118" class="tgtSentence">
                              <ui>路径</ui>：单击“浏览”<ui></ui>指定要在其中存储报表的文件夹。</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence sentenceid="090c8381dadd0cef02e0d08da6a5d306" id="tgt119" class="tgtSentence">单击“下一步”<ui></ui>。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="15b53e54e35c019f6f31f229d9ffac5a" id="tgt120" class="tgtSentence">在“摘要”<ui></ui>页上，检查配置设置。</caps:sentence>
                        <caps:sentence sentenceid="527e9680082730f4a5a613393c61ab8c" id="tgt121" class="tgtSentence"> 单击“上一步”<ui></ui>以更改设置，或单击“下一步”<ui></ui>以在 <token>cmshort</token> 中创建报表。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="eb509d1021d0a40a8af3431075fc0d18" id="tgt122" class="tgtSentence">在“确认”<ui></ui>页上，单击“关闭”<ui></ui>退出向导并打开报表生成器以配置报表设置。</caps:sentence>
                        <caps:sentence sentenceid="c7c1545451d2da0b1bdcb69dd2f4c649" id="tgt123" class="tgtSentence"> 如果出现提示，请输入你的用户帐户和密码，然后单击“确定”<ui></ui>。</caps:sentence>
                        <caps:sentence sentenceid="047c52667072b1876d8eb1bf21aaa3ec" id="tgt124" class="tgtSentence"> 如果计算机上未安装报表生成器，将会提示你进行安装。</caps:sentence>
                        <caps:sentence sentenceid="8ac2cba4642e7d9132448110c2ea4040" id="tgt125" class="tgtSentence"> 单击“运行”<ui></ui>安装修改和创建报表所需的报表生成器。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="68984450c0c5648a8052d53b1d3e8bbe" id="tgt126" class="tgtSentence">在 Microsoft 报表生成器中，为报表提供 SQL 语句或使用可用 SQL Server 视图中的列生成 SQL 语句，向报表中添加参数，诸如此类。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="30c7f66c2bd5dd33fca091d76922f794" id="tgt127" class="tgtSentence">单击“运行”<ui></ui>以运行报表。</caps:sentence>
                        <caps:sentence sentenceid="9f5d9b5b3dffb2b61068fa8b9e1bdbcb" id="tgt128" class="tgtSentence"> 验证报表是否提供了预期信息。</caps:sentence>
                        <caps:sentence sentenceid="a02af188e19898a0a1b6ed6ad123db37" id="tgt129" class="tgtSentence"> 如果需要，单击“设计”<ui></ui>返回到“设计”视图以修改报表。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="589d5efbe1411c7c3ce739074fdc8b4b" id="tgt130" class="tgtSentence">单击“保存”<ui></ui>将报表保存到报表服务器。</caps:sentence>
                        <caps:sentence sentenceid="23bfc1ecbe1b13cc5e08c2b3b72392e9" id="tgt131" class="tgtSentence"> 你可以在“监视”<ui></ui>工作区的“报表”<ui></ui>节点中运行新报表。</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
            </content>
          </section>
        </sections>
      </section>
      <section expanded="true" address="BKMK_ManageReportSubscriptions">
        <title>
          <caps:sentence sentenceid="6f5a958c9f2e1dd4da4dfb9adb694914" id="tgt132" class="tgtSentence">管理报表订阅</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="9b326d9af5116f0c7e7d3d6dec30e7c9" id="tgt133" class="tgtSentence">SQL Server Reporting Services 中的报表订阅使你能够配置按计划的间隔通过电子邮件自动交付指定报表或将指定报表自动交付到文件共享。</caps:sentence>
            <caps:sentence sentenceid="51c3b83729b717c9c0032a4e1f91f52b" id="tgt134" class="tgtSentence"> 使用 <token>cm5short</token> 中的<ui>创建订阅向导</ui>来配置报表订阅。</caps:sentence>
          </para>
        </content>
        <sections>
          <section address="BKMK_ReportSubscriptionFileShare" expanded="true">
            <title>
              <caps:sentence sentenceid="f51edc79d7ec00b0967b7e9cd46aac01" id="tgt135" class="tgtSentence">创建报表订阅以向文件共享传递报表</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="bc3894e68d15c6accd46f0617fa60c07" id="tgt136" class="tgtSentence">创建报表订阅以向文件共享传递报表时，会使用指定的格式将报表复制到你指定的文件共享中。</caps:sentence>
                <caps:sentence sentenceid="18771f9e9c77e8ee1649600217f68ac9" id="tgt137" class="tgtSentence"> 一次只能订阅和请求传递一个报表。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="a18c428308402e9597cd4bd6446ba8cd" id="tgt138" class="tgtSentence">与报表服务器承载和管理的报表不同的是，向共享文件夹传递的报表是静态文件。</caps:sentence>
                <caps:sentence sentenceid="f62faee18cc1cca1a290974f55e3ea8f" id="tgt139" class="tgtSentence"> 对于作为文件系统上的文件存储的报表，为报表定义的交互式功能无效。</caps:sentence>
                <caps:sentence sentenceid="89b36331e8a87e99bb9d3a5062778fd4" id="tgt140" class="tgtSentence"> 交互式功能将呈现为静态元素。</caps:sentence>
                <caps:sentence sentenceid="66051bc2ee7775f50db46f5fd48a331a" id="tgt141" class="tgtSentence"> 如果报表包含图表，则会使用默认的表示形式。</caps:sentence>
                <caps:sentence sentenceid="c89dbc92812dec530dfa85aad48082da" id="tgt142" class="tgtSentence"> 如果报表链接到另一个报表，则链接呈现为静态文本。</caps:sentence>
                <caps:sentence sentenceid="4972ace3d0cd4cb8ea2fcb8b8ad039c7" id="tgt143" class="tgtSentence"> 如果想在传递的报表中保留交互式功能，请改用电子邮件传递。</caps:sentence>
                <caps:sentence sentenceid="e8b652f9a87055766f34ea3fc9ade738" id="tgt144" class="tgtSentence"> 有关电子邮件传递的详细信息，请参阅本主题后面的 <link xlink:href="#BKMK_ReportSubscriptionEmail">Create a report subscription to deliver a report by email</link> 章节。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="59f52c65e18499594f050a50d4ddcbd9" id="tgt145" class="tgtSentence">在创建使用文件共享传递的订阅时，必须将现有的文件夹指定为目标文件夹。</caps:sentence>
                <caps:sentence sentenceid="dc22b8fbf276c04db0096ed437fc1581" id="tgt146" class="tgtSentence"> 报表服务器不会在文件系统上创建文件夹。</caps:sentence>
                <caps:sentence sentenceid="8830162ee9ce7034307a5e309d628459" id="tgt147" class="tgtSentence"> 对于你指定的文件夹，必须可以通过网络连接来访问它。</caps:sentence>
                <caps:sentence sentenceid="3a4be28b0440ed7cd058b577e91526cd" id="tgt148" class="tgtSentence"> 在指定订阅中的目标文件夹时，请使用 UNC 路径，并且不要在文件夹路径中包含末尾的反斜杠。</caps:sentence>
                <caps:sentence sentenceid="e62c2a040061d0aa80f39e0dca32c868" id="tgt149" class="tgtSentence"> 例如，目标文件夹的有效 UNC 路径是：<command>\\&lt;servername&gt;\reportfiles\operations\2011</command>。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="868ed3e06d236e3d37d49264b3188f79" id="tgt150" class="tgtSentence">可以使用各种文件格式（例如 MHTML 或 Excel）来呈现报表。</caps:sentence>
                <caps:sentence sentenceid="7a3043c4097d481e460227c636433a55" id="tgt151" class="tgtSentence"> 若要将报表保存为特定的文件格式，请在创建订阅时选择该呈现格式。</caps:sentence>
                <caps:sentence sentenceid="7f315b0b194a8a7d3c53c92f1483d3cb" id="tgt152" class="tgtSentence"> 例如，选择“Excel”以将报表保存为 Microsoft Excel 文件。</caps:sentence>
                <caps:sentence sentenceid="6023be576c551cca109e70418d20174a" id="tgt153" class="tgtSentence"> 虽然可以选择任何受支持的呈现格式，但在呈现为文件时，某些格式的效果比另一些好。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="490bf7c59ea835aeea16c94e9540a3f0" id="tgt154" class="tgtSentence">使用下列过程来创建向文件共享传递报表的报表订阅。</caps:sentence>
              </para>
              <procedure expanded="false">
                <title>
                  <caps:sentence sentenceid="b673c57655079ca670a74804bc70050c" id="tgt155" class="tgtSentence">创建向文件共享传递报表的报表订阅</caps:sentence>
                </title>
                <steps class="ordered">
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="7d453f68b6a311b28873f5ba0a7e0fbe" id="tgt156" class="tgtSentence">在 <token>cmshort</token> 控制台中，单击“监视”<ui></ui>。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="d9c157f3e6cdea3deef198b988a824ef" id="tgt157" class="tgtSentence">在“监视”<ui></ui>工作区中，展开“报表”<ui></ui>，然后单击“报表”<ui></ui>以列出可用报表。</caps:sentence>
                        <caps:sentence sentenceid="7f068f6026e2089af838bde21e03a9dd" id="tgt158" class="tgtSentence"> 可以选择一个报表文件夹，以仅列出与该文件夹关联的报表。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="0ed050264a9f33e9b45cd47ef9fabcd5" id="tgt159" class="tgtSentence">选择要添加到订阅中的报表，然后在“主页”<ui></ui>选项卡上的“报表组”<ui></ui>部分中，单击“创建订阅”<ui></ui>以打开“创建订阅向导”<ui></ui>。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="02ca3602170053c7d5dfc7a45634b660" id="tgt160" class="tgtSentence">在“订阅传递”<ui></ui>页上，配置下列设置：</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="27d4d4d2d889fd9f32f6d031917cfee7" id="tgt161" class="tgtSentence">报表传递方式：选择“Windows 文件共享”<ui></ui>以向文件共享传递报表。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="722c21d19b43401357d3a088de13ef6a" id="tgt162" class="tgtSentence">
                              <ui>文件名</ui>：指定报表的文件名。</caps:sentence>
                            <caps:sentence sentenceid="35d5326c256578126ad0556569cb641b" id="tgt163" class="tgtSentence"> 默认情况下，报表文件不包含文件扩展名。</caps:sentence>
                            <caps:sentence sentenceid="c877b67abd90ea8d1a7790f9c234eb52" id="tgt164" class="tgtSentence"> 选择“创建时添加文件扩展名”<ui></ui>，以自动根据呈现格式向此报表添加文件扩展名。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="d2549dd1f1e69fc4498f8e2ddbb5a26b" id="tgt165" class="tgtSentence">
                              <ui>路径</ui>：指定想将此报表传递到的现有文件夹的 UNC 路径（例如 \\&lt;服务器名称&gt;\&lt;服务器共享&gt;\&lt;报表文件夹&gt;）。</caps:sentence>
                          </para>
                          <alert class="note">
                            <para>
                              <caps:sentence sentenceid="72df7206528d37ca7131281adaf561fd" id="tgt166" class="tgtSentence">稍后在此页上指定的用户名必须能够访问此服务器共享，并且必须具有目标文件夹的“写入”权限。</caps:sentence>
                            </para>
                          </alert>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="95ef95e9d53ea830aaee0c74c74310a7" id="tgt167" class="tgtSentence">
                              <ui>呈现格式</ui>：为报表文件选择下列格式之一：</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="355ae72bf19458d349a40e4ea1fa824a" id="tgt168" class="tgtSentence">
                                  <ui>具有报表数据的 XML 文件</ui>：以可扩展标记语言格式保存报表。</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="6109ab958d33073a500cb25ccfff434e" id="tgt169" class="tgtSentence">
                                  <ui>CSV (逗号分隔)</ui>：以逗号分隔值格式保存报表。</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="60f18c17c6a68be7e64cfb2d4c789f3b" id="tgt170" class="tgtSentence">
                                  <ui>TIFF 文件</ui>：以标记图像文件格式保存报表。</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="7aa677056f87fe1dc8697d9e18907c1f" id="tgt171" class="tgtSentence">
                                  <ui>Acrobat (PDF)文件</ui>：以 Acrobat 可移植文档格式保存报表。</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="f2aa2fb6ac85362756b9e163dae332de" id="tgt172" class="tgtSentence">
                                  <ui>HTML 4.0</ui>：将报表保存为仅在支持 HTML 4.0 的浏览器中才能查看的网页。</caps:sentence>
                                <caps:sentence sentenceid="028d345a6576c915a10a4ab4eb696675" id="tgt173" class="tgtSentence"> Internet Explorer 5 和更高版本支持 HTML 4.0。</caps:sentence>
                              </para>
                              <alert class="note">
                                <para>
                                  <caps:sentence sentenceid="703ba1fcac22c47e2c85c0eb68e4a665" id="tgt174" class="tgtSentence">如果报表包含图像，HTML 4.0 格式并不会在文件中包含这些图像。</caps:sentence>
                                </para>
                              </alert>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="47aaea759a131826ba5388508882f6ab" id="tgt175" class="tgtSentence">
                                  <ui>MHTML (Web 存档)</ui>：以 MIME HTML 格式 (mhtml) 保存报表，可在多个 Web 浏览器中查看。</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="8a49a2fc562e855de22ffcfc9ff23c14" id="tgt176" class="tgtSentence">
                                  <ui>RPL 呈现器</ui>：以报表页面布局 (RPL) 格式保存报表。</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="46cd22ffe252edc4ed934b82283861c8" id="tgt177" class="tgtSentence">
                                  <ui>Excel</ui>：将报表另存为 Microsoft Excel 电子表格。</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="cebed50f78110eeb07ba82b0b90f384d" id="tgt178" class="tgtSentence">
                                  <ui>Word</ui>：将报表另存为 Microsoft Word 文档。</caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="a2b036677c39229381f01b9809dbd065" id="tgt179" class="tgtSentence">
                              <ui>用户名</ui>：指定具有目标服务器共享和文件夹的访问权限的 Windows 用户帐户。</caps:sentence>
                            <caps:sentence sentenceid="7c89427fde96ae6393b04187b24a909e" id="tgt180" class="tgtSentence"> 该用户帐户必须能够访问此服务器共享，并且必须具有目标文件夹的“写入”权限。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="276975c701234354f28fd0810c63da95" id="tgt181" class="tgtSentence">
                              <ui>密码</ui>：指定 Windows 用户帐户的密码。</caps:sentence>
                            <caps:sentence sentenceid="511026c8d8f10b48a80d67ec81acb1be" id="tgt182" class="tgtSentence"> 在“确认密码”<ui></ui>中，重新输入密码。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="8db94af6a6f5abf11415b5fabdfeaf00" id="tgt183" class="tgtSentence">选择下列选项之一，以配置当目标文件夹中存在同名文件时的行为： </caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="f51a43df9b36e802ec1526e1241e2c1f" id="tgt184" class="tgtSentence">
                                  <ui>使用较新版本覆盖现有文件</ui>：指定在报表文件已存在时用新版本覆盖它。</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="d902ca7464dc0902af785934a147fd18" id="tgt185" class="tgtSentence">
                                  <ui>不覆盖现有文件</ui>：指定在报表文件已存在时不执行任何操作。</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="5f0a3a7faa1c0729f3e2bb816a3a65a0" id="tgt186" class="tgtSentence">
                                  <ui>添加较新版本时递增文件名</ui>：指定在报表文件已存在时，向新报表的文件名添加一个数字，以将它与其他版本区分开来。</caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="6411e75b9687c7d1cc1cd84fe0b9262b" id="tgt187" class="tgtSentence">
                              <ui>描述</ui>：指定报表订阅的描述。</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence sentenceid="090c8381dadd0cef02e0d08da6a5d306" id="tgt188" class="tgtSentence">单击“下一步”<ui></ui>。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="158a0d6a6e91a2dc62e6385d538a1bc3" id="tgt189" class="tgtSentence">在“订阅计划”<ui></ui>页上，为报表订阅选择下列传递计划选项之一：</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="ecd57d955390ecae708a6521795e1051" id="tgt190" class="tgtSentence">
                              <ui>使用共享计划</ui>：共享计划是以前定义的计划，可以由其他报表订阅使用。</caps:sentence>
                            <caps:sentence sentenceid="7382449b74cb1aecf1d9638f0b81d95d" id="tgt191" class="tgtSentence"> 选中此复选框，然后在列表中选择一个共享计划（如果已指定了任何共享计划的话）。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="ed228df70c1507da51f076bba5743ed0" id="tgt192" class="tgtSentence">
                              <ui>创建新计划</ui>：配置此报表的运行计划，包括间隔、开始时间和日期以及此订阅的结束日期。</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="2f6d6dddf0b583a7edd474274f3919b9" id="tgt193" class="tgtSentence">在“订阅参数”<ui></ui>页上，指定在无人参与的情况下运行此报表时所使用的参数。</caps:sentence>
                        <caps:sentence sentenceid="f8d5800e8b78687c994cb59bfd1258eb" id="tgt194" class="tgtSentence"> 如果没有为报表指定参数，则不会显示此页。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="31a1cb40b826af144c2ed8adfd2fdb6d" id="tgt195" class="tgtSentence">在“摘要”<ui></ui>页上，查看报表订阅的设置。</caps:sentence>
                        <caps:sentence sentenceid="e68e6c9be4d279fcb44c5d06393bcbeb" id="tgt196" class="tgtSentence"> 单击“上一步”<ui></ui>以更改设置，或单击“下一步”<ui></ui>以创建报表订阅。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="2d1c95e732f859ed2fb011e895d00934" id="tgt197" class="tgtSentence">在“完成”<ui></ui>页上，单击“关闭”<ui></ui>退出向导。</caps:sentence>
                        <caps:sentence sentenceid="9801e9d877a41192e7c56728ea236a5b" id="tgt198" class="tgtSentence"> 验证是否已成功创建报表订阅。</caps:sentence>
                        <caps:sentence sentenceid="0ae071c5493bd7e18bfa5ed57d1134d2" id="tgt199" class="tgtSentence"> 可以在“监视”<ui></ui>工作区中的“订阅”<ui></ui>节点的“报表”<ui></ui>下查看和修改报表订阅。</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
            </content>
          </section>
          <section address="BKMK_ReportSubscriptionEmail" expanded="true">
            <title>
              <caps:sentence sentenceid="699f8e703fb3e765c0381d5ac413433b" id="tgt200" class="tgtSentence">创建报表订阅以通过电子邮件传递报表</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="c85f104e2cf8ecbcc154768ce5899519" id="tgt201" class="tgtSentence">在创建报表订阅以通过电子邮件传递报表时，将向你配置的收件人发送电子邮件，而且会将报表包含为附件。</caps:sentence>
                <caps:sentence sentenceid="d3b0c4b99f5f7dd2a948394246b2fbd0" id="tgt202" class="tgtSentence"> 报表服务器不会验证电子邮件地址，也不会从电子邮件服务器获取电子邮件地址。</caps:sentence>
                <caps:sentence sentenceid="7ad3621d0852031ec55ded058afafbf5" id="tgt203" class="tgtSentence"> 你必须事先知道要使用的电子邮件地址。</caps:sentence>
                <caps:sentence sentenceid="8cde5913871b019d0e7549552c8d445f" id="tgt204" class="tgtSentence"> 默认情况下，可以将报表通过电子邮件发送到组织内部或外部的任何有效的电子邮件帐户。</caps:sentence>
                <caps:sentence sentenceid="18a5da8d12f70484d97dd56956127f41" id="tgt205" class="tgtSentence"> 可以选择下列一个或全部两个电子邮件传递选项：</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="241f13d38cdc393627e86cff5f8fbda1" id="tgt206" class="tgtSentence">发送通知和所生成的报表的超链接。</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="4142a988d95411811e7958871662886e" id="tgt207" class="tgtSentence">发送嵌入或附加的报表。</caps:sentence>
                    <caps:sentence sentenceid="f4c37d6ceeb12c4e23d9c5c4c71622a9" id="tgt208" class="tgtSentence"> 呈现格式和浏览器决定报表是嵌入的还是附加的。</caps:sentence>
                    <caps:sentence sentenceid="942b7631db6b0a2128d072fb3e2d8cd2" id="tgt209" class="tgtSentence"> 如果浏览器支持 HTML 4.0 和 MHTML，而且你选择“MHTML (Web 存档)”呈现格式，则报表将嵌入到邮件中。</caps:sentence>
                    <caps:sentence sentenceid="cb35ec0e40db57ca759ec7f2f7e2d6bb" id="tgt210" class="tgtSentence"> 所有其他呈现格式（CSV、PDF、Word 等）将报表作为附件传递。</caps:sentence>
                    <caps:sentence sentenceid="1e8147505908f8a7aff0dc048bc3e45d" id="tgt211" class="tgtSentence"> Reporting Services 在发送报表之前不会检查附件或邮件的大小。</caps:sentence>
                    <caps:sentence sentenceid="111428d4ac11abfdf238871e99fe51ae" id="tgt212" class="tgtSentence"> 如果附件或邮件超过了邮件服务器允许的最大限制值，则不会传递报表。</caps:sentence>
                  </para>
                </listItem>
              </list>
              <alert class="important">
                <para>
                  <caps:sentence sentenceid="0e40dc38eed980e725d6509f97d0745c" id="tgt213" class="tgtSentence">必须在 Reporting Services 中配置电子邮件设置，以便让“电子邮件”<ui></ui>传递选项可用。</caps:sentence>
                  <caps:sentence sentenceid="e82e35cd19516539a1fe376f4f851413" id="tgt214" class="tgtSentence"> 有关在 Reporting Services 中配置电子邮件设置的详细信息，请参阅 SQL Server 联机丛书中的<externalLink><linkText>配置报表服务器以进行电子邮件传递</linkText><linkUri>http://go.microsoft.com/fwlink/p/?LinkId=226668</linkUri></externalLink>。</caps:sentence>
                </para>
              </alert>
              <para>
                <caps:sentence sentenceid="0c3ef2f630eb8240ad443dc7ab969c00" id="tgt215" class="tgtSentence">使用下列过程来创建报表订阅，以使用电子邮件传递报表。</caps:sentence>
              </para>
              <procedure expanded="false">
                <title>
                  <caps:sentence sentenceid="d32e8aacefa161743ebf4f54c0d09499" id="tgt216" class="tgtSentence">创建报表订阅以通过电子邮件传递报表</caps:sentence>
                </title>
                <steps class="bullet">
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="7d453f68b6a311b28873f5ba0a7e0fbe" id="tgt217" class="tgtSentence">在 <token>cmshort</token> 控制台中，单击“监视”<ui></ui>。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="d9c157f3e6cdea3deef198b988a824ef" id="tgt218" class="tgtSentence">在“监视”<ui></ui>工作区中，展开“报表”<ui></ui>，然后单击“报表”<ui></ui>以列出可用报表。</caps:sentence>
                        <caps:sentence sentenceid="5bd7b407e4471148999e4cacae6796f6" id="tgt219" class="tgtSentence"> 可以选择一个报表文件夹，以仅列出与该文件夹关联的报表。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="0ed050264a9f33e9b45cd47ef9fabcd5" id="tgt220" class="tgtSentence">选择要添加到订阅中的报表，然后在“主页”<ui></ui>选项卡上的“报表组”<ui></ui>部分中，单击“创建订阅”<ui></ui>以打开“创建订阅向导”<ui></ui>。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="02ca3602170053c7d5dfc7a45634b660" id="tgt221" class="tgtSentence">在“订阅传递”<ui></ui>页上，配置下列设置：</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="2496232b2e26a50be8cf6d2b2a2acf73" id="tgt222" class="tgtSentence">
                              <ui>报表传递方式</ui>：选择“电子邮件”<ui></ui>，以将报表作为电子邮件的附件传递。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="f362750c8f745f330b185b0d8a627ea5" id="tgt223" class="tgtSentence">
                              <ui>收件人</ui>：指定有效的电子邮件地址以接收此报表。</caps:sentence>
                          </para>
                          <alert class="note">
                            <para>
                              <caps:sentence sentenceid="a0f439fbe8915bbf2d4a1a811ae65b0e" id="tgt224" class="tgtSentence">通过用分号来分隔每个电子邮件地址，可以输入多个电子邮件收件人。</caps:sentence>
                            </para>
                          </alert>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="4599256274b844ed6c05278929c29d0a" id="tgt225" class="tgtSentence">
                              <ui>抄送</ui>：根据需要指定要将此报表复制到的电子邮件地址。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="5fbfbe46a73f8633047a2833b71f4420" id="tgt226" class="tgtSentence">
                              <ui>密件抄送</ui>：根据需要指定要将此报表的密件副本发送到的电子邮件地址。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="b77cdf22832b694fcb7aa1407d9f73c5" id="tgt227" class="tgtSentence">
                              <ui>回复</ui>：指定在收件人回复电子邮件时要使用的回复地址。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="c42ebcbc733bce658ed532c1f0bdd13c" id="tgt228" class="tgtSentence">
                              <ui>主题</ui>：指定订阅电子邮件的主题行。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="c65a0addd1a3e4176f7107ba5d53669c" id="tgt229" class="tgtSentence">
                              <ui>优先级</ui>：选择此电子邮件的优先级标记。</caps:sentence>
                            <caps:sentence sentenceid="632a169af237542c2c4f41f4db9b658c" id="tgt230" class="tgtSentence"> 请选择“低”<ui></ui>、“普通”<ui></ui>或“高”<ui></ui>。</caps:sentence>
                            <caps:sentence sentenceid="3bdc631109064a9639f96fd18221122e" id="tgt231" class="tgtSentence"> Microsoft Exchange 使用优先级设置来设置标记，以指示电子邮件的重要性。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="11862cf03cffacd899b93cae21478726" id="tgt232" class="tgtSentence">
                              <ui>备注</ui>：指定要添加到订阅电子邮件的正文的文本。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="8c45931d2a20b4647cdc351677a39072" id="tgt233" class="tgtSentence">
                              <ui>描述</ui>：指定此报表订阅的描述。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="67afde0807351ad49c68d390296e2aee" id="tgt234" class="tgtSentence">
                              <ui>包括链接</ui>：在电子邮件的正文中包括订阅的报表的 URL。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="95e66df1d1dee0a2ce41e703781f3ccd" id="tgt235" class="tgtSentence">
                              <ui>包括报表</ui>：指定将报表附加到电子邮件。</caps:sentence>
                            <caps:sentence sentenceid="829820a5203c1541186d3628fa437a63" id="tgt236" class="tgtSentence"> 在“呈现格式”<ui></ui>列表中指定用于附加报表的格式。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="adba7ea2499c1cdb18598c2bd0008084" id="tgt237" class="tgtSentence">
                              <ui>呈现格式</ui>：为附加的报表选择下列格式之一：</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="355ae72bf19458d349a40e4ea1fa824a" id="tgt238" class="tgtSentence">
                                  <ui>具有报表数据的 XML 文件</ui>：以可扩展标记语言格式保存报表。</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="6109ab958d33073a500cb25ccfff434e" id="tgt239" class="tgtSentence">
                                  <ui>CSV (逗号分隔)</ui>：以逗号分隔值格式保存报表。</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="60f18c17c6a68be7e64cfb2d4c789f3b" id="tgt240" class="tgtSentence">
                                  <ui>TIFF 文件</ui>：以标记图像文件格式保存报表。</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="7aa677056f87fe1dc8697d9e18907c1f" id="tgt241" class="tgtSentence">
                                  <ui>Acrobat (PDF)文件</ui>：以 Acrobat 可移植文档格式保存报表。</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="47aaea759a131826ba5388508882f6ab" id="tgt242" class="tgtSentence">
                                  <ui>MHTML (Web 存档)</ui>：以 MIME HTML 格式 (mhtml) 保存报表，可在多个 Web 浏览器中查看。</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="46cd22ffe252edc4ed934b82283861c8" id="tgt243" class="tgtSentence">
                                  <ui>Excel</ui>：将报表另存为 Microsoft Excel 电子表格。</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="cebed50f78110eeb07ba82b0b90f384d" id="tgt244" class="tgtSentence">
                                  <ui>Word</ui>：将报表另存为 Microsoft Word 文档。</caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </listItem>
                      </list>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="158a0d6a6e91a2dc62e6385d538a1bc3" id="tgt245" class="tgtSentence">在“订阅计划”<ui></ui>页上，为报表订阅选择下列传递计划选项之一：</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="ecd57d955390ecae708a6521795e1051" id="tgt246" class="tgtSentence">
                              <ui>使用共享计划</ui>：共享计划是以前定义的计划，可以由其他报表订阅使用。</caps:sentence>
                            <caps:sentence sentenceid="7382449b74cb1aecf1d9638f0b81d95d" id="tgt247" class="tgtSentence"> 选中此复选框，然后在列表中选择一个共享计划（如果已指定了任何共享计划的话）。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="d782e6a4c8bca491b1b63a6c4fc14220" id="tgt248" class="tgtSentence">
                              <ui>创建新计划</ui>：配置此报表的运行计划，包括间隔、开始时间和日期以及此订阅的结束日期。</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="2f6d6dddf0b583a7edd474274f3919b9" id="tgt249" class="tgtSentence">在“订阅参数”<ui></ui>页上，指定在无人参与的情况下运行此报表时所使用的参数。</caps:sentence>
                        <caps:sentence sentenceid="f8d5800e8b78687c994cb59bfd1258eb" id="tgt250" class="tgtSentence"> 如果没有为报表指定参数，则不会显示此页。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="31a1cb40b826af144c2ed8adfd2fdb6d" id="tgt251" class="tgtSentence">在“摘要”<ui></ui>页上，查看报表订阅的设置。</caps:sentence>
                        <caps:sentence sentenceid="e68e6c9be4d279fcb44c5d06393bcbeb" id="tgt252" class="tgtSentence"> 单击“上一步”<ui></ui>以更改设置，或单击“下一步”<ui></ui>以创建报表订阅。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="2d1c95e732f859ed2fb011e895d00934" id="tgt253" class="tgtSentence">在“完成”<ui></ui>页上，单击“关闭”<ui></ui>退出向导。</caps:sentence>
                        <caps:sentence sentenceid="9801e9d877a41192e7c56728ea236a5b" id="tgt254" class="tgtSentence"> 验证是否已成功创建报表订阅。</caps:sentence>
                        <caps:sentence sentenceid="0ae071c5493bd7e18bfa5ed57d1134d2" id="tgt255" class="tgtSentence"> 可以在“监视”<ui></ui>工作区中的“订阅”<ui></ui>节点的“报表”<ui></ui>下查看和修改报表订阅。</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
            </content>
          </section>
        </sections>
      </section>
      <relatedTopics>
        <link xlink:href="78c1f344-4d72-4718-aad9-3a3834b64dbd">Reporting in Configuration Manager</link>
      </relatedTopics>
    </developerWalkthroughDocument>
  </caps:SxSTarget>
  <caps:SxSSource locale="en-US">
    <developerWalkthroughDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence id="src1" class="srcSentence">After the infrastructure is in place for reporting in <token>cm6long</token>, there are a number of operations that you typically perform to manage reports and report subscriptions.</caps:sentence>
        </para>
        <para>
          <caps:sentence id="src2" class="srcSentence">Use the following sections in this topic to help you manage the operations for reports and report subscriptions in your <token>cmshort</token> hierarchy:</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              <link xlink:href="#BKMK_ManageReports">Manage Configuration Manager Reports</link>
            </para>
            <list class="bullet">
              <listItem>
                <para>
                  <link xlink:href="#BKMK_RunReport">Run a Configuration Manager Report</link>
                </para>
              </listItem>
              <listItem>
                <para>
                  <link xlink:href="#BKMK_ModifyReportProperties">Modify the Properties for a Configuration Manager Report</link>
                </para>
              </listItem>
              <listItem>
                <para>
                  <link xlink:href="#BKMK_EditReport">Edit a Configuration Manager Report</link>
                </para>
              </listItem>
              <listItem>
                <para>
                  <link xlink:href="#BKMK_CreateModelBasedReport">Create a Model-Based Report</link>
                </para>
              </listItem>
              <listItem>
                <para>
                  <link xlink:href="#BKMK_CreateSQLBasedReport">Create a SQL-Based Report</link>
                </para>
              </listItem>
            </list>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="#BKMK_ManageReportSubscriptions">Manage Report Subscriptions</link>
            </para>
            <list class="bullet">
              <listItem>
                <para>
                  <link xlink:href="#BKMK_ReportSubscriptionFileShare">Create a Report Subscription to Deliver a Report to a File Share</link>
                </para>
              </listItem>
              <listItem>
                <para>
                  <link xlink:href="#BKMK_ReportSubscriptionEmail">Create a Report Subscription to Deliver a Report by Email</link>
                </para>
              </listItem>
            </list>
          </listItem>
        </list>
      </introduction>
      <section expanded="true" address="BKMK_ManageReports">
        <title>
          <caps:sentence id="src3" class="srcSentence">Manage Configuration Manager reports</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src4" class="srcSentence">
              <token>cmshort</token> provides over 400 predefined reports that help you gather, organize, and present information about users, hardware and software inventory, software updates, applications, site status, and other <token>cmshort</token> operations in your organization.</caps:sentence>
            <caps:sentence id="src5" class="srcSentence"> You can use the predefined reports as they are, or you can modify a report to meet your requirements.</caps:sentence>
            <caps:sentence id="src6" class="srcSentence"> You can also create custom model-based and SQL-based reports to meet your requirements.</caps:sentence>
            <caps:sentence id="src7" class="srcSentence"> Use the following sections to help you manage <token>cmshort</token> reports.</caps:sentence>
          </para>
        </content>
        <sections>
          <section address="BKMK_RunReport" expanded="true">
            <title>
              <caps:sentence id="src8" class="srcSentence">Run a Configuration Manager report</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src9" class="srcSentence">Reports in <token>cmshort</token> are stored in SQL Server Reporting Services, and the data rendered in the report is retrieved from the <token>cmshort</token> site database.</caps:sentence>
                <caps:sentence id="src10" class="srcSentence"> You can access reports in the <token>cmshort</token> console or by using Report Manager, which you access in a web browser.</caps:sentence>
                <caps:sentence id="src11" class="srcSentence"> You can open reports on any computer that has access to the computer that is running SQL Server Reporting Services, and you must have sufficient rights to view the reports.</caps:sentence>
                <caps:sentence id="src12" class="srcSentence"> When you run a report, the report title, description, and category are displayed in the language of the local operating system.</caps:sentence>
              </para>
              <alert class="note">
                <para>
                  <caps:sentence id="src13" class="srcSentence">In some non-English languages, characters may not appear correctly in reports.</caps:sentence>
                  <caps:sentence id="src14" class="srcSentence">  In this case, reports can be viewed using the web-based Report Manager or through the Remote Administrator Console.</caps:sentence>
                </para>
              </alert>
              <alert class="warning">
                <para>
                  <caps:sentence id="src15" class="srcSentence">To run reports, you must have <ui>Read</ui> rights for the <ui>Site</ui> permission and the <ui>Run Report</ui> permission that is configured for specific objects.</caps:sentence>
                </para>
              </alert>
              <alert class="note">
                <para>
                  <caps:sentence id="src16" class="srcSentence">Report Manager is a web-based report access and management tool that you use to administer a single report server instance on a remote location over an HTTP connection.</caps:sentence>
                  <caps:sentence id="src17" class="srcSentence"> You can use Report Manager for operational tasks, for example, to view reports, modify report properties, and manage associated report subscriptions.</caps:sentence>
                  <caps:sentence id="src18" class="srcSentence"> This topic provides the steps to view a report and modify report properties in Report Manager, but for more information about the other options that Report Manager provides, see <externalLink><linkText>Report Manager</linkText><linkUri>http://go.microsoft.com/fwlink/p/?LinkId=224916</linkUri></externalLink> in SQL Server 2008 Books Online.</caps:sentence>
                </para>
              </alert>
              <para>
                <caps:sentence id="src19" class="srcSentence">Use the following procedures to run a <token>cmshort</token> report.</caps:sentence>
              </para>
              <procedure expanded="false">
                <title>
                  <caps:sentence id="src20" class="srcSentence">To run a report in the <token>cmshort</token> console</caps:sentence>
                </title>
                <steps class="ordered">
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src21" class="srcSentence">In the <token>cmshort</token> console, click <ui>Monitoring</ui>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src22" class="srcSentence">In the <ui>Monitoring</ui> workspace, expand <ui>Reporting</ui>, and then click <ui>Reports</ui> to list the available reports.</caps:sentence>
                      </para>
                      <alert class="important">
                        <para>
                          <caps:sentence id="src23" class="srcSentence">In this version of <token>cmshort</token>, the <ui>All content</ui> reports only display packages, not applications.</caps:sentence>
                        </para>
                      </alert>
                      <alert class="tip">
                        <para>
                          <caps:sentence id="src24" class="srcSentence">If no reports are listed, verify that the reporting services point is installed and configured.</caps:sentence>
                          <caps:sentence id="src25" class="srcSentence"> For more information, see <link xlink:href="55ae86a7-f0ab-4c09-b4da-89cd0e7fa0e0">Configuring reporting in Configuration Manager</link>.</caps:sentence>
                        </para>
                      </alert>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src26" class="srcSentence">Select the report that you want to run, and then on the <ui>Home</ui> tab, in the <ui>Report Group</ui> section, click <ui>Run</ui> to open the report.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src27" class="srcSentence">When there are required parameters, specify the parameters, and then click <ui>View Report</ui>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
              <procedure expanded="false">
                <title>
                  <caps:sentence id="src28" class="srcSentence">To run a report in a web browser</caps:sentence>
                </title>
                <steps class="ordered">
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src29" class="srcSentence">In your web browser, enter the Report Manager URL, for example, <embeddedLabel>http://Server1/Reports</embeddedLabel>.</caps:sentence>
                        <caps:sentence id="src30" class="srcSentence"> You can determine the Report Manager URL on the <ui>Report Manager URL</ui> page in Reporting Services <token>cmshort</token>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src31" class="srcSentence">In Report Manager, click the report folder for <token>cmshort</token>, for example, <embeddedLabel>ConfigMgr_CAS</embeddedLabel>.</caps:sentence>
                      </para>
                      <alert class="tip">
                        <para>
                          <caps:sentence id="src32" class="srcSentence">If no reports are listed, verify that the reporting services point is installed and configured.</caps:sentence>
                          <caps:sentence id="src33" class="srcSentence"> For more information, see <link xlink:href="55ae86a7-f0ab-4c09-b4da-89cd0e7fa0e0">Configuring reporting in Configuration Manager</link>.</caps:sentence>
                        </para>
                      </alert>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src34" class="srcSentence">Click the report category for the report that you want to run, and then click the link for the report.</caps:sentence>
                        <caps:sentence id="src35" class="srcSentence"> The report opens in Report Manager.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src36" class="srcSentence">When there are required parameters, specify the parameters, and then click <ui>View Report</ui>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
            </content>
          </section>
          <section address="BKMK_ModifyReportProperties" expanded="true">
            <title>
              <caps:sentence id="src37" class="srcSentence">Modify the properties for a Configuration Manager report</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src38" class="srcSentence">In the <token>cmshort</token> console, you can view the properties for a report, such as the report name and description, but to change the properties, use Report Manager.</caps:sentence>
                <caps:sentence id="src39" class="srcSentence"> Use the following procedure to modify the properties for a <token>cmshort</token> report.</caps:sentence>
              </para>
              <procedure expanded="false">
                <title>
                  <caps:sentence id="src40" class="srcSentence">To modify report properties in Report Manager</caps:sentence>
                </title>
                <steps class="ordered">
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src41" class="srcSentence">In your web browser, enter the Report Manager URL, for example, <embeddedLabel>http://Server1/Reports</embeddedLabel>.</caps:sentence>
                        <caps:sentence id="src42" class="srcSentence"> You can determine the Report Manager URL on the <ui>Report Manager URL</ui> page in Reporting Services <token>cmshort</token>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src43" class="srcSentence">In Report Manager, click the report folder for <token>cmshort</token>, for example, <embeddedLabel>ConfigMgr_CAS</embeddedLabel>.</caps:sentence>
                      </para>
                      <alert class="tip">
                        <para>
                          <caps:sentence id="src44" class="srcSentence">If no reports are listed, verify that the Reporting Services point is installed and configured.</caps:sentence>
                          <caps:sentence id="src45" class="srcSentence"> For more information, see <link xlink:href="55ae86a7-f0ab-4c09-b4da-89cd0e7fa0e0">Configuring reporting in Configuration Manager</link></caps:sentence>
                        </para>
                      </alert>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src46" class="srcSentence">Click the report category for the report for which you want to modify properties, and then click the link for the report.</caps:sentence>
                        <caps:sentence id="src47" class="srcSentence"> The report opens in Report Manager.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src48" class="srcSentence">Click the <ui>Properties</ui> tab.</caps:sentence>
                        <caps:sentence id="src49" class="srcSentence"> You can modify the report name and description.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src50" class="srcSentence">When you are finished, click <ui>Apply</ui>.</caps:sentence>
                        <caps:sentence id="src51" class="srcSentence"> The report properties are saved on the report server, and the <token>cmshort</token> console retrieves the updated report properties for the report.</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
            </content>
          </section>
          <section address="BKMK_EditReport" expanded="true">
            <title>
              <caps:sentence id="src52" class="srcSentence">Edit a Configuration Manager report</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src53" class="srcSentence">When an existing <token>cmshort</token> report does not retrieve the information that you have to have or does not provide the layout or design that you want, you can edit the report in Report Builder.</caps:sentence>
              </para>
              <alert class="note">
                <para>
                  <caps:sentence id="src54" class="srcSentence">You can also choose to clone an existing report by opening it for editing, and clicking <ui>Save As</ui> to save it as a new report.</caps:sentence>
                </para>
              </alert>
              <alert class="security note">
                <para>
                  <caps:sentence id="src55" class="srcSentence">The user account must have <ui>Site Modify</ui> permission and <ui>Modify Report</ui> permissions on the specific objects associated with the report that you want to modify.</caps:sentence>
                </para>
              </alert>
              <alert class="important">
                <para>
                  <caps:sentence id="src56" class="srcSentence">When <token>cmshort</token> is upgraded to a newer version, new reports overwrite the predefined reports.</caps:sentence>
                  <caps:sentence id="src57" class="srcSentence"> If you modify a predefined report, you must back up the report before you install the new version, and then restore the report in Reporting Services.</caps:sentence>
                  <caps:sentence id="src58" class="srcSentence"> If you are making significant changes to a predefined report, consider creating a new report instead.</caps:sentence>
                  <caps:sentence id="src59" class="srcSentence"> New reports that you create before you upgrade a site are not overwritten.</caps:sentence>
                </para>
              </alert>
              <para>
                <caps:sentence id="src60" class="srcSentence">Use the following procedure to edit the properties for a <token>cmshort</token> report.</caps:sentence>
              </para>
              <procedure expanded="false">
                <title>
                  <caps:sentence id="src61" class="srcSentence">To edit report properties</caps:sentence>
                </title>
                <steps class="ordered">
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src62" class="srcSentence">In the <token>cmshort</token> console, click <ui>Monitoring</ui>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src63" class="srcSentence">In the <ui>Monitoring</ui> workspace, expand <ui>Reporting</ui>, and then click <ui>Reports</ui> to list the available reports.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src64" class="srcSentence">Select the report that you want to modify, and then on the <ui>Home</ui> tab, in the <ui>Report Group</ui> section, click <ui>Edit</ui>.</caps:sentence>
                        <caps:sentence id="src65" class="srcSentence"> Enter your user account and password if you are prompted, and then click <ui>OK</ui>.</caps:sentence>
                        <caps:sentence id="src66" class="srcSentence"> If Report Builder is not installed on the computer, you are prompted to install it.</caps:sentence>
                        <caps:sentence id="src67" class="srcSentence"> Click <ui>Run</ui> to install Report Builder, which is required to modify and create reports.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src68" class="srcSentence">In Report Builder, modify the appropriate report settings, and then click <ui>Save</ui> to save the report to the report server.</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
            </content>
          </section>
          <section address="BKMK_CreateModelBasedReport" expanded="true">
            <title>
              <caps:sentence id="src69" class="srcSentence">Create a model-based report</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src70" class="srcSentence">A model-based report lets you interactively select the items you want to include in your report.</caps:sentence>
                <caps:sentence id="src71" class="srcSentence"> For more information about creating custom report models, see <link xlink:href="f2df88b4-c348-4dcf-854a-54fd6eedf485">Creating Custom Report Models in SQL Server Reporting Services</link>.</caps:sentence>
              </para>
              <alert class="security note">
                <para>
                  <caps:sentence id="src72" class="srcSentence">The user account must have <ui>Site Modify</ui> permission to create a new report.</caps:sentence>
                  <caps:sentence id="src73" class="srcSentence"> The user can only create a report in folders for which the user has <ui>Modify Report</ui> permissions.</caps:sentence>
                </para>
              </alert>
              <para>
                <caps:sentence id="src74" class="srcSentence">Use the following procedure to create a model-based <token>cmshort</token> report.</caps:sentence>
              </para>
              <procedure expanded="false">
                <title>
                  <caps:sentence id="src75" class="srcSentence">To create a model-based report</caps:sentence>
                </title>
                <steps class="ordered">
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src76" class="srcSentence">In the <token>cmshort</token> console, click <ui>Monitoring</ui>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src77" class="srcSentence">In the <ui>Monitoring</ui> workspace, expand <ui>Reporting</ui> and click <ui>Reports</ui>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src78" class="srcSentence">On the <ui>Home</ui> tab, in the <ui>Create</ui> section, click <ui>Create Report</ui> to open the <ui>Create Report Wizard</ui>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src79" class="srcSentence">On the <ui>Information</ui> page, configure the following settings: </caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence id="src80" class="srcSentence">
                              <ui>Type</ui>: Select <ui>Model-based Report</ui> to create a report in Report Builder by using a Reporting Services model.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src81" class="srcSentence">
                              <ui>Name</ui>: Specify a name for the report.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src82" class="srcSentence">
                              <ui>Description</ui>: Specify a description for the report.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src83" class="srcSentence">
                              <ui>Server</ui>: Displays the name of the report server on which you are creating this report.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src84" class="srcSentence">
                              <ui>Path</ui>: Click <ui>Browse</ui> to specify a folder in which you want to store the report.</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence id="src85" class="srcSentence">Click <ui>Next</ui>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src86" class="srcSentence">On the <ui>Model Selection</ui> page, select an available model in the list that you use to create this report.</caps:sentence>
                        <caps:sentence id="src87" class="srcSentence"> When you select the report model, the <ui>Preview</ui> section displays the SQL Server views and entities that are made available by the selected report model.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src88" class="srcSentence">On the <ui>Summary</ui> page, review the settings.</caps:sentence>
                        <caps:sentence id="src89" class="srcSentence"> Click <ui>Previous</ui> to change the settings or click <ui>Next</ui> to create the report in <token>cmshort</token>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src90" class="srcSentence">On the <ui>Confirmation</ui> page, click <ui>Close</ui> to exit the wizard, and then open Report Builder to configure the report settings.</caps:sentence>
                        <caps:sentence id="src91" class="srcSentence"> Enter your user account and password if you are prompted, and then click <ui>OK</ui>.</caps:sentence>
                        <caps:sentence id="src92" class="srcSentence"> If Report Builder is not installed on the computer, you are prompted to install it.</caps:sentence>
                        <caps:sentence id="src93" class="srcSentence"> Click <ui>Run</ui> to install Report Builder, which is required to modify and create reports.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src94" class="srcSentence">In Microsoft Report Builder, create the report layout, select data in the available SQL Server views, add parameters to the report, and so on.</caps:sentence>
                        <caps:sentence id="src95" class="srcSentence"> For more information about using Report Builder to create a new report, see the Report Builder Help.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src96" class="srcSentence">Click <ui>Run</ui> to run your report.</caps:sentence>
                        <caps:sentence id="src97" class="srcSentence"> Verify that the report provides the information that you expect.</caps:sentence>
                        <caps:sentence id="src98" class="srcSentence"> Click <ui>Design</ui> to return to the Design view to modify the report, if needed.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src99" class="srcSentence">Click <ui>Save</ui> to save the report to the report server.</caps:sentence>
                        <caps:sentence id="src100" class="srcSentence"> You can run and modify the new report in the <ui>Reports</ui> node in the <ui>Monitoring</ui> workspace.</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
            </content>
          </section>
          <section address="BKMK_CreateSQLBasedReport" expanded="true">
            <title>
              <caps:sentence id="src101" class="srcSentence">Create a SQL-based report</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src102" class="srcSentence">A SQL-based report lets you retrieve data that is based on a report SQL statement.</caps:sentence>
              </para>
              <alert class="important">
                <para>
                  <caps:sentence id="src103" class="srcSentence">When you create an SQL statement for a custom report, do not directly reference SQL Server tables.</caps:sentence>
                  <caps:sentence id="src104" class="srcSentence"> Instead, reference reporting SQL Server views (view names that start with v_) from the site database.</caps:sentence>
                  <caps:sentence id="src105" class="srcSentence"> You can also reference public stored procedures (stored procedure names that start with sp_) from the site database.</caps:sentence>
                </para>
              </alert>
              <alert class="security note">
                <para>
                  <caps:sentence id="src106" class="srcSentence">The user account must have <ui>Site Modify</ui> permission to create a new report.</caps:sentence>
                  <caps:sentence id="src107" class="srcSentence"> The user can only create a report in folders for which the user has <ui>Modify Report</ui> permissions.</caps:sentence>
                </para>
              </alert>
              <para>
                <caps:sentence id="src108" class="srcSentence">Use the following procedure to create a SQL-based <token>cmshort</token> report.</caps:sentence>
              </para>
              <procedure expanded="false">
                <title>
                  <caps:sentence id="src109" class="srcSentence">To create a SQL-based report</caps:sentence>
                </title>
                <steps class="ordered">
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src110" class="srcSentence">In the <token>cmshort</token> console, click <ui>Monitoring</ui>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src111" class="srcSentence">In the <ui>Monitoring</ui> workspace, expand <ui>Reporting</ui>, and then click <ui>Reports</ui>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src112" class="srcSentence">On the <ui>Home</ui> tab, in the <ui>Create</ui> section, click <ui>Create Report</ui> to open the <ui>Create Report Wizard</ui>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src113" class="srcSentence">On the <ui>Information</ui> page, configure the following settings: </caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence id="src114" class="srcSentence">
                              <ui>Type</ui>: Select <ui>SQL-based Report</ui> to create a report in Report Builder by using a SQL statement.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src115" class="srcSentence">
                              <ui>Name</ui>: Specify a name for the report.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src116" class="srcSentence">
                              <ui>Description</ui>: Specify a description for the report.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src117" class="srcSentence">
                              <ui>Server</ui>: Displays the name of the report server on which you are creating this report.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src118" class="srcSentence">
                              <ui>Path</ui>: Click <ui>Browse</ui> to specify a folder in which you want to store the report.</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence id="src119" class="srcSentence">Click <ui>Next</ui>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src120" class="srcSentence">On the <ui>Summary</ui> page, review the settings.</caps:sentence>
                        <caps:sentence id="src121" class="srcSentence"> Click <ui>Previous</ui> to change the settings or click <ui>Next</ui> to create the report in <token>cmshort</token>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src122" class="srcSentence">On the <ui>Confirmation</ui> page, click <ui>Close</ui> to exit the wizard and open Report Builder to configure the report settings.</caps:sentence>
                        <caps:sentence id="src123" class="srcSentence"> Enter your user account and password if you are prompted, and then click <ui>OK</ui>.</caps:sentence>
                        <caps:sentence id="src124" class="srcSentence"> If Report Builder is not installed on the computer, you are prompted to install it.</caps:sentence>
                        <caps:sentence id="src125" class="srcSentence"> Click <ui>Run</ui> to install Report Builder, which is required to modify and create reports.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src126" class="srcSentence">In Microsoft Report Builder, provide the SQL statement for the report or build the SQL statement by using columns in available SQL Server views, add parameters to the report, and so on.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src127" class="srcSentence">Click <ui>Run</ui> to run your report.</caps:sentence>
                        <caps:sentence id="src128" class="srcSentence"> Verify that the report provides the information that you expect.</caps:sentence>
                        <caps:sentence id="src129" class="srcSentence"> Click <ui>Design</ui> to return to the Design view to modify the report, if needed.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src130" class="srcSentence">Click <ui>Save</ui> to save the report to the report server.</caps:sentence>
                        <caps:sentence id="src131" class="srcSentence"> You can run the new report in the <ui>Reports</ui> node in the <ui>Monitoring</ui> workspace.</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
            </content>
          </section>
        </sections>
      </section>
      <section expanded="true" address="BKMK_ManageReportSubscriptions">
        <title>
          <caps:sentence id="src132" class="srcSentence">Manage report subscriptions</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src133" class="srcSentence">Report subscriptions in SQL Server Reporting Services let you configure the automatic delivery of specified reports by email or to a file share at scheduled intervals.</caps:sentence>
            <caps:sentence id="src134" class="srcSentence"> Use the <ui>Create Subscription Wizard</ui> in <token>cm5short</token> to configure report subscriptions.</caps:sentence>
          </para>
        </content>
        <sections>
          <section address="BKMK_ReportSubscriptionFileShare" expanded="true">
            <title>
              <caps:sentence id="src135" class="srcSentence">Create a report subscription to deliver a report to a file share</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src136" class="srcSentence">When you create a report subscription to deliver a report to a file share, the report is copied in the specified format to the file share that you specify.</caps:sentence>
                <caps:sentence id="src137" class="srcSentence"> You can subscribe to and request delivery for only one report at a time.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src138" class="srcSentence">Unlike reports that are hosted and managed by a report server, reports that are delivered to a shared folder are static files.</caps:sentence>
                <caps:sentence id="src139" class="srcSentence"> Interactive features that are defined for the report do not work for reports that are stored as files on the file system.</caps:sentence>
                <caps:sentence id="src140" class="srcSentence"> Interaction features are represented as static elements.</caps:sentence>
                <caps:sentence id="src141" class="srcSentence"> If the report includes charts, the default presentation is used.</caps:sentence>
                <caps:sentence id="src142" class="srcSentence"> If the report links through to another report, the link is rendered as static text.</caps:sentence>
                <caps:sentence id="src143" class="srcSentence"> If you want to retain interactive features in a delivered report, use email delivery instead.</caps:sentence>
                <caps:sentence id="src144" class="srcSentence"> For more information about email delivery, see the <link xlink:href="#BKMK_ReportSubscriptionEmail">Create a report subscription to deliver a report by email</link> section later in this topic.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src145" class="srcSentence">When you create a subscription that uses file share delivery, you must specify an existing folder as the destination folder.</caps:sentence>
                <caps:sentence id="src146" class="srcSentence"> The report server does not create folders on the file system.</caps:sentence>
                <caps:sentence id="src147" class="srcSentence"> The folder that you specify must be accessible over a network connection.</caps:sentence>
                <caps:sentence id="src148" class="srcSentence"> When you specify the destination folder in a subscription, use a UNC path and do not include trailing backslashes in the folder path.</caps:sentence>
                <caps:sentence id="src149" class="srcSentence"> For example, a valid UNC path for the destination folder is: <command>\\&lt;servername&gt;\reportfiles\operations\2011</command>.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src150" class="srcSentence">Reports can be rendered in a variety of file formats, such as MHTML or Excel.</caps:sentence>
                <caps:sentence id="src151" class="srcSentence"> To save the report in a specific file format, select that rendering format when creating your subscription.</caps:sentence>
                <caps:sentence id="src152" class="srcSentence"> For example, choosing Excel saves the report as a Microsoft Excel file.</caps:sentence>
                <caps:sentence id="src153" class="srcSentence"> Although you can select any supported rendering format, some formats work better than others when rendering to a file.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src154" class="srcSentence">Use the following procedure to create a report subscription to deliver a report to a file share.</caps:sentence>
              </para>
              <procedure expanded="false">
                <title>
                  <caps:sentence id="src155" class="srcSentence">To create a report subscription to deliver a report to a file share</caps:sentence>
                </title>
                <steps class="ordered">
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src156" class="srcSentence">In the <token>cmshort</token> console, click <ui>Monitoring</ui>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src157" class="srcSentence">In the <ui>Monitoring</ui> workspace, expand <ui>Reporting</ui> and click <ui>Reports</ui> to list the available reports.</caps:sentence>
                        <caps:sentence id="src158" class="srcSentence"> You can select a report folder to list only the reports that are associated with the folder.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src159" class="srcSentence">Select the report that you want to add to the subscription, and then on the <ui>Home</ui> tab, in the <ui>Report Group</ui> section, click <ui>Create Subscription</ui> to open the <ui>Create Subscription Wizard</ui>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src160" class="srcSentence">On the <ui>Subscription Delivery</ui> page, configure the following settings:</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence id="src161" class="srcSentence">Report delivered by: Select <ui>Windows File Share</ui> to deliver the report to a file share.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src162" class="srcSentence">
                              <ui>File Name</ui>: Specify the file name for the report.</caps:sentence>
                            <caps:sentence id="src163" class="srcSentence"> By default, the report file does not include a file name extension.</caps:sentence>
                            <caps:sentence id="src164" class="srcSentence"> Select <ui>Add file extension when created</ui> to automatically add a file name extension to this report based on the render format.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src165" class="srcSentence">
                              <ui>Path</ui>: Specify a UNC path to an existing folder where you want to deliver this report (for example, \\&lt;server name&gt;\&lt;server share&gt;\&lt;report folder&gt;).</caps:sentence>
                          </para>
                          <alert class="note">
                            <para>
                              <caps:sentence id="src166" class="srcSentence">The user name specified later on this page must have access to this server share and have Write permissions on the destination folder.</caps:sentence>
                            </para>
                          </alert>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src167" class="srcSentence">
                              <ui>Render Format</ui>: Select one of the following formats for the report file:</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence id="src168" class="srcSentence">
                                  <ui>XML file with report data</ui>: Saves the report in Extensible Markup Language format.</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src169" class="srcSentence">
                                  <ui>CSV (comma delimited)</ui>: Saves the report in comma-separated-value format.</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src170" class="srcSentence">
                                  <ui>TIFF file</ui>: Saves the report in Tagged Image File Format.</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src171" class="srcSentence">
                                  <ui>Acrobat (PDF) file</ui>: Saves the report in Acrobat Portable Document Format.</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src172" class="srcSentence">
                                  <ui>HTML 4.0</ui>: Saves the report as a webpage viewable only in browsers that support HTML 4.0.</caps:sentence>
                                <caps:sentence id="src173" class="srcSentence"> Internet Explorer 5 and later versions support HTML 4.0.</caps:sentence>
                              </para>
                              <alert class="note">
                                <para>
                                  <caps:sentence id="src174" class="srcSentence">If you have images in your report, the HTML 4.0 format does not include them in the file.</caps:sentence>
                                </para>
                              </alert>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src175" class="srcSentence">
                                  <ui>MHTML (web archive)</ui>: Saves the report in MIME HTML format (mhtml), which is viewable in many web browsers.</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src176" class="srcSentence">
                                  <ui>RPL Renderer</ui>: Saves the report in Report Page Layout (RPL) format.</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src177" class="srcSentence">
                                  <ui>Excel</ui>: Saves the report as a Microsoft Excel spreadsheet.</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src178" class="srcSentence">
                                  <ui>Word</ui>: Saves the report as a Microsoft Word document.</caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src179" class="srcSentence">
                              <ui>User Name</ui>: Specify a Windows user account with permissions to access the destination server share and folder.</caps:sentence>
                            <caps:sentence id="src180" class="srcSentence"> The user account must have access to this server share and have Write permission on the destination folder.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src181" class="srcSentence">
                              <ui>Password</ui>: Specify the password for the Windows user account.</caps:sentence>
                            <caps:sentence id="src182" class="srcSentence"> In <ui>Confirm Password</ui>, re-enter the password.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src183" class="srcSentence">Select one of the following options to configure the behavior when a file of the same name exists in the destination folder: </caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence id="src184" class="srcSentence">
                                  <ui>Overwrite an existing file with a newer version</ui>: Specifies that when the report file already exists, the new version overwrites it.</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src185" class="srcSentence">
                                  <ui>Do not overwrite an existing file</ui>: Specifies that when the report file already exists, there is no action.</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src186" class="srcSentence">
                                  <ui>Increment file names as newer versions are added</ui>: Specifies that when the report file already exists, a number is added to the new report to the file name to distinguish it from other versions.</caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src187" class="srcSentence">
                              <ui>Description</ui>: Specifies the description for the report subscription.</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence id="src188" class="srcSentence">Click <ui>Next</ui>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src189" class="srcSentence">On the <ui>Subscription Schedule</ui> page, select one of the following delivery schedule options for the report subscription:</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence id="src190" class="srcSentence">
                              <ui>Use shared schedule</ui>: A shared schedule is a previously defined schedule that can be used by other report subscriptions.</caps:sentence>
                            <caps:sentence id="src191" class="srcSentence"> Select this check box, and then select a shared schedule in the list if any have been specified.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src192" class="srcSentence">
                              <ui>Create new schedule</ui>: Configure the schedule on which this report runs, including the interval, start time and date, and the end date for this subscription.</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src193" class="srcSentence">On the <ui>Subscription Parameters</ui> page, specify the parameters for this report that are used when it is run unattended.</caps:sentence>
                        <caps:sentence id="src194" class="srcSentence"> When there are no parameters for the report, this page is not displayed.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src195" class="srcSentence">On the <ui>Summary</ui> page, review the report subscription settings.</caps:sentence>
                        <caps:sentence id="src196" class="srcSentence"> Click <ui>Previous</ui> to change the settings or click <ui>Next</ui> to create the report subscription.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src197" class="srcSentence">On the <ui>Completion</ui> page, click <ui>Close</ui> to exit the wizard.</caps:sentence>
                        <caps:sentence id="src198" class="srcSentence"> Verify that the report subscription was created successfully.</caps:sentence>
                        <caps:sentence id="src199" class="srcSentence"> You can view and modify report subscriptions in the <ui>Subscriptions</ui> node under <ui>Reporting</ui> in the <ui>Monitoring</ui> workspace.</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
            </content>
          </section>
          <section address="BKMK_ReportSubscriptionEmail" expanded="true">
            <title>
              <caps:sentence id="src200" class="srcSentence">Create a report subscription to deliver a report by email</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src201" class="srcSentence">When you create a report subscription to deliver a report by email, an email is sent to the recipients that you configure, and the report is included as an attachment.</caps:sentence>
                <caps:sentence id="src202" class="srcSentence"> The report server does not validate email addresses or obtain email addresses from an email server.</caps:sentence>
                <caps:sentence id="src203" class="srcSentence"> You must know in advance which email addresses you want to use.</caps:sentence>
                <caps:sentence id="src204" class="srcSentence"> By default, you can email reports to any valid email account within or outside of your organization.</caps:sentence>
                <caps:sentence id="src205" class="srcSentence"> You can select one or both of the following email delivery options:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src206" class="srcSentence">Send a notification and a hyperlink to the generated report.</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src207" class="srcSentence">Send an embedded or attached report.</caps:sentence>
                    <caps:sentence id="src208" class="srcSentence"> The rendering format and browser determine whether the report is embedded or attached.</caps:sentence>
                    <caps:sentence id="src209" class="srcSentence"> If your browser supports HTML 4.0 and MHTML, and you select the MHTML (web archive) rendering format, the report is embedded as part of the message.</caps:sentence>
                    <caps:sentence id="src210" class="srcSentence"> All other rendering formats (CSV, PDF, Word, and so on) deliver reports as attachments.</caps:sentence>
                    <caps:sentence id="src211" class="srcSentence"> Reporting Services does not check the size of the attachment or message before sending the report.</caps:sentence>
                    <caps:sentence id="src212" class="srcSentence"> If the attachment or message exceeds the maximum limit allowed by your mail server, the report is not delivered.</caps:sentence>
                  </para>
                </listItem>
              </list>
              <alert class="important">
                <para>
                  <caps:sentence id="src213" class="srcSentence">You must configure the email settings in Reporting Services for the <ui>Email</ui> delivery option to be available.</caps:sentence>
                  <caps:sentence id="src214" class="srcSentence"> For more information about configuring the email settings in Reporting Services, see <externalLink><linkText>Configuring a Report Server for Email Delivery</linkText><linkUri>http://go.microsoft.com/fwlink/p/?LinkId=226668</linkUri></externalLink> in the SQL Server Books Online.</caps:sentence>
                </para>
              </alert>
              <para>
                <caps:sentence id="src215" class="srcSentence">Use the following procedure to create a report subscription to deliver a report by using email.</caps:sentence>
              </para>
              <procedure expanded="false">
                <title>
                  <caps:sentence id="src216" class="srcSentence">To create a report subscription to deliver a report by email</caps:sentence>
                </title>
                <steps class="bullet">
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src217" class="srcSentence">In the <token>cmshort</token> console, click <ui>Monitoring</ui>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src218" class="srcSentence">In the <ui>Monitoring</ui> workspace, expand <ui>Reporting</ui> and click <ui>Reports</ui> to list the available reports.</caps:sentence>
                        <caps:sentence id="src219" class="srcSentence"> You can select a report folder to list the only the reports that are associated with the folder.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src220" class="srcSentence">Select the report that you want to add to the subscription, and then on the <ui>Home</ui> tab, in the <ui>Report Group</ui> section, click <ui>Create Subscription</ui> to open the <ui>Create Subscription Wizard</ui>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src221" class="srcSentence">On the <ui>Subscription Delivery</ui> page, configure the following settings:</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence id="src222" class="srcSentence">
                              <ui>Report delivered by</ui>: Select <ui>E-mail</ui> to deliver the report as an attachment in an email message.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src223" class="srcSentence">
                              <ui>To</ui>: Specify a valid email address to send this report to.</caps:sentence>
                          </para>
                          <alert class="note">
                            <para>
                              <caps:sentence id="src224" class="srcSentence">You can enter multiple email recipients by separating each email address with a semicolon.</caps:sentence>
                            </para>
                          </alert>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src225" class="srcSentence">
                              <ui>Cc</ui>: Optionally, specify an email address to copy this report to.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src226" class="srcSentence">
                              <ui>Bcc</ui>: Optionally, specify an email address to send a blind copy of this report to.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src227" class="srcSentence">
                              <ui>Reply To</ui>: Specify the reply address to use if the recipient replies to the email message.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src228" class="srcSentence">
                              <ui>Subject</ui>: Specify a subject line for the subscription email message.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src229" class="srcSentence">
                              <ui>Priority</ui>: Select the priority flag for this email message.</caps:sentence>
                            <caps:sentence id="src230" class="srcSentence"> Select <ui>Low</ui>, <ui>Normal</ui>, or <ui>High</ui>.</caps:sentence>
                            <caps:sentence id="src231" class="srcSentence"> The priority setting is used by Microsoft Exchange to set a flag indicating the importance of the email message.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src232" class="srcSentence">
                              <ui>Comment</ui>: Specify text to be added to the body of the subscription email message.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src233" class="srcSentence">
                              <ui>Description</ui>: Specify the description for this report subscription.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src234" class="srcSentence">
                              <ui>Include Link</ui>: Includes a URL to the subscribed report in the body of the email message.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src235" class="srcSentence">
                              <ui>Include Report</ui>: Specify that the report is attached to the e-mail message.</caps:sentence>
                            <caps:sentence id="src236" class="srcSentence"> The format in which the report will be attached is specified in the <ui>Render Format</ui> list.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src237" class="srcSentence">
                              <ui>Render Format</ui>: Select one of the following formats for the attached report:</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence id="src238" class="srcSentence">
                                  <ui>XML file with report data</ui>: Saves the report in Extensible Markup Language format.</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src239" class="srcSentence">
                                  <ui>CSV (comma delimited)</ui>: Saves the report in comma-separated-value format.</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src240" class="srcSentence">
                                  <ui>TIFF file</ui>: Saves the report in Tagged Image File Format.</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src241" class="srcSentence">
                                  <ui>Acrobat (PDF) file</ui>: Saves the report in Acrobat Portable Document Format.</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src242" class="srcSentence">
                                  <ui>MHTML (web archive)</ui>: Saves the report in MIME HTML format (mhtml), which is viewable in many web browsers.</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src243" class="srcSentence">
                                  <ui>Excel</ui>: Saves the report as a Microsoft Excel spreadsheet.</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src244" class="srcSentence">
                                  <ui>Word</ui>: Saves the report as a Microsoft Word document.</caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </listItem>
                      </list>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src245" class="srcSentence">On the <ui>Subscription Schedule</ui> page, select one of the following delivery schedule options for the report subscription:</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence id="src246" class="srcSentence">
                              <ui>Use shared schedule</ui>: A shared schedule is a previously defined schedule that can be used by other report subscriptions.</caps:sentence>
                            <caps:sentence id="src247" class="srcSentence"> Select this check box, and then select a shared schedule in the list if any have been specified.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src248" class="srcSentence">
                              <ui>Create new schedule</ui>: Configure the schedule on which this report will run, including the interval, start time and date, and the end date for this subscription.</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src249" class="srcSentence">On the <ui>Subscription Parameters</ui> page, specify the parameters for this report that are used when it is run unattended.</caps:sentence>
                        <caps:sentence id="src250" class="srcSentence"> When there are no parameters for the report, this page is not displayed.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src251" class="srcSentence">On the <ui>Summary</ui> page, review the report subscription settings.</caps:sentence>
                        <caps:sentence id="src252" class="srcSentence"> Click <ui>Previous</ui> to change the settings or click <ui>Next</ui> to create the report subscription.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src253" class="srcSentence">On the <ui>Completion</ui> page, click <ui>Close</ui> to exit the wizard.</caps:sentence>
                        <caps:sentence id="src254" class="srcSentence"> Verify that the report subscription was created successfully.</caps:sentence>
                        <caps:sentence id="src255" class="srcSentence"> You can view and modify report subscriptions in the <ui>Subscriptions</ui> node under <ui>Reporting</ui> in the <ui>Monitoring</ui> workspace.</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
            </content>
          </section>
        </sections>
      </section>
      <relatedTopics>
        <link xlink:href="78c1f344-4d72-4718-aad9-3a3834b64dbd">Reporting in Configuration Manager</link>
      </relatedTopics>
    </developerWalkthroughDocument>
  </caps:SxSSource>
</caps:SxS>
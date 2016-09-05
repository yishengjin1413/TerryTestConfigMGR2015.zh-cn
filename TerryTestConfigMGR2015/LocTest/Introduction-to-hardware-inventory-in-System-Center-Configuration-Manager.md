---
title: "System Center Configuration Manager 中的硬件清单简介"
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
ms.assetid: 3969952e-9d05-49c9-82a2-e7e90ccef511
caps.latest.revision: 6
caps.handback.revision: 4
author: barlanmsft
---
# System Center Configuration Manager 中的硬件清单简介
<?xml version="1.0" encoding="utf-8"?>
<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  <caps:SxSTarget locale="zh-CN">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence sentenceid="ce01279fab1fe2d41a14d6915cedd6a9" id="tgt1" class="tgtSentence">使用 <token>cm6long</token> 中的硬件清单可收集有关组织中的客户端设备硬件配置的信息。</caps:sentence>
          <caps:sentence sentenceid="d7dd91dadf82aaf130b0770b91922319" id="tgt2" class="tgtSentence"> 要收集硬件清单，必须在客户端设置中启用“针对客户端启用硬件清单”<ui></ui>设置。</caps:sentence>
        </para>
        <para>
          <caps:sentence sentenceid="139d91e698ae55a18965f0f0275ebf34" id="tgt3" class="tgtSentence">启用硬件清单并且由客户端运行硬件清单周期之后，客户端会将它收集的清单信息发送到客户端站点中的管理点。</caps:sentence>
          <caps:sentence sentenceid="a1cef4662f775e33fe6818319382e073" id="tgt4" class="tgtSentence"> 随后，管理点将清单信息转发到 <token>cmshort</token> 站点服务器，后者会将清单信息存储在站点数据库中。</caps:sentence>
          <caps:sentence sentenceid="3c52b1302e1693096b4d977e16c1e2ce" id="tgt5" class="tgtSentence"> 硬件清单会根据你在客户端设置中指定的计划在客户端上运行。</caps:sentence>
        </para>
        <para>
          <caps:sentence sentenceid="407f5d088da78a63672453db0bdbbd4e" id="tgt6" class="tgtSentence">可以使用几种方法来查看 <token>cmshort</token> 收集的硬件清单数据。</caps:sentence>
          <caps:sentence sentenceid="d5b12e0528417b20581aadb32c37c1fe" id="tgt7" class="tgtSentence"> 这些存储包括以下各项：</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              <caps:sentence sentenceid="6d18a308ea44c3a32422f07c2d6897e3" id="tgt8" class="tgtSentence">创建返回基于特定硬件配置的设备的查询。</caps:sentence>
              <caps:sentence sentenceid="2bea7dd5711f892e32a74248af2b942d" id="tgt9" class="tgtSentence"> 有关详细信息，请参阅 <link xlink:href="727bca0d-6458-48dc-9a63-3b66d9799ddb">Queries in Configuration Manager</link>。</caps:sentence>
            </para>
          </listItem>
          <listItem>
            <para>
              <caps:sentence sentenceid="6f56a3d9630c4041de6e444f97e40086" id="tgt10" class="tgtSentence">创建基于特定硬件配置的基于查询的集合。</caps:sentence>
              <caps:sentence sentenceid="699e4e4150275bdb71f42e21204c88b7" id="tgt11" class="tgtSentence"> 基于查询的集合成员身份会按计划自动更新。</caps:sentence>
              <caps:sentence sentenceid="15ecb5d1337f454acd051d92949bddb8" id="tgt12" class="tgtSentence"> 可以将集合用于多个任务（包括软件部署）。</caps:sentence>
              <caps:sentence sentenceid="30bcc2425d923b6cd4bf527efd0684ed" id="tgt13" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="4074d4fd-7a9b-4b80-9a0d-f4bfc63914fa">Collections in Configuration Manager</link>。</caps:sentence>
            </para>
          </listItem>
          <listItem>
            <para>
              <caps:sentence sentenceid="a94f98801c24c5f7a74948247faf71b7" id="tgt14" class="tgtSentence">运行显示有关组织中硬件配置的特定详细信息的报表。</caps:sentence>
              <caps:sentence sentenceid="188382bf5c64d0896d72ca07ca5eaa1b" id="tgt15" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="78c1f344-4d72-4718-aad9-3a3834b64dbd">Reporting in Configuration Manager</link>。</caps:sentence>
            </para>
          </listItem>
          <listItem>
            <para>
              <caps:sentence sentenceid="a9ec990ce3fcf3bf86f9f2bbdaf22552" id="tgt16" class="tgtSentence">使用资源浏览器查看有关从客户端设备收集的硬件清单的详细信息。</caps:sentence>
              <caps:sentence sentenceid="71040319e68ab4707e941cfc35f6b0f4" id="tgt17" class="tgtSentence"> 有关详细信息，请参阅 <link xlink:href="375912f5-436d-4315-bdbe-d77afee6c9f3">How to use Resource Explorer to view hardware inventory in Configuration Manager</link>。</caps:sentence>
            </para>
          </listItem>
        </list>
        <para>
          <caps:sentence sentenceid="05066382fbf35abf6afb64f9681675cd" id="tgt18" class="tgtSentence">当硬件清单在客户端设备上运行时，客户端返回的第一批清单数据始终是完整清单。</caps:sentence>
          <caps:sentence sentenceid="5919c8fb9f79ddf9ba7b9acd570fe216" id="tgt19" class="tgtSentence"> 后续清单信息仅包含增量清单信息。</caps:sentence>
          <caps:sentence sentenceid="6561d14c809bfdbe21b7c7da1cebcc43" id="tgt20" class="tgtSentence"> 站点服务器按收到增量清单信息的顺序对它进行处理。</caps:sentence>
          <caps:sentence sentenceid="040d666edae68db342f2693195848278" id="tgt21" class="tgtSentence"> 如果缺少客户端的增量清单信息，则站点服务器会拒绝其他增量清单信息，并指示客户端运行完整清单周期。</caps:sentence>
        </para>
        <para>
          <caps:sentence sentenceid="9e1608107ad5be9fb5e90616211d915b" id="tgt22" class="tgtSentence">
            <token>cmshort</token> 提供对双引导计算机的有限支持。</caps:sentence>
          <caps:sentence sentenceid="ac9560fa5a8aa493045e6c96922cf80b" id="tgt23" class="tgtSentence">
            <token>cmshort</token> 可以发现双引导计算机，但只从在清单周期运行时处于活动状态的操作系统返回清单信息。</caps:sentence>
        </para>
        <alert class="note">
          <para>
            <caps:sentence sentenceid="13d0f68b103f2d4701de744232e114b2" id="tgt24" class="tgtSentence">有关如何将硬件清单用于运行 Linux 和 UNIX 的客户端的信息，请参阅 <link xlink:href="1026d616-2a20-4fb2-8604-d331763937f8">Hardware inventory for Linux and UNIX in Configuration Manager</link>。</caps:sentence>
          </para>
        </alert>
      </introduction>
      <section expanded="true">
        <title>
          <caps:sentence sentenceid="af2f1bd7a6600312613da1ec48869a0b" id="tgt25" class="tgtSentence">扩展 Configuration Manager 硬件清单</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="595337083443dc686c8b00d2e89b1406" id="tgt26" class="tgtSentence">除了 <token>cmshort</token> 中的内置硬件清单，还可以使用以下方法之一来扩展硬件清单以收集其他信息：</caps:sentence>
          </para>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="ea9f6aca279138c58f705c8d4cb4b8ce" id="tgt27" class="tgtSentence">方法</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="67daf92c833c41c95db874e18fcb2786" id="tgt28" class="tgtSentence">描述</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="c1db1c953ee2ce151c3c9d3226e9650e" id="tgt29" class="tgtSentence">从 <token>cmshort</token> 控制台添加和删除清单类</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="a5d94a79dd9f6841039a093ff4af322e" id="tgt30" class="tgtSentence">在 <token>cmshort</token> 中，你可以从 <token>cmshort</token> 控制台为硬件清单启用、禁用、添加和删除清单类。</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="d9ddfe493de7a6faa8cacac405429029" id="tgt31" class="tgtSentence">NOIDMIF 文件</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="98b968a90c356773eea9eabd61069a54" id="tgt32" class="tgtSentence">使用 NOIDMIF 文件可收集有关无法由 <token>cmshort</token> 列出清单的客户端设备的信息。</caps:sentence>
                    <caps:sentence sentenceid="db9696ffb4ef7067a3a68032605704b2" id="tgt33" class="tgtSentence"> 例如，你可能要收集仅作为设备上的标签存在的设备资产编号信息。</caps:sentence>
                    <caps:sentence sentenceid="3c4af37a6eaad59dfffd6d6992340046" id="tgt34" class="tgtSentence"> NOIDMIF 清单会自动与从中收集到它的客户端设备相关联。</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="e971d1e6d1d82f0780f5410e75ab5b32" id="tgt35" class="tgtSentence">IDMIF 文件</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="23b5d7f0537587d21ba0365825efe3f2" id="tgt36" class="tgtSentence">使用 IDMIF 文件可收集有关组织中不与 <token>cmshort</token> 客户端关联的资产（例如，投影仪、复印机和网络打印机）的信息。</caps:sentence>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
          <para>
            <caps:sentence sentenceid="76d9fd020aae8b9310f615de345f5b9d" id="tgt37" class="tgtSentence">有关使用这些方法扩展 <token>cmshort</token> 硬件清单的详细信息，请参阅<link xlink:href="0e45290e-f8f7-4335-801e-570225d12c2b">How to extend hardware inventory in Configuration Manager</link>。</caps:sentence>
          </para>
        </content>
      </section>
      <relatedTopics>
        <link xlink:href="77419bd8-548c-4f0f-beed-1ea0f752a4c7">Hardware inventory in Configuration Manager</link>
      </relatedTopics>
    </developerConceptualDocument>
  </caps:SxSTarget>
  <caps:SxSSource locale="en-US">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence id="src1" class="srcSentence">Use hardware inventory in <token>cm6long</token> to collect information about the hardware configuration of client devices in your organization.</caps:sentence>
          <caps:sentence id="src2" class="srcSentence"> To collect hardware inventory, the <ui>Enable hardware inventory on clients</ui> setting must be enabled in client settings.</caps:sentence>
        </para>
        <para>
          <caps:sentence id="src3" class="srcSentence">After hardware inventory is enabled and a hardware inventory cycle is run by the client, the client sends the inventory information that it has collected to a management point in the client’s site.</caps:sentence>
          <caps:sentence id="src4" class="srcSentence"> The management point then forwards the inventory information to the <token>cmshort</token> site server which stores the inventory information in the site database.</caps:sentence>
          <caps:sentence id="src5" class="srcSentence"> Hardware inventory runs on clients according to the schedule that you specify in client settings.</caps:sentence>
        </para>
        <para>
          <caps:sentence id="src6" class="srcSentence">You can use several methods to view the hardware inventory data that <token>cmshort</token> collects.</caps:sentence>
          <caps:sentence id="src7" class="srcSentence"> These include the following:</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              <caps:sentence id="src8" class="srcSentence">Create queries that return devices that are based on a specific hardware configuration.</caps:sentence>
              <caps:sentence id="src9" class="srcSentence"> For more information, see <link xlink:href="727bca0d-6458-48dc-9a63-3b66d9799ddb">Queries in Configuration Manager</link>.</caps:sentence>
            </para>
          </listItem>
          <listItem>
            <para>
              <caps:sentence id="src10" class="srcSentence">Create query-based collections that are based on a specific hardware configuration.</caps:sentence>
              <caps:sentence id="src11" class="srcSentence"> Query-based collection memberships automatically update on a schedule.</caps:sentence>
              <caps:sentence id="src12" class="srcSentence"> You can use collections for several tasks, which include software deployment.</caps:sentence>
              <caps:sentence id="src13" class="srcSentence"> For more information, see <link xlink:href="4074d4fd-7a9b-4b80-9a0d-f4bfc63914fa">Collections in Configuration Manager</link>.</caps:sentence>
            </para>
          </listItem>
          <listItem>
            <para>
              <caps:sentence id="src14" class="srcSentence">Run reports that display specific details about hardware configurations in your organization.</caps:sentence>
              <caps:sentence id="src15" class="srcSentence"> For more information, see <link xlink:href="78c1f344-4d72-4718-aad9-3a3834b64dbd">Reporting in Configuration Manager</link>.</caps:sentence>
            </para>
          </listItem>
          <listItem>
            <para>
              <caps:sentence id="src16" class="srcSentence">Use Resource Explorer to view detailed information about the hardware inventory that is collected from client devices.</caps:sentence>
              <caps:sentence id="src17" class="srcSentence"> For more information, see <link xlink:href="375912f5-436d-4315-bdbe-d77afee6c9f3">How to use Resource Explorer to view hardware inventory in Configuration Manager</link>.</caps:sentence>
            </para>
          </listItem>
        </list>
        <para>
          <caps:sentence id="src18" class="srcSentence">When hardware inventory runs on a client device, the first inventory data that the client returns is always a full inventory.</caps:sentence>
          <caps:sentence id="src19" class="srcSentence"> Subsequent inventory information contains only delta inventory information.</caps:sentence>
          <caps:sentence id="src20" class="srcSentence"> The site server processes delta inventory information in the order in which it is received.</caps:sentence>
          <caps:sentence id="src21" class="srcSentence"> If delta inventory information for a client is missing, the site server rejects additional delta inventory information and instructs the client to run a full inventory cycle.</caps:sentence>
        </para>
        <para>
          <caps:sentence id="src22" class="srcSentence">
            <token>cmshort</token> provides limited support for dual-boot computers.</caps:sentence>
          <caps:sentence id="src23" class="srcSentence">
            <token>cmshort</token> can discover dual-boot computers but only returns inventory information from the operating system that was active at the time the inventory cycle ran.</caps:sentence>
        </para>
        <alert class="note">
          <para>
            <caps:sentence id="src24" class="srcSentence">For information about how to use hardware inventory with clients that run Linux and UNIX, see <link xlink:href="1026d616-2a20-4fb2-8604-d331763937f8">Hardware inventory for Linux and UNIX in Configuration Manager</link>.</caps:sentence>
          </para>
        </alert>
      </introduction>
      <section expanded="true">
        <title>
          <caps:sentence id="src25" class="srcSentence">Extending Configuration Manager hardware inventory</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src26" class="srcSentence">In addition to the built-in hardware inventory in <token>cmshort</token>, you can also use one of the following methods to extend hardware inventory to collect additional information:</caps:sentence>
          </para>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src27" class="srcSentence">Method</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src28" class="srcSentence">Description</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src29" class="srcSentence">Add and remove inventory classes from the <token>cmshort</token> console</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src30" class="srcSentence">In <token>cmshort</token>, you can enable, disable, add and remove inventory classes for hardware inventory from the <token>cmshort</token> console.</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src31" class="srcSentence">NOIDMIF files</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src32" class="srcSentence">Use NOIDMIF files to collect information about client devices that cannot be inventoried by <token>cmshort</token>.</caps:sentence>
                    <caps:sentence id="src33" class="srcSentence"> For example, you might want to collect device asset number information that exists only as a label on the device.</caps:sentence>
                    <caps:sentence id="src34" class="srcSentence"> NOIDMIF inventory is automatically associated with the client device that it was collected from.</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src35" class="srcSentence">IDMIF files</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src36" class="srcSentence">Use IDMIF files to collect information about assets in your organization that are not associated with a <token>cmshort</token> client, for example, projectors, photocopiers and network printers.</caps:sentence>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
          <para>
            <caps:sentence id="src37" class="srcSentence">For more information about using these methods to extend <token>cmshort</token> hardware inventory, see <link xlink:href="0e45290e-f8f7-4335-801e-570225d12c2b">How to extend hardware inventory in Configuration Manager</link>.</caps:sentence>
          </para>
        </content>
      </section>
      <relatedTopics>
        <link xlink:href="77419bd8-548c-4f0f-beed-1ea0f752a4c7">Hardware inventory in Configuration Manager</link>
      </relatedTopics>
    </developerConceptualDocument>
  </caps:SxSSource>
</caps:SxS>
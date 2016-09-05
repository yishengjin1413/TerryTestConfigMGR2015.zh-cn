---
title: "在 System Center Configuration Manager 中规划监视迁移活动"
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
ms.assetid: fc731d3f-edd7-4049-b17b-653d6693a564
caps.latest.revision: 4
caps.handback.revision: 3
---
# 在 System Center Configuration Manager 中规划监视迁移活动
<?xml version="1.0" encoding="utf-8"?>
<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  <caps:SxSTarget locale="zh-CN">
    <developerWalkthroughDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence sentenceid="c3c8089dd37f5f407b4b98518dd40f67" id="tgt1" class="tgtSentence">利用 <token>cm6long</token>，你可以在连接到目标层次结构的 <token>cmshort</token> 控制台中监视迁移。</caps:sentence>
          <caps:sentence sentenceid="27121b47eb769466d0a34b55300a1744" id="tgt2" class="tgtSentence"> 在“管理”<ui></ui>工作区的 <token>cmshort</token> 控制台中，可以使用“迁移”<ui></ui>节点监视迁移工作的进度和成功情况。</caps:sentence>
          <caps:sentence sentenceid="b1daa9e40228722a1f0e947becb5f404" id="tgt3" class="tgtSentence"> 你可以查看每个迁移作业的摘要信息，该信息确定已迁移的对象、尚未迁移的那些对象，以及从迁移作业中排除的对象的数量。</caps:sentence>
          <caps:sentence sentenceid="fbd279bbc5e3efc94997c9b78f73a4f3" id="tgt4" class="tgtSentence"> 你还将看到有关任何迁移问题的详细信息。</caps:sentence>
        </para>
      </introduction>
      <section>
        <title>
          <caps:sentence sentenceid="4048c896f11051ba0fa8296bdca78540" id="tgt5" class="tgtSentence">查看迁移进度</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="4015248c4556cc835e80c57c8fadffa3" id="tgt6" class="tgtSentence">若要查看迁移作业的进度，请使用下列任何操作： </caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="be6915b616a81bfba5481d9135893126" id="tgt7" class="tgtSentence">在<ui></ui>“管理”工作区中的 <token>cmshort</token> 控制台中，展开“迁移作业”<ui></ui>节点，选择一个迁移作业，然后选择“作业中的对象”<ui></ui>选项卡。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="469e471c56a67d58d29f21f5d1493dfb" id="tgt8" class="tgtSentence">使用 <token>cmshort</token> 日志文件来查看迁移进度或确定任何问题。</caps:sentence>
                <caps:sentence sentenceid="1884c6f6d2da00cef3489c59f924d85f" id="tgt9" class="tgtSentence"> 迁移管理器是 <token>cmshort</token> 过程，用于跟踪迁移操作并将这些操作记录在站点服务器上 <system>&lt;InstallationPath&gt;\LOGS</system> 文件夹中的 migmctrl.log 文件中。</caps:sentence>
              </para>
              <alert class="note">
                <para>
                  <caps:sentence sentenceid="64ea087ff1edeec83d1085daaeff6ebc" id="tgt10" class="tgtSentence">如果迁移作业失败，请尽快在 migmctrl.log 文件中查看详细信息。</caps:sentence>
                  <caps:sentence sentenceid="1927383526e199783c3b005a7743bb79" id="tgt11" class="tgtSentence"> 迁移日志条目会一直添加到该文件中并覆盖旧详细信息。</caps:sentence>
                  <caps:sentence sentenceid="d9b79d4e313f422a4f73c1942157fcfa" id="tgt12" class="tgtSentence"> 如果条目被覆盖，你可能无法确定你可能遇到的任何迁移对象问题是否与迁移问题相关。</caps:sentence>
                  <caps:sentence sentenceid="fe1446e2fcc66c79ad5a09ac619240fa" id="tgt13" class="tgtSentence"> 不管在配置迁移时 <token>cmshort</token> 控制台连接到哪个站点，迁移活动都记录在层次结构的顶层站点上。</caps:sentence>
                </para>
              </alert>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="3e4fb9f62cbaddb949ef6bc3b046e6ac" id="tgt14" class="tgtSentence">使用 <token>cmshort</token> 报表。</caps:sentence>
                <caps:sentence sentenceid="db1ee2d4fabef4bfa311594ee0b3329d" id="tgt15" class="tgtSentence">
                  <token>cmshort</token> 提供若干内置迁移报表，也可对它们进行编辑以适应你的需求。</caps:sentence>
                <caps:sentence sentenceid="20c3c99ab0d3d3836b754310dbbaf4f2" id="tgt16" class="tgtSentence"> 有关 <token>cmshort</token> 报表的详细信息，请参阅 <link xlink:href="78c1f344-4d72-4718-aad9-3a3834b64dbd">Reporting in Configuration Manager</link>。</caps:sentence>
              </para>
            </listItem>
          </list>
        </content>
      </section>
      <relatedTopics>
        <link xlink:href="b2bf493e-1e10-496f-a139-2646522703ed">Planning for Migration to System Center Configuration Manager</link>
      </relatedTopics>
    </developerWalkthroughDocument>
  </caps:SxSTarget>
  <caps:SxSSource locale="en-US">
    <developerWalkthroughDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence id="src1" class="srcSentence">With <token>cm6long</token>, you can monitor migration in the <token>cmshort</token> console that connects to the destination hierarchy.</caps:sentence>
          <caps:sentence id="src2" class="srcSentence"> In the <token>cmshort</token> console in the <ui>Administration</ui> workspace, you can use the <ui>Migration</ui> node to monitor the progress and success of migration jobs.</caps:sentence>
          <caps:sentence id="src3" class="srcSentence"> You can view summary information for each migration job that identifies objects that have migrated, those objects that have not yet migrated, and the number of objects that are excluded from a migration job.</caps:sentence>
          <caps:sentence id="src4" class="srcSentence"> You will also see details about any migration problems.</caps:sentence>
        </para>
      </introduction>
      <section>
        <title>
          <caps:sentence id="src5" class="srcSentence">View Migration Progress</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src6" class="srcSentence">To view the progress of a migration job, use any of the following actions: </caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src7" class="srcSentence">In the <ui>Administration</ui> workspace of the <token>cmshort</token> console, expand the <ui>Migration Jobs</ui> node, select a migration job, and then select the <ui>Objects in Job</ui> tab.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src8" class="srcSentence">Use the <token>cmshort</token> log files to review the migration progress or to identify any problems.</caps:sentence>
                <caps:sentence id="src9" class="srcSentence"> Migration Manager is the <token>cmshort</token> process that tracks migration actions and records these in the migmctrl.log file in the <system>&lt;InstallationPath&gt;\LOGS</system> folder on the site server.</caps:sentence>
              </para>
              <alert class="note">
                <para>
                  <caps:sentence id="src10" class="srcSentence">If a migration job fails, review the details in the migmctrl.log file as soon as possible.</caps:sentence>
                  <caps:sentence id="src11" class="srcSentence"> The migration log entries are continually added to the file and overwrite old details.</caps:sentence>
                  <caps:sentence id="src12" class="srcSentence"> If the entries are overwritten, you might not be able to identify whether any problems that you might encounter with the migrated objects relate to migration issues.</caps:sentence>
                  <caps:sentence id="src13" class="srcSentence"> Migration activity is logged at the top-level site of the hierarchy regardless of the site your <token>cmshort</token> console connects to when you configure migration.</caps:sentence>
                </para>
              </alert>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src14" class="srcSentence">Use <token>cmshort</token> reporting.</caps:sentence>
                <caps:sentence id="src15" class="srcSentence">
                  <token>cmshort</token> provides several built-in reports for migration, or you can edit those reports to fit your requirements.</caps:sentence>
                <caps:sentence id="src16" class="srcSentence"> For more information about <token>cmshort</token> reports, see <link xlink:href="78c1f344-4d72-4718-aad9-3a3834b64dbd">Reporting in Configuration Manager</link>.</caps:sentence>
              </para>
            </listItem>
          </list>
        </content>
      </section>
      <relatedTopics>
        <link xlink:href="b2bf493e-1e10-496f-a139-2646522703ed">Planning for Migration to System Center Configuration Manager</link>
      </relatedTopics>
    </developerWalkthroughDocument>
  </caps:SxSSource>
</caps:SxS>
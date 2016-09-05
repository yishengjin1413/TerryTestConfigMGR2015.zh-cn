---
title: "如何在 System Center Configuration Manager 中监视 Endpoint Protection"
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
ms.assetid: f4a1335c-bb3d-493e-a124-83a32a107dc8
caps.latest.revision: 8
caps.handback.revision: 5
---
# 如何在 System Center Configuration Manager 中监视 Endpoint Protection
<?xml version="1.0" encoding="utf-8"?>
<developerWalkthroughDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd">
  <introduction>
    <para>你可以通过使用“监视”<ui></ui>工作区中的 <ui><token>epshort</token> 状态</ui>节点、“资产和符合性”<ui></ui>工作区中的 <ui><token>epshort</token></ui> 节点，以及使用报表来监视 <token>cm5long</token> 层次结构中的 <token>epshort</token>。</para>
  </introduction>
  <section address="BKMK_1" expanded="false">
    <title>如何使用 <token>epshort</token> 状态节点监视 <token>epshort</token></title>
    <content>
      <para/>
      <procedure>
        <title/>
        <steps class="ordered">
          <step>
            <content>
              <para>在 <token>cmshort</token> 控制台中，单击“监视”<ui></ui></para>
            </content>
          </step>
          <step>
            <content>
              <para>在“监视”<ui></ui>工作区，单击 <ui><token>epshort</token> 状态</ui>。</para>
            </content>
          </step>
          <step>
            <content>
              <para>在“集合”<ui></ui>列表中，选择你想要查看其状态信息的集合。</para>
              <alert class="important">
                <para>集合在以下情况下可供选择：</para>
                <list class="bullet">
                  <listItem>
                    <para>当在<placeholder>&lt;集合名称&gt;</placeholder> <ui>属性</ui>对话框的“警报”<ui></ui>选项卡上的 <token>epshort</token> 仪表板中</ui>选择<ui>查看该集合时。</para>
                  </listItem>
                  <listItem>
                    <para>当部署 <token>epshort</token> 反恶意软件政策到该集合时。</para>
                  </listItem>
                  <listItem>
                    <para>当启用并部署 <token>epshort</token> 客户端设置到该集合时。</para>
                  </listItem>
                </list>
              </alert>
            </content>
          </step>
          <step>
            <content>
              <para>查看显示在“安全状态”<ui></ui>和“操作状态”<ui></ui>部分的信息。 可以单击任何状态链接，以在“资产和符合性”<ui></ui>工作区的“设备”<ui></ui>节点下创建临时集合。 此临时集合包含具有所选状态的计算机。</para>
              <alert class="important">
                <para>显示在 <ui><token>epshort</token> 状态</ui>节点上的信息基于 <token>cmshort</token> 数据库中汇总的最后的数据，可能不是最新的。 如果想要检索最新数据，则在“主页”<ui></ui>选项卡上，单击“运行摘要”<ui></ui>，或单击“计划摘要”<ui></ui>以调整摘要间隔。</para>
              </alert>
            </content>
          </step>
        </steps>
      </procedure>
    </content>
  </section>
  <section address="BKMK_2" expanded="false">
    <title>如何监视资产和符合性工作区中的 <token>epshort</token></title>
    <content>
      <para/>
      <procedure>
        <title/>
        <steps class="ordered">
          <step>
            <content>
              <para>在 <token>cmshort</token> 控制台中，单击“资产和符合性”<ui></ui>。</para>
            </content>
          </step>
          <step>
            <content>
              <para>在“资产和符合性”<ui></ui>工作区中，执行以下操作之一：</para>
              <list class="bullet">
                <listItem>
                  <para>单击“设备”<ui></ui>。 在“设备”<ui></ui>列表中，选择一台计算机，然后单击“恶意软件详细信息”<ui></ui>选项卡。</para>
                </listItem>
                <listItem>
                  <para>单击“设备集合”<ui></ui>。 在“设备集合”<ui></ui>列表中，选择包含你想要监视的计算机的集合，然后在“主页”<ui></ui>选项卡上，在“集合”<ui></ui>组中，单击“显示成员”<ui></ui>。</para>
                </listItem>
              </list>
            </content>
          </step>
          <step>
            <content>
              <para>在“集合名称”<placeholder>&lt;&gt;</placeholder>列表中，选择一台计算机，然后单击“恶意软件详细信息”<ui></ui>选项卡。</para>
            </content>
          </step>
        </steps>
      </procedure>
    </content>
  </section>
  <section address="BKMK_3" expanded="false">
    <title>如何使用报表监视 <token>epshort</token></title>
    <content>
      <para>使用下列报表来帮助你查看有关层次结构中 <token>epshort</token> 的信息。 你还可以使用这些报表来帮助针对任何 <token>epshort</token> 问题进行故障排除。 有关如何在 <token>cmshort</token> 中配置报表的详细信息，请参阅 <link xlink:href="78c1f344-4d72-4718-aad9-3a3834b64dbd">Configuration Manager 中的报表</link>和 <link xlink:href="c1ff371e-b0ad-4048-aeda-02a9ff08889e">Configuration Manager 中的日志文件</link>。 <token>Epshort</token> 报表位于 <token>epshort</token> 文件夹中。</para>
      <table xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
        <thead>
          <tr>
            <TD>
              <para>报告名称</para>
            </TD>
            <TD>
              <para>描述</para>
            </TD>
          </tr>
        </thead>
        <tbody>
          <tr>
            <TD>
              <para>
                <ui>反恶意软件活动报告</ui>
              </para>
            </TD>
            <TD>
              <para>显示指定集合的反恶意软件活动的概述。</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>
                <ui>受感染的计算机</ui>
              </para>
            </TD>
            <TD>
              <para>显示在其检测到指定的威胁的计算机的列表。</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>
                <ui>通过威胁的前几名用户</ui>
              </para>
            </TD>
            <TD>
              <para>显示具有最多的检测到的威胁的用户列表。</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>
                <ui>用户威胁列表</ui>
              </para>
            </TD>
            <TD>
              <para>显示已找到指定的用户帐户的威胁的列表。</para>
            </TD>
          </tr>
        </tbody>
      </table>
    </content>
  </section>
  <section expanded="false">
    <title>恶意软件警报级别</title>
    <content>
      <para>使用下表来标识可能会显示在报表中或显示在 <token>cmshort</token> 控制台中的不同 <token>epshort</token> 警报级别。</para>
      <table xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
        <thead>
          <tr>
            <TD>
              <para>警报级别</para>
            </TD>
            <TD>
              <para>描述</para>
            </TD>
          </tr>
        </thead>
        <tbody>
          <tr>
            <TD>
              <para>
                <ui>已失败</ui>
              </para>
            </TD>
            <TD>
              <para>
                <token>Epshort</token> 未能修正恶意软件。 检查日志以获取错误的详细信息。</para>
              <alert class="note">
                <para>有关 <token>cmshort</token> 和 <token>epshort</token> 日志文件的列表，请参阅 <link xlink:href="c1ff371e-b0ad-4048-aeda-02a9ff08889e">Configuration Manager 中的日志文件</link>主题中的“Endpoint Protection”部分。</para>
              </alert>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>
                <ui>已删除</ui>
              </para>
            </TD>
            <TD>
              <para>
                <token>Epshort</token> 已成功删除了恶意软件。</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>
                <ui>已隔离</ui>
              </para>
            </TD>
            <TD>
              <para>
                <token>Epshort</token> 已将恶意软件移动到一个安全位置，并已阻止其运行，直到你将其删除或允许其运行。</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>
                <ui>已清理</ui>
              </para>
            </TD>
            <TD>
              <para>恶意软件已清理受感染的文件中。</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>
                <ui>允许</ui>
              </para>
            </TD>
            <TD>
              <para>管理用户选择允许包含要运行的恶意软件的软件。</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>
                <ui>不执行任何操作</ui>
              </para>
            </TD>
            <TD>
              <para>
                <token>Epshort</token> 对恶意软件不执行任何操作。 如果重新启动计算机后检测到恶意软件和不能再检测到恶意软件 ； 这可能会发生例如，如果映射的网络驱动器上检测到的恶意软件是不重新连接时在计算机重新启动。</para>
            </TD>
          </tr>
          <tr>
            <TD>
              <para>
                <ui>已阻止</ui>
              </para>
            </TD>
            <TD>
              <para>
                <token>Epshort</token> 已阻止恶意软件运行。 这可能是如果发现计算机上的进程是包含恶意软件。</para>
            </TD>
          </tr>
        </tbody>
      </table>
    </content>
  </section>
  <relatedTopics>
    
  </relatedTopics>
</developerWalkthroughDocument>

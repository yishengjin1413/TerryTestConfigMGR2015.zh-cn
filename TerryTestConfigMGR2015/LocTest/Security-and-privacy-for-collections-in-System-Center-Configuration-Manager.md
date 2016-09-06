---
title: "System Center Configuration Manager 中的集合的安全和隐私"
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
ms.assetid: 30bf2451-5415-4be2-ba8d-21759370cd83
caps.latest.revision: 5
caps.handback.revision: 3
author: barlanmsft
translationtype: Human Translation
---
# System Center Configuration Manager 中的集合的安全和隐私
<?xml version="1.0" encoding="utf-8"?>
<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  <caps:SxSTarget locale="zh-CN">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence sentenceid="ae5d1e53dc8dd7b65a394ca59e232d8c" id="tgt1" class="tgtSentence">本主题包含 <token>cm6long</token> 中的集合的安全最佳方案和隐私信息。</caps:sentence>
        </para>
        <para>
          <caps:sentence sentenceid="b67726891c2c6037c2f4b2a29816dc74" id="tgt2" class="tgtSentence">没有专门针对 <token>cmshort</token> 中的集合的隐私信息。</caps:sentence>
          <caps:sentence sentenceid="659272b3636404e05d1be7057dc68c00" id="tgt3" class="tgtSentence"> 集合是资源（如用户和设备）的容器。</caps:sentence>
          <caps:sentence sentenceid="a62d181fb68fa315a2529e50233dd8f1" id="tgt4" class="tgtSentence"> 集合成员身份通常依赖于 <token>cmshort</token> 在标准操作过程中收集的信息。</caps:sentence>
          <caps:sentence sentenceid="31aabc237eff47c760b9e8f4d12a0510" id="tgt5" class="tgtSentence"> 例如，通过使用从发现或清单收集的资源信息，可以将集合配置为包含满足指定条件的设备。</caps:sentence>
          <caps:sentence sentenceid="7557bae12a9e7fc6aaf12225c357757a" id="tgt6" class="tgtSentence"> 集合还可以基于客户端管理操作的当前状态信息，例如正在部署软件和正在检查符合性。</caps:sentence>
          <caps:sentence sentenceid="71162266ebe1fbee4c6572826f599708" id="tgt7" class="tgtSentence"> 除了这些基于查询的集合，管理用户还可以将资源添加到集合。</caps:sentence>
        </para>
        <para>
          <caps:sentence sentenceid="9b6931b110faa644f825fdf7ce1ff0bd" id="tgt8" class="tgtSentence">有关集合的详细信息，请参阅 <link xlink:href="d17e1188-d277-438f-9236-db9cd213b421">Introduction to Collections in Configuration Manager</link>。</caps:sentence>
          <caps:sentence sentenceid="a50c7d8ef04127f3f12a369358b310e1" id="tgt9" class="tgtSentence"> 有关 <token>cmshort</token> 操作（可以用于配置集合成员身份）的任何安全最佳方案和隐私信息的详细信息，请参阅 <link xlink:href="b7bff8a0-fe76-4d3b-aac6-065290888bea">Security Best Practices and Privacy Information for System Center Configuration Manager</link>。</caps:sentence>
        </para>
      </introduction>
      <section>
        <title>
          <caps:sentence sentenceid="c5472a08217c383e9c34eba900876e4f" id="tgt10" class="tgtSentence">集合的最佳安全方案</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="eae555e1f16f7939f9118ec319ca24cf" id="tgt11" class="tgtSentence">可将以下最佳安全方案用于集合。</caps:sentence>
          </para>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="a7edd947b42e172210c31a4fdcbc3222" id="tgt12" class="tgtSentence">最佳安全方案</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="5dc731e46ae38b87ff3e3e2eaf459db2" id="tgt13" class="tgtSentence">更多信息</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="c08803329291a22663178ea253dca248" id="tgt14" class="tgtSentence">当你使用保存到网络位置的托管对象格式 (MOF) 文件导出或导入集合时，请保护该位置和网络通道的安全。</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="ed3c9868a04d19c1fa13e3c1b379360b" id="tgt15" class="tgtSentence">限制可访问网络文件夹的人员。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="5eca069f976647f4d79389dad1f5778c" id="tgt16" class="tgtSentence">在网络位置与站点服务器之间使用服务器消息块 (SMB) 签名或 Internet 协议安全性 (IPsec)，以防止攻击者篡改导出的集合数据。</caps:sentence>
                    <caps:sentence sentenceid="9084b86a46d759c7f6448bbfa48d1e53" id="tgt17" class="tgtSentence"> 使用 IPsec 对网络上的数据进行加密以防止信息泄漏。</caps:sentence>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
        <sections>
          <section>
            <title>
              <caps:sentence sentenceid="943bd1ffc09f6f85e1045fd1ecda3038" id="tgt18" class="tgtSentence">集合的安全问题</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="9b751b8987eb98faf32e460e9b072a03" id="tgt19" class="tgtSentence">集合具有以下安全问题：</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="07cfe6cdeb393af9317f51dcae1c6d71" id="tgt20" class="tgtSentence">如果使用集合变量，本地管理员可以读取可能敏感的信息。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="ba635642ea3d437cac62a57c2a783f79" id="tgt21" class="tgtSentence">在部署操作系统时，可以使用集合变量。</caps:sentence>
                  </para>
                </listItem>
              </list>
            </content>
          </section>
        </sections>
      </section>
      <relatedTopics>
        <link xlink:href="4074d4fd-7a9b-4b80-9a0d-f4bfc63914fa">Collections in Configuration Manager</link>
      </relatedTopics>
    </developerConceptualDocument>
  </caps:SxSTarget>
  <caps:SxSSource locale="en-US">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence id="src1" class="srcSentence">This topic contains security best practices and privacy information for collections in <token>cm6long</token>.</caps:sentence>
        </para>
        <para>
          <caps:sentence id="src2" class="srcSentence">There is no privacy information specifically for collections in <token>cmshort</token>.</caps:sentence>
          <caps:sentence id="src3" class="srcSentence"> Collections are containers for resources, such as users and devices.</caps:sentence>
          <caps:sentence id="src4" class="srcSentence"> Collection membership often depends on the information that <token>cmshort</token> collects during standard operation.</caps:sentence>
          <caps:sentence id="src5" class="srcSentence"> For example, by using resource information that has been collected from discovery or inventory, a collection can be configured to contain the devices that meet specified criteria.</caps:sentence>
          <caps:sentence id="src6" class="srcSentence"> Collections might also be based on the current status information for client management operations, such as deploying software and checking for compliance.</caps:sentence>
          <caps:sentence id="src7" class="srcSentence"> In addition to these query-based collections, administrative users can also add resources to collections.</caps:sentence>
        </para>
        <para>
          <caps:sentence id="src8" class="srcSentence">For more information about collections, see <link xlink:href="d17e1188-d277-438f-9236-db9cd213b421">Introduction to Collections in Configuration Manager</link>.</caps:sentence>
          <caps:sentence id="src9" class="srcSentence"> For more information about any security best practices and privacy information for <token>cmshort</token> operations that can be used to configure collection membership, see <link xlink:href="b7bff8a0-fe76-4d3b-aac6-065290888bea">Security Best Practices and Privacy Information for System Center Configuration Manager</link>.</caps:sentence>
        </para>
      </introduction>
      <section>
        <title>
          <caps:sentence id="src10" class="srcSentence">Security Best Practices for Collections</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src11" class="srcSentence">Use the following security best practice for collections.</caps:sentence>
          </para>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src12" class="srcSentence">Security best practice</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src13" class="srcSentence">More information</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src14" class="srcSentence">When you export or import a collection by using a Managed Object Format (MOF) file that is saved to a network location, secure the location, and secure the network channel.</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src15" class="srcSentence">Restricts who can access the network folder.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src16" class="srcSentence">Use Server Message Block (SMB) signing or Internet Protocol security (IPsec) between the network location and the site server to prevent an attacker from tampering with the exported collection data.</caps:sentence>
                    <caps:sentence id="src17" class="srcSentence"> Use IPsec to encrypt the data on the network to prevent information disclosure.</caps:sentence>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
        <sections>
          <section>
            <title>
              <caps:sentence id="src18" class="srcSentence">Security Issues for Collections</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src19" class="srcSentence">Collections have the following security issues:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src20" class="srcSentence">If you use collection variables, local administrators can read potentially sensitive information.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src21" class="srcSentence">Collection variables can be used when you deploy an operating system.</caps:sentence>
                  </para>
                </listItem>
              </list>
            </content>
          </section>
        </sections>
      </section>
      <relatedTopics>
        <link xlink:href="4074d4fd-7a9b-4b80-9a0d-f4bfc63914fa">Collections in Configuration Manager</link>
      </relatedTopics>
    </developerConceptualDocument>
  </caps:SxSSource>
</caps:SxS>
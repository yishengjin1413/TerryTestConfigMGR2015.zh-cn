---
title: "System Center Configuration Manager 中的语言包"
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
ms.assetid: cd74e5f5-33f6-4566-8c9d-d6a93bfe71ed
caps.latest.revision: 10
caps.handback.revision: 7
translationtype: Human Translation
---
# System Center Configuration Manager 中的语言包
<?xml version="1.0" encoding="utf-8"?>
<developerWalkthroughDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd">
  <introduction>
    <para>本主题提供有关 <token>cm6long</token> 中的语言支持的技术的详细信息。</para>
  </introduction>
  <section address="BKMK_SupLanguagePacks">
    <title>支持的操作系统语言</title>
    <content>
      <para>通过在管理中心站点和主站点中安装<embeddedLabel>服务器语言包</embeddedLabel>或<embeddedLabel>客户端语言包</embeddedLabel>，可以安装支持下列显示语言的功能。 在将安装程序作为先决条件和可再发行文件的下载的一部分运行时，会下载语言包。 在运行安装程序之前，你还可以使用 <link xlink:href="118de018-4add-45cd-8efa-e892a745971e#bkmk_SetupDownloader">Setup Downloader</link> 来下载这些文件。 在安装站点期间，你从可用的语言包文件中选择要在该站点支持的服务器和客户端语言。</para>
      <para>使用下表将区域设置 ID 对应到你要在服务器或客户端上支持的语言。 有关区域设置 ID 的详细信息，请参阅 MSDN 联机库中的 <externalLink><linkText>Locale IDs Assigned by Microsoft</linkText><linkUri> http://go.microsoft.com/fwlink/p/?LinkId=252609</linkUri></externalLink>（Microsoft 指定的区域设置 ID）。</para>
    </content>
    <sections>
      <section expanded="false">
        <title>服务器语言</title>
        <content>
          <table xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
            <thead>
              <tr>
                <TD>
                  <para>服务器语言 </para>
                </TD>
                <TD>
                  <para>区域设置 ID (LCID) </para>
                </TD>
                <TD>
                  <para>三个字母的代码</para>
                </TD>
                
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>英语（默认）</para>
                </TD>
                <TD>
                  <para>0409</para>
                </TD>
                <TD>
                  <para>ENU</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>中文（繁体，香港特别行政区）</para>
                </TD>
                <TD>
                  <para>0c04</para>
                </TD>
                <TD>
                  <para>ZHH</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>中文（简体）</para>
                </TD>
                <TD>
                  <para>0804</para>
                </TD>
                <TD>
                  <para>CHS</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>中文（繁体，台湾）</para>
                </TD>
                <TD>
                  <para>0404</para>
                </TD>
                <TD>
                  <para>CHT</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>捷克语</para>
                </TD>
                <TD>
                  <para>0405</para>
                </TD>
                <TD>
                  <para>CSY</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>荷兰语 - 荷兰</para>
                </TD>
                <TD>
                  <para>0413</para>
                </TD>
                <TD>
                  <para>NLD</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>法语</para>
                </TD>
                <TD>
                  <para>040c</para>
                </TD>
                <TD>
                  <para>FRA</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>德语</para>
                </TD>
                <TD>
                  <para>0407</para>
                </TD>
                <TD>
                  <para>DEU</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>匈牙利语</para>
                </TD>
                <TD>
                  <para>040e</para>
                </TD>
                <TD>
                  <para>HUN</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>意大利语 - 意大利</para>
                </TD>
                <TD>
                  <para>0410</para>
                </TD>
                <TD>
                  <para>ITA</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>日语</para>
                </TD>
                <TD>
                  <para>0411</para>
                </TD>
                <TD>
                  <para>JPN</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>朝鲜语</para>
                </TD>
                <TD>
                  <para>0412</para>
                </TD>
                <TD>
                  <para>KOR</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>波兰语</para>
                </TD>
                <TD>
                  <para>0415</para>
                </TD>
                <TD>
                  <para>PLK</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>葡萄牙语 - 巴西</para>
                </TD>
                <TD>
                  <para>0416</para>
                </TD>
                <TD>
                  <para>PTB</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>葡萄牙语 - 葡萄牙</para>
                </TD>
                <TD>
                  <para>0816</para>
                </TD>
                <TD>
                  <para>PTG</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>俄语</para>
                </TD>
                <TD>
                  <para>0419</para>
                </TD>
                <TD>
                  <para>RUS</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>西班牙语 - 西班牙</para>
                </TD>
                <TD>
                  <para>0c0a</para>
                </TD>
                <TD>
                  <para>ESN</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>瑞典语</para>
                </TD>
                <TD>
                  <para>041d</para>
                </TD>
                <TD>
                  <para>SVE</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>土耳其语</para>
                  <para/>
                </TD>
                <TD>
                  <para>041f</para>
                </TD>
                <TD>
                  <para>TRK</para>
                </TD>
                
              </tr>
            </tbody>
          </table>
        </content>
      </section>
      <section expanded="false">
        <title>客户端语言</title>
        <content>
          <table xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
            <thead>
              <tr>
                <TD>
                  <para>客户端语言 </para>
                </TD>
                <TD>
                  <para>区域设置 ID (LCID) </para>
                </TD>
                <TD>
                  <para>三个字母的代码</para>
                </TD>
                
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>英语（默认）</para>
                </TD>
                <TD>
                  <para>0409</para>
                </TD>
                <TD>
                  <para>ENG</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>中文（繁体，香港特别行政区）</para>
                </TD>
                <TD>
                  <para>0c04</para>
                </TD>
                <TD>
                  <para>ZHH</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>中文 - 简体</para>
                </TD>
                <TD>
                  <para>0804</para>
                </TD>
                <TD>
                  <para>CHS</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>中文（繁体，台湾）</para>
                </TD>
                <TD>
                  <para>0404</para>
                </TD>
                <TD>
                  <para>CHT</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>捷克语</para>
                </TD>
                <TD>
                  <para>0405</para>
                </TD>
                <TD>
                  <para>CSY</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>丹麦语</para>
                </TD>
                <TD>
                  <para>0406</para>
                </TD>
                <TD>
                  <para>DAN</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>荷兰语 - 荷兰</para>
                </TD>
                <TD>
                  <para>0413</para>
                </TD>
                <TD>
                  <para>NLD</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>芬兰语</para>
                </TD>
                <TD>
                  <para>040b</para>
                </TD>
                <TD>
                  <para>FIN</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>法语</para>
                </TD>
                <TD>
                  <para>040c</para>
                </TD>
                <TD>
                  <para>FRA</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>德语</para>
                </TD>
                <TD>
                  <para>0407</para>
                </TD>
                <TD>
                  <para>DEU</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>希腊语</para>
                </TD>
                <TD>
                  <para>0408</para>
                </TD>
                <TD>
                  <para>ELL</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>匈牙利语</para>
                </TD>
                <TD>
                  <para>040e</para>
                </TD>
                <TD>
                  <para>HUN</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>意大利语 - 意大利</para>
                </TD>
                <TD>
                  <para>0410</para>
                </TD>
                <TD>
                  <para>ITA</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>日语</para>
                </TD>
                <TD>
                  <para>0411</para>
                </TD>
                <TD>
                  <para>JPN</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>朝鲜语</para>
                </TD>
                <TD>
                  <para>0412</para>
                </TD>
                <TD>
                  <para>KOR</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>挪威语</para>
                </TD>
                <TD>
                  <para>0414</para>
                </TD>
                <TD>
                  <para>NOR</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>波兰语</para>
                </TD>
                <TD>
                  <para>0415</para>
                </TD>
                <TD>
                  <para>PLK</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>葡萄牙语（巴西）</para>
                </TD>
                <TD>
                  <para>0416</para>
                </TD>
                <TD>
                  <para>PTB</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>葡萄牙语（葡萄牙）</para>
                </TD>
                <TD>
                  <para>0816</para>
                </TD>
                <TD>
                  <para>PTG</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>俄语</para>
                </TD>
                <TD>
                  <para>0419</para>
                </TD>
                <TD>
                  <para>RUS</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>西班牙语 - 西班牙</para>
                </TD>
                <TD>
                  <para>0c0a</para>
                </TD>
                <TD>
                  <para>ESN</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>瑞典语</para>
                </TD>
                <TD>
                  <para>041d</para>
                </TD>
                <TD>
                  <para>SVE</para>
                </TD>
                
              </tr>
              <tr>
                <TD>
                  <para>土耳其语</para>
                </TD>
                <TD>
                  <para>041f</para>
                </TD>
                <TD>
                  <para>TRK</para>
                </TD>
                
              </tr>
            </tbody>
          </table>
        </content>
      </section>
      <section expanded="false">
        <title>移动设备客户端语言</title>
        <content>
          <para>在添加对移动设备语言的支持时，会将所有移动设备客户端语言都包括在内。 对于移动设备支持，你无法选择个别语言包。 有关通过本地移动设备管理功能进行管理的设备所支持的语言的信息，请参阅 <link xlink:href="17905b4c-3895-4ad4-a69c-5e0d0fc5a8c3">Configuration Manager 站点系统和客户端的支持</link>主题中的<link xlink:href="17905b4c-3895-4ad4-a69c-5e0d0fc5a8c3#bkmk_OnpremOS">本地移动设备管理</link>部分。</para>
        </content>
      </section>
      <section expanded="false">
        <title>如何识别已安装的语言包</title>
        <content>
          <para>对于运行 <token>cmshort</token> 客户端的计算机，通过在其注册表中查看已安装的语言包的区域设置 ID (LCID)，可以识别在此计算机上安装的语言包。 此信息将出现在以下位置：</para>
          <list class="bullet">
            <listItem>
              <para>
                <ui>HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\CCMSetup\InstalledLangs</ui>
              </para>
            </listItem>
          </list>
          <para>可以使用硬件清单来收集此信息，然后创建自定义报表以查看语言详细信息。 有关收集自定义硬件清单的信息，请参阅<link xlink:href="0e45290e-f8f7-4335-801e-570225d12c2b">如何在 System Center Configuration Manager 中扩展硬件清单</link>。 有关创建报表的信息，请参阅 <link xlink:href="b89bcfbf-f5b6-4fb1-bb5e-a5cc18ec0c78">Configuration Manager 中的报告的操作和维护</link>主题中的<link xlink:href="b89bcfbf-f5b6-4fb1-bb5e-a5cc18ec0c78#BKMK_ManageReports">管理 Configuration Manager 报告</link>部分。</para>
        </content>
      </section>
    </sections>
  </section>
  <relatedTopics>
    <link xlink:href="fef914d6-a4b7-4d17-a030-c81bbf7e27fe">站点和层次结构基础结构技术参考</link>
  </relatedTopics>
</developerWalkthroughDocument>

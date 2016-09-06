---
title: "Endpoint Protection 客户端的常见问题"
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
ms.assetid: e3aaa9d2-a40e-42b1-ad75-5a115351729e
caps.latest.revision: 15
caps.handback.revision: 12
translationtype: Human Translation
---
# Endpoint Protection 客户端的常见问题
<?xml version="1.0" encoding="utf-8"?>
<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  <caps:SxSTarget locale="zh-CN">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xlink="http://www.w3.org/1999/xlink">
      <introduction>
        <para>
          <caps:sentence sentenceid="db6a3219fed8737a6737d2f943369917" id="tgt1" class="tgtSentence">此 FAQ 针对其 IT 管理员已将 Windows Defender 或 Endpoint Protection 部署到其托管计算机的计算机用户。</caps:sentence>
          <caps:sentence sentenceid="f39f1eaa383ef797e88158259739869a" id="tgt2" class="tgtSentence"> 此处的内容可能不适用于其他已应用的反恶意软件，但其中的许多内容对所有计算机用户都是有用的。</caps:sentence>
          <caps:sentence sentenceid="6dabb7c070599cedc4b4be302950e807" id="tgt3" class="tgtSentence"> Microsoft System Center Endpoint Protection 在 Windows 10 之前的计算机上部署和管理 Endpoint Protection 客户端。</caps:sentence>
          <caps:sentence sentenceid="961ff76c949f05171514fe0a4421ea5c" id="tgt4" class="tgtSentence"> 在 Windows 10 中，Windows Defender 替代了 Endpoint Protection。</caps:sentence>
          <caps:sentence sentenceid="ebf4fa2b608fd841615399345bfcc3ae" id="tgt5" class="tgtSentence"> Windows Defender 在所有 Windows 10 操作系统中附带，但由 System Center Endpoint Protection 进行管理。</caps:sentence>
          <caps:sentence sentenceid="bda0a5fa028e2204778f1d57d43667df" id="tgt6" class="tgtSentence"> 虽然本文对 Windows Defender 进行了介绍，但是其信息也适用于 Endpoint Protection。</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence sentenceid="6424fcb814a58b3b535b333677fb732f" id="tgt7" class="tgtSentence">为什么需要防病毒和反间谍软件？</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_Why</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence sentenceid="6968c5cb5827fc5ebfff46e026bc5c59" id="tgt8" class="tgtSentence">如何判断计算机是否感染恶意软件？</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_How</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence sentenceid="e1f7b307e29aaba423d6036b8161ab0a" id="tgt9" class="tgtSentence">如果 Windows Defender 或 Endpoint Protection 在我的计算机上检测到恶意软件，我该怎么办？</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_What</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence sentenceid="869616da9d52542d425a982e33d6d17d" id="tgt10" class="tgtSentence">什么是病毒？</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_Virus</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence sentenceid="a7759778af072c38b833b01039a837a1" id="tgt11" class="tgtSentence">什么是间谍软件？</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_Spy</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence sentenceid="70f7d0f8cdf747024a6e8d25b506a765" id="tgt12" class="tgtSentence">病毒、间谍软件和其他可能有害的软件之间的区别是什么？</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_Diff</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence sentenceid="d270662814b582eafa7144486c52fb61" id="tgt13" class="tgtSentence">病毒、间谍软件以及其他可能不需要的软件来自哪里？</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_Where</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence sentenceid="973410d2d0d71d2059b9c462501a0c02" id="tgt14" class="tgtSentence">我是否会在不知情的情况下获取恶意软件？</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_Can</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence sentenceid="42dae95e42348430c70cc84d7a763ce4" id="tgt15" class="tgtSentence">为什么在安装软件之前查看许可证协议很重要？</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_License</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence sentenceid="d270662814b582eafa7144486c52fb61" id="tgt16" class="tgtSentence">病毒、间谍软件以及其他可能不需要的软件来自哪里？</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_Where</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence sentenceid="32bf62faeb130cd25f37fa773f4b868b" id="tgt17" class="tgtSentence">Endpoint Protection 和 Windows Defender 之间的区别是什么？</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_EPWD</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence sentenceid="d5274d0211e7724d884ad1d95c25a094" id="tgt18" class="tgtSentence">Windows Defender 为什么没有检测到 cookie？</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_Cookies</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence sentenceid="c4a2bbdb977a88fd418e9ce932b07570" id="tgt19" class="tgtSentence">如何防止恶意软件？</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_MalPrev</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence sentenceid="e3f23ae5c9522bfb2214e2ce3ea43787" id="tgt20" class="tgtSentence">病毒和间谍软件的定义是什么？</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_Def</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence sentenceid="b2f1ebe590e4127d9c8c544521cbdb31" id="tgt21" class="tgtSentence">如何使病毒和间谍软件定义保持最新？</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_HowDef</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence sentenceid="aa446ca92d8739b7259c5da3b4ddee4a" id="tgt22" class="tgtSentence">如何删除或还原 Windows Defender 或 Endpoint Protection 隔离的项目？</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_HowRem</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence sentenceid="8a0b911d63f99c17b2b7675a60f10050" id="tgt23" class="tgtSentence">什么是实时保护？</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_Real</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence sentenceid="7d6355875dd936165c103babd0582946" id="tgt24" class="tgtSentence">如何知道 Windows Defender 或 Endpoint Protection 正在我的计算机上运行？</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_Run</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence sentenceid="17ce9e4366d3caeee27b9d089fd1722f" id="tgt25" class="tgtSentence">如何设置 Windows Defender 或 Endpoint Protection 警报？</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_Alert</linkUri>
              </externalLink>
            </para>
          </listItem>
        </list>
      </introduction>
      <section address="BKMK_Why">
        <title>
          <caps:sentence sentenceid="6424fcb814a58b3b535b333677fb732f" id="tgt26" class="tgtSentence">为什么需要防病毒和反间谍软件？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="6fe9ddb88d181f94b770f28944b17489" id="tgt27" class="tgtSentence">确保你的计算机运行的软件能够防护恶意软件至关重要。</caps:sentence>
            <caps:sentence sentenceid="0ad506cfdc15b3b8d94b877519062d92" id="tgt28" class="tgtSentence"> 恶意软件包括病毒、间谍软件或其他可能不需要的软件，每当你连接到 Internet 时它都会试图在计算机上自行安装。</caps:sentence>
            <caps:sentence sentenceid="6bbc7e430f41b700a47071d327753688" id="tgt29" class="tgtSentence"> 当你使用 CD、DVD 或其他可移动介质安装程序时，它也会感染计算机。</caps:sentence>
            <caps:sentence sentenceid="3fb2786b93eef696dde08e922dcb9c4f" id="tgt30" class="tgtSentence"> 恶意软件还可编程为不定时运行，而不仅是在安装时运行。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="5552e6004dd4416976e9911f3cebe27e" id="tgt31" class="tgtSentence">
      Windows Defender 或 Endpoint Protection 提供了三种防止计算机感染恶意软件的方法：</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="509999f3187854ad91d1cdcd2d07fcd9" id="tgt32" class="tgtSentence">
                  <legacyBold>使用实时保护</legacyBold>—利用实时保护，Windows Defender 可以始终监视你的计算机，并在恶意软件（包括病毒、间谍软件或其他可能不需要的软件）试图在你的计算机上自行安装或运行时向你发出警报。</caps:sentence>
                <caps:sentence sentenceid="ce5543af4f843c64ffadb49a74c85317" id="tgt33" class="tgtSentence"> 然后，Windows Defender 会挂起此软件，并允许你遵循有关此软件的建议，或采取替代操作。</caps:sentence>
              </para>
              <table>
                <tbody>
                  <tr>
                    <TD>
                      <para>
                        <legacyBold>
                          <caps:sentence sentenceid="8c4b4b816c4ec9907f382e91dddb9eb2" id="tgt34" class="tgtSentence">实时保护选项</caps:sentence>
                        </legacyBold>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <legacyBold>
                          <caps:sentence sentenceid="4d066bbb0e40abe54f3000755a45aa6e" id="tgt35" class="tgtSentence">目的</caps:sentence>
                        </legacyBold>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="58d618c75ccfbf69f3e415c263ef4dbf" id="tgt36" class="tgtSentence">扫描所有下载</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="bd73c9ad627ce3506eb4d472ea7c6d59" id="tgt37" class="tgtSentence">此选项可监视下载的文件和程序，包括通过 Windows Internet Explorer 和 Microsoft Outlook ® Express 自动下载的文件，例如 ActiveX® 控件和软件安装程序。</caps:sentence>
                        <caps:sentence sentenceid="7d4686281d5b898833f15b492e0b917b" id="tgt38" class="tgtSentence"> 这些文件可通过浏览器自身下载、安装或运行。</caps:sentence>
                        <caps:sentence sentenceid="f9eb59c7bec13af95352a00a19af440e" id="tgt39" class="tgtSentence"> 恶意软件，包括病毒、间谍软件和其他可能不需要的软件可以包含在这些文件中，并在你不知情的情况下安装。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="b1405482cbb9b2283557c21b263fe57c" id="tgt40" class="tgtSentence">使用此实时保护选项，Windows Defender 可以始终监视你的计算机，并检查你可能已下载的任何恶意文件或程序。</caps:sentence>
                        <caps:sentence sentenceid="1bf53fbbe7dd134a248f9c3cf5080f8f" id="tgt41" class="tgtSentence"> 此监视功能意味着 Windows Defender 不需要通过要求检查你可能想要下载的任何文件或程序来减慢你的浏览或电子邮件速度。</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="bf38315519036f9b58f6fad56866a246" id="tgt42" class="tgtSentence">监视计算机上的文件和程序活动</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="5d114353d5e55b62cf817902290f7a53" id="tgt43" class="tgtSentence">此选项是在文件和程序开始在你的计算机上运行时进行监视，然后它会对你发出警报，通知你它们要执行的任何操作和要对它们执行的操作。</caps:sentence>
                        <caps:sentence sentenceid="5a0d5b9aa3c4fe00b2169a8c46e65e96" id="tgt44" class="tgtSentence"> 这非常重要，因为恶意软件会利用已安装程序的漏洞在你不知情的情况下运行恶意或不需要的软件。</caps:sentence>
                        <caps:sentence sentenceid="26d12139c03c293a3b9cc4813d964a69" id="tgt45" class="tgtSentence"> 例如，当你启动经常使用的程序时，间谍软件可以在后台运行。</caps:sentence>
                        <caps:sentence sentenceid="374ba4d1ee8ef9ba3684c27ddb6a7082" id="tgt46" class="tgtSentence"> Windows Defender 监视你的程序，并在检测到可疑活动时向你发出警报。</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="3d208f8fa970e6f17d21f08a7cf1feaf" id="tgt47" class="tgtSentence">启用行为监视</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="7c51b691805397eb48e82818b0dc3303" id="tgt48" class="tgtSentence">此选项可监视传统防病毒检测方法可能检测不到的可疑模式的行为集合。</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="fd14e29fc5bd1f831bc66ba46b0de2ea" id="tgt49" class="tgtSentence">启用网络检查系统</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="b0e4957bee53adaafcb22ce810a057e6" id="tgt50" class="tgtSentence">此选项可帮助保护计算机免受已知漏洞的零日攻击、减小发现漏洞和应用更新之间的时间段。</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </tbody>
              </table>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="1719a33053942b31e0166b8ff25b18fc" id="tgt51" class="tgtSentence">
                  <legacyBold>扫描选项</legacyBold>—你可以使用 Windows Defender 扫描可能给你的计算机带来风险的潜在威胁，如病毒、间谍软件以及其他恶意软件。</caps:sentence>
                <caps:sentence sentenceid="264361d350578876f9d1327d9308a511" id="tgt52" class="tgtSentence"> 你也可以用它来计划定期扫描，并删除在扫描过程中检测到的恶意软件。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="460e7f28624ecd6ac6f8fa8ab6ffca68" id="tgt53" class="tgtSentence">
                  <legacyBold>Microsoft Active Protection Service 社区</legacyBold>—Microsoft Active Protection Service 在线社区可帮助你查看其他人如何应对尚未进行风险评估的软件。</caps:sentence>
                <caps:sentence sentenceid="d0fb66c1f7ac77db6e872955f3fadf80" id="tgt54" class="tgtSentence"> 利用此信息，可帮助你选择是否在你的计算机上允许此软件。</caps:sentence>
                <caps:sentence sentenceid="c8cf99f963b35ffd7e23699f6935aec3" id="tgt55" class="tgtSentence"> 如果你参与其中，你的选择将添加到社区评级，这反过来会帮助其他人决定要做什么。</caps:sentence>
              </para>
            </listItem>
          </list>
        </content>
      </section>
      <section address="BKMK_How">
        <title>
          <caps:sentence sentenceid="6968c5cb5827fc5ebfff46e026bc5c59" id="tgt56" class="tgtSentence">如何判断计算机是否感染恶意软件？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="b40b635553f41baf765a11cb33890c09" id="tgt57" class="tgtSentence">如果存在以下情况，那么你的计算机可能感染了某种形式的恶意软件，包括病毒、间谍软件或其他可能不需要的软件： </caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="404edc16498b42761aca2b0e97fc64d3" id="tgt58" class="tgtSentence">你注意到 Web 浏览器中有一些不是你有意添加的新工具栏、链接或收藏项。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="d55e1620a0548d0dda1817fdb4f4868a" id="tgt59" class="tgtSentence">主页、鼠标指针或搜索程序发生了意外更改。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="779d013ce03e47af4b021eb077c59109" id="tgt60" class="tgtSentence">你键入特定网站的地址，如搜索引擎，但是你却在没有收到通知的情况下被转到另一个网站。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="c2c7deea59fae018b63d1c46ca4df473" id="tgt61" class="tgtSentence">从你的计算机中自动删除文件。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="4807453f31960d74d394159af6f92342" id="tgt62" class="tgtSentence">你的计算机被用于攻击其他计算机。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="75a293ada18f34bb09db34c00272eca8" id="tgt63" class="tgtSentence">即使你不在 Internet 上，也会看到弹出的广告。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="7ac01126d9662f9e9d5ac58f81e9f14d" id="tgt64" class="tgtSentence">你的计算机运行速度突然比平时慢很多。</caps:sentence>
                <caps:sentence sentenceid="583bdbb985e07d15fc4079eb04821a3c" id="tgt65" class="tgtSentence"> 并非所有计算机的性能问题都是由恶意软件引起的，但是恶意软件，尤其是间谍软件可引起显著的更改。</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence sentenceid="bc965d3c28c270116cd9e4182d6c5f69" id="tgt66" class="tgtSentence">即使你未发现任何症状，你的计算机上也可能有恶意软件。</caps:sentence>
            <caps:sentence sentenceid="2a3690ecfe52c8050a28e73825b6347f" id="tgt67" class="tgtSentence"> 此类型软件可以在你不知情或未经你同意的情况下收集有关你和你的计算机的信息。</caps:sentence>
            <caps:sentence sentenceid="98003517996b0aa4caa1d3e0ea4979fc" id="tgt68" class="tgtSentence"> 为了帮助保护你的隐私和你的计算机，你应该时刻运行 Windows Defender 或 Endpoint Protection。</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_What">
        <title>
          <caps:sentence sentenceid="e1f7b307e29aaba423d6036b8161ab0a" id="tgt69" class="tgtSentence">如果 Windows Defender 或 Endpoint Protection 在我的计算机上检测到恶意软件，我该怎么办？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="c02d8a330c3fcac90b4350ed4e177a3f" id="tgt70" class="tgtSentence">如果 Windows Defender 在你的计算机上检测到恶意软件或可能不需要的软件（使用实时保护监视你的计算机时或运行扫描后），它将通过在屏幕右下角显示通知消息来通知你检测到的项目。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="06f3b75717dba189ab90767d7bba615c" id="tgt71" class="tgtSentence">通知消息包括“干净计算机”<ui></ui>按钮和“显示详细信息”<ui></ui>链接，让你可以查看有关检测到的项目的其他信息。</caps:sentence>
            <caps:sentence sentenceid="2b4507005ba4d02892a4a0198cbe9252" id="tgt72" class="tgtSentence"> 单击“显示详细信息”<ui></ui>链接将打开“潜在威胁详细信息”<ui></ui>窗口，从而获取有关检测到的项目的其他信息。</caps:sentence>
            <caps:sentence sentenceid="a343726e785b2ab988fb34f4f23b1757" id="tgt73" class="tgtSentence"> 现在，你可选择要应用于此项目的操作，也可单击“干净计算机”<ui></ui>。</caps:sentence>
            <caps:sentence sentenceid="cd242ec8dcbf2ea15e87acb529175047" id="tgt74" class="tgtSentence"> 如果你需要帮助来确定应用于检测到的项目的操作，请使用 Windows Defender 分配给此项目的警报级别作为指导（有关详细信息，请参阅“了解警报级别”）。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="848351af760bb0e7d9cf5d685fc859c1" id="tgt75" class="tgtSentence">警报级别有助于你选择如何应对病毒、间谍软件和其他潜在有害软件。</caps:sentence>
            <caps:sentence sentenceid="eb8c7100c03512be727d59d69e988d63" id="tgt76" class="tgtSentence"> 当 Windows Defender 建议你删除所有病毒和间谍软件时，并不是所有标记的软件都是恶意的或是不需要的。</caps:sentence>
            <caps:sentence sentenceid="d4cf0662cd8dd2e0bc621e4c2d06828a" id="tgt77" class="tgtSentence"> 当 Windows Defender 在你的计算机上检测到可能不需要的软件时，以下信息可帮助你确定应执行的操作。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="a8b81839072ba0accc6e32d6c710ddb7" id="tgt78" class="tgtSentence">根据警报等级，可选择下列操作之一来应用于检测到的项目：</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="9d1241143e2fcb854952b9c20e4c320d" id="tgt79" class="tgtSentence">
                  <legacyBold>删除</legacyBold> - 此操作将从你的计算机中永久删除软件。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="63bd5dea59402e392612cd31d60b2e77" id="tgt80" class="tgtSentence">
                  <legacyBold>隔离</legacyBold> - 此操作将隔离软件使其不能运行。</caps:sentence>
                <caps:sentence sentenceid="fdce78b711d45f4e62a984fdc5cfb69e" id="tgt81" class="tgtSentence"> 当 Windows Defender 隔离软件时，它将此软件移至计算机上的其他位置，然后阻止此软件运行，直到你选择还原此软件，或从计算机中删除它。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="3089bbebfb56b93050f4eca5f764c2a4" id="tgt82" class="tgtSentence">
                  <legacyBold>允许</legacyBold>—此操作将向 Windows Defender 允许列表添加软件并允许该软件在计算机上运行。</caps:sentence>
                <caps:sentence sentenceid="0aa84c6119c993e730e9da709d323751" id="tgt83" class="tgtSentence"> Windows Defender 将停止提醒你此软件可能会给你的隐私或计算机带来的风险。</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence sentenceid="376758bac688be4ebb94700ad9403892" id="tgt84" class="tgtSentence">如果你对某一项（如软件）选择“允许”<ui></ui>，Windows Defender 将停止提醒你此软件可能会给你的隐私或计算机带来的风险。</caps:sentence>
            <caps:sentence sentenceid="5f8350ade06c86188df0b4a316f5969a" id="tgt85" class="tgtSentence"> 因此，仅当你信任软件及软件发布者时，才可将软件添加到允许列表。</caps:sentence>
          </para>
          <para>
            <embeddedLabel>
              <caps:sentence sentenceid="0e16793f109aabc0bd786ac87bf44dbe" id="tgt86" class="tgtSentence">如何删除可能有害的软件</caps:sentence>
            </embeddedLabel>
          </para>
          <para>
            <caps:sentence sentenceid="1841d9af112d5ad3db2da616570ba7d8" id="tgt87" class="tgtSentence">要方便快捷地删除 Windows Defender 检测到的所有不需要的或可能有害的项目，请使用“清理计算机”<ui></ui>选项。</caps:sentence>
          </para>
          <list class="ordered">
            <listItem>
              <para>
                <caps:sentence sentenceid="7cb66e01866ab6ffee2a86ccc5a7e7a5" id="tgt88" class="tgtSentence">当你看见 Windows Defender 检测到潜在威胁后在通知区域显示的通知消息时，请单击“清理计算机”<ui></ui>。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="86a4cee0e19aabe3c0c78698af8e9ab9" id="tgt89" class="tgtSentence">
          Windows Defender 将删除潜在威胁，然后在清理完你的计算机后通知你。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="4f018ad783f0ff1b19cc457dcce6d9ea" id="tgt90" class="tgtSentence">若要了解有关检测到的威胁的详细信息，请单击“历史记录”<ui></ui>选项卡，然后选择“所有检测到的项目”<ui></ui>。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="4fff69c8e62faf1a751d3b0ea15f783a" id="tgt91" class="tgtSentence">如果你看不到所有检测到的项目，请单击“查看详细信息”<ui></ui>。</caps:sentence>
                <caps:sentence sentenceid="d3fecf0366208e41181c17c81127b50c" id="tgt92" class="tgtSentence"> 如果系统提示你输入管理员密码或进行确认，请键入密码或确认操作。</caps:sentence>
                <caps:sentence sentenceid="97ad0bdb809125150444af99aa73e96e" id="tgt93" class="tgtSentence"> 在运行 Windows XP 的系统上，你可能需要以管理员身份登录到此计算机。</caps:sentence>
              </para>
            </listItem>
          </list>
          <alert class="note">
            <para>
              <caps:sentence sentenceid="d00d672ca556be804ce07a3f7217f2b4" id="tgt94" class="tgtSentence">在清理计算机时，Windows Defender 尽可能只删除文件的受感染部分，而不是整个文件。</caps:sentence>
            </para>
          </alert>
        </content>
      </section>
      <section address="BKMK_Virus">
        <title>
          <caps:sentence sentenceid="869616da9d52542d425a982e33d6d17d" id="tgt95" class="tgtSentence">什么是病毒？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="6244f977588d8d2c667c52d11d51ce9e" id="tgt96" class="tgtSentence">计算机病毒是蓄意设计的软件程序，用来干扰计算机操作，记录、损坏或删除数据，或者感染 Internet 上的其他计算机。</caps:sentence>
            <caps:sentence sentenceid="f5dab667ecb3edb2ca70370d2168eafe" id="tgt97" class="tgtSentence"> 病毒通常会降低运行速度，并在进程中导致其他问题。</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_Spy">
        <title>
          <caps:sentence sentenceid="762ed6e02edd91054aae5949bc8d7ddb" id="tgt98" class="tgtSentence">什么是间谍软件？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="795284ee1fc419df68dc890bb98477f7" id="tgt99" class="tgtSentence">间谍软件是一种软件，它可以自行安装或未经你同意在计算机上运行，并且不会提供足够的通知或控制权。</caps:sentence>
            <caps:sentence sentenceid="ea0e6266d5d78e34d4248bf6cf8c26e1" id="tgt100" class="tgtSentence"> 间谍软件感染你的计算机后可能不会显示任何症状，但许多恶意或不需要的程序可能会影响你的计算机的运行方式。</caps:sentence>
            <caps:sentence sentenceid="b7f22ebdc1f2ba7aac4215460282ae53" id="tgt101" class="tgtSentence"> 例如，间谍软件可以监视你的上网行为或收集你的信息（包括可以标识你的信息或其他敏感信息），还可以更改计算机的设置或导致计算机运行缓慢。</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_Diff">
        <title>
          <caps:sentence sentenceid="70f7d0f8cdf747024a6e8d25b506a765" id="tgt102" class="tgtSentence">病毒、间谍软件和其他可能有害的软件之间的区别是什么？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="96237e77011d0bad6074444159ae7f3f" id="tgt103" class="tgtSentence">病毒和间谍软件都是在你不知情的情况下安装在你的计算机上，并且两者都可能具有侵入性和破坏性。</caps:sentence>
            <caps:sentence sentenceid="d5db5bc7cdeafd5e40ecfa2cc70f8161" id="tgt104" class="tgtSentence"> 它们还具有捕获你的计算机上的信息并损坏或删除这些信息的能力。</caps:sentence>
            <caps:sentence sentenceid="fb7bd093d37af8ebf79eec4361a70419" id="tgt105" class="tgtSentence"> 它们会对你的计算机的性能造成负面影响。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="e215271ee458a5db297fe48030f171aa" id="tgt106" class="tgtSentence">病毒和间谍软件之间的主要区别是它们在计算机上的行为方式。</caps:sentence>
            <caps:sentence sentenceid="299cd7a8b882c131e63940090c735f19" id="tgt107" class="tgtSentence"> 病毒像生命体，想要感染计算机、进行复制，然后尽可能多地传播到其他计算机。</caps:sentence>
            <caps:sentence sentenceid="dac420f87c89c532f8340f51298333c0" id="tgt108" class="tgtSentence"> 但是，间谍软件更像是一个内奸，它想要“打入”你的计算机，并且尽可能长久地停留在那里，在此期间将有关你的计算机的有价值信息发送到外部源。</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_Where">
        <title>
          <caps:sentence sentenceid="d270662814b582eafa7144486c52fb61" id="tgt109" class="tgtSentence">病毒、间谍软件以及其他可能不需要的软件来自哪里？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="f8fcf857d9efff77deaa830c3a1bedd2" id="tgt110" class="tgtSentence">不需要的软件，如病毒，可以通过网站或者你下载的程序进行安装，或者通过 CD、DVD、外部硬盘或设备安装。</caps:sentence>
            <caps:sentence sentenceid="edfa191686077a9999a3d49a5565fdd2" id="tgt111" class="tgtSentence"> 间谍软件通常通过免费软件进行安装，如文件共享、屏幕保护程序或搜索工具栏。</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_Can">
        <title>
          <caps:sentence sentenceid="973410d2d0d71d2059b9c462501a0c02" id="tgt112" class="tgtSentence">我是否会在不知情的情况下获取恶意软件？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="44908afea3e084bb8c4ccf491a2d5490" id="tgt113" class="tgtSentence">是的，一些恶意软件可以通过嵌入式脚本或网页中的程序从网站安装。</caps:sentence>
            <caps:sentence sentenceid="c1f3b8c3c21e67747c8b43e6255f35ed" id="tgt114" class="tgtSentence"> 一些恶意软件要求你的帮助才能安装。</caps:sentence>
            <caps:sentence sentenceid="6a9255327a5a37e02b2629743e411cce" id="tgt115" class="tgtSentence"> 此软件通过 Web 弹出消息或免费软件让你接受可下载文件。</caps:sentence>
            <caps:sentence sentenceid="69efc8f9917baa70ff6223eac795268b" id="tgt116" class="tgtSentence"> 但是，如果保持最新的 Microsoft Windows®，并且不减少安全设置，那么你可以尽量减小受感染的可能性。</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_License">
        <title>
          <caps:sentence sentenceid="42dae95e42348430c70cc84d7a763ce4" id="tgt117" class="tgtSentence">为什么在安装软件之前查看许可证协议很重要？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="d33fcc5b950eb7487f74f4ecf57123d7" id="tgt118" class="tgtSentence">当你访问网站时，不要自动同意下载站点提供的任何内容。</caps:sentence>
            <caps:sentence sentenceid="d4b1c0969fe9832eefbed0ff02800044" id="tgt119" class="tgtSentence"> 如果下载免费软件，如文件共享程序或屏幕保护程序，请仔细阅读许可证协议。</caps:sentence>
            <caps:sentence sentenceid="bafffb8ff5fcb7bd63c8b8cd19672e81" id="tgt120" class="tgtSentence"> 查找提到以下内容的句子：你必须接受来自公司的广告和弹出窗口，或者该软件将发送特定信息给软件发行者。</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_EPWD">
        <title>
          <caps:sentence sentenceid="32bf62faeb130cd25f37fa773f4b868b" id="tgt121" class="tgtSentence">Endpoint Protection 和 Windows Defender 之间的区别是什么？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="cbbc9d72c0c88d7556ff18ee5877a7c6" id="tgt122" class="tgtSentence">
        Endpoint Protection 是反恶意软件，这意味着它设计用于检测恶意软件，并帮助保护你的计算机免受各种恶意软件的攻击，包括病毒、间谍软件和其他可能不需要的软件。</caps:sentence>
            <caps:sentence sentenceid="83e6947fb562200b0cd94496ba3868dc" id="tgt123" class="tgtSentence"> Windows Defender 随 Windows 操作系统一起自动安装，是用于检测并停止间谍软件的软件。</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_Cookies">
        <title>
          <caps:sentence sentenceid="d5274d0211e7724d884ad1d95c25a094" id="tgt124" class="tgtSentence">Windows Defender 为什么没有检测到 cookie？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="c681d869c781d39cd1f29c7be706aeae" id="tgt125" class="tgtSentence">Cookie 是网站放在你的计算机上用于存储你和你的首选项信息的小文本文件。</caps:sentence>
            <caps:sentence sentenceid="844e3d60df8e531e2b402f7312cd9c96" id="tgt126" class="tgtSentence"> 网站使用 cookie 向你提供个性化的体验以及收集有关网站使用的信息。</caps:sentence>
            <caps:sentence sentenceid="d31597579af20f469159567edcde71dc" id="tgt127" class="tgtSentence"> Windows Defender 不会检测 cookie，因为它不认为这些会威胁到你的隐私或你的计算机的安全性。</caps:sentence>
            <caps:sentence sentenceid="c3c571778298172fa4b6c0bfe838d91f" id="tgt128" class="tgtSentence"> 大多数 Internet 浏览器程序允许你阻止 cookie。</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_MalPrev">
        <title>
          <caps:sentence sentenceid="c4a2bbdb977a88fd418e9ce932b07570" id="tgt129" class="tgtSentence">如何防止恶意软件？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="402931b32a53ec51db090de5fa7691bd" id="tgt130" class="tgtSentence">今天的计算机用户关心的两大后顾之忧是病毒和间谍软件。</caps:sentence>
            <caps:sentence sentenceid="a21a06f2efe3a2ee8d5604fbed157b41" id="tgt131" class="tgtSentence"> 虽然这两者都是问题，但是你只需要一点计划，就可以很轻松地保护自己的计算机不受它们的侵袭：</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="d732b2c734ed260aca500ed5a0b5383b" id="tgt132" class="tgtSentence">保持拥有最新的计算机软件，并记得安装所有修补程序。</caps:sentence>
                <caps:sentence sentenceid="d3b12a9bcff8ed92d6d37a6e1a815eb8" id="tgt133" class="tgtSentence"> 记得定期更新你的操作系统。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="6211d1c4dd4b378cf7ef5e8aa72d8cd5" id="tgt134" class="tgtSentence">请确保你的防病毒和反间谍软件 Windows Defender 使用最新的更新应对潜在的威胁（请参阅“如何使病毒和间谍软件定义保持最新？”）。</caps:sentence>
                <caps:sentence sentenceid="f605e3e7f7eb151cc578f4593e171259" id="tgt135" class="tgtSentence"> 此外请确保你始终使用最新版本的 Windows Defender。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="23fb481441cc8a1ee440188cc64f9e61" id="tgt136" class="tgtSentence">仅从可信的来源下载更新。</caps:sentence>
                <caps:sentence sentenceid="9e2501083f9a6973826a3f1ad79de951" id="tgt137" class="tgtSentence"> 对于 Windows 操作系统，请始终访问 <externalLink><linkText>Microsoft Update</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkID=96304</linkUri></externalLink> (http://go.microsoft.com/fwlink/?LinkID=96304)，对于其他软件，请始终使用开发该软件的公司或个人的合法网站。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="b538ac03acb7ef2de5f0b9bf8d485d18" id="tgt138" class="tgtSentence"> 如果你收到一封带有附件的电子邮件，并且你不确定来源，那么你应该立即删除它。</caps:sentence>
                <caps:sentence sentenceid="80a66ef72bdcd5685e8aa96bdd695c37" id="tgt139" class="tgtSentence"> 不要从未知来源下载任何应用程序或可执行文件，与其他用户交换文件时要小心。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="a47cc452926b9955a2482f9c01b5669c" id="tgt140" class="tgtSentence">安装并使用防火墙。</caps:sentence>
                <caps:sentence sentenceid="cd3b1e5336739bf47262719e9746b756" id="tgt141" class="tgtSentence"> 建议启用 Windows 防火墙。</caps:sentence>
              </para>
            </listItem>
          </list>
        </content>
      </section>
      <section address="BKMK_Def">
        <title>
          <caps:sentence sentenceid="e3f23ae5c9522bfb2214e2ce3ea43787" id="tgt142" class="tgtSentence">病毒和间谍软件的定义是什么？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="f75e06dbf9e5e7260b7a096942cfad8f" id="tgt143" class="tgtSentence">使用 Windows Defender 或 Endpoint Protection 时，拥有最新的病毒和间谍软件定义很重要。</caps:sentence>
            <caps:sentence sentenceid="490a5d6a5839cab776c14d6063164a69" id="tgt144" class="tgtSentence"> 定义是一些文件，这些文件就像是一本不断增长的有关潜在软件威胁的百科全书。</caps:sentence>
            <caps:sentence sentenceid="dd2f2a50664d95be91d49c043cfd6134" id="tgt145" class="tgtSentence"> Windows Defender 或 Endpoint Protection 使用定义来确定它检测到的软件是病毒、间谍软件还是其他可能不需要的软件，然后会通过警报来通知你潜在的风险。</caps:sentence>
            <caps:sentence sentenceid="389bbd331eddc769266c2c2d75f13757" id="tgt146" class="tgtSentence"> 为了帮助你保持拥有最新的定义，Windows Defender 或 Endpoint Protection 使用 Microsoft Update 在新的定义发布时自动安装新定义。</caps:sentence>
            <caps:sentence sentenceid="0d82cd4a7c42db2407b858e6955d9390" id="tgt147" class="tgtSentence"> 你还可以将 Windows Defender 或 Endpoint Protection 设置为在扫描之前在线检查已更新的定义。</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_HowDef">
        <title>
          <caps:sentence sentenceid="b2f1ebe590e4127d9c8c544521cbdb31" id="tgt148" class="tgtSentence">如何使病毒和间谍软件定义保持最新？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="003765b7e036a810aa23404c2d3ff076" id="tgt149" class="tgtSentence">病毒和间谍软件定义是一些文件，这些文件就像是已知的恶意软件（包括病毒、间谍软件和其他可能不需要的软件）的百科全书。</caps:sentence>
            <caps:sentence sentenceid="8bf64a91c74b908265b7fd292b93c9bf" id="tgt150" class="tgtSentence"> 因为恶意软件不断发展，Windows Defender 或 Endpoint Protection 需要依靠最新的定义来确定尝试在计算机上安装、运行或更改设置的软件是病毒、间谍软件还是其他可能不需要的软件。</caps:sentence>
          </para>
          <para>
            <embeddedLabel>
              <caps:sentence sentenceid="34fb3cb2542c5eeac1126d5631cf5318" id="tgt151" class="tgtSentence">在执行计划扫描之前自动检查新定义（推荐）</caps:sentence>
            </embeddedLabel>
          </para>
          <list class="ordered">
            <listItem>
              <para>
                <caps:sentence sentenceid="9a5636bc6bda560400e68b61b0ad612d" id="tgt152" class="tgtSentence">单击通知区域中的图标或从“开始”菜单启动来打开 Windows Defender 或 Endpoint Protection 客户端<ui></ui>。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="c1fd551900a9b72145e3024d5a12e202" id="tgt153" class="tgtSentence">单击“设置”，然后单击“计划扫描”<ui></ui><ui></ui>。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="94a9e6d36e971bd6eb74fed675b5df7c" id="tgt154" class="tgtSentence">请确保已选中<ui>在运行计划扫描之前检查最新的病毒和间谍软件定义</ui>复选框，然后单击“保存更改”<ui></ui>。</caps:sentence>
                <caps:sentence sentenceid="d3fecf0366208e41181c17c81127b50c" id="tgt155" class="tgtSentence"> 如果系统提示你输入管理员密码或进行确认，请键入密码或确认操作。</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <embeddedLabel>
              <caps:sentence sentenceid="86ef35be6a4e40730bfe7f9a3a9953c2" id="tgt156" class="tgtSentence">手动检查新定义</caps:sentence>
            </embeddedLabel>
          </para>
          <para>
            <caps:sentence sentenceid="545c0039ffbbdd1a6a16881ac01c80e4" id="tgt157" class="tgtSentence">Windows Defender 或 Endpoint Protection 会自动更新你的计算机上的病毒和间谍软件定义。</caps:sentence>
            <caps:sentence sentenceid="663d8ccc64047df1764e78abf6b6951d" id="tgt158" class="tgtSentence"> 如果超过七天没有更新定义（例如，如果你有一周时间未打开计算机），Windows Defender 或 Endpoint Protection 会通知你定义已过期。</caps:sentence>
          </para>
          <list class="ordered">
            <listItem>
              <para>
                <caps:sentence sentenceid="9a5636bc6bda560400e68b61b0ad612d" id="tgt159" class="tgtSentence">单击通知区域中的图标或从“开始”菜单启动来打开 Windows Defender 或 Endpoint Protection 客户端<ui></ui>。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="0d6def7bf4400f45f5b82c65b3300342" id="tgt160" class="tgtSentence">要手动检查新定义，请单击“更新”<ui></ui>选项卡，然后单击“更新定义”<ui></ui>。</caps:sentence>
              </para>
            </listItem>
          </list>
        </content>
      </section>
      <section address="BKMK_HowRem">
        <title>
          <caps:sentence sentenceid="aa446ca92d8739b7259c5da3b4ddee4a" id="tgt161" class="tgtSentence">如何删除或还原 Windows Defender 或 Endpoint Protection 隔离的项目？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="be22532793fef5e4555c83ce638e161f" id="tgt162" class="tgtSentence">当 Windows Defender 或 Endpoint Protection 隔离软件时，它会将其移至计算机上的其他位置，然后阻止其运行，直到你选择还原此软件，或从计算机中删除它。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="ebaacac5f8c9f0a0e46d1f133223daa2" id="tgt163" class="tgtSentence">对于此过程中提到的所有步骤，如果系统提示你输入管理员密码或确认，请键入密码或提供确认。</caps:sentence>
          </para>
          <para>
            <embeddedLabel>
              <caps:sentence sentenceid="4a61c56c83115db84905e2c1f5ca0592" id="tgt164" class="tgtSentence">删除或还原 Windows Defender 或 Endpoint Protection 隔离的项目</caps:sentence>
            </embeddedLabel>
          </para>
          <list class="ordered">
            <listItem>
              <para>
                <caps:sentence sentenceid="c5afe698e7290bf20ceabf542b2cf1de" id="tgt165" class="tgtSentence">单击“历史记录”<ui></ui>选项卡，选择“隔离的项目”<ui></ui>，然后选择“隔离的项目”选项<ui></ui>。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="2b43b384d8bd0e6a8b5aaf935794dd04" id="tgt166" class="tgtSentence">单击“查看详细信息”<ui></ui>来查看所有项目。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="88bd7e3737232f980958bae1b6bb90bb" id="tgt167" class="tgtSentence">查看每一项，然后针对每一项单击“删除”<ui></ui>或“还原”<ui></ui>。</caps:sentence>
                <caps:sentence sentenceid="57c55e3ce043b8d3c32a83ea84bffea5" id="tgt168" class="tgtSentence"> 如果你希望从计算机中删除所有隔离的项目，请单击“全部删除”<ui></ui>。</caps:sentence>
              </para>
            </listItem>
          </list>
        </content>
      </section>
      <section address="BKMK_Real">
        <title>
          <caps:sentence sentenceid="8a0b911d63f99c17b2b7675a60f10050" id="tgt169" class="tgtSentence">什么是实时保护？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="7899fdb9e9ab6c4b28f8d939fab5d3d4" id="tgt170" class="tgtSentence">通过实时保护可以使 Windows Defender 时刻监视你的计算机，并且当潜在威胁如病毒和间谍软件尝试自行安装或在你的计算机上运行时向你发出警报。</caps:sentence>
            <caps:sentence sentenceid="d87c4b4d533f6de72ef514a9ab4d2862" id="tgt171" class="tgtSentence"> 由于此功能是 Windows Defender 帮助保护你的计算机所采取的方法的重要组成部分，因此需确保实时保护始终处于打开状态。</caps:sentence>
            <caps:sentence sentenceid="fbd7741725d8506746884c5fe7e6b6aa" id="tgt172" class="tgtSentence"> 如果实时保护被关闭，Windows Defender 会通知你，并将计算机的状态更改为“面临风险”。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="1d3e6e43c754ef13f464b37de5db174e" id="tgt173" class="tgtSentence">每当实时保护检测到威胁或潜在威胁时，Windows Defender 会显示一条通知。</caps:sentence>
            <caps:sentence sentenceid="b3c66da2d7cb35c35e0355c7e622bb3d" id="tgt174" class="tgtSentence"> 你可从以下选项中进行选择：</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="4a299835f83f0d3c11ee8a151d0f7284" id="tgt175" class="tgtSentence">单击“清理计算机”<ui></ui>删除检测到的项目。</caps:sentence>
                <caps:sentence sentenceid="191e0b47783119020141bec0785e4ead" id="tgt176" class="tgtSentence"> Windows Defender 将自动从你的计算机删除该项目。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="a4a2faec7b1882a1e8b0ece5da67bc5a" id="tgt177" class="tgtSentence">单击“显示详细信息”<ui></ui>链接以显示潜在威胁的详细信息窗口，然后选择要应用于检测到的项目的操作。</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence sentenceid="fffa95b10a0cb355cb4822f1640f164c" id="tgt178" class="tgtSentence">你可以选择你需要 Windows Defender 监视的软件和设置，但我们建议你打开实时保护，并启用所有实时保护选项。</caps:sentence>
            <caps:sentence sentenceid="ae29a22fafa0c0b9e25223eb370629f2" id="tgt179" class="tgtSentence"> 下表对可用的选项进行了说明。</caps:sentence>
          </para>
          <table>
            <tbody>
              <tr>
                <TD>
                  <table>
                    <tbody>
                      <tr>
                        <TD>
                          <para>
                            <legacyBold>
                              <caps:sentence sentenceid="8c4b4b816c4ec9907f382e91dddb9eb2" id="tgt180" class="tgtSentence">实时保护选项</caps:sentence>
                            </legacyBold>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <legacyBold>
                              <caps:sentence sentenceid="4d066bbb0e40abe54f3000755a45aa6e" id="tgt181" class="tgtSentence">目的</caps:sentence>
                            </legacyBold>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="58d618c75ccfbf69f3e415c263ef4dbf" id="tgt182" class="tgtSentence">扫描所有下载</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="bd73c9ad627ce3506eb4d472ea7c6d59" id="tgt183" class="tgtSentence">此选项可监视下载的文件和程序，包括通过 Windows Internet Explorer 和 Microsoft Outlook ® Express 自动下载的文件，例如 ActiveX® 控件和软件安装程序。</caps:sentence>
                            <caps:sentence sentenceid="7d4686281d5b898833f15b492e0b917b" id="tgt184" class="tgtSentence"> 这些文件可通过浏览器自身下载、安装或运行。</caps:sentence>
                            <caps:sentence sentenceid="f9eb59c7bec13af95352a00a19af440e" id="tgt185" class="tgtSentence"> 恶意软件，包括病毒、间谍软件和其他可能不需要的软件可以包含在这些文件中，并在你不知情的情况下安装。</caps:sentence>
                          </para>
                          <para>
                            <caps:sentence sentenceid="b1405482cbb9b2283557c21b263fe57c" id="tgt186" class="tgtSentence">使用此实时保护选项，Windows Defender 可以始终监视你的计算机，并检查你可能已下载的任何恶意文件或程序。</caps:sentence>
                            <caps:sentence sentenceid="1bf53fbbe7dd134a248f9c3cf5080f8f" id="tgt187" class="tgtSentence"> 此监视功能意味着 Windows Defender 不需要通过要求检查你可能想要下载的任何文件或程序来减慢你的浏览或电子邮件速度。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="bf38315519036f9b58f6fad56866a246" id="tgt188" class="tgtSentence">监视计算机上的文件和程序活动</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="5d114353d5e55b62cf817902290f7a53" id="tgt189" class="tgtSentence">此选项是在文件和程序开始在你的计算机上运行时进行监视，然后它会对你发出警报，通知你它们要执行的任何操作和要对它们执行的操作。</caps:sentence>
                            <caps:sentence sentenceid="5a0d5b9aa3c4fe00b2169a8c46e65e96" id="tgt190" class="tgtSentence"> 这非常重要，因为恶意软件会利用已安装程序的漏洞在你不知情的情况下运行恶意或不需要的软件。</caps:sentence>
                            <caps:sentence sentenceid="26d12139c03c293a3b9cc4813d964a69" id="tgt191" class="tgtSentence"> 例如，当你启动经常使用的程序时，间谍软件可以在后台运行。</caps:sentence>
                            <caps:sentence sentenceid="374ba4d1ee8ef9ba3684c27ddb6a7082" id="tgt192" class="tgtSentence"> Windows Defender 监视你的程序，并在检测到可疑活动时向你发出警报。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="3d208f8fa970e6f17d21f08a7cf1feaf" id="tgt193" class="tgtSentence">启用行为监视</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="7c51b691805397eb48e82818b0dc3303" id="tgt194" class="tgtSentence">此选项可监视传统防病毒检测方法可能检测不到的可疑模式的行为集合。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="fd14e29fc5bd1f831bc66ba46b0de2ea" id="tgt195" class="tgtSentence">启用网络检查系统</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="b0e4957bee53adaafcb22ce810a057e6" id="tgt196" class="tgtSentence">此选项可帮助保护计算机免受已知漏洞的零日攻击、减小发现漏洞和应用更新之间的时间段。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                    </tbody>
                  </table>
                </TD>
              </tr>
            </tbody>
          </table>
          <procedure>
            <title>
              <caps:sentence sentenceid="96cf8686fdbf38d0a505b74cb06f8802" id="tgt197" class="tgtSentence">要关闭实时保护</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="e59dce2392940ade72b1f86e072e4999" id="tgt198" class="tgtSentence">单击“设置”<ui></ui>，然后单击“实时保护”<ui></ui>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="367af574abb2a61a6b4739539505f6b6" id="tgt199" class="tgtSentence">清除你想要关闭的实时保护选项，然后单击“保存更改”<ui></ui>。</caps:sentence>
                    <caps:sentence sentenceid="d3fecf0366208e41181c17c81127b50c" id="tgt200" class="tgtSentence"> 如果系统提示你输入管理员密码或进行确认，请键入密码或确认操作。</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
          </procedure>
        </content>
      </section>
      <section address="BKMK_Run">
        <title>
          <caps:sentence sentenceid="7d6355875dd936165c103babd0582946" id="tgt201" class="tgtSentence">如何知道 Windows Defender 或 Endpoint Protection 正在我的计算机上运行？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="e0a5edc1b2e6a44c17019f721b266196" id="tgt202" class="tgtSentence">在计算机上安装 Windows Defender 后，可关闭主窗口，让 Windows Defender 在后台安静地运行。</caps:sentence>
            <caps:sentence sentenceid="ffe90843fa52257b76be892b628736d9" id="tgt203" class="tgtSentence"> Windows Defender 将继续在计算机上运行、监视它，并帮助保护其免遭威胁。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="f7bcf7c02de9ce0ee7c0250007ac530f" id="tgt204" class="tgtSentence">当然，每当 Windows Defender 在通知区域显示通知消息时，你就会知道它正在运行。</caps:sentence>
            <caps:sentence sentenceid="1d678a8448c17bbc0c2b961ac1e07743" id="tgt205" class="tgtSentence"> 这些通知提醒你 Windows Defender 检测到的潜在威胁。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="15f3cef62455630e16e8e09eb14e9552" id="tgt206" class="tgtSentence">你还将收到其他警报通知，例如，因某种原因关闭了实时保护，你已经有很多天没有更新你的病毒定义和间谍软件定义，或者程序升级已推出。</caps:sentence>
            <caps:sentence sentenceid="bd5b2caa9d23c97d9e3f33bc13fe61ab" id="tgt207" class="tgtSentence"> Windows Defender 还会显示一条简短通知，告知你它正在扫描计算机。</caps:sentence>
          </para>
          <alert class="tip">
            <para>
              <caps:sentence sentenceid="e841cc48b7f465f0240a6aa79b646079" id="tgt208" class="tgtSentence">如果你在通知区域看不到 Windows Defender 图标，则单击通知区域中的箭头以显示隐藏的图标（包括 Windows Defender 图标）。</caps:sentence>
            </para>
          </alert>
          <para>
            <caps:sentence sentenceid="335d4fa92b233cb2803844786b3f0170" id="tgt209" class="tgtSentence">图标颜色取决于你的计算机的当前状态： </caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="fd024d6ffc0268277f5b16f12e1fc954" id="tgt210" class="tgtSentence">绿色表示你的计算机的状态为“受保护”。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="67f243fa754bb469d6cd0611e67d985e" id="tgt211" class="tgtSentence">黄色表示你的计算机的状态为“可能不受保护”。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="cd5d1572a1ddbd6a238df83ccbaf99a8" id="tgt212" class="tgtSentence">红色表示你的计算机的状态为“有风险”。</caps:sentence>
              </para>
            </listItem>
          </list>
        </content>
      </section>
      <section address="BKMK_Alert">
        <title>
          <caps:sentence sentenceid="17ce9e4366d3caeee27b9d089fd1722f" id="tgt213" class="tgtSentence">如何设置 Windows Defender 或 Endpoint Protection 警报？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="bf6c620d80e1a9ee65d31632288db2ee" id="tgt214" class="tgtSentence">当 Windows Defender 在你的计算机上运行时，它会在检测到病毒、间谍软件或其他可能不需要的软件时自动向你发出警报。</caps:sentence>
            <caps:sentence sentenceid="dba1f4eb2960fff54fe4377a535c5ce3" id="tgt215" class="tgtSentence"> 你还可将 Windows Defender 设置为在你运行未经分析的软件时向你发出警报，并且可选择在软件对计算机进行更改时向你发出警报。</caps:sentence>
          </para>
          <procedure>
            <title>
              <caps:sentence sentenceid="12a8476c5f4fd6e7412353895cfc0ad9" id="tgt216" class="tgtSentence">要设置警报</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="e59dce2392940ade72b1f86e072e4999" id="tgt217" class="tgtSentence">单击“设置”<ui></ui>，然后单击“实时保护”<ui></ui>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="cd391e095c72130e5298c07019b8c684" id="tgt218" class="tgtSentence">确保选中“打开实时保护(推荐)”<ui></ui>复选框。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="a7e1f187a3a8c3c76cb79311d758ca95" id="tgt219" class="tgtSentence">选中你希望运行的实时保护选项旁边的复选框，然后单击“保存更改”<ui></ui>。</caps:sentence>
                    <caps:sentence sentenceid="d3fecf0366208e41181c17c81127b50c" id="tgt220" class="tgtSentence"> 如果系统提示你输入管理员密码或进行确认，请键入密码或确认操作。</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
          </procedure>
        </content>
      </section>
      <relatedTopics>
        <link xlink:href="d837253e-fcc2-422a-9e2c-c78b938dfd8c">Troubleshooting Windows Defender or Endpoint Protection client</link>
        <link xlink:href="fdcee455-22e3-451d-bcf3-e7b62792f04a">Endpoint Protection Client Help</link>
      </relatedTopics>
    </developerConceptualDocument>
  </caps:SxSTarget>
  <caps:SxSSource locale="en-US">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xlink="http://www.w3.org/1999/xlink">
      <introduction>
        <para>
          <caps:sentence id="src1" class="srcSentence">This FAQ is for computer users whose IT administrator has deployed Windows Defender or Endpoint Protection to their managed computer.</caps:sentence>
          <caps:sentence id="src2" class="srcSentence"> The content here might not apply to other antimalware software applied, but much of it is useful for all computer users.</caps:sentence>
          <caps:sentence id="src3" class="srcSentence"> Microsoft System Center Endpoint Protection deploys and manages the Endpoint Protection client to computers before Windows 10.</caps:sentence>
          <caps:sentence id="src4" class="srcSentence"> In Windows 10, the Endpoint Protection is replaced by Windows Defender.</caps:sentence>
          <caps:sentence id="src5" class="srcSentence"> Windows Defender comes with all Windows 10 operating systems but is managed by System Center Endpoint Protection.</caps:sentence>
          <caps:sentence id="src6" class="srcSentence"> While Windows Defender is described in this article, its information also applies to Endpoint Protection.</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence id="src7" class="srcSentence">Why do I need antivirus and antispyware software?</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_Why</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence id="src8" class="srcSentence">How can I tell if my computer is infected with malicious software?</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_How</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence id="src9" class="srcSentence">What should I do if Windows Defender or Endpoint Protection detects malicious software on my computer?</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_What</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence id="src10" class="srcSentence">What is a virus?</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_Virus</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence id="src11" class="srcSentence">What is a spyware?</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_Spy</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence id="src12" class="srcSentence">What's the difference between viruses, spyware, and other potentially harmful software?</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_Diff</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence id="src13" class="srcSentence">Where do viruses, spyware, and other potentially unwanted software come from?</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_Where</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence id="src14" class="srcSentence">Can I get malicious software without knowing it?</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_Can</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence id="src15" class="srcSentence">Why is it important to review license agreements before installing software?</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_License</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence id="src16" class="srcSentence">Where do viruses, spyware, and other potentially unwanted software come from?</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_Where</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence id="src17" class="srcSentence">What's the difference between Endpoint Protection and Windows Defender?</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_EPWD</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence id="src18" class="srcSentence">Why doesn't Windows Defender detect cookies?</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_Cookies</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence id="src19" class="srcSentence">How can I prevent malware?</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_MalPrev</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence id="src20" class="srcSentence">What are virus and spyware definitions?</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_Def</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence id="src21" class="srcSentence">How do I keep virus and spyware definitions up to date?</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_HowDef</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence id="src22" class="srcSentence">How do I remove or restore items quarantined by Windows Defender or Endpoint Protection?</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_HowRem</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence id="src23" class="srcSentence">What is real-time protection?</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_Real</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence id="src24" class="srcSentence">How do I know that Windows Defender or Endpoint Protection is running on my computer?</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_Run</linkUri>
              </externalLink>
            </para>
          </listItem>
          <listItem>
            <para>
              <externalLink>
                <linkText>
                  <caps:sentence id="src25" class="srcSentence">How to set up Windows Defender or Endpoint Protection alerts?</caps:sentence>
                </linkText>
                <linkUri>https://technet.microsoft.com/mt679057.aspx#BKMK_Alert</linkUri>
              </externalLink>
            </para>
          </listItem>
        </list>
      </introduction>
      <section address="BKMK_Why">
        <title>
          <caps:sentence id="src26" class="srcSentence">Why do I need antivirus and antispyware software?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src27" class="srcSentence">It is critical to make sure that your computer is running software that protects against malicious software.</caps:sentence>
            <caps:sentence id="src28" class="srcSentence"> Malicious software, which includes viruses, spyware, or other potentially unwanted software can try to install itself on your computer any time you connect to the Internet.</caps:sentence>
            <caps:sentence id="src29" class="srcSentence"> It can also infect your computer when you install a program using a CD, DVD, or other removable media.</caps:sentence>
            <caps:sentence id="src30" class="srcSentence"> Malicious software, can also be programmed to run at unexpected times, not just when it is installed.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src31" class="srcSentence">
      Windows Defender or Endpoint Protection offers three ways to help keep malicious software from infecting your computer:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src32" class="srcSentence">
                  <legacyBold>Using real-time protection</legacyBold>—Real-time protection enables Windows Defender to monitor your computer all the time and alert you when malicious software, including viruses, spyware, or other potentially unwanted software attempts to install itself or run on your computer.</caps:sentence>
                <caps:sentence id="src33" class="srcSentence"> Windows Defender then suspends the software and enables you to you to follow its recommendation on the software or take an alternative action.</caps:sentence>
              </para>
              <table>
                <tbody>
                  <tr>
                    <TD>
                      <para>
                        <legacyBold>
                          <caps:sentence id="src34" class="srcSentence">Real-time protection option</caps:sentence>
                        </legacyBold>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <legacyBold>
                          <caps:sentence id="src35" class="srcSentence">Purpose</caps:sentence>
                        </legacyBold>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src36" class="srcSentence">Scan all downloads</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src37" class="srcSentence">This option monitors files and programs that are downloaded, including files that are automatically downloaded via Windows Internet Explorer and Microsoft Outlook® Express, such as ActiveX® controls and software installation programs.</caps:sentence>
                        <caps:sentence id="src38" class="srcSentence"> These files can be downloaded, installed, or run by the browser itself.</caps:sentence>
                        <caps:sentence id="src39" class="srcSentence"> Malicious software, including viruses, spyware, and other potentially unwanted software, can be included with these files and installed without your knowledge.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src40" class="srcSentence">Using the real-time protection option, Windows Defender monitors your computer all the time and checks for any malicious files or programs that you may have downloaded.</caps:sentence>
                        <caps:sentence id="src41" class="srcSentence"> This monitoring feature means that Windows Defender doesn't need to slow down your browsing or e-mail experience by requiring a check of any files or programs you may want to download.</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src42" class="srcSentence">Monitor file and program activity on your computer</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src43" class="srcSentence">This option monitors when files and programs start running on your computer, and then it alerts you about any actions they perform and actions taken on them.</caps:sentence>
                        <caps:sentence id="src44" class="srcSentence"> This is important, because malicious software can use vulnerabilities in programs that you have installed to run malicious or unwanted software without your knowledge.</caps:sentence>
                        <caps:sentence id="src45" class="srcSentence"> For example, spyware can run itself in the background when you start a program that you frequently use.</caps:sentence>
                        <caps:sentence id="src46" class="srcSentence"> Windows Defender monitors your programs and alerts you if it detects suspicious activity.</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src47" class="srcSentence">Enable behavior monitoring</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src48" class="srcSentence">This option monitors collections of behavior for suspicious patterns that might not be detected by traditional antivirus detection methods.</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src49" class="srcSentence">Enable Network Inspection System</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src50" class="srcSentence">This option helps protect your computer against “zero day” exploits of known vulnerabilities, decreasing the window of time between the moment a vulnerability is discovered and an update is applied.</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </tbody>
              </table>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src51" class="srcSentence">
                  <legacyBold>Scanning options</legacyBold>—You can use Windows Defender to scan for potential threats, such as viruses, spyware, and other malicious software that might put your computer at risk.</caps:sentence>
                <caps:sentence id="src52" class="srcSentence"> You can also use it to schedule scans on a regular basis and to remove malicious software that is detected during a scan.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src53" class="srcSentence">
                  <legacyBold> Microsoft Active Protection Service community</legacyBold>—The online Microsoft Active Protection Service community helps you see how other people respond to software that has not yet been classified for risks.</caps:sentence>
                <caps:sentence id="src54" class="srcSentence"> You can use this information to help you choose whether to allow this software on your computer.</caps:sentence>
                <caps:sentence id="src55" class="srcSentence"> In turn, if you participate, your choices are added to the community ratings to help other people decide what to do.</caps:sentence>
              </para>
            </listItem>
          </list>
        </content>
      </section>
      <section address="BKMK_How">
        <title>
          <caps:sentence id="src56" class="srcSentence">How can I tell if my computer is infected with malicious software?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src57" class="srcSentence">You might have some form of malicious software, including viruses, spyware, or other potentially unwanted software, on your computer if: </caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src58" class="srcSentence">You notice new toolbars, links, or favorites that you did not intentionally add to your Web browser.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src59" class="srcSentence">Your home page, mouse pointer, or search program changes unexpectedly.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src60" class="srcSentence">You type the address for a specific site, such as a search engine, but you are taken to a different Web site without notice.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src61" class="srcSentence">Files are automatically deleted from your computer.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src62" class="srcSentence">Your computer is used to attack other computers.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src63" class="srcSentence">You see pop-up ads, even if you're not on the Internet.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src64" class="srcSentence">Your computer suddenly starts running more slowly than it usually does.</caps:sentence>
                <caps:sentence id="src65" class="srcSentence"> Not all computer performance problems are caused by malicious software, but malicious software, especially spyware, can cause a noticeable change.</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence id="src66" class="srcSentence">There might be malicious software on your computer even if you don't see any symptoms.</caps:sentence>
            <caps:sentence id="src67" class="srcSentence"> This type of software can collect information about you and your computer without your knowledge or consent.</caps:sentence>
            <caps:sentence id="src68" class="srcSentence"> To help protect your privacy and your computer, you should run Windows Defender or Endpoint Protection at all times.</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_What">
        <title>
          <caps:sentence id="src69" class="srcSentence">What should I do if Windows Defender or Endpoint Protection detects malicious software on my computer?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src70" class="srcSentence">If Windows Defender detects malicious software or potentially unwanted software on your computer (either when monitoring your computer using real-time protection or after running a scan), it notifies you about the detected item by displaying a notification message in the bottom right-hand corner of your screen.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src71" class="srcSentence">The notification message includes a <ui>Clean computer</ui> button and a <ui>Show details</ui> link that lets you view additional information about the detected item.</caps:sentence>
            <caps:sentence id="src72" class="srcSentence"> Click the <ui>Show details</ui> link to open the <ui>Potential threat details</ui> window to get additional information about the detected item.</caps:sentence>
            <caps:sentence id="src73" class="srcSentence"> You can now choose which action to apply to the item, or click <ui>Clean computer</ui>.</caps:sentence>
            <caps:sentence id="src74" class="srcSentence"> If you need help determining which action to apply to the detected item, use the alert level that Windows Defender assigned to the item as your guide (for more information see, Understanding alert levels).</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src75" class="srcSentence">Alert levels help you choose how to respond to viruses, spyware, and other potentially unwanted software.</caps:sentence>
            <caps:sentence id="src76" class="srcSentence"> While Windows Defender will recommend that you remove all viruses and spyware, not all software that is flagged is malicious or unwanted.</caps:sentence>
            <caps:sentence id="src77" class="srcSentence"> The following information can help you decide what to do if Windows Defender detects potentially unwanted software on your computer.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src78" class="srcSentence">Depending on the alert level, you can choose one of the following actions to apply to the detected item:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src79" class="srcSentence">
                  <legacyBold>Remove</legacyBold>—This action permanently deletes the software from your computer.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src80" class="srcSentence">
                  <legacyBold>Quarantine</legacyBold>—This action quarantines the software so that it can't run.</caps:sentence>
                <caps:sentence id="src81" class="srcSentence"> When Windows Defender quarantines software, it moves it to another location on your computer, and then prevents the software from running until you choose to restore it or remove it from your computer.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src82" class="srcSentence">
                  <legacyBold>Allow</legacyBold>—This action adds the software to the Windows Defender allowed list and allows it to run on your computer.</caps:sentence>
                <caps:sentence id="src83" class="srcSentence"> Windows Defender will stop alerting you to risks that the software might pose to your privacy or to your computer.</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence id="src84" class="srcSentence">If you choose <ui>Allow</ui> for an item, such as software, Windows Defender will stop alerting you to risks that the software might pose to your privacy or to your computer.</caps:sentence>
            <caps:sentence id="src85" class="srcSentence"> Therefore, add software to the allowed list only if you trust the software and the software publisher.</caps:sentence>
          </para>
          <para>
            <embeddedLabel>
              <caps:sentence id="src86" class="srcSentence">How to remove potentially harmful software</caps:sentence>
            </embeddedLabel>
          </para>
          <para>
            <caps:sentence id="src87" class="srcSentence">To remove all unwanted or potentially harmful items that Windows Defender detects quickly and easily, use the <ui>Clean computer</ui> option.</caps:sentence>
          </para>
          <list class="ordered">
            <listItem>
              <para>
                <caps:sentence id="src88" class="srcSentence">When you see the notification message that  displays in the Notification area after it detects potential threats, click <ui>Clean computer</ui>.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src89" class="srcSentence">
          Windows Defender removes the potential threat (or threats), and then notifies you when it's finished cleaning your computer.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src90" class="srcSentence">To learn more about the detected threats, click the <ui>History</ui> tab, and then select <ui>All detected items</ui>.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src91" class="srcSentence">If you don't see all the detected items, click <ui>View details</ui>.</caps:sentence>
                <caps:sentence id="src92" class="srcSentence"> If you're prompted for an administrator password or confirmation, type the password or confirm the action.</caps:sentence>
                <caps:sentence id="src93" class="srcSentence"> On systems running Windows XP, you may need to log on as an administrator on this computer.</caps:sentence>
              </para>
            </listItem>
          </list>
          <alert class="note">
            <para>
              <caps:sentence id="src94" class="srcSentence">During computer cleanup, whenever possible, Windows Defender removes only the infected part of a file, not the entire file.</caps:sentence>
            </para>
          </alert>
        </content>
      </section>
      <section address="BKMK_Virus">
        <title>
          <caps:sentence id="src95" class="srcSentence">What is a virus?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src96" class="srcSentence">Computer viruses are software programs deliberately designed to interfere with computer operation, to record, corrupt, or delete data, or to infect other computers throughout the Internet.</caps:sentence>
            <caps:sentence id="src97" class="srcSentence"> Viruses often slow things down and cause other problems in the process.</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_Spy">
        <title>
          <caps:sentence id="src98" class="srcSentence">What is spyware?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src99" class="srcSentence">Spyware is software that can install itself or run on your computer without getting your consent or providing you with adequate notice or control.</caps:sentence>
            <caps:sentence id="src100" class="srcSentence"> Spyware might not display symptoms after it infects your computer, but many malicious or unwanted programs can affect how your computer runs.</caps:sentence>
            <caps:sentence id="src101" class="srcSentence"> For example, spyware can monitor your online behavior or collect information about you (including information that can identify you or other sensitive information), change settings on your computer, or cause your computer to run slowly.</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_Diff">
        <title>
          <caps:sentence id="src102" class="srcSentence">What's the difference between viruses, spyware, and other potentially harmful software?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src103" class="srcSentence">Both viruses and spyware are installed on your computer without your knowledge and both have the potential to be intrusive and destructive.</caps:sentence>
            <caps:sentence id="src104" class="srcSentence"> They also have the ability to capture information on your computer and damage or delete that information.</caps:sentence>
            <caps:sentence id="src105" class="srcSentence"> They both can negatively affect your computer's performance.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src106" class="srcSentence">The main differences between viruses and spyware is how they behave on your computer.</caps:sentence>
            <caps:sentence id="src107" class="srcSentence"> Viruses, like living organisms, want to infect a computer, replicate, and then spread to as many other computers as possible.</caps:sentence>
            <caps:sentence id="src108" class="srcSentence"> Spyware, however, is more like a mole—it wants to "move into" your computer and stay there as long as possible, sending valuable information about your computer to an outside source while it is there.</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_Where">
        <title>
          <caps:sentence id="src109" class="srcSentence">Where do viruses, spyware, and other potentially unwanted software come from?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src110" class="srcSentence">Unwanted software, such as viruses, can be installed by Web sites or by programs that you download or that you install using a CD, DVD, external hard disk, or a device.</caps:sentence>
            <caps:sentence id="src111" class="srcSentence"> Spyware is most commonly installed through free software, such as file sharing, screen savers, or search toolbars.</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_Can">
        <title>
          <caps:sentence id="src112" class="srcSentence">Can I get malicious software without knowing it?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src113" class="srcSentence">Yes, some malicious software can be installed from a Web site through an embedded script or program in a Web page.</caps:sentence>
            <caps:sentence id="src114" class="srcSentence"> Some malicious software requires your help to install it.</caps:sentence>
            <caps:sentence id="src115" class="srcSentence"> This software uses Web pop-ups or free software that requires you to accept a downloadable file.</caps:sentence>
            <caps:sentence id="src116" class="srcSentence"> However, if you keep Microsoft Windows® up to date and don't reduce your security settings, you can minimize the chances of an infection.</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_License">
        <title>
          <caps:sentence id="src117" class="srcSentence">Why is it important to review license agreements before installing software?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src118" class="srcSentence">When you visit Web sites, do not automatically agree to download anything the site offers.</caps:sentence>
            <caps:sentence id="src119" class="srcSentence"> If you download free software, such as file sharing programs or screen savers, read the license agreement carefully.</caps:sentence>
            <caps:sentence id="src120" class="srcSentence"> Look for clauses that say that you must accept advertising and pop-ups from the company, or that the software will send certain information back to the software publisher.</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_EPWD">
        <title>
          <caps:sentence id="src121" class="srcSentence">What's the difference between Endpoint Protection and Windows Defender?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src122" class="srcSentence">
        Endpoint Protection is antimalware software, which means that it's designed to detect and help protect your computer against a wide range of malicious software, including viruses, spyware, and other potentially unwanted software.</caps:sentence>
            <caps:sentence id="src123" class="srcSentence"> Windows Defender, which is automatically installed with your Windows operating system, is software that detects and stops spyware.</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_Cookies">
        <title>
          <caps:sentence id="src124" class="srcSentence">Why doesn't Windows Defender detect cookies?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src125" class="srcSentence">Cookies are small text files that web sites put on your computer to store information about you and your preferences.</caps:sentence>
            <caps:sentence id="src126" class="srcSentence"> Web sites use cookies to offer you a personalized experience and to gather information about Web site use.</caps:sentence>
            <caps:sentence id="src127" class="srcSentence"> Windows Defender doesn't detect cookies, because it doesn't consider them a threat to your privacy or to the security of your computer.</caps:sentence>
            <caps:sentence id="src128" class="srcSentence"> Most Internet browser programs allow you to block cookies.</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_MalPrev">
        <title>
          <caps:sentence id="src129" class="srcSentence">How can I prevent malware?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src130" class="srcSentence">Two of the biggest concerns for computer users today are viruses and spyware.</caps:sentence>
            <caps:sentence id="src131" class="srcSentence"> In both cases, while these can be a problem, you can defend yourself against them easily enough with just a little bit of planning:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src132" class="srcSentence">Keep your computer’s software current and remember to install all patches.</caps:sentence>
                <caps:sentence id="src133" class="srcSentence"> Remember to update your operating system on a regular basis.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src134" class="srcSentence">Make sure your antivirus and antispyware software, Windows Defender, is using the latest updates again potential threats (see How do I keep virus and spyware definitions up to date?).</caps:sentence>
                <caps:sentence id="src135" class="srcSentence"> Also make sure you're always using the latest version of Windows Defender.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src136" class="srcSentence">Only download updates from reputable sources.</caps:sentence>
                <caps:sentence id="src137" class="srcSentence"> For Windows operating systems, always go to <externalLink><linkText>Microsoft Update</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkID=96304</linkUri></externalLink> (http://go.microsoft.com/fwlink/?LinkID=96304) and for other software always use the legitimate Web sites of the company or person who produces it.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src138" class="srcSentence"> If you receive an e-mail with an attachment and you're unsure of the source, then you should delete it immediately.</caps:sentence>
                <caps:sentence id="src139" class="srcSentence"> Don't download any applications or executable files from unknown sources, and be careful when trading files with other users.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src140" class="srcSentence">Install and use a firewall.</caps:sentence>
                <caps:sentence id="src141" class="srcSentence"> It is recommended that you enable Windows Firewall.</caps:sentence>
              </para>
            </listItem>
          </list>
        </content>
      </section>
      <section address="BKMK_Def">
        <title>
          <caps:sentence id="src142" class="srcSentence">What are virus and spyware definitions?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src143" class="srcSentence">When you use Windows Defender or Endpoint Protection, it is important to have up-to-date virus and spyware definitions.</caps:sentence>
            <caps:sentence id="src144" class="srcSentence"> Definitions are files that act like an ever-growing encyclopedia of potential software threats.</caps:sentence>
            <caps:sentence id="src145" class="srcSentence"> Windows Defender or Endpoint Protection uses definitions to determine if software that it detects is a virus, spyware, or other potentially unwanted software, and then to alert you to potential risks.</caps:sentence>
            <caps:sentence id="src146" class="srcSentence"> To help keep your definitions up to date, Windows Defender or Endpoint Protection works with Microsoft Update to install new definitions automatically as they are released.</caps:sentence>
            <caps:sentence id="src147" class="srcSentence"> You can also set Windows Defender or Endpoint Protection to check online for updated definitions before scanning.</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_HowDef">
        <title>
          <caps:sentence id="src148" class="srcSentence">How do I keep virus and spyware definitions up to date?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src149" class="srcSentence">Virus and spyware definitions are files that act like an encyclopedia of known malicious software, including viruses, spyware, and other potentially unwanted software.</caps:sentence>
            <caps:sentence id="src150" class="srcSentence"> Because malicious software is continually being developed, Windows Defender or Endpoint Protection relies on up-to-date definitions to determine if software that is trying to install, run, or change settings on your computer is a virus, spyware, or other potentially unwanted software.</caps:sentence>
          </para>
          <para>
            <embeddedLabel>
              <caps:sentence id="src151" class="srcSentence">To automatically check for new definitions before scheduled scans (recommended)</caps:sentence>
            </embeddedLabel>
          </para>
          <list class="ordered">
            <listItem>
              <para>
                <caps:sentence id="src152" class="srcSentence">Open Windows Defender or Endpoint Protection client by clicking the icon in the notification area or launching it from the <ui>Start</ui> menu.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src153" class="srcSentence">Click <ui>Settings</ui>, and then click <ui>Scheduled scan</ui>.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src154" class="srcSentence">Make sure the <ui>Check for the latest virus and spyware definitions before running a scheduled scan</ui> check box is selected, and then click <ui>Save changes</ui>.</caps:sentence>
                <caps:sentence id="src155" class="srcSentence"> If you're prompted for an administrator password or confirmation, type the password or confirm the action.</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <embeddedLabel>
              <caps:sentence id="src156" class="srcSentence">To check for new definitions manually</caps:sentence>
            </embeddedLabel>
          </para>
          <para>
            <caps:sentence id="src157" class="srcSentence">Windows Defender or Endpoint Protection updates the virus and spyware definitions on your computer automatically.</caps:sentence>
            <caps:sentence id="src158" class="srcSentence"> If the definitions haven’t been updated for over seven days (for example, if you didn’t turn on your computer for a week), Windows Defender or Endpoint Protection will notify you that the definitions are out of date.</caps:sentence>
          </para>
          <list class="ordered">
            <listItem>
              <para>
                <caps:sentence id="src159" class="srcSentence">Open Windows Defender or Endpoint Protection client by clicking the icon in the notification area or launching it from the <ui>Start</ui> menu.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src160" class="srcSentence">To check for new definitions manually, click the <ui>Update</ui> tab and then click <ui>Update definitions</ui>.</caps:sentence>
              </para>
            </listItem>
          </list>
        </content>
      </section>
      <section address="BKMK_HowRem">
        <title>
          <caps:sentence id="src161" class="srcSentence">How do I remove or restore items quarantined by Windows Defender or Endpoint Protection?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src162" class="srcSentence">When Windows Defender or Endpoint Protection quarantines software, it moves the software to another location on your computer, and then it prevents the software from running until you choose to restore it or to remove it from your computer.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src163" class="srcSentence">For all the steps mentioned in this procedure, if you're prompted for an administrator password or confirmation, type the password or provide confirmation.</caps:sentence>
          </para>
          <para>
            <embeddedLabel>
              <caps:sentence id="src164" class="srcSentence">To remove or restore items quarantined by Windows Defender or Endpoint Protection</caps:sentence>
            </embeddedLabel>
          </para>
          <list class="ordered">
            <listItem>
              <para>
                <caps:sentence id="src165" class="srcSentence">Click the <ui>History</ui> tab, select <ui>Quarantined items</ui>, and then select the <ui>Quarantined items</ui> option.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src166" class="srcSentence">Click <ui>View details</ui> to see all of the items.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src167" class="srcSentence">Review each item, and then for each, click <ui>Remove</ui> or <ui>Restore</ui>.</caps:sentence>
                <caps:sentence id="src168" class="srcSentence"> If you want to remove of the all quarantined items from your computer, click <ui>Remove All</ui>.</caps:sentence>
              </para>
            </listItem>
          </list>
        </content>
      </section>
      <section address="BKMK_Real">
        <title>
          <caps:sentence id="src169" class="srcSentence">What is real-time protection?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src170" class="srcSentence">Real-time protection enables Windows Defender to monitor your computer all the time and alert you when potential threats, such as viruses and spyware, are trying to install themselves or run on your computer.</caps:sentence>
            <caps:sentence id="src171" class="srcSentence"> Because this feature is an important element of the way that Windows Defender helps protect your computer, you should make sure real-time protection is always turned on.</caps:sentence>
            <caps:sentence id="src172" class="srcSentence"> If real-time protection gets turned off, Windows Defender notifies you, and changes your computer’s status to “At risk”.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src173" class="srcSentence">Whenever real-time protection detects a threat or potential threat, Windows Defender displays a notification.</caps:sentence>
            <caps:sentence id="src174" class="srcSentence"> You can now choose from the following options:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src175" class="srcSentence">Click <ui>Clean computer</ui> to remove the detected item.</caps:sentence>
                <caps:sentence id="src176" class="srcSentence"> Windows Defender will automatically remove the item from your computer.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src177" class="srcSentence">Click the <ui>Show details</ui> link to display the Potential threat details window, and then choose which action to apply to the detected item.</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence id="src178" class="srcSentence">You can choose the software and settings that you want Windows Defender to monitor, but we recommend that you turn on real-time protection and enable all real-time protection options.</caps:sentence>
            <caps:sentence id="src179" class="srcSentence"> The following table explains the available options.</caps:sentence>
          </para>
          <table>
            <tbody>
              <tr>
                <TD>
                  <table>
                    <tbody>
                      <tr>
                        <TD>
                          <para>
                            <legacyBold>
                              <caps:sentence id="src180" class="srcSentence">Real-time protection option</caps:sentence>
                            </legacyBold>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <legacyBold>
                              <caps:sentence id="src181" class="srcSentence">Purpose</caps:sentence>
                            </legacyBold>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src182" class="srcSentence">Scan all downloads</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src183" class="srcSentence">This option monitors files and programs that are downloaded, including files that are automatically downloaded via Windows Internet Explorer and Microsoft Outlook® Express, such as ActiveX® controls and software installation programs.</caps:sentence>
                            <caps:sentence id="src184" class="srcSentence"> These files can be downloaded, installed, or run by the browser itself.</caps:sentence>
                            <caps:sentence id="src185" class="srcSentence"> Malicious software, including viruses, spyware, and other potentially unwanted software, can be included with these files and installed without your knowledge.</caps:sentence>
                          </para>
                          <para>
                            <caps:sentence id="src186" class="srcSentence">Using the real-time protection option, Windows Defender monitors your computer all the time and checks for any malicious files or programs that you may have downloaded.</caps:sentence>
                            <caps:sentence id="src187" class="srcSentence"> This monitoring feature means that Windows Defender doesn't need to slow down your browsing or e-mail experience by requiring a check of any files or programs you may want to download.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src188" class="srcSentence">Monitor file and program activity on your computer</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src189" class="srcSentence">This option monitors when files and programs start running on your computer, and then it alerts you about any actions they perform and actions taken on them.</caps:sentence>
                            <caps:sentence id="src190" class="srcSentence"> This is important, because malicious software can use vulnerabilities in programs that you have installed to run malicious or unwanted software without your knowledge.</caps:sentence>
                            <caps:sentence id="src191" class="srcSentence"> For example, spyware can run itself in the background when you start a program that you frequently use.</caps:sentence>
                            <caps:sentence id="src192" class="srcSentence"> Windows Defender monitors your programs and alerts you if it detects suspicious activity.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src193" class="srcSentence">Enable behavior monitoring</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src194" class="srcSentence">This option monitors collections of behavior for suspicious patterns that might not be detected by traditional antivirus detection methods.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src195" class="srcSentence">Enable Network Inspection System</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src196" class="srcSentence">This option helps protect your computer against “zero day” exploits of known vulnerabilities, decreasing the window of time between the moment a vulnerability is discovered and an update is applied.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                    </tbody>
                  </table>
                </TD>
              </tr>
            </tbody>
          </table>
          <procedure>
            <title>
              <caps:sentence id="src197" class="srcSentence">To turn off real-time protection</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence id="src198" class="srcSentence">Click <ui>Settings</ui>, and then click <ui>Real-time protection.</ui></caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src199" class="srcSentence">Clear the real-time protection options you want to turn off, and then click <ui>Save changes</ui>.</caps:sentence>
                    <caps:sentence id="src200" class="srcSentence"> If you're prompted for an administrator password or confirmation, type the password or confirm the action.</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
          </procedure>
        </content>
      </section>
      <section address="BKMK_Run">
        <title>
          <caps:sentence id="src201" class="srcSentence">How do I know that Windows Defender or Endpoint Protection is running on my computer?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src202" class="srcSentence">After you install Windows Defender on your computer, you can close the main window and let Windows Defender run quietly in the background.</caps:sentence>
            <caps:sentence id="src203" class="srcSentence"> Windows Defender will continue running on your computer, monitor it, and help protect it against threats.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src204" class="srcSentence">Of course, you'll know that Windows Defender is running whenever it displays notification messages in the notification area.</caps:sentence>
            <caps:sentence id="src205" class="srcSentence"> These notifications alert you to potential threats that Windows Defender has detected.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src206" class="srcSentence">You'll also receive other alert notifications, for example, if for some reason real-time protection has been turned off, if you haven't updated your virus and spyware definitions for a number of days, or when upgrades to the program become available.</caps:sentence>
            <caps:sentence id="src207" class="srcSentence"> Windows Defender also briefly displays a notification to let you know that it's scanning your computer.</caps:sentence>
          </para>
          <alert class="tip">
            <para>
              <caps:sentence id="src208" class="srcSentence">If you don’t see the Windows Defender icon in the notification area, click the arrow in the notification area to show hidden icons, including the Windows Defender icon.</caps:sentence>
            </para>
          </alert>
          <para>
            <caps:sentence id="src209" class="srcSentence">The icon color depends on your computer's current status: </caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src210" class="srcSentence">Green indicates that your computer's status is "protected."</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src211" class="srcSentence">Yellow indicates that your computer's status is "potentially unprotected."</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src212" class="srcSentence">Red indicates that your computer's status is "at risk."</caps:sentence>
              </para>
            </listItem>
          </list>
        </content>
      </section>
      <section address="BKMK_Alert">
        <title>
          <caps:sentence id="src213" class="srcSentence">How to set up Windows Defender or Endpoint Protection alerts?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src214" class="srcSentence">When Windows Defender is running on your computer, it automatically alerts you if it detects viruses, spyware, or other potentially unwanted software.</caps:sentence>
            <caps:sentence id="src215" class="srcSentence"> You can also set Windows Defender to alert you if you run software that has not yet been analyzed, and you can choose to be alerted when software makes changes to your computer.</caps:sentence>
          </para>
          <procedure>
            <title>
              <caps:sentence id="src216" class="srcSentence">To set up alerts</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence id="src217" class="srcSentence">Click <ui>Settings</ui>, and then click <ui>Real-time protection.</ui></caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src218" class="srcSentence">Make sure the <ui>Turn on real-time protection (recommended)</ui> check box is selected.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src219" class="srcSentence">Select the check boxes next to the real-time protections options you want to run, and then click <ui>Save changes</ui>.</caps:sentence>
                    <caps:sentence id="src220" class="srcSentence"> If you're prompted for an administrator password or confirmation, type the password or confirm the action.</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
          </procedure>
        </content>
      </section>
      <relatedTopics>
        <link xlink:href="d837253e-fcc2-422a-9e2c-c78b938dfd8c">Troubleshooting Windows Defender or Endpoint Protection client</link>
        <link xlink:href="fdcee455-22e3-451d-bcf3-e7b62792f04a">Endpoint Protection Client Help</link>
      </relatedTopics>
    </developerConceptualDocument>
  </caps:SxSSource>
</caps:SxS>
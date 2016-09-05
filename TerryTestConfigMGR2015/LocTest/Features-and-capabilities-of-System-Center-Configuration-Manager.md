---
title: "System Center Configuration Manager 的特性和功能"
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
ms.assetid: 5d388399-07ca-431c-a9b2-56c69771aa87
caps.latest.revision: 18
caps.handback.revision: 15
---
# System Center Configuration Manager 的特性和功能
<?xml version="1.0" encoding="UTF-8"?>
<developerConceptualDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns:xlink="http://www.w3.org/1999/xlink">
    <introduction>
        <para>下表提供有关 <token>cm6long</token> 的主要管理功能的详细信息。 
        </para>
        <list class="bullet">
            <listItem>
                <para>每个功能都有自己的必备条件</para>
            </listItem>
            <listItem>
                <para>你想要使用的功能可能会影响 <token>cmshort</token> 层次结构 </para>
            </listItem>
        </list>
        <para> 的设计和实现，例如，你希望将软件部署到层次结构中的设备，则必须安装分发点站点系统角色。</para>
        <table>
            <thead>
                <tr>
                    <TH>
                        <para>管理功能</para>
                    </TH>
                    <TH>
                        <para>描述</para>
                    </TH>
                    <TH>
                        <para>更多信息</para>
                    </TH>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <TD>
                        <para>
                            <ui>应用程序管理</ui>
                        </para>
                    </TD>
                    <TD>
                        <para>提供一组工具和资源，这些工具和资源可帮助你创建、管理、部署和监视一系列你管理的不同设备的应用程序。 此外，<token>cmshort</token> 提供了一些工具，这些工具可帮助保护你和用户的应用中的公司数据。</para>
                    </TD>
                    <TD>
                        <para>
                            <link xlink:href="62668e7b-b45c-433f-a8d7-435b19212fa8">使用 Configuration Manager 部署和管理应用程序</link>
                        </para>
                    </TD>
                </tr>
                <tr>
                    <TD>
                        <para>
                            <ui>公司资源访问</ui>
                        </para>
                    </TD>
                    <TD>
                        <para>提供了一组工具和资源，使你能够向机构中的用户授予对远程位置中的数据和应用程序的访问权限。 这些工具包括 Wi-Fi 配置文件、VPN 配置文件、证书配置文件和对 Exchange 和 SharePoint Online 的条件访问权限。</para>
                        
                    </TD>
                    <TD>
                        <para>
                            
                        <link xlink:href="2117f786-d521-4790-9e8d-ec096c63c9d7">保护数据和站点基础结构</link></para>
                    <para><link xlink:href="76d86613-b87f-4fe5-9236-a573e00b613a">Configuration Manager 中的条件性访问</link></para></TD>
                </tr>
                <tr>
                    <TD>
                        <para>
                            <ui>符合性设置</ui>
                        </para>
                    </TD>
                    <TD>
                        <para>提供一组工具和资源，这些工具和资源可帮助你在企业中评估、跟踪和修正客户端设备的配置符合性。</para>
                    <para>此外，你还可以使用符合性设置来配置你管理的设备上的一系列功能和安全设置。</para></TD>
                    <TD>
                        <para>
                            <link xlink:href="7568c9aa-b99e-4466-bfc8-0301aa376930">确保设备与 Configuration Manager 相符合</link>
                        </para>
                    </TD>
                </tr>
                <tr>
                    <TD>
                        <para>
                            <ui>Endpoint Protection</ui>
                        </para>
                    </TD>
                    <TD>
                        <para>提供针对企业中的计算机的安全性、反恶意软件和 Windows 防火墙管理。</para>
                    </TD>
                    <TD>
                        <para>
                            <link xlink:href="76c90f64-d729-456b-8304-01852cd66fb6">Configuration Manager 中的 Endpoint Protection</link>
                        </para>
                    </TD>
                </tr>
                <tr>
                    <TD>
                        <para>
                            <ui>清单</ui>
                        </para>
                    </TD>
                    <TD>
                        <para>提供一组工具以帮助确定和监视资产：</para>
                        <para>
                                    <ui>硬件清单</ui>：收集有关企业中的设备硬件的详细信息。
                                </para><para>
                                    <ui>软件清单</ui>：收集和报告有关存储在组织中客户端计算机上的文件的信息。
                                </para><para>
                                    <ui>资产智能</ui>：提供工具以收集清单数据，并监视企业中的软件许可证使用情况。
                                </para>
                    </TD>
                    <TD>
                        <para>请参阅以下文档：</para>
                        <para>
                                    <link xlink:href="3969952e-9d05-49c9-82a2-e7e90ccef511">Configuration Manager 中的硬件清单简介</link>
                                </para><para>
                                    <link xlink:href="79eb49da-cd2b-4ffc-b355-b595aeba3aea">Configuration Manager 中的软件清单简介</link>
                                </para><para>
                                    <link xlink:href="0bdfdef5-390f-4099-8bde-de51d9a89175">Configuration Manager 中的资产智能简介</link>
                                </para>
                    </TD>
                </tr>
                <tr>
                    <TD>
                        <para>
                            <ui>
使用 <token>mit_first 进行移动设备管理</token></ui>
                        </para>
                    </TD>
                    <TD>
                        <para>可以通过 Internet 使用 <token>cmshort</token> 来管理使用 <token>mit_first</token> 服务的 iOS、Android（包括 Samsung KNOX）、Windows Phone 和 Windows 设备。 
                        </para>
                        <para>尽管你使用 <token>mit_next</token> 服务，但管理任务通过使用服务连接点站点系统角色（可通过 <token>cmshort</token>控制台获得）完成。
                        </para>
                    </TD>
                    <TD>
                        <para>
                                    <link xlink:href="bb95154b-f63e-4491-896e-41d732c802f8">使用 System Center Configuration Manager 和 Microsoft Intune 管理移动设备</link>
                                </para>
                    </TD>
                </tr>
                <tr>
                    <TD>
                        <para>
                            <ui>本地移动设备管理</ui>
                        </para>
                    </TD>
                    <TD><para>使用本地 <token>cmshort</token> 基础结构和内置于设备平台的管理功能（而不是依靠单独安装的 <token>cmshort</token> 客户端）注册、管理电脑和移动设备。 当前支持管理 Windows 10 企业版和 Windows 10 移动版设备。 </para></TD>
                    <TD><para><link xlink:href="497c05c7-fe9f-4b88-983b-1c5b3d59308e">使用 System Center Configuration Manager 进行本地移动设备管理</link></para></TD>
                </tr>
                <tr>
                    <TD>
                        <para>
                            <ui>操作系统部署</ui>
                        </para>
                    </TD>
                    <TD>
                        <para>提供工具以创建操作系统映像。 你随后可使用这些映像，通过 PXE 启动或可启动媒体（例如 CD 集、DVD 或 USB 闪存驱动器）将它们部署到 <token>cmshort</token> 管理的计算机以及不受管理的计算机。
                        </para>
                    </TD>
                    <TD>
                        <para>
                            <link xlink:href="d9a1c545-8301-492c-832f-2c108ff93c77">操作系统部署简介</link>
                        </para>
                    </TD>
                </tr>
                <tr>
                    <TD>
                        <para>
                            <ui>电源管理</ui>
                        </para>
                    </TD>
                    <TD>
                        <para>提供一组工具和资源，你可以使用这些工具和资源来管理和监视企业中的客户端计算机的功耗。</para>
                    </TD>
                    <TD>
                        <para>
                            <link xlink:href="3ddff2a7-99eb-4ef8-b969-f3f7f24053db">在配置管理器中的电源管理简介</link>
                        </para>
                    </TD>
                </tr>
                <tr>
                    <TD>
                        <para>
                            <ui>查询</ui>
                        </para>
                    </TD>
                    <TD>
                        <para>提供工具以检索有关层次结构中的资源的信息，以及有关清单数据和状态消息的信息。 你可以使用此信息为软件部署及配置设置报告或定义设备或用户的集合。</para>
                    </TD>
                    <TD>
                        <para>
                            <link xlink:href="03d1b3a9-41db-4d3a-a70e-e05ab5dc8141">查询在 Configuration Manager 简介</link>
                        </para>
                    </TD>
                </tr>
                <tr>
                    <TD>
                        <para>
                            <ui>远程连接配置文件</ui>
                        </para>
                    </TD>
                    <TD>
                        <para>提供了一组工具和资源，帮助你为机构中的设备创建、部署和监视远程连接设置。 通过部署这些设置，你可以最大程度地减少最终用户连接到公司网络上他们的计算机所需的工作。</para>
                    </TD>
                    <TD>
                        <para>
                            <link xlink:href="eea36ac7-b261-45da-b448-0358c9e74386">在 Configuration Manager 中使用远程连接配置文件</link>
                        </para>
                    </TD>
                </tr><tr><TD><para><ui>用户数据和配置文件的配置项目</ui></para></TD><TD><para><token>cmshort</token> 中的用户数据和配置文件配置项目可为层次结构中的用户管理运行 Windows 8 和更高版本的计算机上的文件夹重定向、脱机文件和漫游配置文件。 </para></TD><TD><para><link xlink:href="a9439076-6a27-4361-a544-49bbfe7abc8a">在 Configuration Manager 中使用用户数据和配置文件配置项目</link></para></TD></tr>
                <tr>
                    <TD>
                        <para>
                            <ui>远程控制</ui>
                        </para>
                    </TD>
                    <TD>
                        <para>提供工具以通过远程方式从 <token>cmshort</token> 控制台中管理客户端计算机。
                        </para>
                    </TD>
                    <TD>
                        <para>
                            <link xlink:href="29350919-6a25-446b-a0da-05e8914fbb26">远程控制在配置管理器简介</link>
                        </para>
                    </TD>
                </tr>
                <tr>
                    <TD>
                        <para>
                            <ui>报表</ui>
                        </para>
                    </TD>
                    <TD>
                        <para>提供一组工具和资源，这些工具和资源帮助你从 <token>cmshort</token> 控制台中使用 SQL Server Reporting Services 的高级报表功能。
                        </para>
                    </TD>
                    <TD>
                        <para>
                            <link xlink:href="230be984-d2cd-4d53-bd7a-bc24dd93fc22">Configuration Manager 中的报表简介</link>
                        </para>
                    </TD>
                </tr>
                <tr>
                    <TD>
                        <para>
                            <ui>软件计数</ui>
                        </para>
                    </TD>
                    <TD>
                        <para>提供工具以监视和收集 <token>cmshort</token> 客户端中的软件使用情况数据。
                        </para>
                    </TD>
                    <TD>
                        <para>
                            <link xlink:href="b1fdaee2-2816-4447-94cd-609f6948f215">使用 Configuration Manager 中的软件计数监视应用使用情况</link>
                        </para>
                    </TD>
                </tr>
                <tr>
                    <TD>
                        <para>
                            <ui>软件更新</ui>
                        </para>
                    </TD>
                    <TD>
                        <para>提供一组工具和资源，这些工具和资源可帮助你在企业中管理、部署和监视软件更新。</para>
                    </TD>
                    <TD>
                        <para>
                            <link xlink:href="e9778b13-c8a3-40eb-8655-34ac8ce9cdaa">软件更新简介</link>
                        </para>
                    </TD>
                </tr>
            </tbody>
        </table>
        <para>
            <br/>有关如何规划和安装 <token>cmshort</token> 以在你的环境中支持这些管理功能的详细信息，请参阅<link xlink:href="3e839a3e-e476-4ec2-bf29-21e78180441d">为 Configuration Manager 做准备</link>。
        </para>
    </introduction>
    <relatedTopics>
        <link xlink:href="3343eccf-bf09-41cd-9e68-03e893c7f904">System Center Configuration Manager 简介</link>
    </relatedTopics>
</developerConceptualDocument>

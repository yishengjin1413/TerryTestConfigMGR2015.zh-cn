---
title: "System Center Configuration Manager 中自动执行任务的规划注意事项"
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
ms.assetid: fc497a8a-3c54-4529-8403-6f6171a21c64
caps.latest.revision: 13
caps.handback.revision: 11
translationtype: Human Translation
---
# System Center Configuration Manager 中自动执行任务的规划注意事项
<?xml version="1.0" encoding="utf-8"?>
<developerWalkthroughDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd">
  <introduction>
    <para>你可以创建任务序列以在 <token>cm6long</token> 环境中自动执行任务。 这些任务涉及从捕获引用计算机上的操作系统到向一个或多个目标计算机部署操作系统在内的各种任务。 序列的各个步骤中定义了任务序列的操作。 运行任务序列时，每个步骤的操作都在本地系统上下文中的命令行级别执行，无需用户干预。  </para>
    <para>使用以下部分来帮助在 <token>cmshort</token>中规划自动执行任务：</para>
  <list class="bullet"><listItem><para><link xlink:href="#BKMK_TSStepsActions">任务序列步骤和操作</link></para></listItem><listItem><para><link xlink:href="#BKMK_TSGroups">任务序列组</link></para></listItem><listItem><para><link xlink:href="#BKMK_TSVariables">任务序列变量</link></para><list class="bullet"><listItem><para><link xlink:href="#BKMK_TSCreateVariables">创建任务序列变量</link></para></listItem><listItem><para><link xlink:href="#BKMK_TSEnvironmentVariables">访问环境变量</link></para></listItem><listItem><para><link xlink:href="#BKMK_ComputerCollectionVariables">计算机和集合变量</link></para></listItem><listItem><para><link xlink:href="#BKMK_TSMediaVariables">任务序列媒体变量</link></para></listItem></list></listItem><listItem><para><link xlink:href="#BKMK_TSCreate">创建任务序列</link></para></listItem><listItem><para><link xlink:href="#BKMK_TSEdit">编辑任务序列</link></para></listItem><listItem><para><link xlink:href="#BKMK_TSDeploy">部署任务序列</link></para></listItem><listItem><para><link xlink:href="#BKMK_TSExportImport">导出和导入任务序列</link></para></listItem><listItem><para><link xlink:href="#BKMK_TSRun">运行任务序列</link></para><list class="bullet"><listItem><para><link xlink:href="#BKMK_RunProgram">运行任务序列之前运行程序</link></para></listItem></list></listItem><listItem><para><link xlink:href="#BKMK_TSMaintenanceWindow">使用维护时段指定任务序列何时可以运行</link></para></listItem><listItem><para><link xlink:href="#BKMK_TSNetworkAccessAccount">任务序列和网络访问帐户</link></para></listItem><listItem><para><link xlink:href="#BKMK_TSCreateMedia">为任务序列创建媒体</link></para></listItem></list></introduction>
  <section address="BKMK_TSStepsActions">
    <title>任务序列步骤和操作</title>
    <content>
      <para>步骤是任务序列的基本组件。 它们可以包含配置和捕获引用计算机操作系统的命令，或者包含在目标计算机上安装操作系统、驱动程序、<token>cmshort</token> 客户端和软件的命令。 任务序列步骤的命令由步骤的操作来定义。 有两种类型的操作。 你使用命令行字符串定义的操作称为自定义操作。 <token>cmshort</token> 预定义的操作称为内置操作。 任务序列可以执行自定义操作和内置操作的任意组合。</para>
      
      <para>任务序列步骤也可以包含控制步骤行为方式（如在出错的情况下停止任务序列或继续任务序列）的条件。 系统通过在步骤中包括任务序列变量，从而将条件添加到步骤中。 例如，你可以使用 <system>SMSTSLastActionRetCode</system> 变量测试上一个步骤的条件。 可以将变量添加到单个步骤或一组步骤中。</para>
      <para>按顺序处理任务序列步骤，包括步骤的操作以及分配给步骤的任何条件。 在 <token>cmshort</token> 开始处理任务序列步骤时，直到上一个操作完成，才会开始下一个步骤。 完成所有任务序列步骤时，或者失败的步骤造成 <token>cmshort</token> 在完成其所有步骤之前停止运行任务序列时，任务序列被视为完成。 例如，任务序列的步骤无法在分发点上定位引用的映像或包，那么任务序列包含损坏的引用，并且 <token>cmshort</token> 会在该点停止运行任务序列，除非失败的步骤具有在出错时继续的条件。 </para>
      <alert class="important">
        <para>默认情况下，一个步骤或操作失败，将导致任务序列失败。 如果你希望在步骤失败后继续进行任务序列，请编辑任务序列：单击“选项”选项卡<ui></ui>，然后选择“出错时继续”<ui></ui>。</para>
      </alert>
      <para>有关可以添加到任务序列的步骤的详细信息，请参阅 <link xlink:href="7c888a6f-8e37-4be5-8edb-832b218f266d">Configuration Manager 中的任务序列步骤</link>。</para>
    </content>
  </section>
  <section address="BKMK_TSGroups">
    <title>任务序列组</title>
    <content>
      <para>
        <ui></ui>“组”是任务序列内的多个步骤。 任务序列组包含名称、可选说明以及在任务序列继续下一步骤之前作为单元进行评估的任何可选条件。 组可以相互嵌套，可以包含步骤和子组的混合。 组对于合并共享公用条件的多个步骤十分有用。 </para>
      <alert class="important">
        <para>默认情况下，如果任务序列组中的任何步骤或嵌入的组失败，将导致此任务序列组失败。 如果希望在步骤或嵌入的组失败后任务序列继续进行，请编辑任务序列：单击“选项”<ui></ui>选项卡，然后选择“出错时继续”<ui></ui>。</para>
      </alert>
      <para>下表显示了分组步骤时“出错时继续”<ui></ui>选项是如何工作的。</para>
      <para>在此示例中，有两组任务序列，每组包含三个任务序列步骤。 </para>
      <table xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
        <thead>
          <tr>
            <TD colspan="1">
              <para>任务序列组或步骤</para>
            </TD>
            <TD colspan="1">
              <para>“出错时继续”设置</para>
            </TD>
          </tr>
        </thead>
        <tbody>
          <tr>
            <TD colspan="1">
              <para>
                <ui>任务序列组 1</ui>
              </para>
            </TD>
            <TD colspan="1">
              <para>
                <ui>已选中“出错时继续”</ui>。</para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>任务序列步骤 1</para>
            </TD>
            <TD colspan="1">
              <para>
                <ui>已选中“出错时继续”</ui>。</para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>任务序列步骤 2</para>
            </TD>
            <TD colspan="1">
              <para> 未设置。</para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>任务序列步骤 3</para>
            </TD>
            <TD colspan="1">
              <para> 未设置。</para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>
                <ui>任务序列组 2</ui>
              </para>
            </TD>
            <TD colspan="1">
              <para> 未设置。</para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>任务序列步骤 4</para>
            </TD>
            <TD colspan="1">
              <para> 未设置。</para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>任务序列步骤 5</para>
            </TD>
            <TD colspan="1">
              <para> 未设置。</para>
            </TD>
          </tr>
          <tr>
            <TD colspan="1">
              <para>任务序列步骤 6</para>
            </TD>
            <TD colspan="1">
              <para> 未设置。</para>
            </TD>
          </tr>
        </tbody>
      </table>
      <list class="bullet">
        <listItem>
          <para>如果任务序列步骤 1 失败，任务序列将继续执行任务序列步骤 2。</para>
        </listItem>
        <listItem>
          <para>如果任务序列步骤 2 失败，任务序列不会运行任务序列步骤 3，但仍会继续运行任务序列步骤 4 和 5（它们在不同的任务序列组中）。</para>
        </listItem>
        <listItem>
          <para>如果任务序列步骤 4 失败，不会运行更多步骤，任务序列将失败，因为尚未对任务序列组 2 配置“出错时继续”<ui></ui>设置。</para>
        </listItem>
      </list>
      <para>虽然组名称不必是唯一的，但必须向任务序列组分配一个名称。 你还可以为任务序列组提供可选描述。</para>
    <para></para></content>
  </section>
  <section address="BKMK_TSVariables">
    <title>任务序列变量</title>
    <content>
      <para>任务序列变量是一组名称和值对，为 <token>cmshort</token> 客户端计算机上的计算机、操作系统和用户状态配置任务提供配置和操作系统部署设置。 任务序列变量提供了一种机制来配置和自定义任务序列中的步骤。 </para>
      <para>运行任务序列时，许多任务序列设置会存储为环境变量。 可以访问或更改内置任务序列变量的值，可以创建新任务序列变量以自定义任务序列在目标计算机上运行的方式。</para>
      <para>你可以使用任务序列环境中的任务序列变量以执行以下操作：</para>
      <list class="bullet">
        <listItem>
          <para>为任务序列操作配置设置</para>
        </listItem>
        <listItem>
          <para>提供任务序列步骤的命令行参数</para>
        </listItem>
        <listItem>
          <para>评估条件以确定是否运行任务序列步骤或组</para>
        </listItem>
        <listItem>
          <para>为任务序列中使用的自定义脚本提供值</para>
        </listItem>
      </list>
      <para>例如，你可能会有一个包括“加入域或工作组”<ui></ui>任务序列步骤的任务序列。 此任务序列可以部署到集合成员资格由域成员身份来决定的不同集合。 在该示例中，你可以为每个集合的域名指定每集合任务序列变量，然后使用该任务序列变量在任务序列中提供合适的域名。</para>
    </content>
    <sections>
      <section address="BKMK_TSCreateVariables">
        <title>创建任务序列变量</title>
        <content>
          <para>你可以添加新任务序列变量以自定义和控制任务序列中的步骤。 例如，你可以创建任务序列变量以替代内置任务序列步骤的设置。 你也可以创建自定义任务序列变量以与任务序列中的条件、命令行或自定义步骤一起使用。 创建任务序列变量时，任务序列变量和关联的值将保留在任务序列环境中，即使该序列重启目标计算机也不例外。 可以跨不同操作系统环境在任务序列中使用变量及其值。 例如，它可在完整的 Windows 操作系统以及 Windows PE 环境中使用。</para>
          <para>下表描述了创建任务序列变量的方法和其他使用情况信息。</para>
          <table xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
            <thead>
              <tr>
                <TD>
                  <para>创建方法</para>
                </TD>
                <TD>
                  <para>用法</para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>使用任务序列编辑器设置任务序列步骤中的字段</para>
                </TD>
                <TD>
                  <para>指定任务序列步骤的默认值。 只有在任务序列中运行步骤时才可以访问变量和值。 它们不是整体序列环境中的一部分，任务序列中的其他任务序列步骤无法访问它们。</para>
                  <para>有关内置变量及其关联操作的列表，请参阅 <link xlink:href="e2269031-0977-4f01-a274-420e00630575">Configuration Manager 中的任务序列操作变量</link>。</para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>在任务序列中添加设置的任务序列变量步骤</para>
                </TD>
                <TD>
                  <para>当运行任务序列中的任务序列步骤时指定任务序列环境中的任务序列变量和值。 所有后续任务序列步骤都可以访问该环境变量及其值。</para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>定义每集合变量</para>
                </TD>
                <TD>
                  <para>为计算机集合指定任务序列变量和值。 针对此集合的所有任务序列都可以访问任务序列变量及其值。</para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>定义每计算机变量</para>
                </TD>
                <TD>
                  <para>为特定计算机指定任务序列变量和值。 针对此计算机的所有任务序列都可以访问任务序列变量及其值。</para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>在任务序列媒体向导的“自定义”<ui></ui>页上添加任务序列变量</para>
                </TD>
                <TD>
                  <para>为从可以访问任务序列变量及其值的媒体中运行的任务序列指定任务序列变量和值。</para>
                </TD>
              </tr>
            </tbody>
          </table>
          <para>要替代内置任务序列变量的默认值，你必须定义与该内置任务序列变量同名的任务序列变量。 有关内置任务序列变量及其关联的操作和使用情况的列表，请参阅 <link xlink:href="02bc6bd4-ca53-4e22-8b80-d8ee5fe72567">Configuration Manager 中的任务序列内置变量</link>。</para>
          <para>你可以使用与创建任务序列变量相同的方法，从任务序列环境中删除任务序列变量。 在这种情况下，要从任务序列环境中删除变量，可以将任务序列变量值设置为空字符串。</para>
          <para>你可以组合方法以将环境任务序列变量设置为相同序列的不同值。 在高级方案中，你可以使用任务序列编辑器为序列中的步骤设置默认值，然后使用默认创建方法设置自定义变量值。 以下列表描述了使用多种方法创建任务序列变量时决定使用哪一个值的规则。</para>
          <list class="ordered">
            <listItem>
              <para>“设置任务序列变量”<ui></ui>步骤将替代所有其他创建方法。</para>
            </listItem>
            <listItem>
              <para>每计算机变量优先于每集合变量。 如果为每计算机变量和每集合变量指定相同的任务序列变量名称，则当目标计算机运行部署的任务序列时将使用每计算机变量值。</para>
            </listItem>
            <listItem>
              <para>可以从媒体运行任务序列。 使用媒体变量替代每集合变量或每计算机变量。 如果正在从媒体运行任务序列，则不应用也不使用每计算机变量和每集合变量。 而是改用任务序列媒体向导的“自定义”<ui></ui>页上定义的任务序列变量设置特定于从媒体中运行的任务序列的值</para>
            </listItem>
            <listItem>
              <para>如果未在整体序列环境中设置任务序列变量值，内置操作使用在任务序列编辑器中设置的步骤默认值。</para>
            </listItem>
          </list>
          <para>除了替代内置任务序列步骤设置的值之外，还可以创建用于任务序列步骤、脚本、命令行或条件的新环境变量。 为新的任务序列变量指定名称时，请遵循以下准则：</para>
          <list class="bullet">
            <listItem>
              <para>指定的任务序列变量名称可以包含字母、数字、下划线字符 (_) 和连字符 (-)。</para>
            </listItem>
            <listItem>
              <para>任务序列变量名称的最小长度为 1 个字符，最大长度为 256 个字符。</para>
            </listItem>
            <listItem>
              <para>用户定义的变量必须以字母（A-Z 或 a-z）开头。</para>
            </listItem>
            <listItem>
              <para>用户定义的变量名称不能以下划线字符开头。 仅只读任务序列变量的前面使用下划线字符</para>
              <alert class="note">
                <para>任务序列中的任务序列步骤可以读取只读任务序列变量，但无法设置该变量。 例如，你可以使用只读任务序列变量作为“运行命令行”<ui></ui>任务序列操作变量的命令行的一部分，但无法使用“设置任务序列变量”<ui></ui>操作变量对只读变量进行设置。</para>
              </alert>
            </listItem>
            <listItem>
              <para>任务序列变量名称不区分大小写。 例如，OSDVAR 和 osdvar 表示同一任务序列变量。</para>
            </listItem>
            <listItem>
              <para>任务序列变量名称不能以空格开始或结尾，也不能包含嵌入的空格。 任务序列变量名称开头或结尾的空格会被忽略。</para>
            </listItem>
          </list>
          <para>下表显示用户指定的有效和无效任务序列变量的示例。</para>
          <table xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
            <thead>
              <tr>
                <TD>
                  <para>用户指定的有效变量名称的示例</para>
                </TD>
                <TD>
                  <para>用户指定的无效变量名称的示例</para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>MyVariable</para>
                </TD>
                <TD>
                  <para>1Variable</para>
                  <para>用户指定的任务序列变量不能以数字开头。</para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>My_Variable</para>
                </TD>
                <TD>
                  <para>MyV@riable</para>
                  <para>用户指定的任务序列变量不能包含 @ 符号。</para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>My_Variable_2</para>
                </TD>
                <TD>
                  <para>_MyVariable</para>
                  <para>用户指定的任务序列变量不能以下划线开头。</para>
                </TD>
              </tr>
            </tbody>
          </table>
          <para>任务序列变量的一般限制：</para>
          <list class="bullet">
            <listItem>
              <para>任务序列变量值不能超过 4,000 个字符。</para>
            </listItem>
            <listItem>
              <para>无法创建或重写只读任务序列变量。 只读变量用以下划线 (_) 字符开头的名称来指定。 你可以访问任务序列中只读任务序列变量的值；但是不能更改相关联的值。</para>
            </listItem>
            <listItem>
              <para>
任务序列变量值可能区分大小写，具体情况视值的使用情况而定。 大多数情况下，任务序列变量值不区分大小写。 但是，某些值可能会区分大小写，例如包含密码的变量。</para>
            </listItem>
            <listItem>
              <para>对于可以创建的任务序列变量的数量没有限制。 但是，变量数受任务序列环境大小的限制。 任务序列环境的总大小限制为 32 MB。</para>
            </listItem>
          </list>
        </content>
      </section>
      <section address="BKMK_TSEnvironmentVariables">
        <title>访问环境变量</title>
        <content>
          <para>使用上一部分中的方法之一指定任务序列变量及其值之后，你可以在任务序列中使用环境变量值。 可以访问内置任务序列变量的默认值、指定内置变量的新值或在命令行或脚本中使用自定义的任务序列变量</para>
          <para>下表列出了可通过访问任务序列环境变量执行的任务序列操作。</para>
          <table xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
            <thead>
              <tr>
                <TD>
                  <para>任务序列操作</para>
                </TD>
                <TD>
                  <para>用法</para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>配置操作设置</para>
                </TD>
                <TD>
                  <para>可以指定在序列运行时由变量值来提供任务序列步骤设置。</para>
                  <para>要使用任务序列环境变量来提供任务序列步骤设置，请使用任务序列编辑器编辑步骤并将变量名称指定为字段值。 变量名称必须括在百分号 (%) 中以指明它是一个环境变量。</para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>提供命令行参数</para>
                </TD>
                <TD>
                  <para>可以通过使用环境变量值，指定部分或整个自定义命令行。</para>
                  <para>要使用环境变量来提供命令行设置，请将变量名称用作“运行命令行”<ui></ui>任务序列步骤的“命令行”<ui></ui>字段的一部分。 变量名称前后必须使用百分符号 (%)。</para>
                  <para>例如，以下命令行使用内置环境变量将计算机名写入到 C:\File.txt。</para>
                  <para><br/></para><para>
                    <userInput>Cmd /C %_SMSTSMachineName% &gt; C:\File.txt </userInput></para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>计算步骤条件</para>
                </TD>
                <TD>
                  <para>你可以使用内置或自定义任务序列环境变量作为任务序列步骤或组条件的一部分。 在运行任务序列步骤或组之前，将计算环境变量值。</para>
                  <para>若要添加计算变量值的条件，请执行以下步骤：</para>
                  <list class="ordered">
                    <listItem>
                      <para>选择要向其添加条件的步骤或组。</para>
                    </listItem>
                    <listItem>
                      <para>在步骤或组的“选项”<ui></ui>选项卡上，从“添加条件”<ui></ui>下拉列表中选择“任务序列变量”<ui></ui>。</para>
                    </listItem>
                    <listItem>
                      <para>在“任务序列变量”<ui></ui>对话框中，指定变量名称、测试的条件以及变量的值。</para>
                    </listItem>
                  </list>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>为自定义脚本提供信息</para>
                </TD>
                <TD>
                  <para>可以在运行任务序列时使用 Microsoft.SMS.TSEnvironment COM 对象读写任务序列变量。</para>
                  <para>下面的示例演示了查询 <system>_SMSTSLogPath</system> 任务序列变量以获取当前日志位置的 Visual Basic 脚本文件。 该脚本还设置自定义变量。</para>
                  <para><br/></para><para><userInput>dim osd: set env = CreateObject("Microsoft.SMS.TSEnvironment")


</userInput></para>
                  <para><br/></para><para><userInput>dim logPath</userInput></para><para><br/></para><para><userInput>可以查询环境以获取现有变量。
</userInput></para><para><userInput>logPath = env("_SMSTSLogPath")

</userInput></para><para><br/></para><para><userInput>还可以在 OSD 环境中设置变量。</userInput></para><para><userInput>env("MyCustomVariable") = "varname"</userInput></para><para><br/></para><para>有关如何在脚本中使用任务序列变量的详细信息，请参阅 SDK 文档</para>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
      </section>
      <section address="BKMK_ComputerCollectionVariables">
        <title>计算机和集合变量</title>
        <content>
          <para>可以将任务序列配置为在多个计算机或集合上同时运行。 你可以指定唯一的每计算机或每集合信息，如指定唯一的操作系统产品密钥，或者将集合的所有成员加入到指定的域中。</para>
          <para>你可以将任务序列变量分配给单一计算机或集合。 当任务序列开始在目标计算机或集合上运行时，会将指定的值应用于目标计算机或集合。</para>
          <para>你可以为单一计算机或集合指定任务序列变量。 当任务序列开始在目标计算机或集合上运行时，会将指定的值添加到环境中，并且该值对任务序列中的所有任务序列步骤可用。</para>
          <alert class="warning">
            <para>如果对每集合和每计算机变量使用相同的变量名称，则计算机变量值优先于集合变量。 分配给集合的任务序列变量优先于内置任务序列变量。</para>
          </alert>
          <para>有关如何为计算机和集合创建任务序列变量的详细信息，请参阅<link xlink:href="a1f099f1-e9b5-4189-88b3-f53e3b4e4add#BKMK_CreateTSVariables">为计算机和集合创建任务序列变量</link>。</para>
        </content>
      </section>
      <section address="BKMK_TSMediaVariables">
        <title>任务序列媒体变量</title>
        <content>
          <para>你可以指定从媒体中运行的任务序列的任务序列变量。 使用媒体部署操作系统时，添加任务序列变量，并在创建媒体时指定其值；变量及其值存储在媒体上。</para>
          <alert class="note">
            <para>任务序列存储在独立媒体上。 但是，所有其他类型的媒体（如预留媒体）从管理点检索任务序列。</para>
          </alert>
          <para>可以在任务序列媒体向导“自定义”<ui></ui>页指定任务序列变量。 有关如何创建媒体的信息，请参阅<link xlink:href="90498b4b-6a9b-43cd-b465-1d6c9a52df1c">创建任务序列媒体</link>。</para>
          <alert class="tip">
            <para>
任务序列会将包 ID 和预启动命令行（包括任何任务序列变量的值）写入到运行 <token>cmshort</token> 控制台的计算机上的 CreateTSMedia.log 日志文件。 你可以查看此日志文件以验证任务序列变量的值。 </para>
          </alert>
        <para><?xm-replace_text Type new maml:para here ?></para></content>
      </section>
    </sections>
  </section>
  <section address="BKMK_TSCreate">
    <title>创建任务序列</title>
    <content>
      <para>你可以通过使用“创建任务序列向导”创建任务序列。 此向导可以创建执行特定任务的内置任务序列，或创建可执行许多不同任务的自定义任务序列。 </para>
      <para>例如，你可以创建构建并捕获引用计算机的操作系统映像包的任务序列、在目标计算机上安装现有操作系统映像包，或者创建执行自定义任务的任务序列。 可以使用自定义任务序列执行特殊的操作系统部署。</para>
      <para>有关如何创建任务序列的详细信息，请参阅<link xlink:href="a1f099f1-e9b5-4189-88b3-f53e3b4e4add#BKMK_CreateTaskSequence">创建任务序列</link>。</para>
    </content>
  </section>
  <section address="BKMK_TSEdit">
    <title>编辑任务序列</title>
    <content>
      <para>可以使用“任务序列编辑器”<ui></ui>编辑任务序列。 编辑器可以对任务序列进行以下更改：</para>
      <list class="bullet">
        <listItem>
          <para>可以从任务序列添加或删除步骤。</para>
        </listItem>
        <listItem>
          <para>可以更改任务序列步骤的顺序。 </para>
        </listItem>
        <listItem>
          <para>可以添加或删除步骤组。</para>
        </listItem>
        <listItem>
          <para>可以指定发生错误时任务序列是否继续。 </para>
        </listItem>
        <listItem>
          <para>你可以将条件添加到任务序列的步骤和组中。 </para>
        </listItem>
      </list>
      <alert class="important">
        <para>如果由于编辑而造成任务序列具有对包或程序的任何无关引用，则必须更正引用、删除任务序列中未引用的程序，或暂时禁用失败的任务序列步骤，直到损坏的引用已更正或删除为止。</para>
      </alert>
      <para>有关如何编辑任务序列的详细信息，请参阅<link xlink:href="a1f099f1-e9b5-4189-88b3-f53e3b4e4add#BKMK_ModifyTaskSequence">编辑任务序列</link>。</para>
    </content>
  </section>
  <section address="BKMK_TSDeploy">
    <title>部署任务序列</title>
    <content>
      <para>可以向位于任何 <token>cmshort</token> 集合中的目标计算机部署任务序列。 这包括用于将操作系统部署到未知计算机的“所有未知计算机”<ui></ui>集合。 但是，你不能将任务序列部署到用户集合。 </para>
      <alert class="important">
        <para>
不要将安装操作系统的任务序列部署到不适合的集合，例如“所有系统”<ui></ui>集合。 请确保任务序列部署到的集合仅包含想在其中安装操作系统的那些计算机。 为帮助避免不需要的操作系统部署，你可以管理部署设置。 有关详细信息，请参阅<link xlink:href="8d37b983-a964-402c-819d-2512ed2d463b">用于管理 System Center Configuration Manager 的高风险部署的设置</link>。</para>
      </alert>
      <para>每个接收任务序列的目标计算机根据部署中指定的设置运行任务序列。 任务序列本身不包含关联的文件或程序。 任务序列引用的任何文件都必须已经存在于目标计算机上或位于客户端可访问的分发点上。 此外，任务序列会安装程序所引用的包，即使已在目标计算机上安装了程序或包也不例外。</para>
      <alert class="note">
        <para>相比包和程序，如果任务序列安装应用程序，则只有在满足应用程序的要求规则且尚未安装该应用程序时，才会根据为应用程序指定的检测方法来安装此应用程序。</para>
      </alert>
      <para><token>Cmshort</token> 客户端在下载客户端策略时运行任务序列部署。 要启动此操作而不是等到下一个轮询周期，请参阅<link xlink:href="3986a992-c175-4b6f-922e-fc561e3d7cb7#BKMK_PolicyRetrieval">为 Configuration Manager 客户端启动策略检索</link>。  </para>
      <para>将任务序列部署到启用了写入筛选器的 Windows Embedded 设备时，你可以指定是否在部署过程中对设备禁用写入筛选器，然后在部署后重启设备。 如果未禁用写入筛选器，则会将任务序列部署到临时覆盖区，并且在重启设备时将不可用。</para>
      <alert class="note">
        <para>在将任务序列部署到 Windows Embedded 设备时，请确保该设备是配置了维护时段的集合的成员。 这允许你管理禁用和启用写入筛选器的时间，以及设备重启的时间。</para>
        <para>如果客户端在维护时段之外下载任务序列，则会下载两次任务序列。 在这种情况下，客户端将下载任务序列、禁用写入筛选器、重启计算机，然后再次下载任务序列，因为任务序列已下载到了设备重启时会进行清除的临时覆盖区。</para>
      </alert>
      <para>有关如何部署任务序列的详细信息，请参阅<link xlink:href="a1f099f1-e9b5-4189-88b3-f53e3b4e4add#BKMK_DeployTS">部署任务序列</link>。</para>
    </content>
  </section>
  <section address="BKMK_TSExportImport">
    <title>导出和导入任务序列</title>
    <content>
      <para>
        <token>cmshort</token> 允许导出和导入任务序列。 导出任务序列时，可以包括任务序列引用的对象。 其中包括操作系统映像包、启动映像、客户端代理包、驱动程序包，以及具有依赖关系的应用程序。</para>
      <alert class="note">
        <para>任务序列的导出和导入过程与 <token>cmshort</token> 中应用程序的导出和导入过程非常相似。</para>
      </alert>
      <para>有关如何导出和导入任务序列的详细信息，请参阅<link xlink:href="a1f099f1-e9b5-4189-88b3-f53e3b4e4add#BKMK_ExportImport">导出和导入任务序列</link>。</para>
    </content>
  </section>
  <section address="BKMK_TSRun">
    <title>运行任务序列</title>
    <content>
      <para>默认情况下，任务序列始终使用本地系统帐户运行。 利用任务序列命令行步骤，你能够用其他帐户运行任务序列。 运行任务序列时，<token>cmshort</token> 客户端首先检查任何引用的包，然后会启动任务序列的步骤。 如果分发点上的引用包未经验证或不可用，则任务序列将为关联任务序列步骤返回错误。 </para>
      <para>如果将分发任务序列配置为下载并运行，则所有从属包和应用程序将被下载到 <token>cmshort</token> 客户端缓存。 所需的包和应用程序从分发点获得，如果 <token>cmshort</token> 客户端缓存太小或找不到包或应用程序，则任务序列将失败并生成一则状态消息。 在选择“需要时通过运行任务序列本地下载内容”<ui></ui>时，也可以指定客户端仅在需要内容时下载内容，或者可以使用“从分发点运行程序”<ui></ui>选项来指定客户端直接从分发点安装文件而不先将其下载到缓存。 只有引用的包在“包”<ui></ui>属性的“数据访问”<ui></ui>选项卡上启用了“将此包中的内容复制到分发点上的包共享中”<ui></ui>设置时，才可以使用“从分发点运行程序”<ui></ui>选项。</para>
      <para>如果运行任务序列的客户端无法定位从属包或应用程序，则客户端在部署被配置为“可用”<ui></ui>时会立即发送错误。 但是，如果部署被配置为“必需”<ui></ui>，则在内容尚未复制到客户端可访问的分发点的情况下，<token>cmshort</token> 客户端会在截止时间前等待并重新尝试下载内容。 </para>
      <para>无论任务序列成功完成与否，<token>cmshort</token> 都会在<token>cmshort</token> 客户端历史记录中记录此情况。 在计算机上启动任务序列后，将无法取消或停止该序列。</para>
      <alert class="important">
        <para>如果任务序列步骤要求重启客户端计算机，则客户端必须能够启动到格式化的磁盘分区。 否则，任务序列将失败，而与任务序列指定的任何错误处理无关。 </para>
      </alert>
      <para>当软件分发包等任务序列从属对象更新到较新版本时，系统将自动更新引用包的任何任务序列并引用最新版本，而与部署的更新数目无关。 </para>
      <alert class="note">
        <para>在 <token>cmshort</token> 客户端运行任务序列之前，客户端会在分发点上检查所有任务序列，看是否有可能的依赖关系及其可用性。 如果客户端发现任务序列所依赖的对象已被删除，则客户端会生成错误，并且不运行任务序列。 </para>
      </alert>
    </content>
    <sections>
      <section address="BKMK_RunProgram">
        <title>在运行任务序列前运行程序</title>
        <content>
          <para>可以选择在任务序列运行之前运行的程序。 要指定首先运行的程序，请打开任务序列的“属性”<ui></ui>对话框，然后选择“高级”<ui></ui>选项卡以设置以下选项：</para>
          <alert class="important">
            <para>若要在运行任务序列之前运行程序，任务序列的所有内容和程序必须在包共享上可供包使用。 可以在包属性的“数据访问”<ui></ui>选项卡上配置包共享。 </para>
          </alert>
          <list class="bullet">
            <listItem>
              <para>
                <ui>首先运行其他程序</ui>：指定想要在运行任务序列前运行其他程序。</para>
              
              <alert class="important">
                <para>此设置仅适用于在完整操作系统中运行的任务序列。 <token>如果通过使用 PXE 或启动媒体启动任务序列，cmshort</token> 将忽略此设置。</para>
              </alert>
            </listItem>
            <listItem>
              <para>
                <ui>包</ui>：指定包含该程序的包。</para>
            </listItem>
            <listItem>
              <para>
                <ui>程序</ui>：指定要运行的程序。</para>
            </listItem>
            <listItem>
              <para>
                <ui>始终先运行此程序</ui>：指定想要 <token>cmshort</token> 每次在同一个客户端上运行任务序列时运行此程序。 默认情况下，在某个程序成功运行之后，如果在同一个客户端上再次运行任务序列，则不会再次运行此程序。 </para>
            </listItem>
          </list>
          <para>如果所选的程序在客户端上运行失败，则不会运行任务序列。 </para>
        </content>
      </section>
    </sections>
  </section>
  <section address="BKMK_TSMaintenanceWindow">
    <title>使用维护时段指定可以运行任务序列的时间</title>
    <content>
      <para>通过为包含目标计算机的集合定义维护时段，可以指定任务序列何时可以运行。 将会配置维护时段的开始日期、开始和完成时间以及定期模式。 此外，在为维护时段设置计划时，可以指定维护时段仅应用于任务序列。 有关详细信息，请参阅<link xlink:href="4564ebcb-41a8-4eb0-afdb-2e1f0795cfa2">如何在 Configuration Manager 中使用维护时段</link>。</para>
      <alert class="important">
        <para>
在配置维护时段以运行任务序列时，一旦任务序列启动，即使维护时段结束，它也会继续运行。 任务序列要么成功完成，要么失败。</para>
      </alert>
    </content>
  </section>
  <section address="BKMK_TSNetworkAccessAccount">
    <title>任务序列和网络访问帐户</title>
    <content>
      <para>虽然任务序列仅在本地系统帐户的上下文中运行，但是你可能需要在以下情况下配置网络访问帐户：</para>
      <list class="bullet">
        <listItem>
          <para>必须正确配置网络访问帐户，否则，如果任务序列为了完成其任务而尝试访问分发点上的 <token>cmshort</token> 包，它将会失败。 有关网络访问帐户的详细信息，请参阅<link xlink:href="c201be2a-692c-4d67-ac95-0a3afa5320fe#bkmk_NAA">网络访问帐户</link>。</para>
          <alert class="note">
            <para>网络访问帐户从不用作运行程序、安装应用程序、安装更新或运行任务序列的安全性上下文，但可用于访问网络上的关联资源。</para>
          </alert>
        </listItem>
        <listItem>
          <para>使用启动映像来启动操作系统部署时，<token>cmshort</token> 使用 Windows PE 环境，它不是完整的操作系统。 Windows PE 环境使用自动生成的随机名称，该名称不是任何域的成员。 如果未正确配置网络访问帐户，则计算机可能没有访问所需的 <token>cmshort</token> 包以完成任务序列的必需权限。 </para>
        </listItem>
      </list>
    </content>
  </section>
  <section address="BKMK_TSCreateMedia">
    <title>为任务序列创建媒体</title>
    <content>
      <para>可以将任务序列及其相关的文件和依赖关系写入到多种类型的媒体中。 这包括写入到可移动媒体（例如捕获、独立和可启动媒体的 DVD 或 CD 集或者 USB 闪存驱动器）中，或者写入到预留媒体的 Windows 映像格式 (WIM) 文件中。 </para>
      <para>可以创建下列类型的媒体：</para>
      <list class="bullet">
        <listItem>
          <para>
            <embeddedLabel>捕获媒体</embeddedLabel>。 捕获媒体捕获在 <token>cmshort</token> 基础结构以外配置和创建的操作系统映像。 捕获媒体可以包含可在任务序列运行之前运行的自定义程序。 自定义程序可以与桌面交互、提示用户输入值，或创建任务序列使用的变量。</para>
          <para>有关详细信息，请参阅<link xlink:href="10eb8958-3848-49d7-95c0-16119b624580">创建捕获媒体</link>。</para>
        </listItem>
        <listItem>
          <para>
            <embeddedLabel>独立媒体</embeddedLabel>。 独立媒体包含任务序列，以及运行任务序列所必需的所有关联对象。 当 <token>cmshort</token> 的网络连接受限或者没有网络连接时，独立媒体任务序列可以运行。 可以通过以下方式运行独立媒体：</para>
          <list class="bullet">
            <listItem>
              <para>如果没有启动目标计算机，则将从独立媒体中使用与任务序列关联的 Windows PE 映像，并且任务序列开始运行。</para>
            </listItem>
            <listItem>
              <para>如果用户登录到网络并启动安装，则可以手动启动独立媒体。</para>
            </listItem>
          </list>
          <alert class="important">
            <para>独立媒体任务序列的步骤必须能够在不从网络检索任何数据的情况下运行，否则，尝试检索数据的任务序列步骤将失败。 例如，需要访问分发点以获取包的任务序列步骤将失败；但是，如果独立媒体上包含必需的包，则任务序列步骤将成功。</para>
          </alert>
          <para>有关详细信息，请参阅<link xlink:href="c6b9ccd2-78d9-4f0e-b25a-70d0866300ba">创建独立媒体</link>。</para>
        </listItem>
        <listItem>
          <para>
            <embeddedLabel>可启动媒体</embeddedLabel>。 可启动媒体包含启动目标计算机所需的文件，以便此计算机能够连接到 <token>cmshort</token> 基础结构，然后根据它的集合成员身份确定要运行的任务序列。 媒体上不包含任务序列和从属对象；但 <token>cmshort</token> 客户端的网络上包含它们。 对于新计算机或裸机部署，或者当目标计算机上没有 <token>cmshort</token> 客户端或操作系统时，此方法很有用。</para>
          <para>有关详细信息，请参阅<link xlink:href="ead79e64-1b63-4d0d-8bd5-addff8919820">创建可启动媒体</link>。</para>
        </listItem>
        <listItem>
          <para>
            <embeddedLabel>预留媒体</embeddedLabel>。 预留媒体将操作系统映像部署到未设置的目标计算机。 预留媒体存储为 Windows 映像格式 (WIM) 文件，可以由制造商安装在裸机上，也可以安装在未连接到 <token>cmshort</token> 环境的企业暂存中心。 </para>
          <para>有关详细信息，请参阅<link xlink:href="ff6e7267-302a-4563-815e-cdc0d1a4b60f">创建预留媒体</link></para>
        </listItem>
      </list>
      <para>在创建媒体时，可以为媒体指定密码，以控制对媒体上包含的文件的访问。 如果要指定密码，则在执行任务序列时，用户必须在目标计算机键入密码。</para>
      <para>使用媒体运行任务序列时，将不会识别媒体上包含的指定计算机芯片体系结构，而且，即使指定的体系结构与目标计算机上实际安装的体系结构不匹配，任务序列也会尝试运行。 如果媒体上包含的芯片体系结构与目标计算机上安装的芯片体系结构不匹配，则安装将失败。</para>
      <para>有关如何使用媒体部署操作系统的详细信息，请参阅<link xlink:href="90498b4b-6a9b-43cd-b465-1d6c9a52df1c">创建任务序列媒体</link>。</para>
    </content>
  </section>
  <relatedTopics>
    <link xlink:href="2299c6af-9793-485c-97c4-d844999644d7">将 Configuration Manager 中的任务自动化</link>
  </relatedTopics>
</developerWalkthroughDocument>

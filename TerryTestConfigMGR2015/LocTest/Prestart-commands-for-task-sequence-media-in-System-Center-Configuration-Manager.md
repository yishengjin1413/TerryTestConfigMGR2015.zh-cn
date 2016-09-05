---
title: "System Center Configuration Manager 中任务序列媒体的预启动命令"
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
ms.assetid: ccc9f652-2953-4c38-8a90-c799484105ca
caps.latest.revision: 6
caps.handback.revision: 3
---
# System Center Configuration Manager 中任务序列媒体的预启动命令
可以在 [!INCLUDE[cm6long](../LocTest/includes/cm6long_md.md)] 中创建一个预启动命令，以用于启动媒体、独立媒体和预留媒体。 预启动命令是一个脚本或可执行文件，它在选择任务序列之前运行并且可以在 Windows PE 中与用户交互。 预启动命令可能会提示用户输入信息并将此信息保存在任务序列环境中，或者在任务序列变量中查询信息。 启动目标计算机后，会在从管理点下载策略之前运行命令行。 使用以下过程创建脚本以用于预启动命令，分发与预启动命令关联的内容，以及在媒体中配置预启动命令。  
  
## 创建脚本文件以用于预启动命令  
 可以在运行任务序列时使用 Microsoft.SMS.TSEnvironment COM 对象读写任务序列变量。 以下示例说明了 Visual Basic 脚本文件，此脚本文件查询 \_SMSTSLogPath 任务序列变量以获取当前日志位置。 该脚本还设置自定义变量。  
  
```  
dim osd: set env = CreateObject("Microsoft.SMS.TSEnvironment")  
dim logPath  
' You can query the environment to get an existing variable.  
logPath = env("_SMSTSLogPath")  
' You can also set a variable in the OSD environment.  
env("MyCustomVariable") = "varname"  
```  
  
## 创建脚本文件包并分发内容  
 为预启动命令创建脚本或可执行文件后，必须创建包源以为脚本或可执行文件承载文件，创建文件包（无需程序），然后将内容分发给分发点。  
  
 有关创建包的详细信息，请参阅[System Center Configuration Manager 中的包和程序](../LocTest/Packages-and-programs-in-System-Center-Configuration-Manager.md)。  
  
 有关分发内容的详细信息，请参阅[Distribute content](../LocTest/Manage-content-and-content-infrastructure-for-System-Center-Configuration-Manager.md#bkmk_dist)。  
  
## 在媒体中配置预启动命令  
 可以在独立媒体、可启动媒体或预留媒体的创建任务序列媒体向导中配置一个预启动命令。 有关媒体类型的详细信息，请参阅[使用 System Center Configuration Manager 创建任务序列媒体](../LocTest/Create-task-sequence-media-with-System-Center-Configuration-Manager.md)。 使用以下过程在媒体中创建预启动命令。  
  
#### 在媒体中创建预启动命令  
  
1.  在 [!INCLUDE[cmshort](../LocTest/includes/cmshort_md.md)] 控制台中，单击“软件库”。  
  
2.  在“软件库”工作区中，展开“操作系统”，然后单击“任务序列”。  
  
3.  在“主页”选项卡上的“创建”组中，单击“创建任务序列媒体”以启动创建任务序列媒体向导。  
  
4.  在“选择媒体类型”页上，选择“独立媒体”、“可启动媒体”或“预留媒体”，然后单击“下一步”。  
  
5.  导航到向导的“自定义”页面。 有关在向导中配置其他页面的详细信息，请参阅[使用 System Center Configuration Manager 创建任务序列媒体](../LocTest/Create-task-sequence-media-with-System-Center-Configuration-Manager.md)。  
  
6.  在“自定义”页上，指定以下信息，然后单击“下一步”。  
  
    -   选择“启用预启动命令”。  
  
    -   在“命令行”文本框中，输入为预启动命令创建的脚本或可执行文件。  
  
        > [!IMPORTANT]  
        >  使用 **cmd \/C \<prestart command\>** 指定预启动命令。 例如，如果使用了 TSScript.vbs 作为预启动命令脚本的名称，你将为命令行输入 **cmd \/C TSScript.vbs**。 其中 **cmd \/C** 会打开一个新的 Windows 命令解释器窗口，并使用路径环境变量查找预启动命令脚本或可执行文件。 也可以指定预启动命令的完整路径，但是在具有不同驱动器配置的计算机上，驱动器号可能不同。  
  
    -   选择“包括预启动命令的文件”。  
  
    -   单击“设置”以选择与预启动命令文件关联的包。  
  
    -   单击“浏览”以选择承载预启动命令内容的分发点。  
  
7.  完成向导。  
  
## 请参阅  
 [System Center Configuration Manager 的操作系统部署技术参考](../LocTest/Operating-system-deployment-technical-reference-for-System-Center-Configuration-Manager.md)
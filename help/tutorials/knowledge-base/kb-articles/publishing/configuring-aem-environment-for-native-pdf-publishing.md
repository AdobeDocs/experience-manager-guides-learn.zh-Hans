---
title: 配置AEM环境以发布本机PDF
description: 配置AEM环境以发布本机PDF
source-git-commit: f26b8f94e1d7a3c9dd0aaab2eb196a77119e47ac
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 1%

---


# 配置AEM环境以发布本机PDF

AEM指南包含一个本机PDF发布引擎，该引擎允许用户以PDF格式设计、开发和发布内容。

它提供了创建不同页面布局、CSS模板以及结合页面布局和CSS设计PDF模板的功能。

在AEM指南中配置此本机PDF的步骤因操作系统而异。 根据安装AEM的操作系统，使用下面的配置步骤。

## 前提条件

设置本机PDF的最低要求：

- 已安装的Java平台、标准版8或11 JDK（Java SE开发工具包）和JRE（Java SE运行时环境）
- AEM 6.5 SP13、SP12、SP11或SP10
- 指南4.1及更高版本（非UUID或UUID）

本机PDF发布引擎需要OracleJDK才能在AEM crx-quickstart文件夹中生成节点模块。 默认情况下，它支持以下操作系统：

- Windows 10、Windows 2019服务器及更高版本。
- Linux — （RHEL 8及更高版本、CentOS 7及更高版本、Ubuntu 18及更高版本）
- Mac操作系统（基于英特尔）

## Windows Server配置步骤(JAVA 11/8)

1. 确保AEM服务器关闭。
2. 在Windows任务栏上，右键单击Windows图标，然后选择“系统”。
3. 在“设置”窗口的“相关设置”下，单击“高级系统设置”。
4. 在高级选项卡上，单击环境变量。
5. 在系统变量部分中，单击“_新建_”创建新的环境变量。
6. 输入变量名称作为JAVA_HOME。
7. 在值字段中，提供Java安装路径，然后单击确定。

   例如：

   JAVA 11:

   C:\Program Files\JAVA\jdk-11.0.15.1

   JAVA 8:

   C:\Program Files\JAVA\ jdk1.8.0_144

8. 添加从系统变量中选择的路径，然后单击编辑。

9. 现在，路径变量内提供服务器路径的值，然后单击确定。

   例如：

   JAVA 11:

   %JAVA_HOME%\bin\server\

   JAVA 8:

   %JAVA_HOME%\jre\bin\server\

10. 再次在环境变量对话框中单击“确定”。
11. 再次在“系统属性”对话框中单击“确定”。
12. 现在，启动AEM服务器。
13. 在Web编辑器中通过预设生成本机PDF。

## Linux服务器配置步骤(RHEL7/centOS 7)

1. 确保AEM服务器关闭
2. 通过执行echo $JAVA_HOME验证JAVA_HOME变量
3. 如果未设置JAVA_HOME变量，请执行步骤4。 否则，请直接移动到步骤5。
4. 根据已安装的java版本，使用以下命令设置JAVA_HOME变量

   例如：

   JAVA 11:

   1. 导出JAVA\_HOME=/usr/lib/jvm/java-11.0.15.1
   2. 导出路径=$PATH:$JAVA\_HOME/bin
   3. 导出LD\_LIBRARY\_PATH=/usr/lib/jvm/jdk-11.0.15.1/lib/server:/usr/java/jdk-11.0.15.1/lib/server

   JAVA 8:

   1. 导出JAVA\_HOME=/usr/lib/jvm/java-11.0.15.1
   2. 导出路径=$PATH:$JAVA\_HOME/bin


5. 重新启动AEM Server
6. 复制“_node_modules.zip_“(在本文底部附加到crx-quickstart/profiles/nodejs—b1aad0a7-9079-e56c-1ed8-6fcababe8166/目录)。
7. 在crx-quickstart/profiles/nodejs—b1aad0a7-9079-e56c-1ed8-6fcababe8166/位置中打开终端。
8. 使用以下命令删除node_modules目录

   **rm -rf节点模块**

9. 使用以下命令解压缩node_modules.zip

   **unzip node_modules.zip**

10. 如果未安装/识别unzip命令，则可以使用以下命令安装该命令

   **yum安装解压缩**

11. 安装fontconfig包。
命令：yum install fontconfig
12. 在Web编辑器中通过预设生成本机PDF。

**注意** :node_modules.zip包可下载 [此处](https://acrobat.adobe.com/link/track?uri=urn:aaid:scds:US:295d8f03-41e1-429b-8465-2761ce3c2fb3).

对于使用指南4.1或更早版本的用户而言，手动导入下载的Linux操作系统节点模块是一种解决方法。

## Mac计算机的配置步骤(JAVA 11/8)

1. 安装OracleJAVA 11或OracleJAVA 8。
2. 将JAVA_HOME环境变量设置为已安装的JAVA目录。
3. 打开Unix外壳。
（此处使用Bash设置配置）

   命令：nano ~/bashrc

4. 根据已安装的java版本，使用以下命令设置JAVA_HOME变量

   例如：

   JAVA 11:

   导出JAVA\_HOME= /Library/Java/JavaVirtualMachines/jdk-11.0.15.1.jdk/Contents/Home

5. 重装巴什克

   命令：来源~/.bashrc。

6. 使用命令echo $JAVA_HOME验证是否已设置JAVA_HOME

7. 从AEM安装路径执行以下三个命令

   C:/{aem-installation-folder}/crx-quickstart/profiles/nodejs—b1aad0a7-9079-e56c-1ed8-6fcababe8166

   i)查找。 -type d -exec chmod 0755 {} \;ii)查找。 -type f -exec chmod 0755 {} \;iii)。/node-darwin/bin/node node-darwin/lib/node_modules/npm/bin/npm-cli.js —prefix 。 install —unsafe-perm —scripts-prepend-node-path

8. 使用以下命令验证是否安装了Java

   i)运行 **./node-darwin/bin/node** 来自/crx-quickstart/profiles/nodejs—b1aad0a7-9079-e56c-1ed8-6fcababe8166文件夹的命令

   ![mac](../assets/publishing/mac.png)

   ii)a = require(&#39;java&#39;)

9. 安装fontconfig包。
命令：apt install fontconfig

10. 在Web编辑器中通过预设生成本机PDF。

## 疑难解答

以下是在环境变量设置不正确的情况下，在PDF生成过程中可能发生的常见错误。

### Windows/Mac操作系统中出现空指针异常

![空指针异常](../assets/publishing/null-pointer-exception.png)

### RHEL 7 Linux OS中缺少库

![缺少库](../assets/publishing/missing-libraries.png)

如果您在执行上述任何步骤时遇到任何问题，请将问题发布到AEM指南社区 [论坛](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation) 以寻求帮助。

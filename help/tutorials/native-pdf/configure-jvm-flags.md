---
title: 本机PDF |为本机PDF发布配置JVM标记
description: 为本机PDF发布配置JVM标记
source-git-commit: cfb1197d0aad7ea3771bc6e1a73c02f540cef0c9
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 1%

---


# 为本机PDF发布配置JVM标记

本机PDF发布会启动单独的JVM进程来生成PDF。 您可能需要调整此JVM的配置以支持不同的场景。 例如，要运行较大的工作负载，应增加派生的JVM进程可用的最大栈大小。

执行以下步骤以配置AEM Guides本机PDF发布JVM标记：

1. 打开Adobe Experience Manager Web控制台配置页面。

   用于访问配置页面的默认URL为：

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. 搜索并选择 *com.adobe.fmdita.config.ConfigManager* 捆绑。

1. 更新属性 **本机pdf的Java命令行选项** (*native.pdf.java.opts*)，以传递任何标准JVM标记。



1. 单击“**保存**”。
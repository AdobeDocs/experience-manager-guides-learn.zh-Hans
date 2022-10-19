---
title: 发行说明 | Adobe Experience Manager指南as a Cloud Service,2022年10月版
description: 最新版本的Adobe Experience Manager指南as a Cloud Service
source-git-commit: f673d53a1f3c76e1089e0a0c633c402722f99d00
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 4%

---

# 最新版本的Adobe Experience Manager指南as a Cloud Service

## 升级到最新版本

升级您当前的Adobe Experience Manager指南as a Cloud Service(以后称为 *AEM指南as a Cloud Service*)设置：
1. 查看Cloud Services的Git代码，并切换到在Cloud Services管道中配置的分支，该管道与您要升级的环境相对应。
2. 更新 `<dox.version>` 属性 `/dox/dox.installer/pom.xml` 将Cloud ServicesGit代码的文件2022.10.183.
3. 提交更改并运行Cloud Services管道以升级到最新版本的AEM指南as a Cloud Service。

## 兼容性矩阵

本部分列出了AEM指南as a Cloud Service于2022年10月版支持的软件应用程序的兼容性矩阵。

### FrameMaker和FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| 不兼容 | 2020更新4及更高版本 |
|  |  |

*从2020.2开始的FMPS版本支持在AEM中创建的基线和条件。

### 氧连接器

| AEM Guides as a Cloud Release | 氧连接器窗口 | 氧连接器Mac | 在氧气窗口中编辑 | 在Oxon Mac中编辑 |
| --- | --- | --- | --- | --- |
| 2022.10.0 | 2.7.13 | 2.7.13 | 2.3 | 2.3 |
|  |  |  |  |


## 新增功能和增强功能

AEM指南as a Cloud Service在最新版本中提供了增强功能和新增功能：


### “快速生成”面板

现在，AEM指南提供了 **快速生成** 面板，可帮助您快速生成和查看为DITA映射创建的预设的输出。

![“快速生成”图标](assets/quick-generate-icon.png)

在 **快速生成** 面板中，您可以看到为DITA映射创建的所有输出预设的列表。

![“快速生成”面板](assets/quick-generate-panel.png)

选择一个或多个预设并快速生成输出。 您还可以快速查看为预设生成的输出。 生成输出时会显示成功消息。 如果输出生成失败，则会显示错误消息。 您还可以查看错误日志，以查看生成过程中发生的错误的详细信息。


## 修复的问题

下面列出了各个区域中修复的错误：

* 本机PDF |从PDF输出中删除仅资源主题时出错。 (10554)
* 本机PDF |空的Keyref会显示在PDF输出中。 (10553)
* 本机PDF | `navtitle` 表示 `topichead` 不受尊重。 (10509)
* 本机PDF |支持amd64 JDK版本。 (10465)
* 本机PDF |无法从目录中隐藏Frontmatter主题。 (10355)
* 本机PDF |在章节布局中重新启动页码会随机从上一章的结尾开始编号。 (10154)
* Chrome浏览器 |从UI中拖放任何元素时，屏幕会变为空白。 例如，从“条件”面板拖动条件时。 (10524)
* 在资产执行复制粘贴操作后，将删除节点属性。 (10053)
* 单击  **关闭** 用户被重定向到资产 — 已更正体验以将用户带至AEM主页。 (9654)

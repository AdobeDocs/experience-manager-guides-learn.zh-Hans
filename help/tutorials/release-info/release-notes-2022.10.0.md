---
title: 发行说明 | Adobe Experience Manager Guidesas a Cloud Service，2022年10月版
description: Adobe Experience Manager Guidesas a Cloud Service10月版
exl-id: 38638080-625c-49c3-9e54-56cc23831546
source-git-commit: 67ba514616a0bf4449aeda035161d1caae0c3f50
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 4%

---

# Adobe Experience Manager Guidesas a Cloud Service10月版

## 升级到10月版

as a Cloud Service升级您当前的Adobe Experience Manager Guides(以后称为 *AEM Guidesas a Cloud Service*)通过以下步骤进行设置：
1. 查看Cloud Services的Git代码，然后切换到在Cloud Services管道中配置的与要升级的环境对应的分支。
1. 更新 `<dox.version>` 中的属性 `/dox/dox.installer/pom.xml` Cloud ServicesGit代码的文件更改为2022.10.183。
1. 提交更改并运行Cloud Services管道，以升级到10月版的AEM Guidesas a Cloud Service。

## 兼容性矩阵

本部分列出了AEM Guides 2022年10月as a Cloud Service版本支持的软件应用程序的兼容性矩阵。

### FrameMaker和FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| 不兼容 | 2020 Update 4及更高版本 |
|  |  |

*从2020.2开始的FMPS版本支持在AEM中创建的基线和条件。

### 氧气连接器

| AEM Guides as a Cloud版本 | 氧气连接器窗口 | 氧气连接器Mac | 在氧气窗口中编辑 | 在氧气Mac中编辑 |
| --- | --- | --- | --- | --- |
| 2022.10.0 | 2.7.13 | 2.7.13 | 2.3 | 2.3 |
|  |  |  |  |


## 新增功能和增强功能

AEM Guidesas a Cloud Service在10月版本中提供了以下增强功能和新功能：


### “快速生成”面板

现在， AEM Guides提供了 **快速生成** 面板，可帮助您快速生成和查看为DITA map创建的预设的输出。

![“快速生成”图标](assets/quick-generate-icon.png)

在 **快速生成** 面板中，您可以看到为DITA map创建的所有输出预设的列表。

![“快速生成”面板](assets/quick-generate-panel.png)

选择一个或多个预设并快速生成输出。 您还可以快速查看为预设生成的输出。 成功消息显示在生成的输出中。 如果输出生成失败，则显示错误消息。 您还可以查看错误日志，以查看生成过程中所发生错误的详细信息。


## 修复的问题

修复了多个区域的错误如下：

* 本机PDF |从PDF输出中删除仅资源主题时出错。 (10554)
* 本机PDF |PDF输出中出现空的键参照。 (10553)
* 本机PDF | `navtitle` 对象 `topichead` 不荣幸。 (10509)
* 本机PDF |支持amd64 JDK风格。 (10465)
* 本机PDF |无法从目录隐藏前台主题。 (10355)
* 本机PDF |在章节布局中重新启动页码会从上一章的结尾开始随机编号。 (10154)
* Chrome浏览器 |从UI拖放任何元素时，屏幕变为空白。 例如，从“条件”面板拖动条件时。 (10524)
* 在对资产执行复制粘贴操作后，将删除节点属性。 (10053)
* 单击  **关闭** 用户被重定向到资源 — 体验已更正，用户可转到AEM主页。 (9654)

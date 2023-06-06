---
title: 发行说明 | Adobe Experience Manager Guidesas a Cloud Service，2023年4月版
description: Adobe Experience Manager Guidesas a Cloud Service版2023年4月版
exl-id: 3b09f0b3-cfa4-422d-91b7-733ab1c1896c
source-git-commit: 99ca14a816630f5f0ec1dc72ba77994ffa71dff6
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 2%

---

# Adobe Experience Manager Guidesas a Cloud Service版2023年4月版

本发行说明涵盖了升级说明、兼容性矩阵，以及2023年4月版Adobe Experience Manager Guides(以后称为 *AEM Guidesas a Cloud Service*)。

有关新增功能和增强功能的更多信息，请参阅 [AEM Guidesas a Cloud Service版2023年4月版的新增功能](whats-new-2023.4.0.md).

## 升级到2023年4月版

通过执行以下步骤升级当前的AEM Guidesas a Cloud Service设置：

1. 查看Cloud Services的Git代码，然后切换到在Cloud Services管道中配置的与要升级的环境对应的分支。
2. 更新 `<dox.version>` 中的属性 `/dox/dox.installer/pom.xml` Cloud ServicesGit代码的文件更改为2023.4.249。
3. 提交更改并运行Cloud Services管道，以升级到2023年4月版的AEM Guidesas a Cloud Service。

## 索引现有内容的步骤(仅当使用的版本早于9月份的AEM Guidesas a Cloud Service版本时)

执行以下步骤来索引现有内容并在映射级别使用新的查找和替换文本：

* 对服务器运行POST请求（使用正确的身份验证） —  `http://<server:port>/bin/guides/map-find/indexing`.
(可选：您可以传递映射的特定路径来索引它们，默认情况下，所有映射都将索引 ||示例： `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* 该API将返回jobId。 要检查作业的状态，您可以将带有作业ID的GET请求发送到同一端点 —  `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(例如：http://&lt;
_localhost：8080_>/bin/guides/map-find/indexing？jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* 作业完成后，上述GET请求将做出成功响应，并提及是否有任何映射失败。 可以从服务器日志中确认已成功编制索引的映射。

## 兼容性矩阵

本部分列出了AEM Guides 2023年4月as a Cloud Service版本支持的软件应用程序的兼容性矩阵。

### FrameMaker和FrameMaker Publishing Server

| AEM Guides as a Cloud版本 | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.04.0 | 不兼容 | 2022或更高版本 |
|  |  |  |


### 氧气连接器

| AEM Guides as a Cloud版本 | 氧气连接器窗口 | 氧气连接器Mac | 在氧气窗口中编辑 | 在氧气Mac中编辑 |
| --- | --- | --- | --- | --- |
| 2023.04.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2.3 | 2.3 |
|  |  |  |  |



## 修复的问题

修复了多个区域的错误如下：

* 本机PDF |发布具有带brackets()的输出类的内容会导致发布冻结。 (11596)
* 在替换启用了跟踪更改的现有列表项时，移动（拖放）出现问题。 (11570)
* 作为启用了跟踪更改的新列表项移动（拖放）时出现问题。 (11569)
* 对于上的“跟踪更改”，缩进或减少缩进列表项无法按预期工作。 (11568)
* 在启用了“跟踪更改”的行中添加内容，然后关闭“跟踪更改”实际上并不会将其关闭。 (11567)
* 难以拖放列表项，文本将移动到列表项的位置。 (11566)
* 已完成审阅不会在只读模式下打开。 (11387)
* AEM站点搜索中出现问题（在2-3级节点之外不起作用）。 (11352)
* 在创作以绿色显示的元素（跟踪更改）时，即使跟踪更改处于禁用状态，新内容也会显示为跟踪更改。 (7021)

### 有变通方法的已知问题

Adobe已发现AEM Guides 2023年4月as a Cloud Service版的以下已知问题。

* 本机PDF |在显式打开输出预设之前，不会填充旧元数据。

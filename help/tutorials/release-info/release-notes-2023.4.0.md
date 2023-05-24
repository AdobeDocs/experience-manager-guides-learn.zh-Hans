---
title: 发行说明 | Adobe Experience Manager Guidesas a Cloud Service，2023年4月版
description: 最新版本的Adobe Experience Manager Guidesas a Cloud Service
exl-id: 3b09f0b3-cfa4-422d-91b7-733ab1c1896c
source-git-commit: cf612da41f79b0bf9da4c4d7454a0e3c86af7a4c
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 2%

---

# Adobe Experience Manager Guidesas a Cloud Service版4月版

## 升级到最新版本

as a Cloud Service升级您当前的Adobe Experience Manager Guides(以后称为 *AEM Guidesas a Cloud Service*)通过以下步骤进行设置：

1. 查看Cloud Services的Git代码，然后切换到在Cloud Services管道中配置的与要升级的环境对应的分支。
2. 更新 `<dox.version>` 中的属性 `/dox/dox.installer/pom.xml` Cloud ServicesGit代码的文件更改为2023.4.249。
3. 提交更改并运行Cloud Services管道，以升级到最新版本的AEM Guidesas a Cloud Service。

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


## 新增功能和增强功能

AEM Guidesas a Cloud Service在最新版本中提供增强功能和新功能：

### PDF发布中的高级元数据支持

AEM Guides现在为映射到PDF输出中元数据的元数据提供高级支持。 元数据选项包括有关文档及其内容的信息，例如作者姓名、文档标题、关键字、版权信息和其他数据字段。

<img src="assets/pdf-metadata.png" alt=" 本机pdf元数据">

您可以导入XMP文件，AEM Guides可以从文件中选取信息。 您还可以选择使用下拉菜单提供元数据名称和值。 您还可以通过直接在名称字段中键入来添加自定义元数据。


### “增强的大纲视图”面板

AEM Guides提供了一个改进的“大纲视图”面板，您可以在其中获得文档中所用元素的分层视图。

<img src="assets/select-element-content-outline-view_cs.png" alt=" 本机pdf元数据">

“大纲视图”提供了以下增强功能：

* “视图选项”下拉列表显示在“大纲视图”面板的顶部。 如果元素具有ID、属性和文本，则可以从下拉列表中选择它们，以与元素一起显示它们。 可以在“大纲视图”面板中显示的属性由管理员在 **编辑器设置**.

* 使用搜索功能，您可以按元素的名称、ID、文本或属性值搜索元素。


### AEM Guidesas a Cloud Service基于微服务的发布

AEM Guidesas a Cloud Service提供了与基于微服务的发布同时运行大型发布工作负载的功能，并利用业界领先的Adobe I/O Runtime无服务器平台。

现在，在4月版本中，您可以使用基于微服务的本机PDF发布来同时运行多个发布请求并非常高效地生成批量PDF输出。
有关更多详细信息，请参阅 [为AEM Guidesas a Cloud Service配置新的基于微服务的发布](../knowledge-base/publishing/configure-microservices.md).


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

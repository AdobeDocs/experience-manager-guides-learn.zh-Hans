---
title: 发行说明 | Adobe Experience Manager指南as a Cloud Service,2023年4月版
description: 最新版本的Adobe Experience Manager指南as a Cloud Service
source-git-commit: 77b118655ad8e37e00b0371497e4a2578ddd276e
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 2%

---

# 4月版Adobe Experience Manager指南as a Cloud Service

## 升级到最新版本

升级您当前的Adobe Experience Manager指南as a Cloud Service(以后称为 *AEM指南as a Cloud Service*)设置：

1. 查看Cloud Services的Git代码，并切换到在Cloud Services管道中配置的分支，该管道与您要升级的环境相对应。
2. 更新 `<dox.version>` 属性 `/dox/dox.installer/pom.xml` 文件中的“Cloud ServicesGit代码”到2023.4.249。
3. 提交更改并运行Cloud Services管道以升级到最新版本的AEM指南as a Cloud Service。

## 索引现有内容的步骤(仅当您使用的是9月版AEM指南之前的版本时as a Cloud Service)

执行以下步骤，为现有内容编制索引，并在映射级别使用新的查找和替换文本：

* 向服务器运行POST请求（验证正确） —  `http://<server:port>/bin/guides/map-find/indexing`.
(可选：您可以传递映射的特定路径来索引它们，默认情况下，所有映射都将编入索引 ||示例： `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* 该API将返回jobId。 要检查作业的状态，您可以向同一端点发送具有作业ID的GET请求 —  `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(例如：http://&lt;
_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* 作业完成后，上述GET请求将做出成功响应，并在任何映射失败时提及。 可以从服务器日志中确认已成功索引的映射。

## 兼容性矩阵

本部分列出了AEM指南as a Cloud Service于2023年4月发布的软件应用程序所支持的兼容性矩阵。

### FrameMaker和FrameMaker Publishing Server

| AEM Guides as a Cloud Release | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.04.0 | 不兼容 | 2022或更高版本 |
|  |  |  |


### 氧连接器

| AEM Guides as a Cloud Release | 氧连接器窗口 | 氧连接器Mac | 在氧气窗口中编辑 | 在Oxon Mac中编辑 |
| --- | --- | --- | --- | --- |
| 2023.04.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2.3 | 2.3 |
|  |  |  |  |


## 新增功能和增强功能

AEM指南as a Cloud Service在最新版本中提供了增强功能和新增功能：

### PDF发布中的高级元数据支持

AEM指南现在为映射到PDF输出中元数据的元数据提供高级支持。 元数据选项包括有关文档及其内容的信息，例如作者的姓名、文档标题、关键字、版权信息和其他数据字段。

<img src="assets/pdf-metadata.png" alt=" 原生pdf元数据">

您可以导入XMP文件，AEM指南可以从文件中选取信息。 您还可以选择使用下拉菜单提供元数据名称和值。 您还可以通过直接在名称字段中键入来添加自定义元数据。


### 增强的“大纲视图”面板

AEM指南提供简易的“大纲视图”面板，您可以在该面板中获取文档中使用的元素的分层视图。

<img src="assets/select-element-content-outline-view_cs.png" alt=" 原生pdf元数据">

“大纲视图”提供了以下增强功能：

* “视图选项”下拉列表显示在“大纲视图”面板的顶部。 如果某个元素具有ID、属性和文本，则您可以从下拉菜单中选择它们以显示它们和元素。 可在“大纲视图”面板中显示的属性由管理员在 **编辑器设置**.

* 使用搜索功能，您可以按元素的名称、ID、文本或属性值搜索元素。


### 基于微服务的AEM指南发布as a Cloud Service

AEM指南as a Cloud Service提供了与基于微服务的发布同时运行大量发布工作负载的功能，并利用行业领先的Adobe I/O Runtime无服务器平台。

现在，在4月版中，您可以使用基于微服务的本机PDF发布，同时运行多个发布请求并非常高效地生成批量PDF输出。
有关更多详细信息，请参阅 [为AEM指南配置新的基于微服务的发布as a Cloud Service](../knowledge-base/publishing/configure-microservices.md).


## 修复的问题

下面列出了各个区域中修复的错误：

* 本机PDF |发布包含带括号()的输出类的内容会导致发布冻结。 (11596)
* 在开启“跟踪更改”的情况下，移动（拖放）以取代现有列表项时出现问题。 (11570)
* 在将“跟踪更改”作为新列表项进行移动（拖放）时出现问题。 (11569)
* 在开启“跟踪更改”时，缩进或缩进列表项无法按预期工作。 (11568)
* 在开启“跟踪更改”的行上添加内容，然后关闭“跟踪更改”实际上不会关闭该行。 (11567)
* 拖放列表项时遇到困难，文本会移动以代替列表项。 (11566)
* 已完成的审阅未在只读模式下打开。 (11387)
* 在AEM网站搜索中出现问题（无法在2-3级节点之外使用）。 (11352)
* 在以绿色显示的元素（“跟踪更改”）中进行创作时，即使禁用了“跟踪更改”，新内容也会显示为“跟踪更改”。 (7021)

### 解决方法的已知问题

Adobe已在2023年4月版AEM指南as a Cloud Service确定以下已知问题。

* 本机PDF |明确打开输出预设后，才会填充旧元数据。


---
title: 发行说明 | Adobe Experience Manager Guidesas a Cloud Service，2023年2月版
description: Adobe Experience Manager Guides的2月版as a Cloud Service
exl-id: c639b136-11ed-4a8b-a595-4bb5da879747
source-git-commit: ee520ab86ea41df7556a1f40d7bfc5e3617b34ae
workflow-type: tm+mt
source-wordcount: '2178'
ht-degree: 2%

---

# Adobe Experience Manager Guides的2月版as a Cloud Service

## 升级到2月版

as a Cloud Service升级您当前的Adobe Experience Manager Guides(以后称为 *AEM Guidesas a Cloud Service*)通过以下步骤进行设置：
1. 查看Cloud Services的Git代码，然后切换到在Cloud Services管道中配置的与要升级的环境对应的分支。
2. 更新 `<dox.version>` 中的属性 `/dox/dox.installer/pom.xml` Cloud ServicesGit代码的文件更改为2023.2.235。
3. 提交更改并运行Cloud Services管道，以升级到AEM Guides的2月版as a Cloud Service。

## 索引现有内容的步骤(仅当使用的版本早于9月份的AEM Guidesas a Cloud Service版本时)

执行以下步骤来索引现有内容，并在映射级别使用新的查找和替换文本：

* 对服务器运行POST请求（使用正确的身份验证） —  `http://<server:port>/bin/guides/map-find/indexing`.
(可选：您可以传递映射的特定路径来索引它们，默认情况下，所有映射都将索引 ||示例： `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* 该API将返回jobId。 要检查作业的状态，您可以将带有作业ID的GET请求发送到同一端点 —  `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(例如：http://&lt;
_localhost：8080_>/bin/guides/map-find/indexing？jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* 作业完成后，上述GET请求将做出成功响应，并提及是否有任何映射失败。 可以从服务器日志中确认已成功编制索引的映射。

## 兼容性矩阵

本部分列出了AEM Guides 2023年2月as a Cloud Service版本支持的软件应用程序的兼容性矩阵。

### FrameMaker和FrameMaker Publishing Server

| AEM Guides as a Cloud版本 | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.02.0 | 不兼容 | 2022或更高版本 |
|  |  |  |

*从2020.2开始的FMPS版本支持在AEM中创建的基线和条件。

### 氧气连接器

| AEM Guides as a Cloud版本 | 氧气连接器窗口 | 氧气连接器Mac | 在氧气窗口中编辑 | 在氧气Mac中编辑 |
| --- | --- | --- | --- | --- |
| 2023.02.0 | 2.8-uuid-8 | 2.8-uuid-8 | 2.3 | 2.3 |
|  |  |  |  |


## 新增功能和增强功能

AEM Guidesas a Cloud Service在2月版本中提供了增强功能和新增功能：

### 从Web编辑器生成报告

AEM Guides在Web编辑器中提供的一项功能使您能够检查技术文档的整体完整性并为其生成报告。
您可以从以下位置查看主题列表、管理元数据以及查看当前映射的所有引用中使用的多媒体：
**报告** 选项卡。

**生成主题列表视图**

可生成主题列表，其中提供有关主题的详细信息，如引用类型、文档状态和作者。 您还可以生成CSV以下载DITA映射中主题的当前快照。

**管理元数据和更改文档状态**

可以在单个主题中应用标记，也可以使用批量标记功能在多个主题、DITA映射或子映射中应用多个标记。 您也可以将所有选定主题的文档状态更改为下一个可能的公用文档状态。

<img src="assets/web-editor-metadata-panel.png" alt="管理元数据" width="600">

**生成多媒体报告**

您可以生成多媒体报告，该报告包含有关当前映射中引用所使用的多媒体的详细信息。 您可以灵活地筛选和排序报告中列出的多媒体文件。
您还可以生成CSV来下载DITA映射中使用的多媒体的当前快照。

<img src="assets/web-editor-reports-multimedia.png" alt="多媒体报告" width="600">

### 针对审阅功能对UX进行了改版

现在，AEM Guides提供了一个经过改进的UX，可帮助您查看共享供查看的主题。 在最新的体验中，审阅功能具有以下增强功能：

* 已刷新用户界面
* 条件面板，允许您根据主题中的可用条件突出显示内容
* 评论面板中的每个评论都链接到当前主题中的相应文本。 它有助于您识别注释的文本。
* 注释按文档中注释文本的顺序显示。
* 审核任务的名称显示在审核工作流中。
* 选择审阅任务的根图，该根图用于解析审阅内容中使用的所有关键引用和术语表。
* 上下文工具栏可帮助您快速高亮显示或删除文本
* 用于编辑或删除您自己的评论的“选项”菜单
* 对于过时的注释，您可以访问并排视图，这有助于将主题的以前版本与当前审阅版本进行比较。
* 在使用过滤器时，右侧面板上的注释将根据所选内容进行过滤，左侧面板中的注释数量将相应地更新。


   <img alt="审核任务" src="assets/comment-pop-up-panel.png" width="600">



### 翻译增强功能

现在，翻译仪表板中提供了更加用户友好的增强功能，可帮助您从Web编辑器轻松翻译文档。

**将版本标签传递到目标版本**

AEM Guides允许您将源文件的标签传递到目标文件。 这有助于您轻松识别已翻译文件的源版本。

<img alt="翻译标签" src="assets/translation-pass-source-label.png" width="600">

例如，如果您有一些源文件应用了版本标签1.0版，那么您还可以将源标签（1.0版）传递到已翻译的文件。

**强制同步不同步的资产**

如果您对某些资源进行了更改，AEM Guides会将这些资源标记为不同步。 您可以重新翻译修改的资产，也可以选择取消不同步状态。 例如，如果您进行了一些确实不需要翻译的次要更改，则可以将其状态标记为同步。

<img src="assets/translation-version-diff.png" alt="翻译板" width="600">

**查看主题或映射的正在进行中的翻译项目**

翻译仪表板上的某些引用可能正在进行中。 现在，AEM Guides提供了一项功能，可帮助您查看包含所选引用的所有正在进行的翻译项目的列表（以及目标语言）。


### 从Web编辑器生成各种格式的输出

现在，您可以轻松地从Web编辑器生成主题或DITA映射的输出。 您可以配置各种输出预设，如AEM Site、PDF、HTML5、JSON（一种Headless输出格式）和自定义输出。 然后，您可以使用这些组件生成相应的输出。

您可以在DITA主题中定义属性，然后使用条件预设在发布输出时应用条件。 还可使用基线发布功能有选择地发布DITA map或主题的特定版本。


### 在映射级别查找和替换文本

AEM Guides允许您在映射中搜索包含特定文本的文件。 搜索到的文本在文件中突出显示。 现在，您还可以用所有文件中的其他单词或短语替换搜索的单词或短语。 您可以选择 **全部替换** 图标，以替换所有文件中搜索词的所有匹配项。

<img src="assets/map-find-replace.png" alt="映射查找替换" width="600">

### 从存储库面板中删除和复制文件

现在，您可以轻松地从创建文件的副本或副本 **选项** 存储库面板中选定文件的菜单。 默认情况下，创建该文件时带有后缀(例如 `filename_1.extension`)。

<img src="assets/options-menu-repo-view-file-level.png" alt="文件选项菜单 " width="500">


### 其他Web编辑器增强功能

* 在AEM Guides中，您可以使用上下文菜单对图像和媒体文件执行一些常见操作。 现在，您还可以在存储库中找到选定的图像或媒体，或者在Assets UI中查看文件预览。

* 当前文件夹配置文件的名称在主工具栏中显示为“用户首选项”图标的标签。 这有助于您识别正在处理的文件夹配置文件。

* 在地图视图中打开地图时，当前地图的标题显示在主工具栏的中央。 这有助于让用户知道当前打开了哪个映射。


### 在氧气编辑器中查看标题代替UUID

现在，AEM Guides允许您选择 **在编辑器和映射管理器中使用标题** 选项。 如果选择此选项，则在编辑器或DITA映射管理器中打开文件时，文件的标题将显示在文件的选项卡上。 如果不选择此选项，则文件的UUID将显示在文件的选项卡上。

### AEM Guidesas a Cloud Service基于微服务的发布

新的发布微服务使您能够同时在AEM Guidesas a Cloud Service上运行大型发布工作负载，并利用业界领先的Adobe I/O Runtime无服务器平台。

对于每个发布请求，AEM Guidesas a Cloud Service会运行一个单独的容器，该容器会根据用户请求水平缩放。 这使您能够运行多个发布请求并获得改进的性能。

有关更多详细信息，请参阅 [为AEM Guidesas a Cloud Service配置新的基于微服务的发布](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/knowledge-base/publishing/configure-microservices.md).

### 本机PDF |在PDF输出中添加自定义书签

现在，您可以在最终PDF输出中为特定内容添加自定义书签以便轻松导航。 这将添加到从DITA map中的主题或节标题创建的目录。

### 本机PDF |对目录条目和主题内容应用自定义样式

AEM Guides提供了对目录条目或PDF输出中的特定主题应用自定义样式的功能。 例如，您可以更改目录和主题标题中文本的颜色。 您还可以在主题内的整个内容上应用样式。


### 本机PDF |在脚注组件中设置页面标记的样式

现在，您可以在脚注中为页面标记设置样式。 例如，您可以添加括号或更改其颜色。 这些样式可帮助用户轻松识别文档中的页面标记。

### 本机PDF |更改栏以指示目录中已更改的主题

AEM Guides现在允许您快速识别PDF输出目录中已更改的主题。  它会在目录中已更改的主题的左侧显示更改栏。 您可以单击目录中的主题并查看详细更改。

<img src="assets/change-marker-toc.png" alt="更改目录中的标记 " width="500">

## 修复的问题

修复了多个区域的错误如下：

### 创作

* Web编辑器html中的更改导致出现问题 `<dl>` 和 `<dlentry>`. (11024)
* 某些属性不会被视为有条件属性，从而导致出现问题。 (10895)
* 三个级别或更多嵌套 `<indexterm>` 未嵌套在本机PDF导出中。 (10799)
* 从“创作”视图切换到“源”视图时，内容在任务正文中消失。 (10735)
* 审阅评论在审阅任务中被错误放置。 (10625)
* **撤消** 或 **重做** 在某些文件上无法正常工作。 (10373)
* 在复制和粘贴操作中，自定义元数据未保留。 (10367)
* XML编辑器中的“撤消”选项可将用户转到页面顶部。 (10091)
* 对资产执行复制和粘贴操作后，将删除节点属性。 (10053)
* mimeType已为DITA资产创建和更新进行硬编码。 (8979)
* 对于通过Assets UI上传的文件，版本历史记录中的版本创建者名称是“fmdita-serviceuser”。 (8910)
* 在云上安装AEM Guides时，无法复制和粘贴内容片段。 (11315)
* 使用自定义架构加载内容时，浏览器（Web编辑器）冻结。 (11211)

### 管理

* 复制DITA映射资产（从资产UI ）会导致所复制的资产中出现错误的基线。 (11218)
* 上传大于AEM中允许的限制（默认为2 GB）的文件时不会显示警告消息。 (10817)
* Web编辑器 — 基线 | Latest列的行为在Web编辑器的新基线仪表板中有所不同。 (10808)
* 翻译 |由于/libs/fmdita/i18n/ja.json无效，翻译作业未开始。 (10543)
* 翻译 |从翻译仪表板（人工翻译）创建的范围设定翻译项目出错。 (10526)
* 翻译 |对于资产位于活动翻译项目中的整个语言文件夹，后处理被阻止。 (10332)
* 如果在基线编辑器中更改并保存了版本，则会为任何资源显示多个弹出窗口。 (10399)
* 会话泄露发生于 `com.day.cq.search.impl.builder.QueryBuilderImpl.createResourceResolver(QueryBuilderImpl.java:210)`. (10279)

### 发布

* 主题重新生成不适用于某些场景。 (10635)
* Publishlistener未在info日志中显示请求的数据，并且还包含一些垃圾日志。( 10567)
* 本机PDF |使用“添加到文件夹配置文件”选项创建输出预设时，PDF生成失败并出现空指针异常。 (10950)
* 本机PDF |旋转表标题时出现问题。 (10555)
* 本机PDF |嵌套 `<indexterm>` 未嵌套在本机PDF导出中。 (10521)
* 本机PDF |在附录中嵌套的topicref全部转换为临时HTML中的h1。 (10454)
* 对于使用FrameMaker Publishing Server 2020生成的PDF，基线发布失败。 (10551)
* 本机PDF |添加 `xref` 到图像不会在生成的PDF上渲染图像。 (11346)
* 本机PDF |图像标记向所有图像添加display-inline属性。 (10653)
* 本机PDF |默认情况下，在生成的输出中隐藏草稿注释。 (10560)
* 本机PDF |不对topichead授予navtitle。 (10509)

---
title: 发行说明 | Adobe Experience Manager指南as a Cloud Service,2023年2月版
description: 2月版Adobe Experience Manager指南as a Cloud Service
exl-id: c639b136-11ed-4a8b-a595-4bb5da879747
source-git-commit: ee520ab86ea41df7556a1f40d7bfc5e3617b34ae
workflow-type: tm+mt
source-wordcount: '2178'
ht-degree: 2%

---

# 2月版Adobe Experience Manager指南as a Cloud Service

## 升级到2月版

升级您当前的Adobe Experience Manager指南as a Cloud Service(以后称为 *AEM指南as a Cloud Service*)设置：
1. 查看Cloud Services的Git代码，并切换到在Cloud Services管道中配置的分支，该管道与您要升级的环境相对应。
2. 更新 `<dox.version>` 属性 `/dox/dox.installer/pom.xml` 文件，以将Cloud ServicesGit代码复制到2023.2.235。
3. 提交更改并运行Cloud Services管道以升级到2月版AEM指南as a Cloud Service。

## 索引现有内容的步骤(仅当您使用的是9月版AEM指南之前的版本时as a Cloud Service)

执行以下步骤以索引现有内容，并在映射级别使用新的查找和替换文本：

* 向服务器运行POST请求（验证正确） —  `http://<server:port>/bin/guides/map-find/indexing`.
(可选：您可以传递映射的特定路径来索引它们，默认情况下，所有映射都将编入索引 ||示例： `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* 该API将返回jobId。 要检查作业的状态，您可以向同一端点发送具有作业ID的GET请求 —  `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(例如：http://&lt;
_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* 作业完成后，上述GET请求将做出成功响应，并在任何映射失败时提及。 可以从服务器日志中确认已成功索引的映射。

## 兼容性矩阵

本部分列出了AEM指南as a Cloud Service于2023年2月版支持的软件应用程序的兼容性矩阵。

### FrameMaker和FrameMaker Publishing Server

| AEM Guides as a Cloud Release | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.02.0 | 不兼容 | 2022或更高版本 |
|  |  |  |

*从2020.2开始的FMPS版本支持在AEM中创建的基线和条件。

### 氧连接器

| AEM Guides as a Cloud Release | 氧连接器窗口 | 氧连接器Mac | 在氧气窗口中编辑 | 在Oxon Mac中编辑 |
| --- | --- | --- | --- | --- |
| 2023.02.0 | 2.8-uuid-8 | 2.8-uuid-8 | 2.3 | 2.3 |
|  |  |  |  |


## 新增功能和增强功能

AEM指南as a Cloud Service在2月版中提供了增强功能和新增功能：

### 从Web编辑器中生成报告

AEM指南在Web编辑器中附带一项功能，让您能够检查技术文档的整体完整性并为其生成报告。
您可以查看主题列表、管理元数据，以及查看
**报表** 选项卡。

**生成主题列表视图**

您可以生成主题列表，其中提供有关主题的详细信息，如引用类型、文档状态和作者。 您还可以生成CSV以下载DITA映射中主题的当前快照。

**管理元数据和更改文档状态**

您可以对单个主题应用标记，或使用批量标记功能对多个主题、DITA映射或子映射应用多个标记。 您还可以将所有选定主题的文档状态更改为下一个可能的通用文档状态。

<img src="assets/web-editor-metadata-panel.png" alt="管理元数据" width="600">

**生成多媒体报告**

您可以生成多媒体报告，其中包含有关当前地图中引用中使用的多媒体的详细信息。 您可以灵活地过滤和排序报告中列出的多媒体文件。
您还可以生成CSV以下载DITA映射中使用的多媒体的当前快照。

<img src="assets/web-editor-reports-multimedia.png" alt="多媒体报告" width="600">

### 对UX进行了审核功能的改进

现在，AEM指南提供了一个经过改进的UX，可帮助您查看共享以供审阅的主题。 在最新体验中，审核功能具有以下增强功能：

* 更新的用户界面
* 允许您根据主题中的可用条件突出显示内容的条件面板
* 注释面板中的每个注释都链接到当前主题中的相应文本。 它有助于您识别已评论的文本。
* 注释按文档中注释文本的顺序显示。
* 审核任务的名称显示在审核工作流中。
* 为审阅任务选择rootmap，该rootmap用于解析审阅内容中使用的所有关键引用和术语表。
* 帮助您快速突出显示或删除文本的上下文工具栏
* 用于编辑或删除您自己的注释的选项菜单
* 对于过时的评论，您可以访问并排视图，该视图可帮助您将主题的先前版本与当前审阅版本进行比较。
* 使用过滤器时，会根据选择过滤右侧面板上的注释，并相应地更新左侧面板中的注释数。


   <img alt="审核任务" src="assets/comment-pop-up-panel.png" width="600">



### 翻译增强功能

现在，翻译仪表板中提供了更易于用户使用的增强功能，帮助您从Web编辑器轻松翻译文档。

**将版本标签传递到目标版本**

AEM指南允许您将源文件的标签传递到目标文件。 这有助于您轻松识别翻译文件的源版本。

<img alt="翻译标签" src="assets/translation-pass-source-label.png" width="600">

例如，如果某些源文件应用了版本标签1.0的版本，则您还可以将源标签（版本1.0）传递到已翻译的文件。

**强制同步不同步的资产**

如果您对某些资产进行了更改，则AEM指南会将其标记为不同步。 您可以重新转换已修改的资产，或选择取消“不同步”状态。 例如，如果您进行了一些确实不需要翻译的细微更改，则可以将其状态标记为“同步”。

<img src="assets/translation-version-diff.png" alt="翻译板" width="600">

**查看主题或映射的正在进行翻译项目**

翻译功能板上的某些引用可能正在进行中。 现在，AEM指南提供了一项功能，可帮助您查看包含所选引用的所有正在进行的翻译项目（以及目标语言）的列表。


### 从Web编辑器中以各种格式生成输出

现在，您可以从Web编辑器轻松生成主题的输出或DITA映射。 您可以配置各种输出预设，如AEM Site、PDF、HTML5、JSON（无标题输出格式）和自定义输出。 然后，可以使用这些参数生成相应的输出。

您可以在DITA主题中定义属性，然后使用条件预设在发布输出时应用条件。 您还可以使用基线发布功能有选择地发布DITA映射或主题的特定版本。


### 在映射级别查找并替换文本

AEM指南允许您在映射中搜索包含特定文本的文件。 在文件中突出显示搜索的文本。 现在，您还可以在所有文件中将搜索的单词或短语替换为其他单词或短语。 您可以选择 **全部替换** 图标，替换所有文件中出现的搜索词的所有内容。

<img src="assets/map-find-replace.png" alt="映射查找替换" width="600">

### 从存储库面板中删除和复制文件

现在，您可以轻松地从 **选项** “存储库”面板中选定文件的菜单。 默认情况下，创建的文件带有后缀(如 `filename_1.extension`)。

<img src="assets/options-menu-repo-view-file-level.png" alt="文件选项菜单 " width="500">


### 其他Web编辑器增强功能

* 在AEM指南中，您可以使用上下文菜单对图像和媒体文件执行一些常见操作。 现在，您还可以在存储库中找到选定的图像或媒体，或在资产UI中查看文件预览。

* 当前文件夹配置文件的名称将作为主工具栏中用户首选项图标的标签显示。 这有助于您识别正在处理的文件夹配置文件。

* 在映射视图中打开映射时，当前映射的标题将显示在主工具栏的中心。 这有助于让用户知道当前打开的地图。


### 在Oxon编辑器中查看标题代替UUID

现在，AEM指南允许您 **在编辑器和映射管理器中使用标题** 选项。 如果选择此选项，则在编辑器或DITA映射管理器中打开文件时，文件的标题将显示在文件的选项卡中。 如果不选择此选项，则文件的UUID会显示在文件的选项卡中。

### 基于微服务的AEM指南发布as a Cloud Service

新的发布微服务使您能够在AEM指南as a Cloud Service上同时运行大量发布工作负载，并利用行业领先的Adobe I/O Runtime无服务器平台。

对于每个发布请求，AEM指南as a Cloud Service会运行一个单独的容器，该容器会根据用户请求水平缩放。 这样，您就可以运行多个发布请求，并获得更好的性能。

有关更多详细信息，请参阅 [为AEM指南配置新的基于微服务的发布as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/knowledge-base/publishing/configure-microservices.md).

### 本机PDF |在PDF输出中添加自定义书签

现在，您可以在最终PDF输出中对特定内容添加自定义书签，以便轻松导航。 此内容将添加到DITA映射中基于主题或区域标题创建的目录中。

### 本机PDF |对目录条目和主题内容应用自定义样式

AEM指南提供了对目录条目或PDF输出中的特定主题应用自定义样式的功能。 例如，您可以更改目录中文本的颜色和主题的标题。 您还可以对主题中的整个内容应用样式。


### 本机PDF |在脚注组件中设置页面标记样式

现在，您可以在脚注中设置页面标记的样式。 例如，可添加括号或更改其颜色。 这些样式可帮助用户轻松识别文档中的页面标记。

### 本机PDF |更改栏以指示目录中已更改的主题

AEM指南现在允许您快速识别PDF输出目录中已更改的主题。  它会在目录中的已更改主题左侧显示一个更改栏。 您可以单击目录中的主题，并查看详细更改。

<img src="assets/change-marker-toc.png" alt="在目录中更改标记 " width="500">

## 修复的问题

下面列出了各个区域中修复的错误：

### 创作

* Web编辑器html中的更改会导致 `<dl>` 和 `<dlentry>`. (11024)
* 某些属性未被视为条件属性并会导致问题。 (10895)
* 三个级别或更多嵌套级别 `<indexterm>` 未嵌套在本机PDF导出中。 (10799)
* 从“创作”视图切换到“源”视图时，内容会在任务正文中消失。 (10735)
* 在审阅任务中，审阅注释放错位置。 (10625)
* **撤消** 或 **重做** 无法正确处理某些文件。 (10373)
* 复制并粘贴操作时不会保留自定义元数据。 (10367)
* XML编辑器中的“撤消”选项会将用户带到页面顶部。 (10091)
* 复制并粘贴资产操作后，将删除节点属性。 (10053)
* mimeType经过硬编码，用于创建和更新DITA资产。 (8979)
* 对于通过Assets UI上传的文件，版本历史记录中的版本创建者名称是“fmdita-serviceuser”。 (8910)
* 在Cloud上安装AEM指南后，无法复制和粘贴内容片段。 (11315)
* 使用自定义模式加载内容时，浏览器（Web编辑器）冻结。 (11211)

### 管理

* 复制DITA映射资产（从资产UI）会导致复制的资产中出现错误的基线。 (11218)
* 如果文件的上载大于AEM中允许的限制（默认为2 GB），则不会显示警告消息。 (10817)
* Web编辑器 — 基线 |在Web编辑器的新基线功能板中，“最新”列的行为不同。 (10808)
* 翻译 |由于/libs/fmdita/i18n/ja.json无效，翻译作业未开始。 (10543)
* 翻译 |从翻译仪表板（人文翻译）创建的范围翻译项目中出错。 (10526)
* 翻译 |对于活动翻译项目中存在资产的整个语言文件夹，将阻止进行后处理。 (10332)
* 如果版本发生更改并保存在基线编辑器中，则会为任何资产显示多个弹出窗口。 (10399)
* 会话泄漏发生在 `com.day.cq.search.impl.builder.QueryBuilderImpl.createResourceResolver(QueryBuilderImpl.java:210)`. (10279)

### 发布

* 某些情况下无法重新生成主题。 (10635)
* Publishlistener不在信息日志中显示请求的数据，它还包含一些垃圾日志。( 10567)
* 本机PDF |在创建包含“添加到文件夹配置文件”选项的输出预设时，PDF生成失败，出现空指针异常。 (10950)
* 本机PDF |旋转表标题时出现问题。 (10555)
* 本机PDF |嵌套 `<indexterm>` 未嵌套在本机PDF导出中。 (10521)
* 本机PDF |附录中嵌套的topicref全部在临时HTML中转换为h1。 (10454)
* 对于使用FrameMaker Publishing Server 2020生成的PDF，基线发布失败。 (10551)
* 本机PDF |添加 `xref` “图像”不会在生成的PDF上呈现图像。 (11346)
* 本机PDF |图像标记可向所有图像添加display-inline属性。 (10653)
* 本机PDF |默认情况下，草稿注释会在生成的输出中隐藏。 (10560)
* 本机PDF | topichead不接受navtitle。 (10509)

---
title: 的发行说明 [!DNL AEM Guides], 2022年3月版
description: 3月版 [!DNL Adobe Experience Manager Guides] as a Cloud Service
exl-id: 885edbb5-dfe4-4bdc-bb66-0df64addb094
source-git-commit: 67ba514616a0bf4449aeda035161d1caae0c3f50
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 2%

---

# 3月版 [!DNL Adobe Experience Manager Guides] as a Cloud Service

## 升级到3月版

升级当前版本 [!DNL Adobe Experience Manager Guides] as a Cloud Service(后称为 *[!DNL AEM Guides]as a Cloud Service*)设置：
1. 查看Cloud Services的Git代码，并切换到在与要升级的环境对应的Cloud Services管道中配置的分支。
1. 更新 `<dox.version>` 属性 `/dox/dox.installer/pom.xml` 文件，以将Cloud ServicesGit代码复制到2022.3.123。
1. 提交更改并运行Cloud Services管道以升级到的3月版 [!DNL AEM Guides] as a Cloud Service。

## 兼容性矩阵

本部分列出了支持的软件应用程序的兼容性矩阵 [!DNL AEM Guides] as a Cloud Service于2022年3月版。

### FrameMaker和FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| 不兼容 | 2020更新4及更高版本 |
|  |  |


### 氧连接器

| [!DNL AEM Guides] Cloud版本 | 氧连接器窗口 | 氧连接器Mac |
| --- | --- | --- |
| 2022.3.0 | 2.4.0 | 2.4.0 |
|  |  |  |

*从2020.2开始的FMPS版本支持在AEM中创建的基线和条件。

## 新增功能和增强功能

### 新建基线仪表板

[!DNL AEM Guides] as a Cloud Service的3月版提供了集成在Web编辑器中的基线功能。 现在，您可以从Web编辑器创建基线，并使用这些基线发布或翻译不同版本的主题。

注意：对于已升级的系统，请更新 **ui_config.json** 文件夹配置文件。

使用此功能可创建基线，基线中包含特定日期和时间提供的主题的特定版本。 此外，您还获得API支持，以使用为主题版本定义的标签来创建或更新基线。

![基线管理选项卡](assets/baseline-manage.png)

您可以根据文件名或文件位置搜索文件。 您还可以过滤要在基线编辑窗口中显示的主题，并根据特定列对它们进行排序。

![基线管理选项卡](assets/baseline-filter.png)

基线创建过程的性能已得到进一步改进。 创建基线的过程是异步的，因此在创建基线时，您可以在Web编辑器中继续编辑其他文件。 有关更多详细信息，请参阅 *从Web编辑器创建和管理基线* 中。

注意：默认情况下，“映射”功能板上的“基线”选项卡处于隐藏状态。 您的管理员可以在映射功能板上启用“基线”选项卡。

### 改进了Web编辑器刷新行为

现在，在Web编辑器中执行浏览器刷新操作时，可以使用以下增强功能：

* 现在，您在Web编辑器中编辑内容时，可以获得刷新浏览器的支持。 如果在打开一个或多个具有未保存更改的文件进行编辑时点击浏览器刷新图标，则系统会提示您保存文件或取消刷新操作。

* 即使刷新浏览器，左侧面板和右侧面板的视图也会保留。

* 活动主题或DITA映射在内容编辑区域中重新打开。

### 发布增强功能

3月发布的 [!DNL AEM Guides] as a Cloud Service:

* 已为AEM网站输出的元数据遵循基线。 您还可以将基线版本的属性作为元数据进行处理。 如果未定义基线，则最新版本的属性将作为元数据进行处理。

* 的 **文件名** 和 **DITA-OT命令行参数** 已为HTML5、EPUB和自定义输出预设添加选项。 现在，您可以指定要保存输出的文件名。 您还可以指定希望DITA-OT在生成输出时处理的其他参数。

## 修复的问题

下面列出了各个区域中修复的错误：

* 无法使用Web编辑器的“创作”视图在书签中添加Frontmatter和Backmatter元素。 (7652)
* 删除主题并执行移动操作后，引用树会中断。 (8804)
* 上传资产后，查看内容时出现异常。 (3638)
* 在“Ox”(使用 **在氧气中编辑** 按钮)。 (8918)
* 的 **在存储库中找到** 选项不会在XML编辑器中查找和突出显示DITA映射。 (8796)
* 在XML编辑器中向内容添加多个属性时，筛选不会显示相应的结果。 (8795)
* 当用户ID为数字时，在文件夹配置文件中将用户添加为管理员时出错。 (8908)

## 已知问题

Adobe在 [!DNL AEM Guides] as a Cloud Service的3月版。

* 删除直接引用上的标签也会从间接引用中删除标签。

* 如果不手动刷新基线面板，则无法反映更新的基线标题。

* “版本历史记录”面板中的版本预览功能不显示所选主题的预览。

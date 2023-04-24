---
title: 发行说明 | Adobe Experience Manager指南as a Cloud Service,2022年4月版
description: 4月版Adobe Experience Manager指南as a Cloud Service
exl-id: c735ba24-a803-454b-8723-57dacf90061b
source-git-commit: 67ba514616a0bf4449aeda035161d1caae0c3f50
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 3%

---

# 4月版Adobe Experience Manager指南as a Cloud Service

## 升级到4月版

升级当前版本 [!DNL Adobe Experience Manager Guides] as a Cloud Service(后称为 *[!DNL AEM Guides]as a Cloud Service*)设置：
1. 查看Cloud Services的Git代码，并切换到在与要升级的环境对应的Cloud Services管道中配置的分支。
1. 更新 `<dox.version>` 属性 `/dox/dox.installer/pom.xml` 文件，以将Cloud ServicesGit代码复制到2022.4.133。
1. 提交更改并运行Cloud Services管道以升级到4月版的 [!DNL AEM Guides] as a Cloud Service。

## 兼容性矩阵

本部分列出了支持的软件应用程序的兼容性矩阵 [!DNL AEM Guides] as a Cloud Service于2022年4月版。

### FrameMaker和FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| 不兼容 | 2020更新4及更高版本 |
|  |  |


### 氧连接器

| AEM Guides Cloud版本 | 氧连接器窗口 | 氧连接器Mac |
| --- | --- | --- |
| 2022.4.0 | 2.5.6 | 2.5.6 |
|  |  |  |

*从2020.2开始的FMPS版本支持在AEM中创建的基线和条件。

## 新增功能和增强功能

Web编辑器中添加了许多增强功能和新功能：

### 改进了键分辨率

DITA内容键引用将一部分内容从一个主题插入到另一个主题中。 它使用键来查找内容。 需要解析与DITA主题关联的键引用。 选定的根映射具有最高的优先权来解析键引用。

![用户首选项对话框](assets/user-preferences.png)

现在，关键引用会根据根映射集按以下优先级顺序进行解析：

1. 用户首选项
1. “映射视图”面板
1. 文件夹配置文件

有关更多详细信息，请参阅 *解决键引用* 中。

### 在左侧面板中添加自定义面板

现在，您可以在Web编辑器的左侧面板中添加自定义面板。 您可以将自定义面板用于各种目的，例如提供帮助或对项目进行测试。 如果已配置自定义面板，则它也会显示在 **编辑器设置**. 您可以切换开关以显示或隐藏自定义面板。

### 能够更改DITA映射中主题的文档状态

现在，您可以轻松地在DITA映射中更改所选主题的文档状态。 您还可以从 **更多选项** 菜单。

![选定主题属性](assets/map-view-properties.png)

### 在预览模式下显示的版本信息

Web编辑器可帮助您管理您的版本。 现在，您还可以在主题的预览模式下，在主题文件选项卡的右上角查看活动主题或DITA映射的版本。

![预览版本](assets/preview-version.png)

## 修复的问题

下面列出了各个区域中修复的错误：

* 新标签不会自动反映在“添加/删除”标签下拉列表中，而是需要基线刷新。 (9249)
* 如果基线是通过标签标准创建的，则无法编辑基线标题。 (9171)
* 如果基线状态变为“失败”，则使用基线发布作业会卡在“正在等待”状态中。 (9194)
* 删除直接引用上的标签也会从间接引用中删除标签。 (9257)
* 在键入时搜索会在“存储库”视图中产生不需要的搜索请求。 (9307)
* 在选项卡的标题中使用任何关键字时出现问题。 (9318)
* 添加带有空格的标签时基线失败。 (9362)
* AEM网站输出无法正确显示术语表元素。 (8936)
* 打开 **输出** 选项卡。 (8715)
* 通过Salesforce发布手动记录类型时显示的错误消息不直观。 (8952)
* 使用条件属性设置进行验证不会立即打开，而是用户需要重新打开文件才能查看验证。 (9300)
* 使用元数据发布DITA映射后，无法删除元数据。  (9178)
* 即使在映射编辑器中打开DITA映射时，翻译面板也可见。 (9053)
* 用户定义的自定义DTD不优先于DITA-OT中嵌入的标准DITA DTD。 (9104)
* 在本机PDF功能中，非DITA和非图像文件的模板中上传失败。 (9070)
* 授权机制在某些特殊情况下执行两个查询而不是一个查询。 (9221)
* 使用自定义DTD时发布AEM站点输出失败。 (9243)
* 按引用使用脚注不会滚动到AEM网站输出中的脚注部分。 (9234)

## 已知问题

Adobe在 [!DNL AEM Guides] as a Cloud Service的4月版。

* 当使用相同名称创建了两个或多个基线，但有空格或大小写差异时，Web编辑器不会报告错误。 例如，“adobe”和“Adobe”或“Adobe”。
* 在执行频繁登录或注销或在不同身份验证类型之间切换时，氧气连接器间歇性挂起。

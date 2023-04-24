---
title: 发行说明 | Adobe Experience Manager指南as a Cloud Service,2023年3月版
description: 3月版Adobe Experience Manager指南as a Cloud Service
source-git-commit: d762cccc4a8f89eb91a1a8eb2c1410a7e0358b85
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 2%

---

# 3月版Adobe Experience Manager指南as a Cloud Service

## 升级到3月版

升级您当前的Adobe Experience Manager指南as a Cloud Service(以后称为 *AEM指南as a Cloud Service*)设置：
1. 查看Cloud Services的Git代码，并切换到在Cloud Services管道中配置的分支，该管道与您要升级的环境相对应。
2. 更新 `<dox.version>` 属性 `/dox/dox.installer/pom.xml` 文件中的“Cloud ServicesGit代码”到2023.3.242。
3. 提交更改并运行Cloud Services管道以升级到3月版AEM指南as a Cloud Service。

## 索引现有内容的步骤(仅当您使用的是9月版AEM指南之前的版本时as a Cloud Service)

执行以下步骤，为现有内容编制索引，并在映射级别使用新的查找和替换文本：

* 向服务器运行POST请求（验证正确） —  `http://<server:port>/bin/guides/map-find/indexing`.
(可选：您可以传递映射的特定路径来索引它们，默认情况下，所有映射都将编入索引 ||示例： `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* 该API将返回jobId。 要检查作业的状态，您可以向同一端点发送具有作业ID的GET请求 —  `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(例如：http://&lt;
_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* 作业完成后，上述GET请求将做出成功响应，并在任何映射失败时提及。 可以从服务器日志中确认已成功索引的映射。

## 兼容性矩阵

本部分列出了AEM指南as a Cloud Service于2023年3月版支持的软件应用程序的兼容性矩阵。

### FrameMaker和FrameMaker Publishing Server

| AEM Guides as a Cloud Release | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.03.0 | 不兼容 | 2022或更高版本 |
|  |  |  |


### 氧连接器

| AEM Guides as a Cloud Release | 氧连接器窗口 | 氧连接器Mac | 在氧气窗口中编辑 | 在Oxon Mac中编辑 |
| --- | --- | --- | --- | --- |
| 2023.03.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2.3 | 2.3 |
|  |  |  |  |


## 新增功能和增强功能

AEM指南as a Cloud Service在2023年3月版中提供了增强功能和新增功能：

### 在Web编辑器中打开并播放视频或音频文件

AEM指南现在提供了在Web编辑器中打开和播放音频或视频文件的功能。 您可以更改视频的音量或视图。 在快捷菜单中，您还可以选择 **下载**，更改 **播放速度**，或查看 **画中画**.

<img src="assets/video-web-editor.png" alt="播放视频" width="600">


## 修复的问题

下面列出了各个区域中修复的错误：

* 下载PDF过程在Web编辑器中无法正常工作。 (11496)
* JSON输出 |将属性值为 `"value in spaces and double quotes"` 会导致发布错误。 (11438)
* 音频和视频多媒体文件的插入在YouTube格式下失败，格式为 **插入多媒体** 图标。 (11320)
* 使用具有专门标题元素的模板创建映射时会出现验证错误。 (11212)
* 本机PDF |表标题中存在的脚注会导致PDF输出中相应页脚中的粗体和居中对齐文本。 (10610)
>[!NOTE]
>
>要反映本机PDF更改，请删除位于/content/dam/dita-templates的PDF文件夹，然后升级到最新内部版本。 (10610)

### 解决方法的已知问题

Adobe已在2023年3月版AEM指南中确定了以下已知问题。

* 用户无法保存或创建重复资产的版本。

**解决方法**:在对重复资产进行任何更改之前，请先从资产UI中重新处理该资产。


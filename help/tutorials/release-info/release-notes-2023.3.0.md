---
title: 发行说明 | Adobe Experience Manager Guidesas a Cloud Service，2023年3月版
description: Adobe Experience Manager Guidesas a Cloud Service3月版
exl-id: b3fe7cc8-1654-467a-ab18-6e6912855ecc
source-git-commit: 8073716bccacbe8d6a158b44d5106b083e3a5dcd
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 2%

---

# Adobe Experience Manager Guidesas a Cloud Service3月版

## 升级到3月版

as a Cloud Service升级您当前的Adobe Experience Manager Guides(以后称为 *AEM Guidesas a Cloud Service*)通过以下步骤进行设置：
1. 查看Cloud Services的Git代码，然后切换到在Cloud Services管道中配置的与要升级的环境对应的分支。
2. 更新 `<dox.version>` 中的属性 `/dox/dox.installer/pom.xml` Cloud ServicesGit代码的文件更改为2023.3.242。
3. 提交更改并运行Cloud Services管道，以升级到AEM Guides的3月版as a Cloud Service。

## 索引现有内容的步骤(仅当使用的版本早于9月份的AEM Guidesas a Cloud Service版本时)

执行以下步骤来索引现有内容并在映射级别使用新的查找和替换文本：

* 对服务器运行POST请求（使用正确的身份验证） —  `http://<server:port>/bin/guides/map-find/indexing`.
(可选：您可以传递映射的特定路径来索引它们，默认情况下，所有映射都将索引 ||示例： `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* 该API将返回jobId。 要检查作业的状态，您可以将带有作业ID的GET请求发送到同一端点 —  `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(例如：http://&lt;
_localhost：8080_>/bin/guides/map-find/indexing？jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* 作业完成后，上述GET请求将做出成功响应，并提及是否有任何映射失败。 可以从服务器日志中确认已成功编制索引的映射。

## 兼容性矩阵

本部分列出了AEM Guides 2023年3月as a Cloud Service版本支持的软件应用程序的兼容性矩阵。

### FrameMaker和FrameMaker Publishing Server

| AEM Guides as a Cloud版本 | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.03.0 | 不兼容 | 2022或更高版本 |
|  |  |  |


### 氧气连接器

| AEM Guides as a Cloud版本 | 氧气连接器窗口 | 氧气连接器Mac | 在氧气窗口中编辑 | 在氧气Mac中编辑 |
| --- | --- | --- | --- | --- |
| 2023.03.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2.3 | 2.3 |
|  |  |  |  |


## 新增功能和增强功能

AEM Guidesas a Cloud Service在2023年3月版中提供了以下增强功能和新功能：

### 在Web编辑器中打开并播放视频或音频文件

AEM Guides现在提供在Web编辑器中打开和播放音频或视频文件的功能。 您可以更改视频的音量或视图。 在快捷菜单中，您还可以选择 **下载**，更改 **回放速度**，或视图 **画中画**.

<img src="assets/video-web-editor.png" alt="播放视频" width="600">


## 修复的问题

修复了多个区域的错误如下：

* 下载PDF过程在Web编辑器中无法正常工作。 (11496)
* JSON输出 |将属性值映射为 `"value in spaces and double quotes"` 会导致发布错误。 (11438)
* 音频和视频多媒体文件的插入在YouTube格式下失败。 **插入多媒体** 图标。 (11320)
* 使用具有专门化标题元素的模板创建映射时，发生验证错误。 (11212)
* 本机PDF |表页眉中的脚注会导致PDF输出中相应页脚中的粗体和居中对齐文本。 (10610)
>[!NOTE]
>
>要反映本机PDF更改，请删除位于/content/dam/dita-templates的PDF文件夹，然后升级到最新内部版本。 (10610)

### 有变通方法的已知问题

Adobe已发现AEM Guides 2023年3月as a Cloud Service版的以下已知问题。

* 用户无法保存或创建重复资源的版本。

**解决方法**：对重复资产进行任何更改之前，请从Assets UI重新处理该资产。

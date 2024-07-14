---
title: 使用报表
description: 在 [!DNL Adobe Experience Manager Guides]中使用报告
exl-id: 755506a6-c416-4a8c-8359-8db7e63a90a4
source-git-commit: 67ba514616a0bf4449aeda035161d1caae0c3f50
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 0%

---

# 使用报表

地图仪表板中的“报表”选项卡允许您识别和解决断开的链接、引用和重复使用的内容(conref)、交叉引用或其他缺少的信息。

>[!VIDEO](https://video.tv.adobe.com/v/339039?quality=12&learn=on)

## 为练习做准备

您可以在此处下载练习的示例文件。

[练习 — 下载](assets/exercises/working-with-reports.zip)

## 上传Assets

1. 在存储库视图中，选择主文件夹中的省略号图标以打开选项菜单。

   ![省略号–9.png](images/ellipses-9.png)

1. 选择&#x200B;**[!UICONTROL 上传Assets]**。

   ![upload-assets.png](images/upload-assets.png)

1. 选择要上载到文件夹的文件，然后选择&#x200B;**上载**。

将打开DITA文件，您应该检查这些文件是否存在缺少内容、conref或交叉引用的问题。

## 创建映射

1. 选择主文件夹中的省略号图标以打开选项菜单。

   ![省略号–9.png](images/ellipses-9.png)

1. 选择&#x200B;**创建>映射**。

   ![create-map.png](images/create-map.png)

   此时将显示创建新映射对话框。

1. 在“模板”字段中，从下拉菜单中选择&#x200B;**Bookmap**（或根据您创建的内容类型选择&#x200B;**Map**），并为您的地图提供一个标题。

1. 选择&#x200B;**创建**。

这将创建您的地图，并且左边栏会自动从“存储库”视图更改为“地图”视图。

## 插入映射组件

1. 选择左边栏中的铅笔图标。
这是“编辑”图标，允许您在编辑器中打开映射。

   ![edit-map.png](images/edit-map.png)

1. 选择存储库图标，切换回存储库视图。

   ![repository-button.png](images/repository-button.png)

1. 通过将主题从存储库拖放到编辑器中的映射中，将其添加到映射中。
行指示器将显示主题将放置的位置。

1. 根据需要继续添加主题。

1. 完成后，选择&#x200B;**另存为新版本。**

   ![save-as-new-version.png](images/save-as-new-version.png)

1. 在新版本&#x200B;*的*&#x200B;注释字段中，输入描述性注释。

1. 选择&#x200B;**保存**。

## 生成AEM Site输出

1. 在存储库中，选择地图上的省略号图标以打开“选项”菜单，然后&#x200B;**打开地图仪表板。**

   ![open-map-dashboard.png](images/open-map-dashboard.png)

   “映射仪表板”将在另一个选项卡中打开。
1. 在“输出预设”选项卡中，选择&#x200B;**AEM Site**。

   ![aem-site-checkbox](images/aem-site-checkbox.png)

1. 选择&#x200B;**生成**。

1. 导航到“输出”页面，查看生成的输出的状态。
如果出现错误，“输出”选项卡可能会在“层代设置”列下显示一个橙色圆圈，而不是绿色，这表示层代已完成。

1. 选择“生成设置”列下的链接以打开生成的输出。
查看输出中缺少的内容。

## “报表”选项卡

“报告”选项卡显示主题摘要，以及一个包含主题信息和映射中问题的表。

理想情况下，在导入内容后，您始终可以在报表中查看映射。

![reports.png](images/reports.png)

“缺少的元素”列指示缺少的图像和损坏的conref的数量。 您可以选择&#x200B;**铅笔**&#x200B;图标以在编辑器中打开主题。

## 解析缺少的图像

如果文件中缺少图像，常见原因可能是内容已上传，但图像未上传。 如果是这样，请将图像上传到与文件预期的路径和文件名匹配的特定文件夹，从而解决缺少图像的问题。

1. 在&#x200B;*存储库视图*&#x200B;中，选择图像文件夹上的省略号图标以打开“选项”菜单。

   ![image-ellipsis.png](images/image-ellipsis.png)

1. 选择&#x200B;**[!UICONTROL 上传Assets]**，然后选择缺少的图像。

1. 选择&#x200B;**上传**。

丢失的图像已上传。 现在，新生成的AEM站点输出将显示这些图像，并且“报表”选项卡将不再显示任何缺少的图像错误。

## 解决中断的conref

如果在其他位置引用的内容(conref)链接到其他文件夹中的文件（例如，名为“重用”的文件），则不会返回任何内容。 并且内容未上传，必须解决错误。 例如，您必须创建一个名为“reuse”的子文件夹，然后将缺少的文件上传到“reuse”中。

### 使用[!UICONTROL Assets] UI上传资源

除了[!UICONTROL 上传Assets]选项之外，您还可以通过拖放到Assets UI中来上传资源。

1. 在“存储库视图”中，选择重用文件夹上的省略号图标以打开“选项”菜单。

   ![重用 — 省略号.png](images/reuse-ellipsis.png)

1. 选择&#x200B;**在Assets UI中查看**。

   ![assets_ui.png](images/assets_ui.png)

1. 将文件拖放到文件夹中。
文件已上传，并解决了conref错误。

所有错误现已得到解决。 “报表”页面将指示没有其他错误，生成AEM Site将导致完整输出，并且没有缺少的组件。

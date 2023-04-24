---
title: 下载文件
description: 了解如何下载文件
source-git-commit: cc0fbca257d82cc82db5b5da8d263309fd71de55
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---


# 下载文件 {#id216MC0H0BE8}

您可以下载资产，包括DITA和非DITA文件。 您可以通过多种方式下载资产，一些方法是AEM的本机方法，而其他方法则受AEM指南支持。 有关本机AEM资产下载信息，请参阅 [从Adobe Experience Manager下载资产](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/download-assets-from-aem.html) 在AEM文档中。 以下部分介绍在AEM指南中通过DITA映射控制台下载文件的机制。

## 导出DITA映射文件

将DITA映射文件放入AEM存储库后，即可下载映射文件及其依赖项。 这样，您就可以灵活地共享完整的映射文件，以便进行离线编辑、验证、审阅或仅创建备份。

执行以下步骤以下载DITA映射文件及其相关文件：

1. 在资产UI中，导航到要下载的DITA映射。

1. 单击DITA映射以在DITA映射控制台中将其打开。

1. 选择 **主题** 选项卡，查看DITA映射中可用的主题列表。

1. 在主工具栏中，单击 **下载地图**.

   此时会出现“下载映射”对话框。

   ![](images/download-map.png){width="300" align="left"}

1. 单击&#x200B;**下载**。在“下载映射”对话框中，您可以选择以下选项：

   - **使用基线**:选择此选项可获取为DITA映射创建的基线列表。 如果要根据特定基线下载映射文件及其内容，请从下拉列表中选择基线。 有关使用基线的更多详细信息，请参阅 [使用基线](generate-output-use-baseline-for-publishing.md#).
   - **扁平化文件层次结构**:选择此选项可将所有引用的主题和媒体文件保存在一个文件夹中。

   >[!NOTE]
   >
   > 您还可以在不选择任何选项的情况下下载映射文件。 在这种情况下，将下载引用主题和媒体文件的最后一个持久版本。

1. 在单击 **下载** 按钮，则映射下载请求将排入队列。 地图准备好下载后，您将收到以下通知。

   ![](images/download-map-prompt.png){width="550" align="left"}

   - 单击 **下载** 下载.zip格式的映射文件。

   - 单击 **稍后下载** 以在以后下载映射文件。 可以从AEM通知收件箱访问下载链接。 单击收件箱中生成的映射通知以下载.zip格式的映射。
   >[!NOTE]
   >
   > 默认情况下，下载的映射会在AEM通知收件箱中保留五天。

![](images/download-map-inbox.png){width="300" align="left"}

下载映射后，您可以选择映射，然后使用顶部的打开图标打开选定的报表。

**父主题：**[&#x200B;管理内容](authoring.md)


---
title: 使用基线创建和发布
description: 在中使用基线创建和发布 [!DNL Adobe Experience Manager Guides]
exl-id: 3c229c30-f2e0-4fb0-b60c-7bae60ef1a5b
source-git-commit: 67ba514616a0bf4449aeda035161d1caae0c3f50
workflow-type: tm+mt
source-wordcount: '739'
ht-degree: 1%

---

# 使用基线创建和发布

通过使用基线，您可以创建地图主题和相关参考内容的版本。 这可以基于特定的日期或时间或标签。

>[!VIDEO](https://video.tv.adobe.com/v/338993?quality=12&learn=on)

## 访问映射仪表板中的“基线”选项卡

您可以在地图功能板中访问基线。

1. 存储库视图，选择地图上的省略号图标以打开选项菜单，然后 **打开地图功能板。**

   ![省略号 — map-dashboard.png](images/ellipsis-map-dashboard.png)
“映射仪表板”将在另一个选项卡中打开。

1. 选择 **基线**.

   ![baseline-tab.png](images/baseline-tab.png)

此时将显示“基线”选项卡。

## 基于标签创建基线

1. 在基线选项卡中，选择 **创建**.

   ![create-baseline.png](images/create-baseline.png)

   此时将显示新基线的信息。 其默认名称基于其创建日期。

1. 如果需要，为您的基线提供一个新名称。

1. 在“Set the version based”（设置版本依据）标题下，为“Label”（标签）选择圆圈。
   ![set-the-version.png](images/set-the-version.png)

   >[!NOTE]
   >
   >注意： *如果标签不存在，则使用最新版本* 默认情况下，复选框处于选中状态。 如果未选择此选项，并且映射中存在没有所选标签的主题或媒体文件，则基线创建过程将失败。

1. 输入要使用的标签。

1. 选择&#x200B;**保存**。

您的基线已创建。 此时将显示一个包含所有主题及其相关信息的表。

### 使用“浏览所有主题”功能

使用“浏览所有主题”功能，可以查看主题的信息，包括版本和标签，以及指定使用的版本。 您可以通过选择 **浏览所有主题** 创建或编辑基线时。

![browse-all-topics.png](images/browse-all-topics.png)

## 根据日期和时间创建基线

您还可以创建及时作为快照的基线。

1. 确保打开了“基线”选项卡，然后选择创建。

   ![create-baseline.png](images/create-baseline.png)

1. 在“Set the version based（设置版本依据）”标题下，选择“Version On（开启版本）”的圆圈。

   ![version-on.png](images/version-on.png)

1. 选择日历图标并指定所需的日期和时间。

   ![calendar.png](images/calendar.png)

1. 如果需要，为您的基线提供一个新名称。

1. 选择&#x200B;**保存**。

您的基线已创建。 此时将显示一个包含所有主题及其相关信息的表。

### 向基线添加标签

您可能需要为所有映射内容批量分配新标签。

1. 选择要为其添加标签的基线。

1. 选择 **添加标签**.

   ![add-labels.png](images/add-labels.png)

   此时将显示“添加标签”对话框。

1. 输入要分配的标签，然后选择 **添加**.

标签已添加到所有主题。

## 使用基线生成AEM Site输出

1. 导航到“映射仪表板”中的“输出预设”选项卡。

1. 选中AEM Site复选框。

   ![aem-site-checkbox.png](images/aem-site-checkbox.png)

1. 选择&#x200B;**编辑**。

   ![edit-aem.png](images/edit-aem.png)

   此时将显示一个新页面。

1. 选中使用基线复选框，然后从下拉列表中选择要使用的基线。

   ![baseline.png](images/baseline.png)

1. 选择 **完成**.

   ![done.png](images/done.png)

1. 选择 **生成**.

   ![generate.png](images/generate.png)

   您的输出已使用基线生成。

## 查看生成的输出

1. 导航到“映射仪表板”中的“输出”选项卡。

1. 在“层代设置”列中选择文本以打开输出。
   ![aem-site-link.png](images/aem-site-link.png)

## 删除基线

1. 在基线选项卡中，选择要删除的基线。

1. 选择 **移除**.

   ![remove-baseline.png](images/remove-baseline.png)

   此时将显示“删除基线”对话框。

1. 选择 **移除**.

基线被删除。

## 复制基线

1. 在“基线”选项卡中，选择要复制的基线。

1. 选择 **复制**.

   ![复制.png](images/duplicate.png)

1. 选择&#x200B;**保存**。

   ![save.png](images/save.png)

将创建重复基线。

## 修改基线

您可以直接指定基线中使用的主题版本。

1. 在基线选项卡中，选择要修改的基线。
1. 选择&#x200B;**编辑**。

   ![edit-aem.png](images/edit-aem.png)

1. 选择 **浏览所有主题**.

   ![browse-all-topics.png](images/browse-all-topics.png)

   此时将显示一个主题及其关联信息的表。

1. 对于要修改的主题，请从版本列下的下拉列表中选择所需的版本。

   ![version-dropdown.png](images/version-dropdown.png)

1. 选择&#x200B;**保存**。

已保存您的更改。 现在，基线将使用您指定的主题版本。

## 创建自定义的AEM站点输出预设

在“输出”选项卡中，很难区分同一类型的默认输出。 通过为自定义输出预设使用唯一的用户友好名称，您可以解决此问题。

在本例中，我们将基于基线创建输出预设。

1. 导航到“映射仪表板”中的“输出预设”选项卡。

1. 选择&#x200B;**创建**。

   ![create-output-preset.png](images/create-output-preset.png)

   此时将显示一个新的输出预设页面，称为“新输出”。
1. 在设置名称字段中，输入用户友好名称。

1. 选中使用基线复选框，然后从下拉菜单中选择所需的基线。

   ![baseline.png](images/baseline.png)

1. 选择 **完成**.

已创建新的输出预设，并显示在输出预设页面上。

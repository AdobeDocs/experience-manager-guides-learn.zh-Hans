---
title: AEM指南编辑器配置
description: 为AEM指南配置编辑器
exl-id: 437d9598-4afc-431f-81bd-6762e22656b7
source-git-commit: 1c4d278a05f2612bc55ce277efb5da2e6a0fa9a9
workflow-type: tm+mt
source-wordcount: '780'
ht-degree: 0%

---

# XML编辑器配置

如果您在限制性环境中工作，则可以通过在特定文件夹配置文件中自定义编辑器配置来选择作者能够查看的功能。 应用此文件夹配置文件可以更改编辑器本身、CSS模板、可用片段和内容版本标签的外观。

文件中提供了您可以选择用于本课程的示例文件 [xmleditorconfiguration.zip](assets/xmleditorconfiguration.zip).

>[!VIDEO](https://video.tv.adobe.com/v/342762?quality=12&learn=on)

## 自定义默认编辑器UI配置

您始终可以将默认UI配置下载到本地系统，在所选的文本编辑器中对其进行更改，然后再次上传。

1. 在导航屏幕中，单击 [!UICONTROL **工具**] 图标。

   ![“工具”图标](images/reuse/tools-icon.png)

2. 选择 **指南** 中。

3. 单击 [!UICONTROL **文件夹配置文件**] 拼贴。

   ![文件夹配置文件](images/reuse/folder-profiles-tile.png)

4. 选择文件夹配置文件。

5. 单击 [!UICONTROL **XML编辑器配置**] 选项卡。

6. 单击 [!UICONTROL **下载**] 默认。

   ![下载默认](images/lesson-4/download-default.png)

您现在可以在文本编辑器中打开和修改内容。 的 _AEM指南安装和配置_ 指南包含如何删除、自定义或将函数添加到UI配置的示例。

## 上载修改后的XML编辑器UI配置

自定义UI配置后，您可以上传该配置。 请注意，示例配置文件 _ui-config-restricted-editor.json_ 提供了本课程的一组支持主题。

1. 在文件夹配置文件中，单击 [!UICONTROL **XML编辑器配置**] 选项卡。

2. 在XML编辑器UI配置下，单击 [!UICONTROL **上传**].

   ![上传](images/lesson-4/upload.png)

3. 双击用于修改的UI配置的文件，或如此处所示，提供的示例文件。

   ![示例配置文件](images/lesson-4/sample-config-file.png)

4. 单击 [!UICONTROL **保存**] 中。

您已成功上传修改后的UI配置。

## 自定义CSS模板布局

与UI配置一样，您可以下载CSS模板布局。 您可以在文本编辑器中打开该主题，并进行修改以在上传之前自定义主题的外观。

1. 在导航屏幕中，单击 [!UICONTROL **工具**] 图标。

   ![“工具”图标](images/reuse/tools-icon.png)

2. 选择 **指南** 中。

3. 单击 [!UICONTROL **文件夹配置文件**] 拼贴。

   ![文件夹配置文件](images/reuse/folder-profiles-tile.png)

4. 选择文件夹配置文件。

5. 单击 [!UICONTROL **XML编辑器配置**] 选项卡。

6. 在“CSS模板布局”下，单击 [!UICONTROL **下载**].

   ![下载CSS](images/lesson-4/download-css.png)

您现在可以在文本编辑器中修改和保存CSS内容。

## 上载修改后的CSS模板布局

自定义CSS模板布局后，您可以上传它。 请注意，示例文件 _css-layout-ONLY-draft-comment-change.css_ 提供了本课程的一组支持主题。 此文件仅包含“草稿注释更改”，而 _css-layout-draft-comment-change.css_ 是整个文件，仅供您测试或查看。

1. 在文件夹配置文件中，单击 [!UICONTROL **XML编辑器配置**] 选项卡。

2. 在“CSS模板布局”下，单击 [!UICONTROL **上传**].

   ![上传 CSS](images/lesson-4/upload-css.png)

3. 双击您自己的自定义CSS布局或此处显示的提供示例文件的文件。

   ![示例CSS文件](images/lesson-4/sample-css-file.png)

4. 单击 [!UICONTROL **保存**] 中。
您已成功上传自定义CSS模板布局。

## 编辑XML编辑器代码段

片段是可特定于产品或组的可重用内容片段。 请注意，示例代码片段随本课程的支持文件一起提供。

1. 在导航屏幕中，单击 [!UICONTROL **工具**] 图标。

   ![“工具”图标](images/reuse/tools-icon.png)

2. 选择 **指南** 中。

3. 单击 [!UICONTROL **文件夹配置文件**] 拼贴。

   ![文件夹配置文件](images/reuse/folder-profiles-tile.png)

4. 选择文件夹配置文件。

5. 单击 [!UICONTROL **XML编辑器配置**] 选项卡。

6. 在“XML Editor Snippets（XML编辑器代码片段）”下，单击 **上传**.

   ![上载片段](images/lesson-4/upload-snippets.png)

7. 选择您自己的代码片段或使用提供的示例。

   ![示例代码片段](images/lesson-4/sample-snippet.png)

8. 单击 [!UICONTROL **保存**] 中。

您已成功将新的代码片段添加到编辑器中。

## 自定义XML内容版本标签

默认情况下，作者可以创建自己选择的标签，并将它们与主题文件相关联。 这可能会导致同一标签上出现不同的变体。 为避免标签不一致，您还可以从预定义标签列表中进行选择。

1. 在导航屏幕中，单击 [!UICONTROL **工具**] 图标。

   ![“工具”图标](images/reuse/tools-icon.png)

2. 选择 **指南** 中。

3. 单击 [!UICONTROL **文件夹配置文件**] 拼贴。

   ![文件夹配置文件](images/reuse/folder-profiles-tile.png)

4. 选择文件夹配置文件。

5. 单击 [!UICONTROL **XML编辑器配置**] 选项卡。

6. 在“XML内容版本标签”下，单击 [!UICONTROL **下载**].

   ![下载标签](images/lesson-4/download-labels.png)

现在，您可以根据需要自定义标签。

## 上传XML内容版本标签

下载并修改标签后，即可上载XML内容版本标签主题。 您可以选择使用样例文件 _labels.json_，提供了本课程的一组支持主题。

1. 在文件夹配置文件中，单击 [!UICONTROL **XML编辑器配置**] 选项卡。

2. 在“XML内容版本标签”下，单击 [!UICONTROL **上传**].

   ![上传标签](images/lesson-4/upload-labels.png)

3. 双击您自己的自定义标签或此处显示的示例文件的文件。

   ![示例标签文件](images/lesson-4/sample-labels-file.png)

4. 单击 [!UICONTROL **保存**] 中。

您已成功上传自定义XML内容版本标签。

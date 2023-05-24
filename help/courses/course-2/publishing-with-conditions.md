---
title: 使用条件发布
description: 使用Adobe Experience Manager Guides发布带条件的内容
exl-id: ea94824a-884b-447f-9562-e6c629b8133b
source-git-commit: 67ba514616a0bf4449aeda035161d1caae0c3f50
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 1%

---

# 使用条件发布

条件发布允许为一个或多个受众、产品或平台编写一个内容源。 然后，可以动态发布此信息，并且输出中仅包含特定必需的内容。

>[!VIDEO](https://video.tv.adobe.com/v/339041?quality=12&learn=on)

## 为练习做准备

您可以在此处下载练习的样例文件。

[练习 — 下载](assets/exercises/publishing-with-conditions.zip)

## 使用条件属性标记内容

1. 打开要修改的主题。

1. 输入要变为有条件的文本。 例如，一个或多个段落、整个表、插图或其他内容。

   ![演示信息](images/presenting-info.png)

1. 选择要为其分配条件属性的特定内容。 例如，源中的单个段落。

   ![Template-Choice](images/template-choice.png)

1. 在右边栏中，确保显示“Properties（属性）”。

1. 为受众、产品或平台添加属性。

1. 为属性分配一个值。 内容显示更新以显示已应用条件标记。

   ![Specify-Template](images/specify-template.png)

## 预览条件内容

1. 单击 **预览**.

1. 下 **筛选器**，选择或取消选择要显示或隐藏的条件。

1. 选择或取消选择 **突出显示条件文本**.

   ![Preview-Conditional-Content](images/preview-conditional-content.png)

## 创建条件预设

条件预设是属性的集合，这些属性定义在生成输出期间要包含或排除的内容，或以其他方式标记的内容。

1. 从地图仪表板中，选择 **条件预设** 选项卡。

1. 单击&#x200B;**创建**。

1. 选择 **添加** (或 **全部添加**)。

1. 为条件命名。

1. 选择属性、标签和操作组合。

   ![Create-Condition-Preset](images/create-condition-preset.png)

1. 根据需要重复执行上述步骤。

1. 单击“**保存**”。

## 生成条件输出

将条件应用于内容后，可以将其生成为输出。 这可以使用条件预设或DITAval文件。

## 使用条件预设生成条件输出

1. 选择 **输出预设** 选项卡。

1. 选择输出预设。

1. 单击 **编辑**.

1. 下 **应用条件，使用** 选择条件预设。

   ![Generate-Contional-Output](images/generate-conditional-output.png)

1. 单击 **完成**.

1. 生成输出预设并查看内容。

## 使用DITAval文件生成条件输出

DITAval文件可用于发布条件内容。 这需要创建或上传文件，然后在发布时引用该文件。

1. 选择 **输出预设** 选项卡。

1. 选择输出预设。

1. 单击 **编辑**.

1. 在应用条件使用下，选择一个DITAval文件。

   ![Generate-Using-DITAval](images/generate-using-ditaval.png)

1. 单击 **完成**.

1. 生成输出预设并查看内容。

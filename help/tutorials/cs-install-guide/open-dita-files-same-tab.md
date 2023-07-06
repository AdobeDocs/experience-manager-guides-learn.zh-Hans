---
title: 在同一选项卡中打开DITA主题或映射文件
description: 了解如何在同一选项卡中打开DITA主题或映射文件
source-git-commit: 4f15166b1b250578f07e223b0260aacf402224be
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 0%

---


# 在同一选项卡中打开DITA主题或映射文件 {#id223HH0301J3}

在某些工作流中，当您单击主题或映射文件的链接时，它将在新选项卡中打开。 这可能会导致在浏览器中打开许多选项卡，从而影响您的工作效率。 您可以更改在新选项卡中打开主题或映射文件的这种行为，并在当前选项卡中强制打开它。

请按照以下说明进行操作： [配置覆盖](download-install-additional-config-override.md#) 创建配置文件。 在配置文件中，提供以下\(property\)详细信息以在新选项卡中打开主题或映射文件：

| PID | 属性键 | 属性值 |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinsametab` | 布尔值\(true/false\)。 <br> **默认值**： `false` |

此设置会影响以下您可以访问主题或映射文件的位置：

- 创建DITA主题\(在工作流结束时，当您单击 **打开主题** button\)

- 创建DITA映射\(在工作流结束时，当您单击 **打开映射** button\)

- DITA map控制台中的“主题”选项卡

- DITA map控制台中的“基线”选项卡

- DITA映射控制台中的“报表”选项卡


**父主题：**[&#x200B;自定义Web编辑器](conf-web-editor.md)

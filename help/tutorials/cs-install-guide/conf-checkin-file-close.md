---
title: 配置关闭时签入文件的提示
description: 了解如何配置关闭时签入文件的提示
source-git-commit: 4f15166b1b250578f07e223b0260aacf402224be
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 1%

---


# 配置关闭时签入文件的提示 {#id222HC040PE8}

当用户尝试关闭在Web编辑器中打开的文件时 **关闭** 按钮或 **关闭**&#x200B;选项菜单中的选项，如果文件具有未保存的数据或未保存的版本，则会出现一个对话框。 如果文件被锁定，则提示用户解锁文件。

请按照以下说明进行操作： [配置覆盖](download-install-additional-config-override.md#) 创建配置文件。 在配置文件中，提供以下\(property\)详细信息以配置关闭时签入文件的提示：

| PID | 属性键 | 属性值 |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.checkin` | 布尔值\( true/ false\)。<br> **默认值**： false |

启用此配置后， **解锁文件** 复选框在对话框中默认处于选中状态。

有关更多详细信息，请参阅 *文件关闭和保存方案* 部分(在使用Adobe Experience Manager Guidesas a Cloud Service指南中)。

**父主题：**[&#x200B;自定义Web编辑器](conf-web-editor.md)

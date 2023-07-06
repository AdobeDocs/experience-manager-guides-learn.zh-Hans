---
title: 配置基于UUID的链接的显示
description: 了解如何配置基于UUID的链接的显示
source-git-commit: 4f15166b1b250578f07e223b0260aacf402224be
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 1%

---


# 配置基于UUID的链接的显示 {#id2035G20M0QN}

默认情况下，当您使用Web编辑器中的插入引用或插入重用内容选项创建链接时，将使用引用内容的UUID创建链接。 此 **链接** 可以将引用内容的属性\（在“属性”面板中\）配置为显示引用内容的相对文件路径或UUID。 默认情况下，引用内容的UUID显示在“属性”面板中。

请按照以下说明进行操作： [配置覆盖](download-install-additional-config-override.md#) 创建配置文件。 在配置文件中，提供以下\（属性\）详细信息以在Web编辑器中显示引用内容的相对路径或UUID：

| PID | 属性键 | 属性值 |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uuid` | 布尔值\(true/false\)。 如果要显示链接内容的相对路径，则将此属性设置为false。 <br> **默认值**： true |

**父主题：**[&#x200B;自定义Web编辑器](conf-web-editor.md)

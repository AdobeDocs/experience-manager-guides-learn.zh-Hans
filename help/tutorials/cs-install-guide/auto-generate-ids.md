---
title: 自动生成元素ID
description: 了解如何自动生成元素ID
source-git-commit: 4f15166b1b250578f07e223b0260aacf402224be
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 1%

---


# 自动生成元素ID {#id20CIL40016I}

AEM Guides会为您创建的任何新文档生成一个文档ID。 例如，创建DITA映射时，ID如下所示 `map.ditamap_random_digits` 会分配到映射的ID。 您还可以定义自动为其生成和分配ID的元素。

AEM Guides提供了简单的配置设置，您需要在其中定义自动生成ID的元素以及ID的模式。 默认情况下，某些元素包括 `section`， `table`， `ul`， `ol`，配置为自动生成ID。 您可以向此列表中添加其他元素，以便每当在文档中插入这些元素时，AEM Guides都会根据给定的模式生成并分配ID

请按照以下说明进行操作： [配置覆盖](download-install-additional-config-override.md#) 创建配置文件。 在配置文件中，提供以下\(property\)详细信息以配置自动生成的元素ID：

| PID | 属性键 | 属性值 |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.classes` | 指定以逗号分隔的元素列表。 <br> **默认值**： `"topic, section, table, simpletable, fig, image, ul, ol"` |

要为自动生成的ID配置模式，请创建具有以下属性的配置文件：

| PID | 属性键 | 属性值 |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.pattern` | 此字段的默认值设置为 `${elementName}_${id}`. 此 `${elementName}` 值将被替换为元素的名称。 此 `${id}` 变量为元素生成序列号。 例如，如果您将段落元素指定为具有自动生成的ID，则主题或文档中的第一个段落将获得p\_1之类的ID，而下一个段落将获得p\_2等。 但是，在另一个文档中，ID生成过程将重新启动。 这意味着，在不同的文档中，可以将p\_1和p\_2等ID分配给段落元素。 **默认值**： ``${elementName}_${id}`` |

**父主题：**[&#x200B;自定义Web编辑器](conf-web-editor.md)


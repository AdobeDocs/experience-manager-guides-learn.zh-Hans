---
title: 本机PDF发布功能 |对目录条目和主题内容应用自定义样式
description: 了解如何创建样式表和为内容创建样式。
source-git-commit: 09918abbdade934468dea1c55d0ca2cd60622b35
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 0%

---


# 对目录条目和主题内容应用自定义样式

有时，您可能希望对目录条目或特定主题应用自定义样式。 这可以通过关联 `outputclass` 属性 `<topicref>` 元素。 此外，如果您要将自定义格式应用于整个主题，则还可以通过在CSS中扩展属性的样式定义来实现这一点。

让我们以您要发送以供审阅的新主题为例。 为便于识别更新的主题，您需要添加 `outputclass` 属性 `<topicref>` 元素，然后在CSS中为其定义自定义样式。

在以下示例中， *飞行历史* 已分配主题 `outputclass` 值为 `new-topic`.

<img src="./assets/new-topic-attribute-in-map.png" width="500">

的类定义 `new-topic` 在CSS中，您可以定义以下项的样式：
* 目录或mini-TOC中的主条目
* 主内容中主题的标题
* 主题的整个内容，包括标题

让我们看看如何在CSS中定义这些方案。 在的以下CSS定义中 `new-topic` 类中，文本颜色已更改。

```css
…
.new-topic {
  color: #CC5309
}
…
```

此定义控制目录中文本的颜色和主题的标题。 以下PDF输出显示了对目录条目应用的不同颜色：

<img src="./assets/pdf-output-toc-entry.jpg" width="500">

主题的标题也使用相同的颜色设置样式。

<img src="./assets/pdf-output-topic-title.jpg" width="500">

如果希望目录条目和主题标题具有不同的样式，则可以单独定义它们，如下所示：

```css
...
/*for styling TOC entry */
.new-topic {
  color: #CC3509
}

/* for styling topic's title */
.new-topic.title {
  color: #092ACC
}
...
```

最后，您还可以对主题中的整个内容应用样式。 为此，您需要添加后缀“`-content`&quot;到类名。 在以下示例中，在主题的整个内容中添加了一个更改栏：

```css
...
/* for styling the topic's content */
.new-topic-content {
  -ro-change-bar-color: #A609CC;
}
...
```

使用上述样式属性，更改栏会添加到 *飞行历史* 主题，如下所示：

<img src="./assets/pdf-output-topic-content.jpg" width="500">



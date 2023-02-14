---
title: 本机PDF发布功能 |对目录条目和主题内容应用自定义样式
description: 了解如何创建样式表和为内容创建样式。
source-git-commit: fbb81704ea8d9d2793b066fa159b405460fa1dcf
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---


# 在PDF输出中添加自定义书签

通常，DITA映射中的目录会作为最终PDF输出中的书签复制。 此目录是从DITA映射中的主题或区域标题创建的。 有时，您可能想要在PDF输出中的特定内容上添加自定义书签，以便轻松导航。 可通过添加 `outputclass` 属性，并将以下属性应用于该元素：

`bookmark-level: 3`

这里， `bookmark-level` 是属性和数字 `3` 是指示书签在书签层次结构中添加的级别的值。 在以下示例中，第一级主题“联系人”有一个表格“联系人列表”，我们在该表格中添加了 `outputclass` 值为 `custom-bookmark`.

<img src="./assets/custom-bookmark-attribute.png" width="500">

以下定义 `custom-bookmark` 类将添加到CSS文件中：

```css
…
/*Adding a custom bookmark*/
.custom-bookmark{
    bookmark-level: 2
}
…
```

在PDF输出中， *联系人列表* 表格添加在PDF书签列表的第2级，如下所示：

<img src="./assets/custom-bookmark-in-pdf-output.png" width="500">

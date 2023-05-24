---
title: 本机PDF发布功能 |在脚注中使用自定义样式
description: 了解如何在脚注中对数字应用样式。
exl-id: f1068f2f-2ace-4bdb-b5a4-46b03d4e43d6
source-git-commit: 7b48633ef2418fa7c91842a8d2c2a4177017ef58
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 0%

---

# 在脚注中使用自定义样式

脚注是放置在页面底部的注释，用于注释或引用指定文本部分的引用。

您可以设置主题内容和页面底部脚注标记中出现的脚注调用中的数字的样式。 例如，您可以在数字周围添加括号或更改其颜色。 这些样式可帮助您轻松识别文档中的脚注。

```css
...
.footnote::footnote-call { 
content: "(" counter(footnote, decimal) ")"; 
} 

.footnote::footnote-marker { 
content: "(" counter(footnote, decimal) ")"; 
} 

...
```

在给定示例中，在脚注调用和标记之前和之后添加一个括号：

* 使用中的内容属性添加前缀“（”和后缀“）” `footnote-call` 样式，该样式将在主题内容的脚注编号周围添加括号。
* 使用中的内容属性添加前缀“（”和后缀“）” `footnote-marker` 样式，该样式将在页面底部的脚注编号周围添加括号。

<img src="./assets/pdf-output-footer-numbers.png" alt="PDF输出中的页脚" width="500">

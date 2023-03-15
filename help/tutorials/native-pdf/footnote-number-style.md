---
title: 本机PDF发布功能 |在脚注中使用自定义样式
description: 了解如何对脚注中的数字应用样式。
source-git-commit: ef562c43f5b70d3fe425427108ad8277e1456f24
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 0%

---

# 在脚注中使用自定义样式

脚注是放置在页面底部的注释，用于对文本的指定部分添加评论或引用引用。

您可以设置主题内容中出现的脚注调用和页面底部显示的脚注标记中的数字样式。 例如，您可以在数字周围添加括号或更改其颜色。 这些样式可帮助您轻松识别文档中的脚注。

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

在给定示例中，在脚注调用和标记前后添加括号：

* 使用 `footnote-call` 样式，该样式将在主题内容的脚注编号周围添加方括号。
* 使用 `footnote-marker` 样式，该样式将在页面底部的脚注编号周围添加方括号。

<img src="./assets/pdf-output-footer-numbers.png" alt="PDF输出中的页脚" width="500">

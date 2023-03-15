---
title: 本机PDF发布功能 |使用自定义更改栏样式
description: 了解如何对更改栏应用样式。
source-git-commit: 79de97e667bffae8d120deee68a0a82011047cf5
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# 使用自定义更改栏样式

更改栏是一条垂直线，可直观地标识新内容或修订内容。 AEM指南允许您在主题中更改内容的左侧显示一个更改栏，以及PDF输出目录中更改的主题。

有关显示更改栏的更多详细信息，请参阅 *在已发布版本之间使用更改栏创建PDF* 设置
[发布PDF输出](../web-editor/native-pdf-web-editor.md).

## 主题中的更改内容

更改栏显示在已插入、更改或删除的主题中内容的左侧。

您可以修改以下样式以显示更改的内容，以及其中的更改栏。


>[!NOTE]
>
>这些样式是 `layout.css` 文件，并且您可以根据需要对其进行编辑。

例如，您可以在 `.inserted-block` 样式来定义插入内容在已发布PDF输出中的显示方式。


```css
...
.inserted-block { 
  color: #2ECC40; 
  display: inline; 
  -ro-comment-content: " "; 
  -ro-comment-style: underline; 
  -ro-comment-title: "Inserted"; 
  -ro-comment-date: attr(data-time); 
  -ro-comment-dateformat: "yyyy/dd/MM HH:mm:ss"; 
} 
...
```

同样，您也可以使用 `.deleted-block` 样式来定义已删除内容在已发布PDF输出中的显示方式。

```css
...
.deleted-block { 
  display: inline; 
  color: #FF6961; 
  text-decoration: line-through; 
  -ro-comment-content: " "; 
  -ro-comment-style: strikeout; 
  -ro-comment-title: "Deleted"; 
  -ro-comment-date: attr(data-time); 
  -ro-comment-dateformat: "yyyy/dd/MM HH:mm:ss"; 
} 
...
```

您可以使用 `.inserted-change-bar` 和 `.deleted-change-bar` 样式来修改更新内容左侧显示的更改栏的外观。

例如，您可以使用 `-ro-change-bar-color` 属性 `.inserted-change-bar` 样式以绿色显示插入的更改栏。 您还可以使用 `-ro-change-bar-color` 属性 `.deleted-change-bar` 样式以红色显示已删除的更改栏。

```css
...
.inserted-change-bar { 
  -ro-change-bar-color: #2ECC40; 
} 

.deleted-change-bar { 
  -ro-change-bar-color: #FF6961; 
  } 
...
```

<img src="./assets/changed-bar-content.png" alt="更改了条形主题内容" width="500">

## 目录（目录）中更改了主题

您还可以在PDF输出的目录中，在已更改主题的左侧添加更改栏。 您可以使用 `-ro-change-bar-color` 属性 `.changed-topic` 样式，以在“目录”列表中为更新主题选择的颜色中添加更改栏。

例如，您可以添加绿色的更改栏。

```css
...
.changed-topic { 
 -ro-change-bar-color: #2ECC40; 
}  
...
```


此时会针对目录中已完成某些更新的所有主题显示一个绿色更改栏。 您可以单击目录中更改的主题，并查看详细更改。

<img src="./assets/changed-bar-TOC.png" alt="更改了栏目目录" width="500">

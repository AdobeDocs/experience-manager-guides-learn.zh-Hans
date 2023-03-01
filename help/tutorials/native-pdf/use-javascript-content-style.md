---
title: 本机PDF发布功能 |使用JavaScript处理内容或样式
description: 了解如何创建样式表和为内容创建样式。
source-git-commit: 09918abbdade934468dea1c55d0ca2cd60622b35
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---


# 使用JavaScript处理内容或样式

“本机PDF发布”功能允许您运行JavaScript以在生成最终PDF之前处理应用于内容的内容或样式。 利用此功能，可完全控制最终输出的生成方式。 例如，您可能希望向PDF输出添加法律声明信息，该信息位于其他PDF中。 使用JavaScript，在为基本内容创建PDF后，但在生成最终PDF之前，您可以添加法律声明信息。\
为了支持JavaScript执行，本机PDF发布功能为您提供了以下回调函数：

* `window.pdfLayout.onBeforeCreateTOC(callback)`:此回调函数在生成目录之前执行。
* `window.pdfLayout.onBeforePagination(callback)`:此回调函数在生成目录后、在PDF中添加分页符之前执行。
* `window.pdfLayout.onAfterPagination(callback)`:此回调函数在目录后执行，并在PDF中添加分页符。

>[!NOTE]
>
>在内部，将维护这些标注函数的执行序列。 首先，执行onBeforeCreateTOC，然后执行onBeforePagination，最后执行onAfterPagination。

根据要执行的内容类型或样式修改类型，您可以选择要使用的回调函数。 例如，如果要添加内容，则建议在生成目录之前执行该操作。 同样，如果您想要更新一些样式，则可以在分页之前或分页之后完成这些更新。

在以下示例中，图标标题的位置从图像上方更改为图像下方。 为此，您需要在预设中启用JavaScript执行选项。 为此，请执行以下步骤：

1. 打开预设进行编辑。
1. 转到 **高级** 选项卡。
1. 选择 **启用JavaScript** 选项。
1. 保存预设并关闭。

接下来，使用以下代码创建一个JavaScript文件，并将其保存在模板的Resources文件夹中：

```css
...
/*
* DITA only allows the figure title to be placed above images 
* This JavaScript code is used to move the figure title below the image
* */
window.addEventListener('DOMContentLoaded', function () {
    window.pdfLayout.onBeforeCreateTOC(function() {
        var titleNodes = document.querySelectorAll('.fig > .title')
        for (var i = 0; i < titleNodes.length; i++) {
            var titleNode = titleNodes[i]
            var figNode = titleNode.parentNode
            var imageNode = figNode.querySelector('.image')
            if(imageNode && imageNode.parentNode !== figNode) {
              imageNode = imageNode.parentNode
            }
            if (figNode && imageNode && imageNode.parentNode === figNode) {
                figNode.insertBefore(imageNode, titleNode)
            }
        }
    })
});
...
```

>[!NOTE]
>
>的 `window.addEventListener('DOMContentLoaded', function ()` 函数之前，必须先调用该函数。

接下来，必须从用于生成PDF输出的模板文件中调用此脚本。 例如，我们将在目录模板中添加它。 确保 `<script>` 标记在预定义的 `<div>` 标记内部 `<body>` 标记。 如果将其添加到 `<head>` 标记或在 `<body>` 标记时，脚本将不会执行。

<img src="./assets/js-added-resources-template.png" width="500">

使用此代码生成的输出，模板会在图像下方显示图标：

<img src="./assets/fig-title-below-image.png" width="500">
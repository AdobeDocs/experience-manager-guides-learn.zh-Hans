---
title: 将自定义样式添加到参考线编辑器
description: 了解如何添加自定义样式以更改指南向导的外观。
source-git-commit: 9e7d5bb4c8f6c6ebe21bfcebdd7d2e13971b8df2
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 将自定义样式添加到参考线编辑器

在本文中，我们将了解如何添加自定义样式以更改Webeditor默认外观。

这将涉及以下步骤：
- 通过文件夹配置文件XML编辑器配置添加自定义样式
- 在Weditor中选择相应的文件夹配置文件并测试更改


## 以示例实施

让我们通过一个示例来了解这一点，我们希望在该示例中，将简短描述和标题显示为单独的块，并在编辑器中对某些样式方面进行说明。

![使用自定义样式预览编辑器](../../../assets/authoring/webeditor-customstyles-preview.png)


## 实施此


### 将自定义CSS添加到文件夹配置文件

使用文件夹配置文件检查 *css_layout.css* 在“XML编辑器配置”选项卡下，添加具有自定义样式的CSS

[使用此链接可了解有关文件夹配置文件和配置CSS模板布局的更多信息](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/videos/advanced-user-guide/editor-configuration.html?lang=en#customize-the-css-template-layout)

使用以下内容在您的Webeditor中设置上述样式：
- 使用 [css_layout.css](../../../assets/authoring/webeditor-customstyles-css_layout.css) 并将其上传到您选择的文件夹配置文件
- 安装附加的包 [webeditor-styles-resources.zip](../../../assets/authoring/webeditor-styles-resources.zip) 使用AEM包管理器安装上述CSS文件中使用的资源

```
This will install the resources at path "/content/dam/resources" which will include sub-folders "fonts" and "images"
```


### 测试

- 打开Web编辑器
- 从用户首选项中，选择您在其中添加自定义样式的文件夹配置文件。 如果将其添加到全局配置文件，则您可能已经在使用了该配置文件。
- 打开一个主题时，您会注意到编辑区域应具有自定义UI

```
Please note this is compatible to AEM Guides version 4.2 and AEM Guides cloud version 2303 (March)
```


## 引用

您还可能有兴趣参加有关以下内容所涵盖的浏览器配置和自定义的专家会议 [韦贝迪托专家会议](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/knowledge-base/expert-session/webbased-authoring-jan2023.html?lang=en)
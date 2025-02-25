---
title: AEM Guides编辑器配置
description: 为新的AEM Guides编辑器自定义JSON配置和转换UI配置。
source-git-commit: ec6f5685d690e53e5c6eb29d6b61436833f62c68
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 0%

---

# 概述

从旧UI迁移到新AEM Guides UI时，**ui_config**&#x200B;的更新必须转换为更灵活和模块化的UI配置。 此框架有助于将更改无缝地纳入&#x200B;**editor_toolbar**&#x200B;和[其他工具栏](/help/courses/course-3/conver-ui-config.md#editing-json-for-different-screens)。 该过程还支持修改应用程序中的其他视图和小部件。


## 为不同屏幕编辑JSON

可以将JSON文件添加到各种屏幕和小组件的“XML编辑器UI配置”部分。 下面是广泛使用的构件及其ID列表：

1. [editor_toolbar](assets/toolbars/editor_toolbar.json)： Webeditor工具栏包含文件和内容操作。
1. [editor_tab_bar](assets/toolbars/editor_tab_bar.json)： webeditor中打开文件的选项卡式视图，具有可以对打开的文件执行的操作。
1. [file_mode_switcher](assets/toolbars/file_mode_switcher.json)：它有助于在webeditor中已打开文件的不同可用模式（创作、源、预览）之间进行切换。

   ![editor_toolbar](images/reuse/editor_toolbar.png)

1. [map_console_navigation_bar](assets/toolbars/map_console_navigation_bar.json)：这是在地图控制台中打开的地图的信息栏。 它允许更改映射并提供对设置的访问权限。
1. [map_console_action_bar](assets/toolbars/map_console_action_bar.json)：这是映射控制台项目的操作栏，例如“输出预设”、“基线”、“翻译”和“报表”，它们提供了相关信息以及各自的操作按钮。

   ![map_console](images/reuse/map_console.png)

1. [home_navigation_bar](assets/toolbars/home_navigation_bar.json)： Guides主页标题栏，其中欢迎消息与选定的文件夹配置文件一起显示。

   ![home_navigation_bar](images/reuse/home_navigation_bar.png)

<br>

## 每个JSON的一般结构

每个JSON遵循一致结构：

1. **id**：指定要自定义组件的小组件。
1. **targetEditor**：使用编辑器和模式属性定义何时显示或隐藏按钮：

   当前系统中有这些&#x200B;**编辑器**&#x200B;和&#x200B;**模式**。

   **编辑器**： ditamap， bookmap， subjectScheme， xml， css，翻译，预设， pdf_preset

   **模式**：作者，源，预览，目录，拆分

   （注意：目录模式适用于布局视图。）

1. **target**：指定将添加新组件的位置。 它使用键值对或索引进行唯一标识。 视图状态包括：

   * **附加**：在末尾添加。

   * **前置词**：在开头添加。

   * **替换**：替换现有组件。

示例JSON结构：

```json
{
  "id" : "editor_toolbar",
  "view": {
    "items": [
      {
        ...,
        "targetEditor": {
          "mode": [
            "preview"
          ],
          "editor": [
            "xml"
          ]
        },
        "target": {
          "key": "label",
          "value": "Table",
          "viewState": "prepend"
        },
        ...
      },
    ]
  }
}
```

<br>

## 示例

下面是如何在编辑器工具栏中添加、删除或替换按钮的示例。

### 添加按钮

添加新按钮&#x200B;**在** editor_toolbar **中插入自定义表**&#x200B;以添加仅在预览模式下可见的简单表。

```json
{
  "id": "editor_toolbar",
  "view": {
    "items": [
      {
        "icon": "table",
        "title": "Insert Custom Table",
        "on-click": {
          "name": "$$AUTHOR_INSERT_ELEMENT",
          "args": [
            "simpletable",
            "table",
            "choicetable"
          ]
        },
        "key": "$$AUTHOR_INSERT_ELEMENT",
        "targetEditor": {
          "mode": [
            "preview"
          ],
        },
        "target": {
          "key": "label",
          "value": "Table",
          "viewState": "prepend"
        }
      }
    ]
  }
}
```

![插入自定义表](images/reuse/insert-custom-table.png)

### 删除按钮

从工具栏中删除按钮。 在此，我们从编辑器工具栏中删除了添加图像按钮。

```json
{
  "id": "editor_toolbar",
  "view": {
    "items": [
      {
        "hide": true,
        "target": {
          "key": "label",
          "value": "Image",
          "viewState": "replace"
        }
      }
    ]
  }
}
```

### 替换按钮

将工具栏中的&#x200B;**多媒体**&#x200B;按钮替换为&#x200B;**Youtube**&#x200B;链接插入按钮，该按钮仅在创作模式下可见。

```json
{
  "id": "editor_toolbar",
  "view": {
    "items": [
      {
        "icon": "s2youtube",
        "title": "Youtube",
        "on-click": {
          "name": "$$AUTHOR_INSERT_ELEMENT",
          "args": "<object data='http://youtube.com'></object>"
        },
        "targetEditor": {
          "mode": [
            "author"
          ]
        },
        "target": {
          "key": "elementId",
          "value": "toolbar-multimedia",
          "viewState": "replace"
        }
      }
    ]
  }
}
```

![Youtube按钮](images/reuse/youtube-button.png)

<br>

## 如何上传自定义JSON

1. 在&#x200B;**XML编辑器配置**&#x200B;选项卡上，单击顶部栏中的&#x200B;**编辑**。
1. 现在，在&#x200B;**XML编辑器UI配置**&#x200B;子部分中，您将能够看到&#x200B;**上载**&#x200B;按钮。

   ![上载按钮](images/reuse/ui-config-upload.png){width="400" height="150"}

1. 您可以单击并上传修改后的json。 （要上传的json应与自定义小组件ID同名）
1. 上传后，在顶部栏中点击&#x200B;**Save**。

   对于每个上传的文件，您还可以&#x200B;**删除**&#x200B;从UI中删除其json自定义项，或者&#x200B;**下载**&#x200B;以再次查看或修改它。

   ![下载按钮](images/reuse/download-delete-json.png){width="400" height="150"}

<br>


## 如何上传自定义的CSS

您还可以添加css以自定义已添加自定义按钮或UI上已存在构件或按钮的外观。

对于新添加的自定义按钮，请将&#x200B;**extraclass**添加到JSON中的自定义按钮或组件。
对于旧类，可以检查元素并修改现有类。

```json
{
  "icon": "table",
  "title": "Insert Custom Table",
  "extraclass": "custom-css",
  "key": "$$AUTHOR_INSERT_ELEMENT",
  "targetEditor": {
    "mode": [
      "preview"
    ],
  },
  "target": {
    "key": "label",
    "value": "Table",
    "viewState": "prepend"
  }
}
```

1. 在&#x200B;**XML编辑器配置**&#x200B;选项卡上，单击顶部栏中的&#x200B;**编辑**。
1. 现在，在&#x200B;**XML编辑器页面布局**&#x200B;子部分中，您将能够看到&#x200B;**上传**&#x200B;按钮。

   ![上载按钮](images/reuse/page-layout-upload.png){width="400" height="150"}

1. 您可以单击并上传修改的css。 （仅支持css文件）
1. 上传后，在顶部栏中点击&#x200B;**Save**。

   对于每个上载的文件，您还可以&#x200B;**删除**&#x200B;用于从UI中删除其自定义项的css，或者&#x200B;**下载**&#x200B;用于再次查看或修改它。

   ![下载按钮](images/reuse/download-delete-css.png){width="400" height="150"}


<br>

### 自定义按钮css的示例

在此处，我们将添加一个新按钮&#x200B;**在** editor_toolbar **中插入自定义表**，以添加仅在预览模式下可见的简单表并对其应用自定义css。
此css可修改按钮的背景及其标题的字体大小。

![CSS示例](images/reuse/css-customization.png)


```css
#editor_toolbar {
  .custom-css {
    background-color: burlywood;
    font-size: 2rem;  
  }
}
```

```json
{
  "id": "editor_toolbar",
  "view": {
    "items": [
      {
        "icon": "table",
        "title": "Insert Custom Table",
        "extraclass": "custom-css",
        ...
      }
    ]
  }
}
```

<br>

## 将ui配置转换为模块化Jsons的步骤

1. 在“导航”屏幕中，单击&#x200B;[!UICONTROL **工具**]&#x200B;图标。

   ![工具图标](images/reuse/tools.png)

1. 在左侧面板上选择&#x200B;**参考线**。

1. 单击&#x200B;[!UICONTROL **文件夹配置文件**]&#x200B;拼贴。

   ![文件夹配置文件](images/reuse/folder-profiles-tile.png)

1. 选择文件夹配置文件。

1. 单击&#x200B;[!UICONTROL **XML编辑器配置**]&#x200B;选项卡。

1. 您可以单击&#x200B;**将用户界面配置转换为JSON**&#x200B;按钮。 这将生成&#x200B;**editor_toolbar**&#x200B;和&#x200B;**map_console_action_bar** json，其中包含在&#x200B;**ui_config**&#x200B;中完成的更改。

   ![将UI配置转换为JSON](images/reuse/convert-ui-config-json.png)

1. 您可以检查[编辑器工具栏](assets/editor_toolbar.json)和[映射控制台操作栏](assets/map_console_action_bar.json)的示例生成的json


>[!NOTE]
>
>对&#x200B;**toolbar**&#x200B;和&#x200B;**topbar**&#x200B;节所做的更改已添加到&#x200B;**editor_toolbar** json中，这些更改可在编辑器页面上看到。 对&#x200B;**ui_config**&#x200B;中与“预设”或“翻译”相关的按钮所做的更改已添加到&#x200B;**map_console_action_bar** json，可在映射控制台页面上看到该内容。

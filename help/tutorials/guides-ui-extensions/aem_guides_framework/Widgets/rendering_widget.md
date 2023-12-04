---
sidebar_position: 2
source-git-commit: 42052b37724f97e34ab007db4cc3d9f9524ad3a2
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 0%

---


# 渲染构件

我们可以通过引用小组件来呈现它，它使用 `id`

渲染构件 `widget_languages` 在应用程序中的任意位置，我们可以使用简单语法：

```json
{
    "component": "widget",
    "id": "widget_languages"
}
```

小组件也可用于呈现复杂的项目，例如，我想呈现每个文件的参与者列表。
在这里，构件可以构造为：

```js title="fileContributorsWidget.js"
const widgetJSON =  {
    component: "div", 
    id: "file_contributors", 
    items: [ // adding components to the widget
        {
            component: "div",
            items: [
                {
                    component: "icon",
                    icon: "file"
                },
                {
                    component: "label",
                    label: "@fileName"
                }
            ]
        },
        {
            component: "list",
            data: "@contributors",
            itemConfig: {
                component: "label"
            }
        }
    ]
},
```

现在，为了呈现每个文件的参与者列表，我们将该列表编写为：

```js title="fileContributorsList.js"
const listJSON = {
    component: "list"
    data: "@files"
    itemConfig: {
        component: "widget",
        id: "file_contributors"
    }
}
```

此处 `@files` 是包含字段的文件对象列表

```typescript
- fileName: string
- contributors: Array<String>
```
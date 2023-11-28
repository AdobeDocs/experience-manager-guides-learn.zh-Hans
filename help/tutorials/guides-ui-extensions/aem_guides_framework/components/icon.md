---
sidebar_position: 4
source-git-commit: 0f20681fa4de859053c8d2baae0e53f347ce5859
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 2%

---


# 图标

要显示图标，我们使用组件“图标”。
JUI中的文本区域组件表示html `<icon/>`.

图标位于 [Adobe频谱图标](https://spectrum.adobe.com/page/icons/) 与我们的应用程序兼容。

```js title="icon.js"
const iconJSON =  {
    "component": "icon", //tells the component name
    "icon": "info", // name of the icon to be used
    "size": "S", // size of the icon
    "title": "Information" // tooltip corresponding to the icon.
},
```

图标也可以添加到按钮中。

呈现的图标将如下所示：

![图标](./imgs/info_icon.png "图标")

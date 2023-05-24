---
title: 配置关闭时另存为新版本的提示
description: 了解如何配置关闭时另存为新版本的提示
source-git-commit: 801c306fa120e7889d4b9428fd5bee2849bf1956
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---


# 配置关闭时另存为新版本的提示 {#id222HBI00XXA}

当用户尝试关闭在Web编辑器中打开的文件时 **关闭** 按钮或 **关闭** 选项菜单中的选项，如果文件具有未保存的数据或未保存的版本，则会出现一个对话框。 如果未保存该版本，则提示用户将文件另存为新版本。

此 **另存为新版本** 默认情况下未启用此复选框，您需要从configMgr启用此复选框。 执行以下步骤以在Web编辑器中默认启用此选项：

1. 打开“Adobe Experience Manager Web控制台配置”页面。

   用于访问配置页面的默认URL是：

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. 搜索并单击 **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** 捆绑。

1. 选择 **关闭时询问新版本** 选项。

1. 单击“**保存**”。


如果选择该选项， **另存为新版本** 复选框在对话框中默认处于选中状态。

有关更多详细信息，请参阅 *文件关闭和保存方案* 部分(在使用Adobe Experience Manager Guidesas a Cloud Service指南中)。

**父主题：**[&#x200B;自定义Web编辑器](conf-web-editor.md)


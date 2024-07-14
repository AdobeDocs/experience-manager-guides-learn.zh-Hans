---
title: 键
description: 利用键，可在AEM Guides中使用DITA时将变量信息包含到
exl-id: cb64e094-fe6d-4a5e-8f0e-25ae58aaa2c6
source-git-commit: 67ba514616a0bf4449aeda035161d1caae0c3f50
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---

# 键

不同的材料集可能包含类似的信息，需要在特定位置进行定制。 键允许您在使用DITA时包含变量信息。

您可以选择用于本课程的示例文件在文件[keys.zip](assets/keys.zip)中提供。

>[!VIDEO](https://video.tv.adobe.com/v/342756?quality=12&learn=on)

## 启用键

1. 上传提供的示例文件集。

   a.加载压缩文件。

   b.刷新AEM环境。

   c.选择要提取的文件。

   ![选择Zip](images/lesson-9/select-zip.png)

   d.单击顶部工具栏中的&#x200B;[!UICONTROL **提取存档**]。

   ![工具栏](images/lesson-9/extract-archive.png)

   e.在对话框中，选择要提取的文件的特定位置，例如名为“密钥”的文件夹。

   f.单击&#x200B;[!UICONTROL **下一步**]。

   g.跳过任何冲突，因为以前从未上传过的内容不存在这些冲突。

   h.选择屏幕右上方的&#x200B;[!UICONTROL **提取**]。

1. 提取完成后，单击&#x200B;[!UICONTROL **转到目标文件夹**]。

   ![确认](images/lesson-9/go-to-target.png)

## 将键解析为引用的值

要正确使用密钥，用户首选项必须将特定映射引用为根映射。 此映射内部是键的集合，这些键在主题组中分组在一起。 打开映射和主题将键解析为此映射引用的值。

1. 指定根映射。

   a.在“按键”屏幕中，打开地图。

   b.配置用户首选项。

   c.单击顶部工具栏上的&#x200B;[!UICONTROL **用户首选项**]&#x200B;图标。

   ![顶部工具栏](images/lesson-9/author-view.png)

   d.单击键图标以指定将用于解析键的&#x200B;**根映射**。

   e.选中任何所需的Assets对应的复选框。

   ![Assets下拉列表](images/lesson-9/select-assets.png)

   f.单击&#x200B;[!UICONTROL **选择**]。

   g. **保存**&#x200B;用户首选项。

1. 导航到&#x200B;**映射视图**。

1. 打开指定的映射。

键已解析。

## 手动添加新键盘

1. 使用指定的根映射打开映射。

1. 选择一个键。

   ![键下拉列表](images/lesson-9/hybrid-key.png)

1. 插入新键盘。

   a.在地图中的有效位置单击。

   b.选择顶部工具栏上的&#x200B;**Keydef**&#x200B;图标。

   ![Keydef工具栏](images/lesson-9/key-icon.png)

   c.在“插入Keydef”对话框中，为键输入对您创建的定义有意义的唯一值。

   d.单击&#x200B;[!UICONTROL **插入**]。

1. 在keydef中添加topicmeta。

   a.单击顶部工具栏上的&#x200B;[!UICONTROL **插入元素**]&#x200B;图标。

   ![Keydef工具栏](images/lesson-9/add-icon.png)

   b.在插入元素对话框中，搜索并选择“topicmeta”。

1. 在topicmeta中添加关键字。

   a.单击顶部工具栏上的&#x200B;[!UICONTROL **插入元素**]&#x200B;图标。

   ![Keydef工具栏](images/lesson-9/add-icon.png)

   b.在“插入元素”对话框中，搜索并选择“关键字”。

1. 在topicmeta中添加关键字。

   a.单击顶部工具栏上的&#x200B;[!UICONTROL **插入元素**]&#x200B;图标。

   ![Keydef工具栏](images/lesson-9/add-icon.png)

   b.在&#x200B;**插入元素**&#x200B;对话框中，搜索并选择“关键字”

1. 在关键字中键入keydef的值。

在地图中，您的keydef现在应如下所示：

![Keydef已完成](images/lesson-9/keydef.png)

## 将keydef配置为代码片段

片段是小型内容片段，可在文档项目的各种主题中重复使用。 您可以配置单个密钥作为代码片段，而不是手动生成每个密钥文件。

1. 在映射中选择keydef元素。

1. 在上下文菜单中，单击&#x200B;[!UICONTROL **创建代码片段**]。

1. 在新代码片段对话框中，添加标题和描述。
您可能还希望从内容中删除现有的键或关键字定义。

1. 单击&#x200B;[!UICONTROL **创建**]。

1. 在左侧面板上，选择&#x200B;**代码片段**。

1. 将您刚刚创建的代码片段从“代码片段”面板拖放到地图中。

1. 根据需要使用内容属性更新keydef。
保存并刷新后，此组密钥将可供已定义包含相同根映射的映射的任何用户使用。

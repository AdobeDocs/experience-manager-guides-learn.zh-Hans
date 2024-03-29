---
title: 交叉引用和链接
description: 在AEM Guides中创建交叉引用和链接
exl-id: bee7d50f-cbdd-4ac8-b15b-101febc4ae80
source-git-commit: 67ba514616a0bf4449aeda035161d1caae0c3f50
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 0%

---

# 交叉引用和链接

XML编辑器和DITA为主题之间的链接提供了一种强大的方式。 有效管理您的内容引用非常重要，其中包括使用唯一的ID值。

文件中提供了您可选择在本课程中使用的示例文件
[crossreferencesandlinks.zip](assets/crossreferencesandlinks.zip)

>[!VIDEO](https://video.tv.adobe.com/v/342764?quality=12&learn=on)

## 创建外部主题的交叉引用

可以通过将主题从存储库拖放到打开的文件中来创建外部交叉引用。 但是，为了避免交叉引用失效，必须首先将ID定义为与父元素相关的值。 这是创建交叉引用并确保正确分配ID的一种简单方法。

1. 打开要插入外部交叉引用的文件。

1. 为要引用的元素分配一个ID。

   a.单击元素内部。

   b.在“内容属性”面板上，选择 **ID** 属性下拉列表中。

   c.在“值”字段中键入逻辑名称。

   d.在中查看元素及其值 **大纲视图** 如果需要。

1. **保存** 确保存储库具有更新ID的主题。

1. 单击 [!UICONTROL **引用**] 图标。

   ![工具栏](images/lesson-7/references-icon.png)

1. 从 **内容引用** 选项卡中，选择要作为交叉引用插入的ID和元素配对。

1. 单击 [!UICONTROL **选择**].

交叉引用已添加到主题中。

## 链接到网站

您可以在任何主题中插入指向网站的链接。 有关更多信息，请参阅有关链接到网站的AEM Guides课程1视频。


## 查看断开的链接

某些修改可能会导致交叉引用断开。 这些操作包括删除主题、重新组织包含交叉引用的截面，或在插入交叉引用后更改ID。 请注意，一个示例主题 _crossreferencesandlinks.zip_ 随本课程一起提供，该课程将导致对内部内容的多个项目符号交叉引用中断。

1. 导航到 **大纲视图** ，位于左侧面板。

1. 单击 [!UICONTROL **筛选条件**] 图标。

1. 选择 **断开的链接**.

   ![过滤器下拉列表](images/lesson-7/broken-links.png)

断开的链接显示为可单击对象。 您可以在主题中以红色文本标识它们。

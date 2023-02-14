---
title: 交叉引用和链接
description: 在AEM指南中创建交叉引用和链接
exl-id: bee7d50f-cbdd-4ac8-b15b-101febc4ae80
source-git-commit: 1c4d278a05f2612bc55ce277efb5da2e6a0fa9a9
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 0%

---

# 交叉引用和链接

XML编辑器和DITA为主题之间的链接提供了一种强大的方式。 有效管理内容引用，包括使用唯一ID值，这一点非常重要。

文件中提供了您可以选择用于本课程的示例文件
[crossreferencesandlinks.zip](assets/crossreferencesandlinks.zip)

>[!VIDEO](https://video.tv.adobe.com/v/342764?quality=12&learn=on)

## 创建对外部主题的交叉引用

可以通过将存储库中的主题拖放到打开的文件中来创建外部交叉引用。 但是，为避免交叉引用损坏，必须首先将ID定义为与父元素相关的值。 这是创建交叉引用的一种简单方法，同时可确保正确分配ID。

1. 打开要在其中插入外部交叉引用的文件。

2. 为要引用的元素分配ID。

   a.单击元素内部。

   b.在“内容属性”面板上，选择 **ID** 从属性下拉列表中。

   c.在“值”字段中键入逻辑名称。

   d.在中查看元素及其值 **大纲视图** 。

3. **保存** 确保存储库具有更新的ID的主题。

4. 单击 [!UICONTROL **参考**] 图标。

   ![工具栏](images/lesson-7/references-icon.png)

5. 从 **内容参考** 选项卡，选择要作为交叉引用插入的ID和元素配对。

6. 单击 [!UICONTROL **选择**].

交叉引用已添加到主题中。

## 链接到网站

您可以在任何主题中插入指向网站的链接。 有关更多信息，请参阅关于链接到网站的AEM指南课程1视频。


## 查看断开的链接

某些修改可能会导致交叉引用断开。 这些操作包括删除主题、重新组织包含交叉引用的部分，或在插入交叉引用后更改ID。 请注意示例主题 _crossreferencesandlinks.zip_ 本课程中提供了一些项目符号交叉引用，这些引用会中断对内部内容的多个引用。

1. 导航到 **大纲视图** 中。

2. 单击 [!UICONTROL **过滤器**] 图标。

3. 选择 **断开的链接**.

   ![过滤器下拉列表](images/lesson-7/broken-links.png)

断开的链接显示为可单击对象。 您可以在主题中以红色文本标识它们。

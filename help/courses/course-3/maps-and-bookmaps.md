---
title: 映射和书图
description: 在AEM Guides中创建和编辑映射和书图
exl-id: 9c717e4b-017b-4f2b-b93e-f2c0e7525c55
source-git-commit: 67ba514616a0bf4449aeda035161d1caae0c3f50
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 1%

---

# 映射和书图

Adobe Experience Manager Guides的映射编辑器允许您创建和编辑映射文件。 使用“映射编辑器”，可以编辑两种类型的文件 — DITA映射和bookmap。 在我们的目的中，将这些概念视为基本上可互换的概念。
地图编辑器提供两种模式 — 基本地图编辑器和高级地图编辑器。

>[!VIDEO](https://video.tv.adobe.com/v/342766?quality=12&learn=on)

## 创建映射

AEM Guides提供两个现成的映射模板 — DITA映射和书图。 您还可以创建自己的映射模板并与作者共享这些模板以创建映射文件。

执行以下步骤以创建映射文件。

1. 在Assets UI中，导航到要创建映射文件的位置。

1. 单击&#x200B;[!UICONTROL **创建> DITA映射**]。

1. 在Blueprint页面上，选择要使用的映射模板类型，然后单击&#x200B;[!UICONTROL **下一步**]。

1. 在“属性”页面上，输入映射的&#x200B;**标题**&#x200B;和&#x200B;**名称**。

1. 单击&#x200B;[!UICONTROL **创建**]。

## 使用高级映射编辑器打开映射

1. 在&#x200B;**Assets UI**&#x200B;中，选择要编辑的映射。

1. 单击&#x200B;[!UICONTROL **编辑主题**]。

   ![编辑主题UI](images/lesson-14/edit-topics.png)

或者

1. 将鼠标悬停在地图图标上。

1. 从&#x200B;**操作**&#x200B;菜单中选择&#x200B;**编辑主题**。


## 将内容添加到地图或书图

1. 导航到&#x200B;**存储库视图**。

1. 将内容从“存储库视图”拖放到地图或书图中的有效位置。

或者

1. 在地图或书签映射中的有效位置单击。

1. 单击相应的&#x200B;[!UICONTROL **工具栏图标**]&#x200B;以添加章节、主题或主题引用。

   ![工具栏图标](images/lesson-14/toolbar-icons.png)

1. 选择要添加的一个或多个Assets。

1. 单击&#x200B;[!UICONTROL **选择**]。

### 提升或降级映射中的元素

使用&#x200B;**工具栏箭头**&#x200B;在地图或书签映射中提升或降级章节和主题引用。

1. 在图中选择元素。

1. 单击&#x200B;[!UICONTROL **向左箭头**]&#x200B;可将topicref提升为章节，单击&#x200B;[!UICONTROL **向右箭头**]&#x200B;可将topicref降级。

   ![箭头图标](images/lesson-14/toolbar-arrows.png)

1. 如果需要，请保存映射并进行版本控制。

或者

1. 拖放元素以重新组织它们。

## 将元数据添加到映射

1. 从&#x200B;**映射工具栏**&#x200B;插入主题组。

   ![添加属性](images/lesson-14/add-topicgroup.png)

1. 单击&#x200B;[!UICONTROL **加号图标**]&#x200B;插入元素。

1. 选择要插入的元素。

   ![插入元数据](images/lesson-14/insert-metadata.png)

1. 单击&#x200B;[!UICONTROL **关闭**]。

## 向映射添加关系

可以在构造映射后添加关系。

1. 在要插入相关表的映射中单击。

1. 使用&#x200B;**工具栏图标**&#x200B;向映射添加相关表。

   ![可读图标](images/lesson-14/reltable-icon.png)

1. 配置对话框。

1. 单击&#x200B;[!UICONTROL **插入**]。

1. 将所需主题从&#x200B;**存储库**&#x200B;拖放到关联表中。

1. 使用标准键盘快捷键将映射中的所需元素复制并粘贴到表中。

## 将属性分配给映射中的topicref

1. 突出显示地图中的topicref或嵌套的topicref集合。

1. 在“内容属性”面板中的“其他属性”下，选择&#x200B;**属性**&#x200B;及其&#x200B;**值。**

   ![添加属性](images/lesson-14/add-attribute.png)

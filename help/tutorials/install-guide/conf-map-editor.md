---
title: 将高级映射编辑器设置为默认值
description: 了解如何将高级映射编辑器设置为默认值
source-git-commit: 801c306fa120e7889d4b9428fd5bee2849bf1956
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%

---


# 将高级映射编辑器设置为默认值 {#id181AI0003PN}

AEM Guides附带一个基本映射编辑器和一个高级映射编辑器。 基本映射编辑器为您提供了创建映射文件所需的所有功能。 高级映射编辑器功能更丰富，并且集成在Web编辑器中。 高级映射编辑器允许作者使用易于使用的界面创建和编辑DITA映射文件。

默认情况下，每当创建新映射文件时，都会在基本映射编辑器中打开该文件。 通过启用默认打开“高级映射编辑器”的设置，可以更改此行为。

执行以下步骤，使高级映射编辑器成为映射文件的默认编辑器：

1. 打开“Adobe Experience Manager Web控制台配置”页面。

   用于访问配置页面的默认URL是：

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. 搜索并单击 **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** 捆绑。

1. 选择 **隐藏基本映射编辑器** 选项。

   选中此选项后，用户将看不到用户界面中的任何位置的基本映射编辑器链接。 默认情况下，映射文件将在高级映射编辑器中打开。



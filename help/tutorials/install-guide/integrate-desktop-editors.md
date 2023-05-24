---
title: 集成基于桌面的XML编辑器
description: 了解如何集成基于桌面的XML编辑器
source-git-commit: 5ac066bb8db32944abd046f64da11eeb1bdbe467
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---


# 集成基于桌面的XML编辑器 {#id181GB01G0HS}

市场上有许多XML编辑器，而且您已经可以使用了一个。 Adobe FrameMaker是AEM连接器中最强大的XML编辑器之一。 使用FrameMaker中的AEM连接器，您可以轻松地与AEM存储库连接、签出和签入文件，以及直接在FrameMaker中编辑文件。 您还可以将AEM Guides配置为从Web编辑器启动FrameMaker。 在FrameMaker中打开文件后，您可以编辑该文件并将其签回AEM存储库。

## 从Web编辑器在FrameMaker中启用文件编辑

可以使用FrameMaker或任何其他DITA编辑器创建和更新DITA内容。 但是，如果贵组织使用FrameMaker作为DITA编辑器，则可以为用户提供直接在FrameMaker中从AEM打开DITA文档的选项。

默认情况下，您的用户不会看到 **在FrameMaker中打开** AEM按钮。 执行以下步骤以在AEM工具栏中添加此按钮：

1. 打开“Adobe Experience Manager Web控制台配置”页面。

   用于访问配置页面的默认URL是：

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. 搜索并单击 **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** 捆绑。

   ![](assets/open-in-fm-toolbar.png){width="550" align="left"}

1. 选择 **显示“在FrameMaker中打开”按钮** 选项。

1. 单击“**保存**”。


当您启用 **显示“在FrameMaker中打开”按钮** 选项，然后 **在FrameMaker中打开** 选择AEM存储库中的任意DITA文件时将显示按钮。 当此选项为 *未启用*，则 **在FrameMaker中打开** 按钮仅在您选择存储库中的.fm或.book文件时显示。


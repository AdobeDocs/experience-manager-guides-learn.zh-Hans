---
title: 创建和使用条件
description: 了解如何创建条件，然后在中设置条件内容生成 [!DNL AEM Guides]
role: User
exl-id: a86007e3-48d1-458b-84a7-b683e113e5b2
source-git-commit: b5e64512956f0a7f33c2021bc431d69239f2a088
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 0%

---

# 创建和使用条件并生成条件输出

**用例**

* 作者可以对一段内容设置条件，以便控制该内容是否显示在输出中。

* 作者可以在发布时选择显示/隐藏不同的条件。

* 例如，作者可以在内容中添加属性作为版本1.0和版本2.0，并使用条件包括版本1.0的版本1.0和排除版本2.0。

**步骤 1**

在中定义与文档相关的条件 [!UICONTROL 文件夹配置文件]：请参阅部分 **为全局或文件夹级别的配置文件配置条件属性** 在 [安装和配置指南第64页](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/3-8/XML-Documentation-for-Adobe-Experience-Manager_Installation-Configuration-Guide_EN.pdf)

![在文件夹配置文件中配置条件](assets/conditions-in-profiles.png)

**步骤2**

选择 **[!UICONTROL 文件夹配置文件]** 中的步骤1中定义 **用户首选项** 在XML编辑器中：请参阅部分 **用户首选项** 在 [用户指南第39页](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/3-8/XML-Documentation-for-Adobe-Experience-Manager_User-Guide_EN.pdf)


**步骤3**

使用条件对内容的各个部分进行条件化：请参阅部分 **条件** 在 [用户指南第81页](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/3-8/XML-Documentation-for-Adobe-Experience-Manager_User-Guide_EN.pdf)

![Web编辑器中的使用条件](assets/conditions-in-web-editor.png)

**步骤4**

在映射级别定义条件预设以选择要在输出中启用的条件：请参阅部分 **使用条件预设** 在 [用户指南第184页](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/3-8/XML-Documentation-for-Adobe-Experience-Manager_User-Guide_EN.pdf)

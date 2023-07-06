---
title: 配置自定义DITA映射模板
description: 了解如何配置自定义DITA映射模板
source-git-commit: 6051181e243cf71919901093c1b5590f21832545
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 1%

---


# 配置自定义DITA映射模板 {#id1774F04F05Z}

AEM Guides附带两个现成的映射模板 — DITA map和Bookmap。 您可以基于这些模板创建映射；或者，您可以定义自己的映射模板，然后可以将其用于创建新映射。

执行以下步骤以添加自定义映射模板：

1. 以管理员身份登录Adobe Experience Manager。

1. 在Assets UI中，导航到配置为存储映射模板文件的文件夹。 默认情况下，所有映射模板都存储在/content/dam/dita-templates/maps文件夹中。

   >[!NOTE]
   >
   > 要配置用于存储主题或映射模板的自定义位置，请参阅 [配置自定义DITA模板文件夹路径](conf-template-tags-custom-dita-topic-template.md#id191LCF0095Z)

1. 单击 **创建** \> **DITA模板**.

1. 在Blueprint页面上，选择要创建的映射模板的类型。

   >[!NOTE]
   >
   > 您可以使用Map或Bookmap模板作为新模板的基。

1. 单击&#x200B;**下一步**。

1. 在新模板的“属性”页面中，输入 **标题** 和 **名称** 模板的。

   >[!NOTE]
   >
   > 系统会根据模板标题自动建议名称。 如果要手动指定名称，请确保该名称不包含任何空格、撇号或大括号，并且以.ditamap结尾。

1. 单击&#x200B;**创建**。

   将显示“已创建映射”消息。

   您可以选择在映射编辑器中打开模板进行编辑，或将模板文件保存到模板存储位置。 创建模板后，您可以使用映射编辑器根据创作需求自定义模板。 建立模板后，请确保将其与全局或文件夹级别的配置文件相关联。


下次创建新映射时，模板将显示在Blueprint页面中。 有关创建DITA映射的更多信息，请参阅使用Adobe Experience Manager Guidesas a Cloud Service指南。

>[!TIP]
>
> 参见 *自定义模板* 部分，以了解有关使用自定义映射模板的最佳实践。

**父主题：**[&#x200B;配置主题和映射模板](conf-template-tags.md)

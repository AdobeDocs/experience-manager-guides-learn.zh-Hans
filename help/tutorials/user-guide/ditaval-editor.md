---
title: 使用DITAVAL编辑器
description: 了解如何使用DIAVAL编辑器
source-git-commit: 7cd719921e68ac1763d09d9665d912e3697e5849
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 0%

---


# DITAVAL编辑器 {#id17C5E0U0OQE}

DITAVAL文件用于生成条件输出。 在单个主题中，您可以使用元素属性添加条件以条件化内容。 然后，创建一个DITAVAL文件，其中指定了生成内容时应选取的条件，以及最终输出中应排除的条件。

AEM指南允许您使用DITAVAL编辑器轻松创建和编辑DITAVAL文件。 DITAVAL编辑器可检索系统中定义的属性\（或标记\），您可以使用这些属性创建或编辑DITAVAL文件。 有关在AEM中创建和管理标记的更多详细信息，请参阅 [管理标记](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/tags.html?lang=en) 部分。

## 创建DITAVAL文件

执行以下步骤以创建DITAVAL文件：

1. 在资产UI中，导航到要创建DITAVAL文件的位置。

1. 单击 **创建** \> **DITA主题**.

1. 在Blueprint页面上，选择DITAVAL文件模板，然后单击 **下一个**.

1. 在属性页面上，指定 **标题** 和 **名称** 的值。

   >[!NOTE]
   >
   > 该名称会根据文件的标题自动建议使用。 如果要手动指定文件名，请确保“名称”不包含任何空格、撇号或大括号，并以.ditaval结尾。

1. 单击&#x200B;**创建**。此时会显示“主题已创建”消息。

   您可以选择在DITAVAL编辑器中打开DITAVAL文件进行编辑，或在AEM存储库中保存主题文件。


## 编辑DITAVAL文件

执行以下步骤以编辑DITAVAL文件：

1. 在资产UI中，导航到要编辑的DITAVAL文件。

1. 要获得对文件的独占锁定，请选择文件并单击 **结帐**.

1. 选择文件并单击 **编辑** 要在AEM Guides DIAVAL编辑器中打开文件，请执行以下操作：

   DITAVAL编辑器允许您执行以下任务：

   答：切换左侧面板：切换左侧面板视图。 如果您已通过DITA映射打开DITAVAL文件，则映射和存储库将显示在此面板中。 有关通过DITA映射打开文件的更多信息，请参阅 [通过DITA映射编辑主题](map-editor-advanced-map-editor.md#id17ACJ0F0FHS).

   B:保存：保存您在文件中所做的更改。 所有更改都将保存在文件的当前版本中。

   C:添加属性：在DITAVAL文件中添加单个资产。

       ![](images/ditaval-editor-props.png)
       
       第一个下拉列表列出了可在DITAVAL文件中使用的允许的DITA属性。 支持五个属性 — “audience”、“platform”、“product”、“prop”和“otherprop”。
   
   :第二个下拉列表显示为选定属性配置的值。 然后，下一个下拉列表会显示您可以对选定属性配置的操作。 操作下拉列表中允许的值为 —  `include`, `exclude`, `passthrough`和 `flag`. 有关这些值的更多信息，请参阅 [prop](http://docs.oasis-open.org/dita/dita/v1.3/errata01/os/complete/part3-all-inclusive/langRef/ditaval/ditaval-prop.html#ditaval-prop) 元素

   D:添加所有属性：如果要通过单击添加系统中定义的所有条件属性或属性，请使用添加所有属性功能。

>[!NOTE]
>
> 如果DITAVAL文件中已存在所有定义的条件属性，则无法添加更多属性。 在此方案中，您会收到一条错误消息。

    ![](images/ditaval-all-props.png)

1. 编辑完DITAVAL文件后，单击 **保存**.

   >[!NOTE]
   >
   > 如果在不保存的情况下关闭文件，则更改将丢失。 如果不希望将更改提交到AEM存储库，请单击 **关闭**，然后单击 **关闭而不保存** 在 **未保存的更改** 对话框。


## DITAVAL编辑器视图

AEM指南的DITAVAL编辑器支持以两种不同模式或视图查看DITAVAL文件：

作者：这是DITAVAL编辑器的典型“What You Get \(WYSISYG\)”视图。 您可以使用简单的用户界面添加或删除属性，该用户界面会在下拉列表中显示属性、其值和操作。 在“创作”视图中，您可以选择插入单个资产，并通过单击插入所有资产。

:您还可以通过将指针悬停在文件名上方来查找当前正在处理的DITAVAL文件版本。

来源：“源”视图显示构成DITAVAL文件的基础XML。 除了在此视图中进行常规文本编辑之外，作者还可以使用智能目录添加或编辑属性。

    要调用智能目录，请将光标放在任何属性定义的末尾，并输入“&lt;”。 编辑器将显示可在该位置插入的所有有效XML元素的列表。
    
    ![](images/ditaval-source-view.png)


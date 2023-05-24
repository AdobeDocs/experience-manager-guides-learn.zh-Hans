---
title: 从Web编辑器创建输出预设
description: 了解如何从Web编辑器创建输出预设
exl-id: 7fde0057-06a5-428e-a91b-9e9386a56270
source-git-commit: 3bca42f0954afc2362ab24f369e698113324dbc3
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 0%

---

# 从Web编辑器创建输出预设 {#id218CL400JW3}

执行以下步骤可为DITA map创建输出预设：

1. 在Assets UI中，导航到要编辑的映射文件。

1. 要获取对映射文件的独占锁定，请选择映射文件并单击 **签出**.

1. 选择 **编辑主题** 操作菜单中的选项。

   将打开映射文件以在Web编辑器中编辑。

   >[!NOTE]
   >
   > 您可以使用高级映射编辑器在映射中添加或删除任何主题。 有关更多详细信息，请参阅 [使用高级映射编辑器](map-editor-advanced-map-editor.md#).

1. 在 **输出** 选项卡，选择+图标以创建DITA map的输出预设。

   ![](images/output-tab-preset_cs.png){width="350" align="left"}

1. 在“添加预设”对话框中输入预设的名称，然后单击 **添加**.

1. 输入以下配置详细信息。

   1. 在中选择所需的选项 **常规** 选项卡。 您可以选择创建附带或不附带条件的输出预设。 您也可以使用DITVAL文件。 AEM Guides还允许您选择用于发布特定版本的DITA map的基线。
   1. 在中输入AEM Site详细信息 **AEM** 选项卡。 **站点** 显示AEM存储库中可用的AEM Sites列表。 **类别**， **区域模板**、和 **文章模板** 是用于组织输出外观的结构组件。 这些在AEM站点模板中预定义。

      >[!NOTE]
      >
      > 刷新每个下拉列表以在下一个下拉列表中获取进一步的分类。

   1. 从 **文章** 选项卡，选择要为其生成输出的主题。
1. 选择 **生成预设** 图标，以生成输出。

   ![](images/add-preset-articles-tab_cs.png){width="800" align="left"}

1. 您将看到输出生成过程的状态。 此 **主题** 列列出了生成输出的主题， **状态** 列显示每个主题的发布状态。

   要查看输出，请将鼠标指针悬停在主题上，然后单击“查看输出”。

   ![](images/add-preset-output-generated_cs.png){width="800" align="left"}


>[!NOTE]
>
> 也可以从“选项”菜单中“编辑”、“重命名”、“复制”或“删除”现有输出预设。

![](images/edit-preset_cs.png){width="550" align="left"}

**父主题：**[&#x200B;从Web编辑器发布基于文章](web-editor-article-publishing.md)

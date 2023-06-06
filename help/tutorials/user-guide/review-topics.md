---
title: 查看主题
description: 了解如何查看主题
exl-id: ca94ec2e-cd45-418d-9b35-73d587ba51ec
source-git-commit: 8823669fd29e8a40a41f9ca5d654b38fbea8e2fa
workflow-type: tm+mt
source-wordcount: '2271'
ht-degree: 0%

---

# 查看主题 {#id2056B0W0FBI}

如果您是审阅人，则会收到一封包含审阅主题链接的审阅请求电子邮件。 单击链接将转到审阅页面，您可以在其中添加有关共享主题的反馈。

执行以下步骤来复查主题：

1. 单击审阅请求电子邮件中提供的直接链接。

   将在浏览器中打开主题或映射链接。

   >[!NOTE]
   >
   > 您还可以从AEM用户界面的“收件箱通知”区域访问主题查看链接。

1. 根据主题审阅的启动方式，您可以看到以下两个屏幕中的任意一个：

   >[!NOTE]
   >
   > 如果您已在以下位置创建审核，则UI可能不同：
   >
   > - AEM Guides 2022年11月版as a Cloud Service或更早版本
   > - AEM Guides版本4.1或更低版本




   使用DITA map启动审阅工作流时，将显示以下屏幕：

   ![](images/multiple-topics-review.png){width="800" align="left"}

   以下选项在此屏幕上可用：

   - **A**：审核任务的名称。
   - **B**：单击主题视图图标可显示或隐藏主题面板。

   - **C**：突出显示的数字 ***F*** 可以通过从此处选择所需的过滤器选项进行过滤。 您可以按注释的类型、状态、审阅者或版本来筛选注释。 例如，如果要查看在每个审核主题中发表了多少删除线注释，请单击过滤器图标，然后选择 **审核类型** \> **删除**.

      >[!NOTE]
      >
      > 应用过滤器时，只有与所选过滤器匹配的注释才会显示在注释面板中。 过滤的评论数显示在左侧的主题面板中。

   - **D**：指定给当前审阅人审阅的主题以黑色显示，可点击。 当查看者单击某个主题链接时，该主题将出现在屏幕顶部。
   - **E**：不可用于审阅的主题呈灰显状态。 该主题以只读模式显示，不允许在此类主题中添加任何审阅注释。

   - **F**：收到的关于某个主题的评论数量。 此数字会根据您应用的过滤器而发生更改。

   映射中的所有主题都显示为单个复合文档。 正常显示允许审阅人审阅的主题。 不允许审阅的主题不显示。

   ![](images/review-read-only.png){width="800" align="left"}

   在上面的屏幕截图中，将共享“常规”描述主题以查看当前查看者，该主题正常显示。 但是，下一个主题“外部测试版的历史记录”内容不会共享以供审阅，并且会以只读模式显示。 目录中也突出强调了当前关注的专题。

   选择并共享一个或多个主题以进行审阅时，将显示以下屏幕：

   ![](images/review-composite-view.png){width="800" align="left"}

   >[!NOTE]
   >
   > 如果有多个主题，它们会在文档视图中显示为一个复合文档。 上面的屏幕快照突出显示了在单个视图中一个接着另一个呈现的两个不同主题。

1. 通过单击 **评论** 图标（位于工具栏的右上角）。

   通过从工具栏中选择适当的评论类型来提供评论评论，然后按Enter提交您的评论。

   >[!NOTE]
   >
   > “注释”面板仅显示有关当前主题的注释。 将焦点移动到其他主题时，将显示针对其他主题给出的注释。

1. 单击 **关闭** 按钮。 单击 **关闭** 按钮时，您将被重定向到从中访问“复查”主题的页面。

## 查看屏幕上可用的添加功能

**文档视图和主题视图**  — 默认情况下，如果共享多个主题以供审阅，则向审阅人显示主题的复合文档视图。 对于DITA map审阅，映射中的所有主题都以单个文档的形式显示，类似于书籍视图。 如果需要，您还可以单击特定主题，然后查看屏幕上仅显示该主题。

当您查看单个主题时，您会获得另一个选项以切换回文档视图。 在下面的屏幕快照中，将打开映射文件中的特定主题以供审阅。 高亮显示的选项 —  **显示文档视图** 允许用户切换回映射文件的文档视图。

![](images/switch-document-view.png){width="800" align="left"}

**使用不同类型的注释工具**  — 可以通过加亮文本、在文本中加亮标记、插入文本或添加注释注释来添加内联注释。 “注释”工具栏中提供的不同类型的注释工具如下所述：

![](images/comments-toolbar.png){width="350" align="left"}

- **突出显示** \(![](images/review-highlight-icon.svg)\)：要添加高亮注释，请选择文本并单击高亮图标。 或者，单击高亮图标并选择所需的文本：

   ![](images/highlight-comment.png){width="650" align="left"}

   “注释”面板中会显示一个弹出窗口，您可以在其中为突出显示的内容添加注释。

- **删除线** \(![](images/review-text-strike-through-icon.svg)\)：如果要建议删除内容，可以通过选择内容并单击删除线图标来执行此操作。 或者，选择所需的文本并单击Delete键：

   “注释”面板中会显示一个弹出窗口，您可以在其中为已删除的内容添加注释。

- **插入文本** \(![](images/review-insert-text-icon.svg)\)：如果要插入文本，请单击“插入文本”图标，并将光标置于要插入文本的位置，然后键入信息。 或者，将光标放在要插入文本的位置并开始键入。 添加的信息以绿色字体显示：

- **添加评论**\(![](images/review-comment-icon.svg)\)：如果要添加注释类型的便笺，请单击“添加注释”图标，然后在弹出窗口中输入注释。


**上下文工具栏**

您还可以使用上下文工具栏快速突出显示或删除文本。 执行以下步骤以使用上下文工具栏进行注释：

1. 选择要加亮或删除的文本。 出现上下文工具栏。

   ![](images/review-quick-launch-toolbar.png){width="550" align="left"}

1. 单击 **突出显示**&#x200B;或 **删除线** 图标。
1. 您可以在注释面板中为高亮或删除线操作添加注释。

**使用“注释”面板进行审核** - “注释”面板显示有关当前主题的注释列表。 如果将主题发送给多个审阅人，则此面板还会列出来自其他审阅人的注释。 评论面板中的每个评论都链接到当前主题中的相应文本。 它有助于您识别注释的文本。 每个注释都显示已添加注释的审阅人的姓名以及时间戳。

注释按文档中注释文本的顺序显示。 例如，在第一段中的第一句上有高亮的注释并在第二句上插入文本注释，然后高亮的文本注释显示在插入的文本注释之前。

使用“注释”面板可以执行的任务如下所述：

- 单击注释会突出显示并显示相应注释在文档中的位置。
- 您可以向评论添加回复。
- 您可以通过单击“注释”面板中注释的文本，然后选择 **编辑** 从“选项”菜单中。
- 您可以通过单击“注释”面板中的注释，然后选择 **删除** 选项。

   ![](images/review-comment-options-menu.png){width="300" align="left"}

   >[!NOTE]
   >
   > 仅当将鼠标悬停在您自己的注释上时，“选项”菜单才会出现。 对于其他审阅人的注释，不会显示它。

- 所有参与的用户都可以对其他用户提交的注释做出响应。 在注释上，单击 **回复** 并按Enter键提交响应。

**预览模式**

- 在“预览”模式下打开主题会显示主题在应用所有更改后被作者查看时的显示方式。 例如，所有插入的文本均显示为普通文本，而所有删除的\（已删除\）文本都将从内容中删除。

- 以下屏幕截图显示了中的内容 *审核* 模式：

![](images/review-author-mode.png){width="550" align="left"}

以下屏幕截图显示了中的内容 *预览* 模式：

![](images/review-preview-mode.png){width="550" align="left"}

**将附件添加到注释**  — 如果要通过提供其他某个文件中提供的附加信息来补充注释，可以通过将其与注释一起附加来补充。 作为审阅人，您可以轻松地将本地系统中的一个或多个文件添加到您的评论中。 可以将文件添加到所有受支持的注释形式 — 高亮、删除线、插入文本或注释。

插入任何注释时，将出现注释弹出窗口。 在弹出窗口中提供其他注释或信息后，可通过按Enter键提交注释。 添加注释后，您可以选择将附件添加到该注释。

![](images/comment-pop-up-panel.png){width="800" align="left"}

在上面的屏幕快照中，文档包含高亮注释的弹出窗口，并且注释也会添加到“注释”面板中。 文件附件图标 ![](images/file-attach-review.svg)随注释一起在两个位置提供。

执行以下步骤以将附件添加到注释：

1. 单击 *添加附件* 图标 ![](images/file-attach-review.svg) 添加附件的注释。

   此时将显示文件“打开”对话框。

1. 选择一个或多个要附加的文件。

   所选文件与注释一起显示在“注释”面板中。

   在“注释”面板中，您可以看到文件名及其大小。 您还可以选择通过单击删除图标来删除文件 ![](images/Delete_icon.svg) 与文件名相关联。

1. 单击 **提交**.

   附件将上传并添加到评论中。


**有关使用附件的其他注释：**

- 默认情况下，仅显示两个附加了注释的文件。 如果有更多文件，则 **查看附件** 按钮右侧显示与注释关联的所有附件\（两个以上\）的数量。 您可以单击该编号以查看所有附件。 例如，如果您有四个带有注释的附件，您将在按钮上看到+2。

![](images/review-view-attachment.png){width="550" align="left"}

- 将鼠标指针悬停在附件上时，可以下载或删除附件。 仅当当前查看者已添加该评论时，才可移除附件，如下面的屏幕快照所示：

![](images/current-user-comment-options.png){width="550" align="left"}

其他审阅人或作者只能获得下载附件选项。

![](images/other-reviewer-download.png){width="550" align="left"}

- 您可以从以下位置下载与注释关联的所有附件： **查看附件** 对话框。 选择附件并单击 **下载** 图标进行查看。

- 您也可以从以下位置删除与注释关联的附件： **查看附件** 对话框。 选择附件并单击 **删除** 图标。

![](images/attach-files-comments-panel.png){width="550" align="left"}


**“条件”面板**  — 如果您的主题包含条件内容，则会显示 **条件** \(![](images/conditions-icon.svg)\)图标。 单击 **条件** 图标会打开“条件”面板，允许您根据主题中的可用条件突出显示内容。

：默认情况下 **突出显示所有条件** 选项，选中所有条件，显示整个内容，并在审阅和预览模式下将条件化内容显示为高亮显示。

：您可以禁用 **突出显示所有条件** 选项，并将主题中存在的所有内容视为不带任何高亮显示的普通文本。

![](images/review-conditions-panel.png){width="350" align="left"}

您可以选择隐藏或显示特定条件。

- 如果隐藏条件，则审阅模式下不会突出显示具有该条件的内容。
- 如果显示条件条件化内容，则审阅模式中会高亮显示该内容。 例如，在以下屏幕截图中，仅内容使用两个条件 —  `win` 和 `mac` 高亮显示。


![](images/review-condition-normal-mode.png){width="650" align="left"}

在预览模式下，非条件化内容和使用两个显示条件的条件化内容 —  `win` 和 `mac` 将显示。 不会显示隐藏条件的其余条件化内容。

**实时审查**  — “评论”面板实时更新了评论以及作者对评论提出的反馈或采取的操作。

- 多个审阅人将能够在同一文档上同时留下注释或回复注释。 通过将鼠标悬停在屏幕右上角的用户图标上，可以确定当前正在查看文档的用户。

- 如果一个主题是多个审阅任务的一部分，则在一个任务中所做的注释不会显示在另一个任务中。

- 单击已过期的评论图标\(![](images/outdated-comment-icon.svg)\)显示文档的最新版本与注释版本之间的差异。 版本号\（正在比较的版本\）显示在文档顶部。

   ![](images/comments-page-review-mode.png){width="800" align="left"}

   >[!NOTE]
   >
   > 当您将鼠标悬停在过时的评论图标上时，将显示添加评论的主题的版本号。 例如，如果在1.0版上提供了注释，则会显示相同的注释。

- 单击过时的注释会在左侧面板中打开该注释的版本。 左侧面板中显示的是以前的版本，右侧面板中显示的是当前的版本。 过期版本上的所有注释都将在左侧导入。 您可以将以前的版本与当前版本进行比较。

**筛选注释**  — 您可以筛选文档中的注释以根据需要查看特定注释。 要筛选注释，请单击 **筛选条件** 图标\(![](images/filter-search-icon.svg)\)显示在“注释”面板的“搜索注释”文本框右侧的菜单中。

从中选择以下一个或多个筛选选项 **筛选器类型** 对话框，然后单击 **应用**.

- **审核类型**  — 根据注释类型进行筛选 — Highlight、Deletion、Insertion或Comment。
- **审核状态**  — 根据评论的状态进行筛选，如“已接受”、“已拒绝”或“无”。
- **审阅者**  — 根据查看者的姓名进行筛选。

- **版本**  — 根据收到的关于该主题特定版本的评论进行筛选。

   使用过滤器时，右侧面板上的注释会根据所选内容进行过滤，左侧面板中的注释数量会相应地更新。


要删除筛选器并查看所有注释，请从 **筛选器类型** 对话框，然后单击 **应用**.

**父主题：**[&#x200B;查看主题或地图](review.md)
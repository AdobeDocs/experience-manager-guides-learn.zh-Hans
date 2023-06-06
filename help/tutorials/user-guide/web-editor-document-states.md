---
title: 文档状态
description: 了解如何记录状态
exl-id: 6ab85a63-02d2-4802-a6b8-99e6551a567b
source-git-commit: 3bca42f0954afc2362ab24f369e698113324dbc3
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 0%

---

# 文档状态 {#id1821HC00URO}

为了管理文档的准备工作，AEM Guides提供了文档状态属性来指示文档的当前状态。 文档状态可帮助您快速确定文档是新文档、处于审阅状态还是审阅完成状态。

## 文档状态的类型

文档可以具有在文档状态配置文件中定义的任何文档状态。 例如，一个文档可能具有以下任一文档状态：

- 草稿 — 指示文档是在新更改的情况下创建和保存的。
- 正在审阅 — 表示已启动文档的审阅工作流。
- 已审阅 — 表明文档已由目标用户审阅。

根据文档状态配置文件设置，可手动或自动设置这些状态。 例如，如果“文档状态”配置文件的开始状态配置为“草稿”，并且为审阅中的文档定义了“审阅中”状态。 然后，在创建文档时，文档状态将设置为 *草稿*. 如果启动审阅任务，则文档状态将更改为“正在审阅”。

您也可以手动更改单个或多个文档的文档状态。 但是，如果选择更改多个文档的文档状态，则允许的状态由所选文档允许的一般状态确定。 例如，假设您已按相同顺序将文档状态定义为“草稿”、“正在审阅”、“已审核”和“准备发布”。 在文档1.dita上，状态设置为 *草稿* 而在文档2.dita中，状态设置为“已审阅”。 同时选择one.dita和two.dita时，允许的文档状态将为 *发布准备就绪*. 当two.dita *已审核* 状态，两个的下一个可能状态为。dita只是 *发布准备就绪*，在选择两个文档时显示。

>[!NOTE]
>
> 文档一次只能存在于一种状态。

## 更改文档状态

要更改文档状态，请执行以下步骤：

1. 在Assets UI中，选择要更改其文档状态的一个或多个文档。
1. 在主工具栏中，单击 **属性**.
1. 从中选择新状态 **文档状态** 下拉菜单。 您只能选择在文档状态配置文件的“状态转换”部分中允许的那些文档状态。

   >[!NOTE]
   >
   >管理员可以查看所有文档状态并将文档更改为任何可能的状态。

1. 单击“**保存并关闭**”。

## 查看文档状态

Assets UI的卡片视图显示当前状态以及相应DITA主题或DITA映射的创建日期和大小。

![](images/document_state.png){width="800" align="left"}

## 在DDLC中使用文档状态

文件状态在管理DDLC中文件的生命周期方面发挥着重要作用。 如果您的组织严格遵循DDLC，则根据文档的状态来控制文档编辑的机制将成为一项基本功能。 例如，您可以允许在文档处于以下状态时编辑文档 *草稿* 或 *正在审核* 状态。 但是，一旦文档经过审查并准备好发布，就应该有办法防止进一步修改文档。

AEM Guides提供了文档审批工作流，可帮助您控制文档开发过程的生命周期。 一旦文档准备好发布或达到倒数第二状态，您就可以将其标记为已批准。 文档获得批准后，AEM Guides会创建文档的新版本并将其设置为只读。 然后，您可以移动文档以进行发布，或创建基线以进行进一步处理。

要从标记为已批准的文档开始新版本，作者必须开始新版本。 启动新版本会将文档状态更改为 *草稿* 再来一次。 通过将文档状态更改为 *草稿*，则文档将再次变为可编辑，您可以继续开发下一个版本。

要使用文档审批功能，请执行以下步骤：

>[!NOTE]
>
> 审批工作流功能必须由您的管理员启用。 有关更多详细信息，请参阅 *启用审批工作流* 安装和配置Adobe Experience Manager Guidesas a Cloud Service中的部分。

1. 在Web编辑器中，打开要标记为批准的文档。

1. 单击 **标记为已批准**![](images/mark_approve_icon.svg)&#x200B;图标。

1. 如果文档处于标记为已批准状态，则将显示以下对话框：

   ![](images/mark-approved-correct-state.png){width="300" align="left"}

   如果文档无法标记为已批准，则会显示以下消息：

   ![](images/mark-approved-incorrect-state.png){width="300" align="left"}

1. 如果您的文档已准备好标记为已批准，请从下拉列表中选择一个标签并单击 **批准**.

   >[!NOTE]
   >
   > 如果管理员未配置预定义的标签列表，则会向您显示一个用于输入标签的自由格式文本字段。

1. 成功将文档标记为已批准后，将 **预览** 以只读模式显示。

   ![](images/approved-doc-read-only.png){width="650" align="left"}

   >[!NOTE]
   >
   > 在“预览”模式下，将从工具栏中删除所有编辑选项。 此外，文档的“作者”和“源”视图也已从顶部导航中删除。


文档标记为已批准后，便无法再进行编辑。 如果要将该文档用于下一个版本，则需要将其带回 *草稿* 省/州。 要将已批准文档的文档状态更改为 *草稿* 模式，请执行以下步骤：

1. 在批准的文档中，单击 **启动新版本** 图标 ![](images/approved-restart-draft-mode-icon.svg).

   出现“Start New Release（开始新版本）”信息。

1. 单击 **确认**.

   文档的状态将更改为“草稿”，并在Web编辑器中以编辑模式打开文档。


**父主题：**[&#x200B;使用Web编辑器](web-editor.md)
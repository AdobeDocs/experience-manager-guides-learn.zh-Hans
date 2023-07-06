---
title: 插入数据源中的内容片段
description: 了解如何从数据源插入内容片段
source-git-commit: 6061d35b86790e24c6f55e4ccac5dbb40c43aae8
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 0%

---


# 插入数据源中的内容片段

AEM Guides提供了与数据源连接的功能。 您可以获取数据，将其插入主题中并进行编辑。 您可以使用内容片段生成器轻松创建内容片段，并在主题中重复使用。

执行以下步骤，使用内容片段生成器创建内容片段并将其插入到主题中：

1. 选择 **数据源** ![](images/data-source-icon.svg)   ，以查看连接的数据源。 “数据源”面板随即打开并显示所有连接的数据源。 有关更多详细信息，请参阅 [配置数据源连接器](../cs-install-guide/conf-data-source-connector.md).

   >[!NOTE]
   >
   > 您将看到管理员为其配置了连接器的数据源。

1. 选择数据源以查看可用于所选数据源的内容片段生成器。
   ![](images/code-snippet-generator.png){width="300" align="left"}
1. 选择 **添加** 以添加新的内容代码片段生成器。 此 **添加内容片段生成器** 面板打开。

1. 在“数据查询”文本框中输入查询。
1. 从中选择与数据源映射的模板 **数据映射模板** 下拉菜单。
所选数据源的现成模板将显示在下拉列表中。 例如，您可以查看名为“PostgreSQL”数据源的“sql-table”模板。

   >[!NOTE]
   >  
   > 如果您的管理员配置了自定义模板，则您还会在下拉列表中看到这些模板（基于管理员完成的模板路径配置）。

1. 单击 **Fetch** 从数据源获取数据，并将模板应用于从SQL查询生成的数据。

1. 您可以在预览或DITA源视图中查看数据。

   1. 预览显示插入内容时数据的显示方式。 预览以所选模板的格式显示一小部分数据。
例如：
      * 如果已选择SQL表模板，则可以使用表格式查看SQL数据。
      * 如果您选择了jira-ordered-list模板，则可以查看Jira问题的已排序列表。

   1. 源视图在DITA源视图中显示数据。
      ![](images/add-content-snippet-generator.png){width="800" align="left"}
1. 要保存查询结果，请输入生成器的名称，然后单击 **添加**.   新的内容代码片段生成器将添加到列表中。

   >[!NOTE]
   >
   > 您需要遵循新内容生成器的名称的文件命名约定。 内容代码片段生成器的名称中不能有空格。 此外，不能使用现有内容生成器的名称保存新的内容生成器。 出现错误。

## 内容片段生成器的选项

右键单击内容代码片段生成器以打开“选项”。 使用这些选项，可以执行以下操作：
* **插入**：使用此选项可将选定的内容片段插入到在Web编辑器中打开进行编辑的主题中。 当数据作为代码片段插入时，您还可以在Web编辑器中编辑主题中的数据。

  >[!NOTE]
  > 
  > 插入选项仅在编辑主题时显示。

* **编辑**：使用此选项可以在内容代码片段生成器中做出更改并保存。
* **删除**：使用此选项可删除选定的内容片段生成器。
* **复制**：使用此选项可创建所选内容片段生成器的副本或副本。 缺省情况下，将使用后缀（如generator_1）创建副本。

### 插入查询代码片段

您还可以使用 **插入查询代码片段** ![](images/data-source-icon.svg)   以将数据片段插入到主题中。  您可以从下拉菜单中选择生成器，编辑查询，或更改模板并在主题中插入数据。

![](images/insert-content-snippet.png){width="800" align="left"}




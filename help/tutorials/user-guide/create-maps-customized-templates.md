---
title: 根据自定义模板创建映射
description: 了解如何基于自定义模板创建地图
exl-id: 02513148-3876-4549-962a-9984f619030f
source-git-commit: be1a61d9475185da594b382c1daf361d3fe60b08
workflow-type: tm+mt
source-wordcount: '870'
ht-degree: 0%

---

# 根据自定义模板创建映射 {#id225VF0808MP}

您可以创建自定义的映射模板，并使用它们创建DITA映射以及映射模板中引用的主题模板和映射模板

您可以从自定义的映射模板中引用其他映射模板和主题模板。 引用的映射模板可以引用各种映射模板、主题模板、主题、映射、图像、视频和其他资源。 自定义的映射模板可以帮助您非常轻松地复制映射模板和整个引用的文件夹结构。 这些自定义模板对于创建和重新创建具有递归结构和引用的多个映射特别有用。

>[!NOTE]
>
> 主题模板不是递归创建的。 只生成直接位于映射模板中的主题模板，而主题模板中的任何主题模板都只是在父项中直接引用。

## 创建自定义模板

AEM Guides允许您从dita-templates文件夹创建自定义映射和主题。 您可以使用这些自定义模板来创建映射和主题。 您还可以与作者共享这些模板，他们可以使用这些模板创建自己的文件。 使用这些模板，您可以允许作者保留模板文件夹中特定资源的单独副本。

>[!NOTE]
>
> 任何仅在中引用和维护的资源都必须保留在templates文件夹之外。

**主题模板**

执行以下步骤可创建主题模板：

1. 在 **资产UI**，导航到dita-templates文件夹。

   ![](images/dita-templates.png){width="800" align="left"}

1. 单击 **主题** 文件夹以将其打开。单击 **创建\> DITA模板**.
1. 在Blueprint页面上，选择 **主题** 然后单击 **下一个。**
1. 在“属性”页上，指定主题模板 **标题**.
1. 指定文件 **名称**

   >[!NOTE]
   >
   > 文件名必须具有.dita扩展名。

1. \（可选\）添加说明。
1. 单击&#x200B;**创建**。此时将显示主题模板创建消息。 然后，您可以打开主题模板并对其进行编辑。

**映射模板**

执行以下步骤可创建映射模板：

1. 在 **资产UI**，导航到dita-templates文件夹。
1. 单击 **映射** 文件夹以将其打开。
1. 单击 **创建** > **DITA模板。**

   ![](images/create-dita-template.png){width="300" align="left"}

1. 在Blueprint页面上，选择 **地图** 并单击 **下一个**.
1. 在属性页面上，指定映射模板 **标题**.
1. 指定文件 **名称**.

   >[!NOTE]
   >
   > 文件名必须具有.ditamap扩展名。

1. （可选\）添加说明。单击 **创建**. 出现“map template created（已创建映射模板）”消息。 然后，您可以打开映射模板并对其进行编辑。 您可以在映射模板中添加对主题模板、映射模板以及其他资源的引用。

## 传递模板中定义的标题

如果要将模板内使用的主题或映射的标题传递到使用该模板创建的DITA映射，请在标题周围使用大括号。

示例

```XML
<pubtitle>
   <mainpubtitle outputclass="booktitle">
   {title}
   </mainpubtitle>
   <subtitle>Subtitle</subtitle>
</pubtitle>

The resultant DITA map with title "Rootmap1" will look like as follows:
<pubtitle>
   <mainpubtitle outputclass="booktitle">Rootmap1
   </mainpubtitle>
   <subtitle>Subtitle</subtitle>
</pubtitle>
```

>[!NOTE]
> 只有第一个出现的花括号会被替换为标题。

如果您不在标题周围使用大括号，则仅会选取生成的DITA映射的第一个元素，并且不会从模板中选取标题的嵌套，其将如下所示：

```XML
<pubtitle> Rootmap1 </pubtitle>
```

>[!NOTE]
> 也可以使用文本周围的大括号将其嵌套结构从自定义模板传递到DITA映射。

示例

```XML
<title>    
    <sub>        
        <b>{title}</b>    
    </sub>
</title>
```

## 使用映射模板创建新映射

>[!NOTE]
>
> 映射模板必须配置并可由管理员进行创作。 有关更多详细信息，请参阅 *配置创作模板* 安装和配置Adobe Experience Manager Guidesas a Cloud Service中的部分。

执行以下步骤以使用自定义映射模板创建映射：

1. 在 **资产UI、** 导航到要创建映射的文件夹。
1. 单击 **创建\> DITA映射**.
1. 在Blueprint页面上，选择要使用的映射模板并单击 **下一个**. 例如，如果您已创建映射模板“test-template”，请选择它。
1. 在属性页面上，指定映射 **标题**.
1. 指定文件 **名称**.

   >[!NOTE]
   >
   > 文件名必须具有.ditamap扩展名。

1. 单击&#x200B;**创建**。此时将显示映射创建消息。


映射会生成在模板文件夹中引用的所有资源。 地图中引用的某些资源类型如下所示：

- 如果映射包含对主题模板的引用，则会在文件夹中创建主题模板的副本，该副本的层次结构与 `dita-templates` 文件夹。
- 如果映射包含对映射模板的引用，则会在文件夹中创建该模板的副本，其层次结构与中的映射文件夹中的相同。 `dita-templates` 文件夹。
- 如果映射包含对主题或 `dita-templates/topics` 或 `dita-templates/maps` 文件夹内，只会引用相同的内容，而不会创建任何副本。

  >[!NOTE]
  >
  > `dita-templates/topics` 和 `dita-templates/maps` 是指南中的默认路径，并且可以配置。


  如果映射模板中有主题模板键定义，则会创建一个新键\（因此是新主题\），并在映射中引用该键。

- 如果在文件夹的同一级别创建另一个映射或主题，则新创建的资源的名称将附加0、1、2等。 您可以选择打开映射进行编辑，或将映射文件保存到存储库中。

**父主题：**[&#x200B;使用映射编辑器](map-editor.md)

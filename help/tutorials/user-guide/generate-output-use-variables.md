---
title: 使用变量设置目标路径、站点名称或文件名选项
description: 了解如何使用变量来设置目标路径、网站名称或文件名选项
exl-id: e8d5b7c7-4f80-4ab6-9ad1-308bf0d4cf74
source-git-commit: 8073716bccacbe8d6a158b44d5106b083e3a5dcd
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---

# 使用变量设置目标路径、站点名称或文件名选项


在AEM站点或PDF中生成输出时，您可以使用变量来定义“目标路径”、“AEM站点名称”或“PDF文件名”选项。 您可以使用单个变量或变量组合来定义这些选项。

下表列出了现成支持的变量：

| 变量 | 最终目标路径 | 示例 |
| --- | --- | --- |
| `${map_filename}` | 使用DITA映射文件名称创建目标路径。 | **DITA映射文件名**：<br>`AEMGuides.ditamap`<br><br>**目标路径** 配置为：<br>`/content/output/sites/${map_filename}`<br><br>**最终输出位置**：<br>`/content/output/sites/aemGuides/AEMGuides.html` |
| `${map_title}` | 使用DITA映射标题创建目标路径。 | **DITA映射文件名**：<br>`AEMGuides.ditamap`<br><br>**DITA映射标题**：<br>`AEMGuides`<br><br>**目标路径** 配置为：<br>`/content/output/sites/${map_title}`<br><br>**最终输出位置**：<br>`/content/output/sites/AEMGuides/AEMGuides.html` |
| `${preset_name}` | 使用输出预设名称创建目标路径。 | **输出预设名称**：<br>`AEM Guides PDF Output`<br><br>**DITA映射文件名**：<br>`SampleDita.ditamap`<br><br>**目标路径** 配置为：<br>`/content/output/sites/${preset_name}`<br><br>**最终输出位置**：<br>`/content/output/sites/AEM Guides PDF Output/SampleDita.html` |
| `${language_code}` | 使用映射文件所在的语言代码创建目标路径。 | **DITA映射文件名**：<br>`SampleDita.ditamap`<br><br>**DITA映射文件路径**：<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**目标路径** 配置为：<br>`/content/output/sites/${language_code}`<br><br>**最终输出位置**：<br>`/content/output/sites/en/SampleDita.html` |
| `${map_parentpath}` | 使用映射文件的完整路径创建目标路径。<br><br>**注释**：此变量不能用于指定AEM站点名称或PDF文件名。 | **DITA映射文件名**：<br>`SampleDita.ditamap`<br><br>**DITA映射文件路径**：<br>`/content/dam/projects/AEM-Guides/en/user-guide`/<br><br>**目标路径** 配置为：<br>`/content/output/sites/${map_parentpath}`<br><br>**最终输出位置**：<br>`/content/output/sites/content/dam/projects/AEM-Guides/en/user-guide/SampleDita.html` |
| `${path_after_langfolder}` | 使用语言文件夹后的映射文件的路径创建目标路径。<br><br>**注释**：此变量不能用于指定AEM站点名称或PDF文件名。 | **DITA映射文件名**：<br>`SampleDita.ditamap`<br><br>**DITA映射文件路径**：<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**目标路径** 配置为：<br>`/content/output/sites/${path\_after\_langfolder}`<br><br>**最终输出位置**：<br>`/content/output/sites/user-guide/SampleDita.html` |

此外，您还可以将为DITA映射或书签映射文件定义的元数据用作变量。 元数据可在下找到 `/jcr:content/metadata` DITA map或bookmap文件的节点。 例如，在中定义的元数据属性之一 `/jcr:content/metadata` 节点为 `dc:title`. 您可以指定 `${dc:title}` 并在最终输出中使用标题值。
**父主题：**[&#x200B;输出生成](generate-output.md)

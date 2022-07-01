---
title: 本机PDF |PDF输出生成
description: 在Adobe Experience Manager指南中生成PDF输出as a Cloud Service
exl-id: ec3d59b7-1dda-4fd1-848e-21d8a36ff5e4
source-git-commit: b5e64512956f0a7f33c2021bc431d69239f2a088
workflow-type: tm+mt
source-wordcount: '2171'
ht-degree: 0%

---

# 发布PDF输出

使用AEM Guides解决方案，您可以生成单个主题的PDF或整个映射文件。 您可以使用以下三种方法之一以PDF格式发布内容：

* **DITA-OT**

使用此方法可从地图仪表板为地图生成PDF输出。 您可以通过为地图功能板中打开的地图创建输出预设，在生成PDF之前设置发布属性。 要创建或编辑输出预设，请使用 *了解输出预设* 部分 [AEM指南as a Cloud Service用户指南](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/cs-apr-22/XML-Documentation-for-Adobe-Experience-Manager_CS_User-Guide_EN.pdf).

有关使用DITA-OT方法生成PDF的更多信息，请参阅 [使用DITA-OT生成PDF](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-pdf.html).

* **FrameMaker Publishing Server(FMPS)**

使用此方法不仅可以从DITA内容生成PDF输出，还可以从AEM存储库中提供的FrameMaker文档(.book和.fm)生成数据输出。 PDF可以通过配置输出预设并使用FrameMaker Publishing Server(FMPS)进行发布来创建。 您可以设计并配置输出的外观以用于PDF和其他格式，并将其存储在设置文件(.sts)中。 然后，FMPS使用此设置文件为DITA映射或.book文件生成输出。 要创建或编辑输出预设，请参阅  *了解输出预设* 部分 [AEM指南as a Cloud Service用户指南](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/cs-apr-22/XML-Documentation-for-Adobe-Experience-Manager_CS_User-Guide_EN.pdf).

有关配置FMPS的详细信息，请参阅 [从FrameMaker文档生成输出](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Ffm-output-generatation.html).

* **本机PDF发布**

使用此方法可根据W3C CSS3和CSS分页媒体标准生成功能丰富的PDF输出。 通过本机PDF发布，您可以使用模板来设置内容的布局和样式，并应用各种设置来微调PDF。 此外，您还可以使用模板编辑器修改和创建自己的模板。

有关本机PDF发布的更多信息，请参阅 [使用本机PDF发布](#native-pdf-publishing).


## 使用本机PDF发布 {#native-pdf-publishing}

在创作内容时，必须确保内容已针对查看、编辑和打印进行了优化。 使用W3C CSS3等标准来设置内容样式，使用CSS分页媒体标准来设置页面定义属性（如大小、边距、方向、分页、页眉、页脚和页码），您可以为PDF文档设置视图和布局，以确保一致性和可用性。 本机PDF发布功能使用这些标准生成PDF。

通过本机PDF发布，您可以使用预定义模板来确保内容布局和结构的一致性、应用样式表以更改输出的外观、优化PDF、设置打印机标记、允许屏幕阅读器支持、设置PDF符合性、嵌入字体等。

使用本机PDF发布生成PDF有两个方面：

* 使用模板将样式应用于内容、设置页面布局和各种设置来微调您的PDF。 作者可以选择使用/修改提供的示例模板，或创建自定义模板并设置发布者和开发人员使用的高级配置选项。

* 创建或配置PDF输出预设以控制PDF设置。 创建PDF输出预设后，即可生成PDF。

有关更多信息，请参阅 [生成PDF输出](#generate-pdf-output).

## 创建PDF输出预设 {#create-output-preset}

生成PDF输出的第一步是创建PDF输出预设，该预设是分配给映射的发布属性的集合。 您可以为在“映射视图”面板中打开的任何映射创建输出预设，也可以配置现有预设以快速为同一映射生成PDF。

从PDF输出预设中，您可以选择模板、应用条件、设置限制以控制用户与PDF的交互方式、配置高级设置，如压缩、符合性等。

要创建或配置PDF输出预设，请执行以下操作：

1. 在“输出”选项卡中，单击 **预设** 中。
此时将打开“预设”面板。
   ![预设面板](assets/preset-panel.png)
2. 在输出中 **预设** 面板中，执行以下操作之一：
   * 双击某个预定义的PDF输出预设以查看该预设。
   * 单击对应的+图标 **预设** 要添加新的输出预设，请执行以下操作 **类型：PDF**
3. 要配置现有PDF预设的设置，请执行以下操作：
   * 单击  **选项** ![选项](assets/options.svg) 图标，然后选择 **编辑**.
您可以在 **常规**, **布局**, **安全性**&#x200B;和 **高级** 用于配置PDF输出预设的选项卡：

**常规**

使用可指定基本的输出设置，如指定输出路径、PDF文件名等。

| 设置 | 描述 |
| --- | --- |
| **输出路径** | 存储PDF输出的AEM存储库中的路径。 确保输出路径未位于项目文件夹中。 如果留为空白，将在默认DITA映射输出位置中生成输出。 |
| **PDF 文件** | 指定用于保存PDF的文件名。 默认情况下，PDF文件名会添加DITA映射名称和预设名称。 例如，ditamap为“TestMap”，预设的名称为“preset1”，则PDF的默认名称将为“TestMap_preset1.pdf”。 |
| **使用** | 对于条件化内容，请从以下选项中进行选择，以根据这些条件生成PDF输出： <br>* **未应用** 如果不想对映射和源内容应用任何条件，请选择此选项。 <br> * **Ditaval文件** 选择DITAVAL文件以生成条件化内容。 要进行选择，请单击条件预设并找到文件。 <br> * **条件预设** 从下拉列表中选择条件预设，以在发布输出时应用条件。 如果为DITA映射文件添加了条件，则会显示此选项。 条件设置在DITA映射控制台的条件预设选项卡中可用。 要详细了解条件预设，请参阅 [使用条件预设](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-condition-presets.html). <br> |
| **使用基线** | 如果已为选定的DITA映射创建基线，请选择此选项以指定要发布的版本。 请参阅 [使用基线](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-baseline-for-publishing.html) 以了解更多详细信息。 |

**布局**

使用可设置页面布局，并为PDF输出指定页面查看选项（如“页面显示”）和设置缩放级别。

| 设置 | 描述 |
| --- | --- |
| **PDF模板** | PDF模板为定义页面布局、内容样式和将各种设置应用于PDF输出提供了清晰的结构。 从PDF模板下拉选项中选择，以选择首选模板。 |
| **页面显示** | 使用“页面显示”进行页面查看，以显示打开PDF时页面的显示方式。 从“页面显示”下拉选项中选择以选择首选视图。 <br>* **默认**  根据用户计算机上PDF查看器的默认设置显示。  <br> * **单页面查看** 一次显示一个页面。   <br> * **单页滚动** 在连续的垂直列中显示单个页面。  <br> * **双页查看** 一次并排显示两页跨页。.<br> * **双页滚动** 通过连续滚动并排显示两页跨页。 |
| **缩放** | 选择以调整页面视图的大小，以显示打开PDF时页面的显示方式。  <br>* **默认** 根据用户计算机上PDF查看器的默认设置显示    <br> * **100%** 使页面以实际大小显示。     <br> * **适合页面** 使页面宽度和高度适合文档窗格。.<br> * **适合页面宽度** 使页面宽度填充文档窗格的宽度。  <br> * **适合页面高度** 使页面高度填充文档窗格的高度。 |

**安全性**

通过添加打开和读取文件的限制来Protect您的PDF。 使用以下选项可避免未经授权的访问。

| 设置 | 描述 |
| --- | --- |
| **设置密码以打开文档** | 选择以添加安全密码以查看PDF文件。 在 **用户密码** 字段。 用户只能通过输入此字段中提供的密码来打开PDF。 |
| **设置文档限制** | 选择以限制用户与PDF的交互方式。 在 **所有者密码** 字段，以使以下限制设置正常工作。  <br>* **打印** 选择以允许用户打印PDF。 <br> * **草稿质量打印** 选择以允许用户以较低分辨率打印PDF。  <br> * **内容复制** 选择以允许用户从PDF复制内容。   <br> * **批注** 选择以允许用户在PDF中添加注释或注释。  <br> * **内容修改** 选择以允许用户更改PDF中的内容。  <br> * **为辅助功能复制内容** 选择以允许屏幕阅读器阅读和导航PDF中的内容。  <br> * **文档组件** 选择以允许用户在PDF中插入页面。  <br> **注意**:用户需要输入所有者密码，才能通过Adobe Acrobat中的“文件”>“属性”更改任何限制。 |

**高级**

使用以下选项指定用于合并PDF、使用压缩、选择符合性标准等的高级设置。

| 设置 | 描述 |
| --- | --- |
| **创建可访问（已标记）PDF** | 选择此选项可生成带有标记的PDF。 标记的PDF使屏幕阅读器更容易阅读和导航内容、超链接、书签等。 例如，如果表格已标记，屏幕阅读器将知道它正在阅读表格，而不只是线条和文本。 |
| **目录中包含的合并PDF** | 选择此选项可通过将现有PDF添加到目录中，将其合并到输出中。 PDF将插入到目录中表示的位置，并且页面会相应地递增。 |
| **嵌入使用的字体** | 使用可能未安装在最终用户计算机上的字体时，请选择此选项。 选择此选项后，使用的字体将嵌入到PDF中，这可确保用户即使未在其计算机上安装字体，也能按预期看到PDF。 <br> **注意**:仅当字体包含字体供应商允许嵌入的设置时，才能嵌入字体。 在嵌入字体之前，请确保您具有所需的设置或许可证。 |
| **使用自动连字** | 启用自动连字后，行尾的单词会在语法正确的位置中以连字符断开。 |
| **启用JavaScript** | 如果您有JavaScript代码，要使用该代码在生成PDF之前动态转换内容，请启用此选项。 |
| **嵌入多媒体文件** | 选择此选项可将任何音频、视频和任何交互式内容包含到PDF中。 |
| **使用完全压缩可优化PDF大小** | 如果要压缩/缩小大型PDF的大小，请选择此选项。 请记住，压缩PDF可能会降低文件质量。 |
| **使用图像压缩来优化PDF大小** | 如果要压缩/缩小在PDF中使用的图像大小，请选择此选项。 请记住，压缩图像可能会降低图像质量。 |
| **使用自定义分辨率（每英寸像素数）** | 它是以每英寸像素为单位的页面显示分辨率。 在选择此选项时显示的字段中输入首选值。 默认值为96像素/英寸。 如果设置一个较低的值，则设置一个较高的值以适合一英寸内的更多内容，反之亦然。 |
| **显示水印** | 选择此选项可渲染内容中存在的MathML方程式。 否则，方程将被忽略。 |
| **启用MathML方程式** | 选择此选项可渲染内容中存在的MathML方程式。 否则，将默认忽略该等式。 |
| **PDF符合性** | 这是您打算保存PDF以确保其符合标准的标准。 从下拉菜单中选择，以从可用PDF标准列表中进行选择。 有关支持标准的更多详细信息，请参阅 [关于PDF标准](https://helpx.adobe.com/acrobat/using/pdf-conversion-settings.html#about_pdf_x_pdf_e_and_pdf_a_standards). |

## 生成PDF输出 {#generate-pdf-output}

配置输出预设后，您可以使用 **生成预设** 功能。

1. 在 **作者** 选项卡，选择 **存储库** 查看。\
   此时将打开“存储库”面板。

2. 在“存储库”面板中，在 **映射视图**.

3. 在 **输出** ，单击 **预设** 查看“预设”面板。
要创建或配置输出预设，请参阅 [创建PDF输出预设](#create-output-preset).
4. 要保存设置，请单击 **全部保存** ![全部保存](assets/SaveFloppy_icon.svg) 图标。
5. 单击 **生成预设** ![生成预设](assets/generate-output.svg) 图标。
您可以在“输出预设”面板中查看选定输出预设旁边的进度条。
6. 输出生成完成后，单击  **查看输出** ![查看输出](assets/view-output.svg) 图标来查看输出。\
   A **成功** 对话框。
如果输出失败，将显示以下错误消息。
   ![错误日志](assets/error-log.png)

要查看错误日志，请单击 **取消**，将鼠标悬停在选定的预设选项卡上，然后单击 ![选项](assets/options.svg) **选项** > **查看日志**.
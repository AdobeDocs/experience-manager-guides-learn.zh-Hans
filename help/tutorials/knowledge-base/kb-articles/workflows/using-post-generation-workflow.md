---
title: 后生成工作流
description: 以示例介绍帖子生成工作流程
source-git-commit: 447cd512d1b6cdce3bd1ddded1575dab87daa04a
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---


# AEM指南发布 — 帖子生成工作流程

AEM指南让您能够灵活地指定输出后生成工作流。 您可以对使用AEM指南生成的输出执行一些后处理任务。
例如，您可能想要在PDF输出中设置某些属性，或者在生成输出后向一组用户发送电子邮件。


## 使用后代工作流程涉及哪些步骤

### 创建工作流流程

创建基于Java或ECMA的工作流进程，以对生成的输出执行操作。 例如，将某些元数据从源复制到生成的内容或处理生成输出的元数据。
- 我们将举一个使用ECMA脚本创建此类流程的示例（您可以引用附加的包）
- 有关基于Java的工作流流程，请参阅章节“*自定义输出后生成工作流*“ [安装和配置指南](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_Installation-Configuration-Guide_EN.pdf#page=119)


### 创建工作流模型

使用您在上一步中创建的自定义工作流流程，创建工作流模型并将该流程步骤添加到该模型中。
- 您还需要添加强制流程步骤“*完成后生成*”作为工作流的最后一步。

请参阅下面显示的工作流模型示例：

![后代工作流模型](../assets/workflows/pgwf-workflow-model.png)


### 在地图上使用此后生成工作流

生成后工作流是一个属性，可在AEM指南发布机制内的任何输出预设上配置。 示例:

![输出预设的后处理工作流](../assets/workflows/pgwf-preset-settings.png)


假定已创建所选模型。


### 测试

现在，您可以使用此预设运行发布并验证流程步骤输出


## 示例

有关参考，您可以使用以下包并通过包管理器安装该包，以测试示例后生成工作流(*如上面的屏幕截图所述*)

[基于ECMA的后生成工作流模型](../assets/workflows/sample-pgwf-ecma-test-wfmetadata.zip)

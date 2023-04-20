---
title: 在WebDitor工具栏中添加新的自定义可操作按钮
description: 了解如何在浏览器工具栏中添加新的自定义按钮并调用javascript以自定义操作该按钮。
source-git-commit: 26a6acde54953eab1d751f165d0f7769c7e790fe
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 在WebDitor工具栏中添加新的自定义可操作按钮

在本文中，我们将了解如何在浏览器工具栏中添加新的自定义按钮，以及如何调用javascript以执行所需的自定义操作。

向Webeditor添加可操作的按钮涉及以下步骤：
- 在 *ui_config.json* 在需要它的位置
- 在编辑器中注册按钮单击事件，以便用户在单击按钮时执行操作


## 以示例实施

让我们通过一个示例来了解这个示例，其中作者希望将jira引用添加到主题主题部分。 嵌入了jira reference-id的prolog部分可能如下所示：

![包含JIRA ID引用的Prolog部分](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-sample.png)

应从API中检索包含JIRA ID的“change-request-id”元素（例如，基于应用程序描述的特定JIRA查询）。 当用户创作prolog部分时，用户应该能够单击按钮并从Web编辑器工具栏插入jira引用id，类似于：

![Prolog部分 — 添加JIRA引用](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-insertjirareference.png)

当用户单击该按钮时，应显示一个对话框，该对话框应提取可能的选项并允许用户选择所需的JIRA ID，类似于：

![Prolog部分添加JIRA ID对话框](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-insertjirareference-dialog.png)

然后，应将“change-request-id”添加到prolog:

![包含JIRA ID引用的Prolog部分](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-sample.png)



## 实施此


### 通过在Webiditor中配置按钮，将其添加到 *ui_config.json*

使用文件夹配置文件检查 *ui_config.json* 在“XML编辑器配置”选项卡下，将按钮配置JSON添加到“工具栏”组的所需部分

```
{
    "on-click":"insertJIRARef",
    "icon":"linkCheck",
    "variant":"quiet",
    "type":"button",
    "title":"Insert JIRA Reference"
}
```

[使用此链接可了解有关文件夹配置文件和配置ui_config.json的更多信息](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/videos/advanced-user-guide/editor-configuration.html?lang=en)


### 处理新按钮的单击事件

    注意：下面提到的步骤将作为本帖子中附加的包提供


- 保存文件夹配置文件后，在项目目录下创建一个“cq:ClientLibraryFolder”(可以位于 */apps*)并添加属性，如以下屏幕截图所示：
   ![Webeditor的客户端库设置](../../../assets/authoring/webeditor-add-customtoolbarbutton-clientlibrarysettings.png)

```
This example uses "coralui3" library to show a dialog as it is used in the Javascript sample we presented.
You may use different library of your choice.
```

- 在此客户端库文件夹下，创建两个文件，如下所述：
   - *overrides.js*:将具有用于处理“insertJIRARef”的点击事件的javascript代码（使用附加的包获取此javascript的内容）
   - *js.txt*:其中将包含“overrides.js”以启用此javascript

- 保存更改后，您应该可以进行测试。


### 测试

- 打开Web编辑器
- 从用户首选项中选择您在其中添加自定义的文件夹配置文件 *ui_config.json*. 如果将其添加到全局配置文件，则您可能已经在使用了它。
- 打开一个主题，您会注意到工具栏中有一个新按钮“插入日志引用”
- 然后，您可以按照下面给出的方式，将prolog部分添加到主题中，并尝试在prolog元素“change-request-reference”内单击“Insert Jira Reference”按钮

```
<prolog>
    <change-historylist>
        <change-item>
            <change-request-reference>
            </change-request-reference>
            <change-completed></change-completed>
            <change-summary></change-summary>
        </change-item>
    </change-historylist>
</prolog>
```

请参阅下面的屏幕截图，了解其外观：

![测试新按钮](../../../assets/authoring/webeditor-add-customtoolbarbutton-testing.png)


### 附件

- 将安装具有工具栏按钮操作javascript代码的Webeditor客户端库的示例clientlibs包： [使用此链接下载](../../../assets/authoring/webeditor-addbuttonontoolbar-insertjira-clientlib.zip)
- 示例 *ui_config.json* 上传到文件夹配置文件时，您可以执行以下操作： [下载示例ui_config.json](../../../assets/authoring/sample_ui_config_Guides4.2-InsertJiraReference.json)

```
Please note this is compatible to AEM 6.5 and AEM Guides version 4.2.
If you are using a different version please add the toolbar button to the ui_config.json manually.
```

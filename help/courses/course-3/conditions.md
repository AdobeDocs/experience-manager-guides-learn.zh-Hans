---
title: 条件
description: 使用AEM Guid中的条件
exl-id: 2cb670d9-1a22-47c6-8409-52d1d526010a
source-git-commit: 67ba514616a0bf4449aeda035161d1caae0c3f50
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 2%

---

# 条件

在DITA中，条件通常通过“产品”、“平台”和“受众”等属性驱动。 还可以为这些用户指定特定值。 用户可以通过文件夹配置文件控制所有这些操作。

文件中提供了您可选择在本课程中使用的示例文件 [conditions.zip](assets/conditions.zip).

>[!VIDEO](https://video.tv.adobe.com/v/342755?quality=12&learn=on)

## 将条件分配给文件夹配置文件

1. 选择 **文件夹配置文件** 图块。

1. 单击 [!UICONTROL **条件属性**].

1. 单击 [!UICONTROL **编辑**] 在配置文件的左上角。

1. 单击 [!UICONTROL **添加**].

   ![文件夹配置文件中的条件](images/lesson-13/add-name.png)

1. 填写必填字段。

   - 名称应该对应于用于分析的属性。

   - 值是将在DITA代码源中使用的确切条目。

   - 标签是输入属性的用户将看到的单词。

1. 单击“[!UICONTROL **保存**]”。

>[!NOTE]
>
>注意：配置全局配置文件可能是控制属性和值使用的早期有效方法，以便遵循一致的样式指南。

## 将属性分配给元素

如果尚未将自定义文件夹配置文件分配给概念，则您可能希望将属性分配给特定元素，例如段落。

1. 从 **存储库视图**，单击要使用的元素以将其选中。

1. 在 **内容属性** 面板上，单击 [!UICONTROL **属性**] 下拉菜单。

1. 选择要分配的属性。

1. 添加 **值**.

属性和值配对现在已指定给选定的元素。

## 使用条件分配属性和值对

“条件”面板允许对属性和值配对进行受控分配。

1. 修改 **用户首选项**.

   a.单击用户首选项图标。

   ![用户偏好设置图标](images/lesson-13/user-prefs-icon.png)

   b.填妥 **用户首选项** 对话框。 例如：

   ![用户首选项](images/lesson-13/user-preferences.png)

   c.单击 [!UICONTROL **保存**].

1. 从条件面板中，展开Audience和Platform的下拉列表。 请注意，可用的条件特定于文件夹配置文件。

1. 将条件拖放到所需的元素上以进行分配。

## 分配主题方案

主题方案映射是一种专门的ditamap形式，由映射引用。 主题方案用于定义分类。 它们提供对可用值的控制。

1. 导航到 **存储库视图**.

1. 选择引用主题方案动态映射的映射。 此示例使用名为 _设计和布局_.

   ![用户首选项](images/lesson-13/subject-scheme-map.png)

1. 配置用户首选项。

   a.单击 [!UICONTROL **用户首选项**] 图标。

   ![用户首选项](images/lesson-13/user-prefs-icon-2.png)

   b.填充 **用户首选项** 对话框。

   c.单击“基本路径”字段旁边的文件夹符号，选择所需文件的路径。

   d.单击 [!UICONTROL **选择**].

   e.单击 **根映射** 输入路径的字段。

   >[!IMPORTANT]
   >
   >重要信息：选定的根映射必须是包含主题方案的映射。

   ![用户首选项](images/lesson-13/user-preferences-2.png)

   f.通过选择要使用的文件夹来限制显示的资产。

   g.单击 [!UICONTROL **选择**].

   h.单击 [!UICONTROL **保存**].

主题方案现已分配。

## 从“条件”面板中查看“主题方案”

1. 导航到 **编辑器设置**.

1. 选择 **条件** 选项卡。

1. 选中框 **在“条件”面板中显示主题方案**

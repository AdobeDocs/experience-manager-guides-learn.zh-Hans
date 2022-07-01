---
title: 如何添加 [!DNL AEM Guides] 至 [!DNL AEM as a Cloud Service] 环境
description: 了解如何添加 [!DNL AEM Guides] 至 [!DNL AEM as a Cloud Service] 环境
exl-id: a1e020c2-360c-4d71-b5fd-8179d9ceacda
source-git-commit: b5e64512956f0a7f33c2021bc431d69239f2a088
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 0%

---

# [!DNL AEM Guides] as a Cloud Service部署

了解如何添加 [!DNL Guides] 至 [!DNL AEM as a Cloud Service] 环境。

## 通过Cloud Manager git管道手动部署

如果您购买了 [!DNL AEM Guides] as a Cloud Service于2022年3月29日，请按照以下部署说明操作：

* 如果您是从头开始，则可以替换由 [!UICONTROL Cloud Manager] 与以下存储库中的代码（其中已集成XML插件）一起使用：https://github.com/Adobe-TCS/XML-documentation-for-AEMaaCS

* 如果您已在 [!UICONTROL Cloud Manager] git repo中，有关如何在现有代码中添加XML插件的说明，请参阅以下repo:https://github.com/Adobe-TCS/DoX-Installer-for-AEMaaCS

## 通过Cloud Manager部署

如果您是购买过 [!DNL AEM Guides] as a Cloud Service于03/29/2022或之后，按照以下说明添加 [!DNL Guides] 至 [!DNL AEM as a Cloud Service] 环境：

1. 登录 [!UICONTROL Cloud Manager].

1. 编辑要配置的程序 [!DNL AEM Guides].

1. 切换到 **[!UICONTROL 解决方案和附加组件]** 选项卡。

1. 在 **[!UICONTROL 解决方案和附加组件]** 表格，单击 **[!UICONTROL 资产]**.

1. 选择 **[!UICONTROL 指南]** 选择 **[!UICONTROL 保存]**.

您已成功配置程序以自动配置AEM指南解决方案。

![配置AEM指南解决方案](assets/addon-configuration.png)

>[!NOTE]
>
>安装 [!DNL AEM Guides] 在集成程序下的任何环境中，必须运行与该环境关联的管道。 在您的CM Git代码库中，安装无需其他配置 [!DNL AEM Guides].

---
title: 在 [!DNL AEM Guides]
description: 了解如何在 [!DNL Adobe Experience Manager Guides]
role: Admin
exl-id: f479c2cf-5b8b-4517-be97-81303468007a
source-git-commit: b5e64512956f0a7f33c2021bc431d69239f2a088
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 0%

---

# 在 [!DNL AEM Guides] for AEM

添加自定义DITA-OT的步骤介绍在部分中 _使用自定义DITA-OT插件_ 的 _安装和配置指南_.

在高级别上，这些步骤包括：

+ 获取基本DITA-OT
   + 如果要从获取现成DITA-OT的副本，请执行以下操作 [!DNL AEM Guides]，从路径下载 `/etc/fmdita/dita_resources/DITA-OT.zip`
   + 如果您想要获取其他版本，则可以从 [dita-ot repo](https://www.dita-ot.org/download)
+ 对DITA-OT进行类似更改 [添加新插件](https://www.dita-ot.org/dev/topics/plugins-installing.html)，或自定义现有插件（请参阅下面相关链接部分中的示例）
+ 上传 `DITA-OT.zip` 接收 `/apps/<project-folder>/dita_resources` （推荐创建自定义项目文件夹）
+ 通过 **[!UICONTROL 工具]** > **[!UICONTROL 指南]** > **[!UICONTROL DITA配置文件]** （使用上传自定义DITA-OT的DITA-OT路径，请参阅下面的屏幕截图）
   ![DITA配置文件](assets/dita-profile.png)

>[!MORELIKETHIS]
>
>+ [自定义DITA-OT插件示例](https://www.dita-ot.org/dev/topics/pdf-customization.html)


---
title: 验证AEM Guides的安装
description: 了解如何验证AEM Guides的安装
source-git-commit: 5ac066bb8db32944abd046f64da11eeb1bdbe467
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---


# 验证AEM Guides的安装 {#id213BD030FBE}

安装AEM Guides后，您需要验证安装是否成功。 执行以下步骤来验证安装过程：

1. 登录到AEM实例，然后导航到AEM Web Console的“捆绑包”页面。 用于访问包页面的默认URL是：

   ```http
   http://<server name>:<port>/system/console/bundles
   ```

   此时将显示一个捆绑包列表。

1. 通过在过滤文本框中输入fmdita来过滤捆绑列表，然后按 **输入**.

   将筛选捆绑包列表，以显示AEM Guides安装的捆绑包。 如果安装成功，则所有已安装的捆绑包都将具有 **状态** 之 **活动**.

   如果任何捆绑包中没有 **活动** 状态，然后检查AEM日志以解决安装问题。


>[!IMPORTANT]
>
> 您可以考虑使用许多性能优化建议来提高系统性能。 参见 [用于性能优化的Recommendations](download-install-recommend-perf-optimiz.md#) 了解详细信息。

**父主题：**[&#x200B;下载并安装](download-install.md)

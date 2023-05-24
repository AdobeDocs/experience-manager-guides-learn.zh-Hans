---
title: 为AEM站点输出配置有效文件名
description: 了解如何为AEM站点输出配置有效文件名
source-git-commit: 801c306fa120e7889d4b9428fd5bee2849bf1956
workflow-type: tm+mt
source-wordcount: '140'
ht-degree: 0%

---


# 为AEM站点输出配置有效文件名 {#id214GK0X0KXA}

与DITA主题允许的有效文件名字符列表类似，您还可以为AEM站点输出配置有效文件名字符列表。 URL中不允许使用的一些已知字符包括： ```'<>`@$```. 这些字符配置为在生成AEM Site输出文件名时发现时自动转换为下划线“_”。 允许您在AEM Site输出中设置有效字符的配置位于 `com.adobe.fmdita.common.SanitizeNodeNameImpl` 捆绑。 **设置不允许发布到AEM Sites的字符集** 设置为在AEM Site输出文件名中包含要用下划线替换的字符。

**父主题：**[&#x200B;配置文件名](conf-file-names.md)


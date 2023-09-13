---
title: 用于创建和激活包的REST API
description: 了解用于创建和激活包的REST API
source-git-commit: fad5049962f258bbe59c7d172436d82b3d6cd68f
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 0%

---


# 用于创建和激活包的REST API {#id198CF0260Y4}

以下REST API允许您创建和激活CRX包。

## 创建和激活包

一种POST方法，用于创建和激活CRX包。

**请求URL**： http://*&lt;aem-guides-server>*： *&lt;port-number>*/bin/fmdita/activate

**参数**：请求查询包含JSON规则字符串。 POST请求的内容类型必须设置为 `application/json; charset=UTF-8`.

**示例**：以下示例显示使用curl命令的API调用：

    ```
    curl -u &lt;*用户名*>：&lt;*password*> -H &quot;Content-Type： application/json； charset=UTF-8&quot; -k -XPOST-d &quot;{[JSON规则字符串](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}&quot; http://&lt;*aem-guides-server*>：&lt;*port-number*>/bin/fmdita/activate
    ```
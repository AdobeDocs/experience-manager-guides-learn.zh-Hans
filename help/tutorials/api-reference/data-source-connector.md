---
title: 用于注册数据源连接器的REST API
description: 了解用于注册数据源连接器的REST API
source-git-commit: 8707acf3ba01b7488eea6597c434da73a901d037
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 3%

---


# 用于注册数据源连接器的REST API {#id236LG0Y0CXA}

以下REST API允许您注册数据源连接器。

## 注册数据源连接器

注册数据源连接器的GET方法。

**请求 URL**:
`http://server:port/bin/guides/v1/konnect/config/register?path=<uploaded file path>`

**参数**： |名称|类型|必需|描述| --------------------------- |`path`|字符串|是|指向AEM存储库中路径的字符串。 它可以是 `/content/dam or /var/dxml`.|

**示例**:\
`http://host:4502/bin/guides/v1/konnect/config/register?path=/var/dxml/konnect/jira.json`


---
title: 配置查询的LimitReads数
description: 了解如何为查询配置LimitReads的数量
source-git-commit: 801c306fa120e7889d4b9428fd5bee2849bf1956
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 2%

---


# 配置查询的LimitReads数 {#id231RC0HL0ID}

要增加查询一次可读取的节点数，请执行以下步骤：

1. 打开Adobe Experience Manager Web控制台JMX页面。

   用于访问配置页面的默认URL是：

   ```http
   http://<server name>:<port>/system/console/jmx
   ```

1. 搜索并单击 **QueryengineSettings**.

1. 更改属性的值 **限制读取** 属性。

1. 单击“**保存**”。


当增加此属性值时，它有助于为较大的DITA映射生成报告。

**父主题：**[&#x200B;自定义Web编辑器](conf-web-editor.md)

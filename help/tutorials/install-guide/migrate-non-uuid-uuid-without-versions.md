---
title: 将不带版本的非UUID内容转换为UUID内容
description: 了解如何迁移不带版本的非UUID内容。
source-git-commit: c3edc3c637c2757d5c750646d8bd8dec416d26e5
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 0%

---


# 迁移不带版本的非UUID内容

>[!IMPORTANT]
>
> 如果打算忽略或不迁移资产版本，可以选择此迁移方法。


1. 使用AEM桌面应用程序等Adobe工具，直接从AEM Assets UI将资产从非UUID实例下载并上传到UUID实例。

1. 确保您启用了DAM更新资产工作流，并在导入内容以创建GUID后在所有资产上执行该工作流。

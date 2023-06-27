---
title: 用于性能优化的Recommendations
description: 了解Recommendations以实现性能优化
source-git-commit: 6051181e243cf71919901093c1b5590f21832545
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 3%

---


# 用于性能优化的Recommendations {#id213BD0JG0XA}

对于性能优化，请考虑以下几点：

- 要优化内容和索引体验，请参阅 [优化内容搜索和索引](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html) 在AEM文档中。

- 使用自定义DITA-OT进行发布时为Xerces Jar打补丁。 根据您的用例，这是一个强制性配置。 仅当使用自定义DITA-OT发布输出时，才需要此更改。

  *必需的配置*：将自定义DITA-OT包中的Xerces Jar文件替换为附带的OOTB文件。 /libs/fmdita/dita\_resources/DITA-OT.zip文件中提供了默认的OOTB xercesImpl-2.11.0.jar文件。 确保重命名xercesImpl-2.11.0.jar文件以匹配要替换的旧Xerces Jar文件。 这可以在运行时完成。

  此更改减少了发布包含大量主题的DITA映射时的发布时间和内存使用率。


**父主题：**[&#x200B;下载并安装](download-install.md)


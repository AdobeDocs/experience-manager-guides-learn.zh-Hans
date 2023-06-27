---
title: 升级AEM指南
description: 了解如何升级AEM Guides
source-git-commit: 6051181e243cf71919901093c1b5590f21832545
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 0%

---


# 升级AEM指南 {#id213BD050YPH}

1. 访问您的Cloud Manager的Git存储库。

1. 更新dox/dox.installer/pom.xml文件。

1. 将dox.version变量的值更新为Adobe提供的版本详细信息。

1. 提交更改并运行Cloud Manager管道以部署升级后的包。


>[!NOTE]
>
> 有关使用CI/CD管道的更多详细信息，请参阅 [在AdobeCloud Manager中使用CI/CD管线](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/cloud-manager/use-the-cicd-pipeline-in-cloud-manager-for-aem.html).

## 清除浏览器缓存

完成升级过程后，所有用户必须先清除浏览器缓存，然后才能使用AEM Guides的升级版本。

**父主题：**[&#x200B;下载并安装](download-install.md)


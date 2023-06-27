---
title: 验证AEM Guides的安装
description: 了解如何验证AEM Guides的安装
source-git-commit: 6051181e243cf71919901093c1b5590f21832545
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 5%

---


# 验证AEM Guides的安装 {#id213BD030FBE}

安装AEM Guides后，您需要验证安装是否成功。 执行以下步骤来验证安装：

1. 访问Cloud Service的开发人员控制台。

   有关访问开发人员控制台的详细信息，请参阅 [开发人员控制台访问](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html) 在AEM文档中。

1. 访问AEM中的OSGi包列表。

   有关访问捆绑包的详细信息，请参阅 [包](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=en#bundles) 在AEM文档中。

1. 在捆绑列表中搜索fmdita并检查其状态。

   状态应显示 *活动* 成功部署的包。 如果有任何捆绑包的状态不是“活动”，请检查AEM日志以解决安装问题。


**父主题：**[&#x200B;下载并安装](download-install.md)


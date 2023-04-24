---
title: 上传文件
description: 了解如何上传文件
source-git-commit: cc0fbca257d82cc82db5b5da8d263309fd71de55
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 0%

---


# 上传文件 {#id176FF000JUI}

您很可能拥有要与AEM指南一起使用的现有DITA内容存储库。 对于此类现有内容，您可以使用以下任何方法将内容批量上传到AEM存储库：

>[!IMPORTANT]
>
> 请参阅 [将数字资产添加到Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html) 有关AEM中支持的内容上传方法的详细信息。

## 资产控制台用户界面

您可以在桌面上选择内容，然后将AEM用户界面\（Web浏览器\）拖动到目标文件夹。 有关更多详细信息，请参阅 [上传资产](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html#upload-assets) 在AEM文档中。

## AEM桌面应用程序

如果您是创意专业人士，并且想要管理本地桌面上的资产，请使用AEM桌面应用程序。 您可以使用桌面应用程序打开和编辑这些资产。 您还可以维护版本并与其他用户共享您的文件。 有关更多详细信息，请参阅 [AEM桌面应用程序](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html).

## 资产批量摄取

如果您有大规模迁移和偶尔进行批量摄取，请使用资产批量摄取来上传内容。 使用此工具，您可以从Azure或S3等受支持的数据存储中上传批量内容。 有关更多详细信息，请参阅 [资产批量摄取](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=en#asset-bulk-ingestor).

## 使用FrameMaker批量上传

Adobe FrameMaker附带一个功能强大的AEM连接器，可让您轻松上传现有的DITA和其他FrameMaker文档\(`.book` 和 `.fm`\)到AEM。 您可以使用各种文件上传功能，例如上传单个文件、上传包含或不包含依赖项的完整文件夹\（如内容引用、交叉引用和图形\）。

有关在FrameMaker中使用批量上传功能的更多详细信息，请参阅部分 *创建CRX文件夹并上传文件* 在《FrameMaker用户指南》中。

## 上传内容时处理错误 {#id201MI0I04Y4}

如果上传一个或多个文件失败，则在上传过程结束时会显示提示，其中包含无法上传的文件列表：

![](images/uuid-files-failed-to-upload_cs.png){width="650" align="center"}

有关各种文件上传方案的详细信息，请参阅 [上传DITA内容](authoring-file-management.md#).

如果您使用AEM桌面应用程序或资产批量摄取等工具，则对重复文件执行的操作将由AEM服务器中的设置进行控制。 请联系您的系统管理员以了解此配置。

**父主题：**[&#x200B;管理内容](authoring.md)


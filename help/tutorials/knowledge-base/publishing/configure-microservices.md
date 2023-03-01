---
title: 为AEM Guidesas a Cloud Service配置新的基于微服务的发布
description: 了解如何为AEM Guides配置新的基于微服务的发布。
source-git-commit: c2981b5635353eb84c9e46a03de1b1ed07aa5bf3
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 0%

---

# 为AEM Guidesas a Cloud Service配置新的基于微服务的发布

新的发布微服务使用户能够在AEM Guidesas a Cloud Service上同时运行大量发布工作负载，并利用业界领先的Adobe I/O Runtime无服务器平台。

对于每个发布请求，AEM Guidesas a Cloud Service会运行一个单独的容器，该容器会根据用户请求水平缩放。 这使用户能够运行多个发布请求，并获得比其大型本地AEM服务器更好的性能。

由于新的云发布服务受基于Adobe IMS JWT的身份验证保护，因此客户应遵循以下给定步骤，将其环境与Adobe的安全基于令牌的身份验证工作流集成，并开始使用新的基于云的可扩展发布解决方案。


## 在Adobe Developer控制台中创建IMS配置

**创建配置所需的角色**：系统管理员

执行以下步骤可在Adobe Developer控制台中创建IMS配置：

1. 打开开发人员控制台： `https://developer.adobe.com/console`.

1. 切换到 **项目** 从上往下按Tab键。

   <img src="assets/projects-tab.png" alt="“项目”选项卡" width="500">

1. 要创建新的空项目，请选择 **空项目** 从 **创建新项目** 下拉菜单。

   <img src="assets/create-new-project.png" alt="创建新项目" width="500">

1. 选择 **API** 从 **添加到项目** 用于将IO管理API添加到项目的下拉列表。

   <img src="assets/add-project.png" alt="添加项目" width="300">

   <img src="assets/io-management-api.png" alt="io管理" width="500">

1. 在添加API时创建新的私钥/公钥对。 这将自动下载系统上的私钥。

   <img src="assets/generate-key-pair.png" alt="生成密钥对" width="500">

1. 保存配置的API。

   <img src="assets/save-api.png" alt="保存api" width="600">

1. 返回到 **项目** 选项卡，然后单击 **项目概述** 左边。

   <img src="assets/project-overview.png" alt="项目概述" width="500">

1. 单击 **下载** 按钮以下载服务JSON。

   <img src="assets/download-json.png" alt="下载json" width="500">

您现在已配置JWT身份验证详细信息，并且已下载私钥和服务详细信息JSON。 请准备好这两个文件，因为下一节需要用到这些文件。

### 将IMS配置添加到环境

执行以下步骤以将IMS配置添加到环境中：

1. 打开Experience Manager，然后选择包含要配置的环境的程序。
1. 切换到 **环境** 选项卡。
1. 单击要配置的环境名称。 这应该会将您导航到“环境信息”页面。
1. 切换到 **配置** 选项卡。
1. 上传私钥和项目JSON，如下面的屏幕快照所示。 确保您使用的名称和配置与下面高亮显示的名称和配置相同。

   <img src="assets/ims-config-environment.png" alt="ims配置" width="500">

>[!NOTE]
>
> 您需要打开、复制私钥和服务详细信息JSON文件的内容，并将其粘贴到配置面板的值列，如上面的屏幕快照所示。

将IMS配置添加到环境后，请执行以下步骤，以使用OSGi将这些属性与AEM Guides链接：

1. 在您的Cloud Manager Git项目代码中，添加以下两个给定的文件(有关文件内容，请参阅 [附录](#appendix))。

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`
   * `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`
1. 确保新添加的文件包含在您的 `filter.xml`.
1. 提交并推送您的Git更改。
1. 运行管道以将更改应用于环境。

完成此操作后，您应该能够使用新的基于微服务的云发布。

## 附录 {#appendix}

**文件**：
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**内容**:

```
{
  "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
  "private.key": "$[secret:PRIVATE_KEY]"
}
```

**文件**： `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`

**内容**:

```
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:jcr="http://www.jcp.org/jcr/1.0" xmlns:sling="http://sling.apache.org/jcr/sling/1.0"
          jcr:primaryType="sling:OsgiConfig"
          dxml.publish.microservice.url="https://adobeioruntime.net/api/v1/web/543112-guidespublisher/default/publishercaller.json"
          dxml.use.publish.microservice="{Boolean}true"
/>
```
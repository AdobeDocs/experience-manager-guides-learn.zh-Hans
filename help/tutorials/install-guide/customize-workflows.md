---
title: 配置和自定义工作流
description: 了解如何配置和自定义工作流
source-git-commit: 9fe396dcfd2e3570ec386c958d7d4efdb4d608e5
workflow-type: tm+mt
source-wordcount: '1781'
ht-degree: 3%

---


# 配置和自定义工作流 {#id181AI0OJ0RO}

通过工作流，您可以自动化Adobe Experience Manager \(AEM\)活动。 工作流包含一系列按特定顺序执行的步骤。 您可以定义要在每个步骤中执行的不同活动。 例如，您可以在创建主题审阅时向组中的所有审阅人发送电子邮件通知。 或者，在输出生成任务完成时向发布者发送通知。

有关AEM中工作流的详细信息，请参阅：

- [管理工作流](https://helpx.adobe.com/cn/experience-manager/6-5/sites/administering/using/workflows.html)

- 应用和参与工作流： [使用工作流](https://helpx.adobe.com/cn/experience-manager/6-5/sites/authoring/using/workflows.html).

- 创建工作流模型和扩展工作流功能： [开发和扩展工作流](https://helpx.adobe.com/cn/experience-manager/6-5/sites/developing/using/workflows.html).

- 提高使用大量服务器资源的工作流的性能： [并发工作流处理](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/configuring-performance.html#ConfiguringforPerformance).


本主题中的部分将指导您逐步完成AEM Guides中提供的默认工作流中的各种自定义设置。

## 自定义审核工作流 {#id176NE0C00HS}

每个组织的内容创作团队都以特定的方式工作，以满足其业务要求。 有些组织设有专门的编辑人员，而有些其他组织则设有自动编辑审查系统。 例如，在组织中，典型的创作和发布工作流可能包括以下任务：每当作者完成创作内容时，它会自动转到审阅人，审阅完成后，它转到发布者来生成最终输出。 在AEM中，您可以采用流程的形式组合对内容和资产执行的活动并将其映射到AEM工作流。 有关AEM中工作流的详细信息，请参阅 [管理工作流](https://helpx.adobe.com/cn/experience-manager/6-5/sites/administering/using/workflows.html) 在AEM文档中。

AEM Guides允许您自定义默认的审阅工作流。 您可以将以下四个与自定义审阅相关的流程用于其他创作或发布工作流。

- **创建审核**：此流程用于准备创建审阅任务所需的元数据。 例如，它将为审阅人分配审阅权限、将主题的状态设置为正在审阅、设置审阅时间表等。 在四个流程中，这是自定义工作流中必须包含的唯一一个必需流程。 在工作流中，您可以选择包括或排除其他三个进程。

- **分配审阅任务**：此进程创建审阅任务并将任务通知发送给发起者和审阅者。

- **发送审核电子邮件**：此过程会将审阅电子邮件发送给发起人和审阅人。

- **计划关闭审阅的作业**：此过程可确保审核过程在到达截止日期时完成。


创建自定义审阅工作流时，第一项任务是设置创建审阅流程所需的元数据。 为此，您可以创建一个ECMA脚本。 下面提供了分配元数据的ECMA脚本示例：

```json
var workflowdata=workItem.getWorkflowData();
workflowdata.getMetaDataMap().put("initiator","admin");
workflowdata.getMetaDataMap().put("operation","AEM_REVIEW");
workflowdata.getMetaDataMap().put("orgTopics","/content/dam/xml-solution/review.xml");
workflowdata.getMetaDataMap().put("payloadJson","{\"base\":\"/content/dam/xml-solution\",\"asset\":[\"/content/dam/xml-solution/review.xml\"],\"referrer\":\""}");
workflowdata.getMetaDataMap().put("deadline","2017-06-27T13:19:00.000+05:30");
workflowdata.getMetaDataMap().put("title","Review through custom workflow");
workflowdata.getMetaDataMap().put("description","Initiate this review process using the AEM workflow");
workflowdata.getMetaDataMap().put("assignee","user-one", "user-two");
workflowdata.getMetaDataMap().put("status","1");
workflowdata.getMetaDataMap().put("projectPath","/content/projects/review");
workflowdata.getMetaDataMap().put("startTime", System.currentTimeMillis());
```

您可以在中创建此脚本 `/etc/workflows/scripts` 节点。 下表描述了此ECMA脚本所分配的属性：

| 属性 | 类型 | 描述 |
|--------|----|-----------|
| `initiator` | 字符串 | 启动审阅任务的用户的用户ID。 |
| `operation` | 字符串 | 静态值设置为 `AEM_REVIEW`. |
| `orgTopics` | 字符串 | 共享以供审阅的主题的路径。 指定多个以逗号分隔的主题。 |
| `payloadJson` | JSON对象 | 指定以下值：<br> - `base`：包含已发送以供审阅的主题的父文件夹的路径。<br>- `asset`：发送以供审阅的主题路径。 <br>- `referrer`：将其留空。 |
| `deadline` | 字符串 | 指定时间 `yyyy-MM-dd'T'HH:mm:ss.SSSXXX` 格式。 |
| `title` | 字符串 | 输入审阅任务的标题。 |
| `description` | 字符串 | 输入审阅任务的描述。 |
| `assignee` | 字符串 | 要向其发送主题以供审阅的用户的用户ID。 |
| `status` | 整数 | 静态值设置为1。 |
| `startTime` | 长整型 | 使用 `System.currentTimeMillis()` 函数以获取当前系统时间。 |

创建脚本后，在工作流中调用创建审阅进程之前调用该脚本。 然后，根据您的要求，您可以调用其他审阅工作流进程。

### 从清除配置中删除审核工作流

为了提高工作流引擎性能，您可以定期从AEM存储库中清除已完成的工作流实例。 如果您使用的是默认AEM配置，则会在特定时间段后清除所有已完成的工作流实例。 这也会导致所有审阅工作流从AEM存储库中清除。

您可以通过从自动清除配置中删除审核工作流模型\(information\)来阻止自动清除审核工作流。 您需要使用 **AdobeGranite工作流清除配置** 要从自动清除列表中删除审核工作流模型。

在 **AdobeGranite工作流清除配置**，请确保至少列出一个可安全清除的工作流。 例如，您可以使用AEM Guides创建的以下任何工作流：

- /etc/workflow/models/publishditamap/jcr：content/model
- /etc/workflow/models/post-dita-project-creation-tasks/ jcr：content/model

在中添加工作流 **AdobeGranite工作流清除配置** 确保AEM仅清除配置中列出的那些工作流。 这会阻止AEM清除审阅工作流信息。

有关配置的更多详细信息 **AdobeGranite工作流清除配置**，请参见 *管理工作流实例* 在AEM文档中。

### 自定义电子邮件模板

许多AEM Guides工作流都使用电子邮件通知。 例如，如果您启动审阅任务，则会向审阅人发送电子邮件通知。 但是，为确保发送电子邮件通知，您必须在AEM中启用此功能。 要在AEM中启用电子邮件通知，请参阅文章 [配置电子邮件通知](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=zh-Hans) 在AEM文档中。

AEM Guides包含一组您可自定义的电子邮件模板。 执行以下步骤可自定义这些模板：

1. 登录AEM并打开CRXDE Lite模式。

1. 在“导航”选项卡中，转到以下位置：

   `/libs/fmdita/mail`

   >[!NOTE]
   >
   > 请勿使默认配置文件中的任何自定义设置在 ``libs`` 节点。 您必须创建一个叠加 ``libs`` 中的节点 ``apps`` 节点并更新以下文件中的所需文件： ``apps`` 仅节点。

1. 邮件文件夹包含以下可自定义的模板：

   | 模板文件名 | 描述 |
   |-----------------|-----------|
   | closereview.html | 在关闭审核任务时，将使用此电子邮件模板。 |
   | createreview.html | 创建新审阅任务时使用此电子邮件模板。 |
   | reviewapproval.css | 此CSS文件包含电子邮件模板的样式。 |


## 自定义输出后生成工作流 {#id17A6GI004Y4}

AEM Guides使您能够灵活地指定输出后生成工作流程。 您可以对使用AEM Guides生成的输出执行一些后处理任务。 例如，您可能希望在生成的AEM Site输出中应用一些CQ标记，或在PDF输出中设置某些属性，或者在生成输出后向一组用户发送电子邮件。

您可以创建新的工作流模型以用作输出后生成工作流。 触发输出后生成工作流时，输出生成工作流通过工作流元数据映射共享上下文信息，您可以使用工作流元数据映射对生成的输出执行处理。 下表描述了作为元数据共享的上下文信息：

| 属性 | 类型 | 描述 |
|--------|----|-----------|
| ``outputName`` | 字符串 | 用于生成输出的输出预设的名称。 |
| `generatedPath` | 字符串 | DAM中存储生成的输出的路径。 |
| `outputType` | com.adobe.fmdita.output.OutputType | 输出预设的类型。 |
| `outputTitle` | 字符串 | 输出预设的标题。 |
| `outputHistoryPath` | 字符串 | 历史记录节点的存储库路径。 |
| `isSuccess` | 布尔值 | 描述输出生成过程的最终状态（成功或失败）的标记。 |
| `logPath` | 字符串 | DAM中保存输出生成日志的路径。 |
| `generatedTime` | 长整型 | 触发输出生成过程的时间。 |
| `initiator` | 字符串 | 触发输出生成工作流的用户的用户ID。 |

要使用输出生成元数据，您可以创建ECMA脚本或OSGi捆绑包。 下面给出了使用元数据的ECMA脚本示例：

>[!NOTE]
>
> 您可以在中创建此脚本 ``/etc/workflows/scripts`` 节点。

```json
var session = workflowSession.getSession(); // Obtain session object to read/write the repository.
var payload = workItem.getWorkflowData().getPayload().toString(); // Get the workflow payload (the ditamap file on which the generation was triggered)
var metadata = workItem.getWorkflowData().getMetaDataMap(); // Get the workflow metadata object
var generatedPath = metadata.get("generatedPath"); // supplied by AEM Guides
var username = metadata.get("initiator"); // supplied by AEM Guides
var successful = metadata.get("isSuccess"); // supplied by AEM Guides
var title = metadata.get("outputTitle"); // supplied by AEM Guides
var subject = "Output Generation Finished";
var message = "Generation of output " + title + " just finished " + 
(successful ? "successfully. " : "unsuccessfully. ");
    message += "It was triggered by " + username;    
if (successful) {
    message += "<br/><br/>The path to the generated output is " + 
generatedPath;
}
/*
    MailerAPI.sendMail("dl-docs-authors", subject, message);
*/
```

创建脚本后，在工作流中调用自定义脚本。 然后，根据您的要求，您可以调用其他工作流进程。 设计自定义工作流后，调用 *最终确定帖子生成* 作为工作流进程的最后一步。 此 *最终确定帖子生成* 步骤可确保输出生成任务的状态更新为 *已完成* 在输出生成过程完成时。 创建自定义输出后生成工作流后，可以使用任何输出生成预设来配置该工作流。 在中选择所需的工作流 *运行后期生成工作流* 所需的预设的属性。 使用配置的输出预设运行输出生成任务时，任务状态\（在“输出”选项卡中\）将更改为 *后处理*.

## 自定义更新资产工作流 {#id18C3D0I0B5Z}

默认情况下， *DAM更新资产* 每当创建或更新任何AEM Asset \（XML或非XML\）时，都会触发工作流。 例如，在创建主题或更新主题时， *DAM更新资产* 工作流将执行。 此 *DAM更新资产* 工作流会尝试从资产中提取相关元数据。 开箱即用 *资产更新工作流* 没有从DITA文件和 *DAM更新资产* 工作流在执行时生成大量日志。 如果要避免额外的日志，可以配置工作流以跳过所有XML文件的处理。

执行以下步骤以自定义 *DAM更新资产* 工作流：

1. 打开 **工作流启动器** 页面。

   用于访问“工作流启动器”页面的默认URL为：

   ```http
   http://<server name>:<port>/libs/cq/workflow/admin/console/content/launchers.html
   ```

1. 从工作流启动器的列表中，打开 **DAM更新资产** 工作流。

1. 使用以下表达式添加条件：

   ```json
   jcr:content/metadata/dc:format!=application/xml
   ```

1. 单击 **保存并关闭**


## 配置后处理XML工作流 {#id18CJB03J0Y4}

AEM Guides创建了一系列允许您在AEM中使用DITA内容的工作流。 例如，有些工作流会在您上传DITA内容或更新现有内容时执行。 这些工作流解析DITA文档并执行各种任务，例如设置元数据、将默认输出预设添加到新的DITA映射以及其他相关任务。

>[!NOTE]
>
> 要自定义或扩展默认后处理工作流，您可以使用 *Adobe Experience Manager Guides的API参考*.

以下属性控制AEM Guides执行后处理工作流的方式：

>[!NOTE]
>
> 可通过Web控制台访问以下属性： http://&lt;server name=&quot;&quot;>：&lt;port>/system/console/configMgr.

| 属性 | 包名称 | 描述 |
|--------|-----------|-----------|
| 动态外置 | `com.adobe.fmdita.postprocess.PostProcessObservation` | 对于尚未对其执行后处理的所有文件，它通过解析主题文件来检索传出引用。 建议禁用此选项，因为如果要处理的文件数量很大，此选项可能会使系统过载。 |
| 后处理线程 | `com.adobe.fmdita.config.ConfigManager` | 设置用于后处理工作流的后处理线程数。 <br>默认值为 1。 |


---
title: 从Non-UUID迁移到UUID内容
description: 了解如何将非UUID内容迁移到UUID
source-git-commit: 5ac066bb8db32944abd046f64da11eeb1bdbe467
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---


# 从Non-UUID迁移到UUID内容 {#id226TI0U20XA}

>[!IMPORTANT]
>
> 您可以将非UUID内容迁移到UUID服务器。 要迁移到UUID服务器，您应该安装带有AEM guides版本4.0的非UUID服务器。

执行以下步骤来迁移非UUID内容：

>[!NOTE]
>
> 每个步骤都非常重要，缺少任何步骤都可能导致服务器数据失败或损坏。 确保完成所有步骤。

1. 确保 **启用后处理工作流启动器** 在 *com.adobe.fmdita.config.ConfigManager* 和 **启用版本后处理** 在 *com.adobe.fmdita.postprocess.version.PostProcessVersionObservation* 已启用。

   ```http
   http://<server name>:<port>/system/console/configMgr/com.adobe.fmdita.config.ConfigManager
   ```

1. 与非UUID版本相比，安装下一个主要发行版的UUID版本。 例如，如果您使用的是4.0非UUID内部版本，则需要安装UUID版本4.1。

1. 在“启动器”选项卡中，禁用以下工作流以及使用中的启动器在/content/dam上运行的任何其他工作流 `http://localhost:4502/libs/cq/workflow/content/console.html`：

   - **DAM更新资产** 工作流
   - **DAM元数据写回** 工作流

1. 禁用 **启用后处理工作流启动器** 在 *com.adobe.fmdita.config.ConfigManager* 和禁用 **启用版本后处理** 在 *com.adobe.fmdita.postprocess.version.PostProcessVersionObservation*.

   ```http
   http://<server name>:<port>/system/console/configMgr/com.adobe.fmdita.config.ConfigManager
   ```

1. 添加单独的日志程序 `com.adobe.fmdita.uuid.upgrade.UuidUpgrade.`

   浏览器响应也可在/content/uuid-upgrade/logs中找到。

1. 在具有较小数据的文件夹上运行给定查询 `doReviews=false` 在/content/dam上运行它之前： `http://localhost:4502/bin/dxml/uuid_upgrade?root=/content/dam/test&doReviews=false`

   >[!TIP]
   >
   >  您可以检查文件夹中的所有文件是否都已正确升级，以及所有功能是否仅对该文件夹起作用。

**查询的参数：**

    - &#39;root&#39;：必须升级的根文件夹\（对所有存储库使用/content/dam）。\)
    - &#39;doReviews&#39;： true/false \(如果必须升级审核，则不会升级。 默认值为false。\)
    - &#39;doBaselines&#39;： true/false \(是否必须升级基线。 默认值为true。\)
    - &#39;processLevel&#39;： -1\（失败但不还原\）、0\（失败但还原\）、1\（失败但出现错误\）、2\（已成功升级\） \(在失败后重试脚本时，将仅再次处理具有“fmUpgradeStatus”&lt;= processLevel的文件，否则将忽略该文件。 默认值为 1。\)
    - &#39;ignoreImageVersions&#39;： true/false \(忽略图像版本的处理。 默认值为false。\)
    >[！注意]
    >
    >我们可以在文件夹级别或完整内容/dam或同一文件夹上运行内容迁移\（重新运行迁移\）。

1. 成功迁移服务器后，请启用以下工作流和后处理以继续在服务器上工作：

   - **DAM更新资产** 工作流
   - **DAM元数据** 工作流

>[!NOTE]
>
> 如果某些文件在迁移前未处理或损坏，则即使在迁移后，它们仍会保持损坏状态。


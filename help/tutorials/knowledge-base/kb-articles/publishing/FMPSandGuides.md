---
source-git-commit: da88662ec770b12a25ba4afd876e6eeac793cfc5
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 0%

---


# FrameMaker Publishing Server (FMPS)和AEM指南

**如果您希望获得高质量的自动发布，AEM Guides与FrameMaker Publishing Server的集成可以为您的解决方案提供帮助。\
下面的文章将帮助您使用AEM Guides设置和运行FMPS。**

## FMPS与AEM Guides的兼容性：

- 与4.1 AEM Guides的兼容性： [链接](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/release-notes/on-prem-release-notes/release-notes-4.1.html?lang=en/#compatibility-matrix)

- 与4.0 AEM Guides的兼容性： [链接](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-4-0.html/#Compatibility%20matrix)

- 未来版本： [链接](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/latest-release-info.html?lang=en)

## 安装:

### AEM Guides：

安装和配置请参阅： [链接](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf)

### FMPS：

对于FMPS安装，您可以参考给定的 [视频链接](https://www.youtube.com/watch?v=2deelyM5VA8&amp;t) 或 [文档](https://help.adobe.com/en_US/framemaker/server/index.html#t=fmps-user-guide%2Finstall_config_fmps.html%23install_config_fmps&amp;rhtocid=_2)

## 所需的配置：

可以使用FrameMaker Publishing Server (FMPS)输出DITA内容。 您可以用FMPS支持的多种格式中的任意格式创建输出。
在Web控制台中，修改com.adobe.fmdita.config.ConfigManager包的以下属性以将AEM Guides设置为使用FMPS。

要打开Web控制台，请转到URL访问http://\&lt;server name=&quot;&quot;>：\&lt;port>/system/console/configMgr 。

**配置属性及其描述：** [链接](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf#page=89)

## 正在运行测试：

使用FMPS，您可以自动发布 **PDF，响应式HTML5**、和 **Epub** 用于DITA和FM资产。

从“使用生成PDF”菜单中，选择FrameMaker Publishing Server。

用户可以提供“Settings File(.sts)”和“ditaval”。 将基于您提供的条件使用Ditaval进行筛选。

- **设置文件**：FrameMaker /FMPS发布设置，其中包含您希望FMPS在发布时遵循的所有设置例如： 、使用自定义模板生成输出、生成标记和出血(PDF) 、使用目录生成PDF、索引等。
- **存在FMPS：** 预定义的Ditaval和设置文件组合，用户可以预创建FMPS预设，可以重复用于发布需要，而不是提供单独的Ditaval和设置文件。

**注意：**  如果您未选择任何设置或FMPS预设，则FMPS将使用默认系统设置发布。

如果您选择了FMPS预设，并且还从AEM提供了设置/Ditaval文件，则会发生冲突，并且FMPS预设将优先于自定义设置/Ditaval文件。

### 使用FMPS进行基线发布：

您可以使用FMPS2020.0.2或更高版本发布已创建的基线。

**开始使用的FMPS设置文件（.sts文件）示例：** [链接](https://acrobat.adobe.com/link/track?uri=urn:aaid:scds:US:ef750752-7a7e-4e51-923e-6b7d9861ed54) （解压缩此文件）

## 常见问题和疑难解答：

- ### FMPS发布失败，出现“超时异常”

检查并增加/system/console/configMgr/com.adobe.fmdita.config.ConfigManager中“FMPS超时”（秒）的值

- ### 无法在下拉列表中获取FMPS预设

确保在服务器上创建了预定义的FMPS预设，并且您的连接设置正确。

- ### 发布时出现空白PDF。

如果您使用的是UUID，请确保已选中FrameMaker EditPreferences中的“使用基于UUID的引用”，对于非UUID AEM指南，则反之亦然

- ### 我的设置/Ditaval未应用于最终发布的输出

确保没有同时选择Setting/Ditaval文件和FMPS预设。使用FrameMaker手动验证输出

- ### 未从FMPS发布基线

基线发布与FMPS2020.0.2或更高版本兼容。\
确保正确创建了基线。要验证，请转到映射仪表板主题下载映射并选择“使用基线”。

- ### 从FMPS发布任务所花的时间比其他引擎多。

存在理想的固定标头约。 从FMPS发布时需要3-4分钟（而不是其他引擎），如果您认为持续时间更长，请联系FMPS管理员或联系Adobe支持部门。

## 其他资源：

### [FMPS学习和支持](https://helpx.adobe.com/support/framemaker-publishing-server.html)

### [AEM学习和支持](https://helpx.adobe.com/in/support/xml-documentation-for-experience-manager.html)

### [FrameMaker和FMPS社区](https://community.adobe.com/t5/framemaker/ct-p/ct-framemaker?page=1&amp;sort=latest_replies&amp;lang=all&amp;tabid=all)

### [AEM Guides社区](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation)

---
title: AEM指南版本
description: 最新AEM指南版本和先决条件AEM版本
exl-id: 780697a9-bdc6-40c2-b258-64639fe30f88
source-git-commit: f74a9168708299d66d014dbc4bf280a1a4f07592
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 0%

---

# [!DNL AEM Guides] 发行版本

[!DNL Adobe Experience Manager Guides] 是部署在AEM上的应用程序。 它是功能强大的企业级组件内容管理解决方案(CCMS)，在Adobe Experience Manager中支持本机DITA，使AEM能够处理基于DITA的内容创建和交付。

AEM指南包有两个变体 — UUID内部版本和非UUID内部版本。

## UUID和非UUID内部版本

UUID内部版本与非UUID内部版本之间的主要区别如下：

|  | 非UUID内部版本 | UUID内部版本 |
|---|---|---|
| **资产标识** | 所有资产均使用存储库中资产的路径进行标识。 | 所有资产均使用其UUID（首次上传资产时系统生成的唯一ID）进行标识。 |
| **参考创建** | 所有内容引用均基于其路径创建。 | 所有内容引用均基于其UUID进行创建。 |

### UUID构建的好处

* UUID安装的性能更高：
   * 引用与路径无关：引用管理系统了解这些链接，因为引用是基于UUID而不是路径创建的。
   * 移动/更新操作非常有效：即使资产移动到存储库中的其他路径，UUID也会保持不变。 因此，在移动/更新操作中，无需进行任何处理即可为资产之间的引用添加修补程序。
* UUID内部版本具有前瞻性，因为我们也将此框架用于AEM指南的云设置。


### 在两个内部版本之间进行选择

* 如果您是新客户，我们建议您使用UUID内部版本。
* 如果您是现有客户，则可以选择转为使用UUID内部版本，因为现在可以从非UUID内部版本迁移到UUID内部版本。 有关更多详细信息，请参阅 *非UUID到UUID内容迁移* 部分 **安装和配置Adobe Experience Manager指南。**

>[!NOTE]
>
>* 客户在首次设置时将需要确定UUID模式与非UUID模式之间的关系（如果您需要帮助，请联系客户成功经理以帮助您根据您的用户情况做出决策）。
>* 从一个AEM指南版本升级到较新版本时，客户需要确保选择相同的模式（UUID/非UUID）来匹配其现有模式。 非UUID内部版本不应直接升级到UUID内部版本。 从非UUID内部版本迁移到UUID内部版本时，需要迁移内容。


**升级内部版本**

从旧版本升级到较新版本的 [!DNL AEM Guides]，则可能需要执行迁移脚本。 有关升级说明，请参阅发行说明和特定于版本的文档。

并非所有升级路径都直接受支持。 例如，只能从版本3.8直接升级到版本4.0。如果您使用的是3.8之前的版本，请参阅特定于您的版本的文档以了解升级说明 [帮助存档](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).
请联系您的客户成功经理以验证升级路径。

**[!DNL AEM Guides]内部版本**

以下列表包含最新的 [!DNL AEM Guides] 包可用于在AMS或On-Prem上安装，相应的AEM版本（先决条件），包的下载链接以及其他有用信息。 建议仅使用 [!DNL AEM Guides]. 如果出于某些原因，您需要访问旧版本，请联系您帐户的客户成功经理。

>[!NOTE]
>
>请联系您的客户成功经理，以访问 [!DNL AEM Guides] 为AEMas a Cloud Service构建。

| [!DNL AEM Guides] 发行版 | 发行说明 | AEM先决条件 | 生成下载链接 |
|---|---|---|---|
| **AEM指南4.1** | [4.1.x发行说明](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/release-notes/on-prem-release-notes/release-notes-4.1.html) | **非UUID和UUID 4.1.2**<br><br> AEM 6.5 SP13、SP12、SP11或SP10 <br>Java:11或8 <br><br>**非UUID和UUID 4.1**<br><br> AEM 6.5 SP13、SP12、SP11或SP10 | **非UUID**: <br> **AEM 6.5** <br>[4.1](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1%2F4-1-non-uuid%2Fcom.adobe.fmdita-6.5-4.1.159.zip)<br>[4.1.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1-2%2F4-1-2-non-uuid%2Fcom.adobe.fmdita-6.5-sp-4.1.2.11.zip)<br>[4.1.3](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1-3%2F4-1-3-non-uuid%2Fcom.adobe.fmdita-6.5-sp-4.1.3.2.zip)<br><br> **UUID** <br>**AEM 6.5** <br>[4.1](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1%2F4-1-uuid%2Fcom.adobe.fmdita-6.5-uuid-4.1.159.zip)<br>[4.1.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1-2%2F4-1-2-uuid%2Fcom.adobe.fmdita.uuid-6.5-sp-4.1.2.11.zip)<br>[4.1.3](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1-3%2F4-1-3-uuid%2Fcom.adobe.fmdita.uuid-6.5-sp-4.1.3.2.zip) |
| **AEM指南4.0** | [4.0.x发行说明](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-4-0.html) | **非UUID和UUID 4.0.3**<br> AEM 6.5 SP12、SP11、SP10或SP9 <br>Java:11或8 <br><br> <br>**非UUID和UUID 4.0.2** <br> AEM 6.5 SP12、SP11、SP10或SP9 <br>Java:11或8 <br><br> **非UUID和UUID 4.0** <br> AEM 6.5 SP11、SP10或SP9 | **非UUID**: <br> **AEM 6.5** <br>[4.0.3](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-0-3%2F4-0-2-non-uuid%2Fcom.adobe.fmdita-6.5-hotfix-4.0.3.1.zip)<br>[4.0.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-0-2%2F4-0-2-non-uuid%2Fcom.adobe.fmdita-6.5-sp-4.0.2.10.zip)  <br> [4.0](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/4-0/4-0-non-uuid/com.adobe.fmdita-6.5-4.0.70.zip)  <br><br> **UUID** <br>**AEM 6.5**  <br>[4.0.3](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-0-3%2F4-0-3-uuid%2Fcom.adobe.fmdita.uuid-6.5-hotfix-4.0.3.1.zip) <br>[4.0.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-0-2%2F4-0-2-uuid%2Fcom.adobe.fmdita.uuid-6.5-sp-4.0.2.10.zip)<br> [4.0](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/4-0/4-0-uuid/com.adobe.fmdita-6.5-uuid-4.0.70.zip) |
| **AEM指南3.8.5** <br> 3.8.5是3.8之上的SP版本。 <br>3.8版本不能独立安装，因为3.8.5 SP包含关键修复。 <br>客户必须先安装3.8，然后再安装SP 3.8.5。 | [3.8.x发行说明](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-3-8.html) | **非UUID** <br> AEM 6.5 SP9或SP8 <br> AEM 6.4 SP8 <br> AEM 6.3 SP3 <br><br> **UUID** <br> AEM 6.5 SP9或SP8 | **非UUID**: <br> **AEM 6.5** <br> [3.8.5 SP](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8-5/com.adobe.fmdita-6.5-hotfix-3.8.5.2.zip) <br>[3.8](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8/com.adobe.fmdita-6.5-3.8.166.zip)<br> **AEM 6.4** <br> [3.8.5 SP](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8-5/com.adobe.fmdita-6.4-hotfix-3.8.5.1.zip) <br>[3.8](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8/com.adobe.fmdita-6.4-3.8.166.zip) <br> **AEM 6.3** <br> [3.8.5 SP](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8-5/com.adobe.fmdita-6.3-hotfix-3.8.5.1.zip) <br>[3.8](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8/com.adobe.fmdita-6.3-3.8.166.zip) <br><br> **UUID** <br>**AEM 6.5** <br> [3.8.5 SP](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8-5uuid/com.adobe.fmdita.uuid-6.5-hotfix-3.8.5.2.zip) <br> [3.8](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8uuid/com.adobe.fmdita.uuid-6.5-3.8.168.zip) |

---
title: 用户管理和安全性
description: 了解用户管理和安全性的工作方式
source-git-commit: 801c306fa120e7889d4b9428fd5bee2849bf1956
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 10%

---


# 用户管理和安全性 {#id181AED00G5Z}

要访问和配置AEM Guides中的功能，您需要创建用户。 然后，可以为这些用户分配访问AEM Guides中所有功能或特定功能的权限。 了解如何配置和维护用户授权，并了解身份验证和授权如何在AEM中工作背后的理论。

AEM文档中的以下主题将帮助您了解用户管理与安全相关的概念和功能：

- [AEM中的用户和组](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#UsersandGroupsinAEM)

- [AEM中的权限](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#PermissionsinAEM)

- [管理用户和组](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#ManagingUsersandGroups)

- [管理权限](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#ManagingPermissions)


## 由AEM Guides创建的用户组 {#id181TF0K0MHT}

AEM Guides提供了三个现成的组来管理DITA项目中的不同任务。 这些组包括： *作者*， *审阅者*、和 *发布者*. 根据用户关联的组，允许他们执行特定任务。 例如，发布任务只能由发布者执行，而不能由作者或审阅者执行。 同样，作者可以创建新主题，而审阅人只能审阅主题。

>[!TIP]
>
> 请参阅 *权限* 部分，了解有关设置用户权限的最佳实践。

下表列出了各种任务以及可以执行这些任务的组：

| 任务 | 作者 | 审阅者 | 发布者 |
|----|-------|---------|----------|
| 创建DITA主题 | 是 |   | 是 |
| 创建DITA映射 | 是 |   | 是 |
| 映射收藏集 | 是 |   | 是 |
| 创建审阅任务 | 是 |   | 是 |
| 审核主题[1](#fntarg_1) | 是 | 是 | 是 |
| 关键解决方法 | 是 |   | 是 |
| 在FrameMaker中打开 | 是 |   | 是 |
| 签出/签入 | 是 |   | 是 |
| 编辑主题 | 是 |   | 是 |
| 移动主题 | 是 |   | 是 |
| 编辑主题属性 | 是 |   | 是 |
| 复制 | 是 |   | 是 |
| 删除 | 是 |   | 是 |
| 共享 | 是 |   | 是 |
| **文档状态** |
| 创建/编辑文档状态配置文件 |   |   | 是 |
| 更改文档状态[2](#fntarg_2) | 是 | 是 | 是 |
| **DITA map控制台中可用的功能\（输出预设选项卡\）** |
| 生成 |   |   | 是 |
| 编辑 |   |   | 是 |
| 复制 |   |   | 是 |
| 创建 |   |   | 是 |
| 删除预设 |   |   | 是 |
| **DITA映射控制台中可用的功能\（输出选项卡\）** |
| 查看生成的输出 | 是 |   | 是 |
| **DITA map控制台中可用的功能\（主题选项卡\）** |
| 创建审阅任务 | 是 |   | 是 |
| 编辑 | 是 |   | 是 |
| **DITA映射控制台中可用的功能\（“基线”选项卡\）** |
| 创建 |   |   | 是 |
| 编辑 |   |   | 是 |
| 复制 |   |   | 是 |
| 删除 |   |   | 是 |
| DITA映射控制台\（报告选项卡\） | 是 |   | 是 |
| **DITA映射控制台中可用的功能\（条件预设\）** |
| 创建/编辑条件预设 |   |   | 是 |

## 有关用户组的其他说明

以下列表包含一些与用户组和相应权限相关的建议和点：

- 如果您希望用户启动翻译或审阅工作流，请确保该用户是 *发布者* 和 *projects-administrators group*.

- 用户必须在需要处理的源语言文件夹和目标语言文件夹上拥有读取、创建、删除和修改权限。

- 如果您创建项目，则您是该项目的所有者， *发布者* 权限。 要让项目中的其他用户能够查看其团队成员、创建任务或创建工作流，他们必须具有读取权限 `/home/users` 和 `/home/groups` 节点。 一种赋予读取权限的方式 `/home/users` 和 `/home/groups` 节点是通过对以下项授予读取权限： `projects-users` 组。

- *审阅者* 可以从“项目”控制台或收件箱通知链接访问和添加有关正在审阅主题的审阅注释。 此外，此访问权限仅在审阅任务打开时可用。

- 默认情况下， *发布者* 被授予对DAM中以下文件夹的访问和权限：

   - ``/var/dxml``–\> 读取和写入

   - `/content/dam/fmdita-outputs` –\> 读取和写入

   - `/content/output/sites` –\> 读取和写入

   如果您使用除上述默认发布位置之外的任何其他位置，则必须向发布者授予明确的读取和写入权限。

- 下的所有用户 *作者*， *审阅者*、和 *发布者* 组对DAM中的所有内容具有读取权限。

- 必须通过用户管理页面将文件夹级别的权限分配给用户。

- 如果您希望您的用户能够在DAM上执行搜索操作，则让您的用户成为 *dam-users* 组。

- 如果要向任何用户授予管理员权限，可以通过以下的AEM标准组向用户提供访问权限 *管理员*， *projects-administrator*&#x200B;或OSGI配置\（Felix控制台\）。

- 要授予用户更改文档状态的权限，请确保在文档状态配置文件的状态转换部分添加用户。

[1](#fnsrc_1) 如果 *作者* 和 *发布者* 已邀请进行审阅。[2](#fnsrc_2) 根据在文档状态配置文件中授予用户的权限。

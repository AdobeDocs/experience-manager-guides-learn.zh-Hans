---
title: 卸载AEM Guides
description: 了解如何卸载AEM Guides
source-git-commit: 5ac066bb8db32944abd046f64da11eeb1bdbe467
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---


# 卸载AEM Guides {#id21BHG0C0SXA}

您可以使用CRX包管理器卸载AEM Guides。 在卸载过程中，存储库的内容将恢复到紧接在安装软件包之前创建的快照。

执行以下步骤卸载AEM Guides：

1. 登录AEM实例并导航到CRX包管理器。 访问包管理器的默认URL是：

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

1. 搜索com.adobe.fmdita包。
1. 单击包以将其展开。
1. 单击 **更多** 以打开下拉菜单。
1. 单击 **卸载** 并等待卸载完成。
1. 如果您不再需要此包，请单击 **删除** 卸载包之后。

## 卸载后

要在卸载后清除剩余文件，请执行以下步骤：

1. 使用以下方式清除脚本缓存：

   ```http
   http://<host>:<port>/system/console/scriptcache
   ```

1. 您可以使用以下命令使缓存失效：

   ```http
   http://<host>:<port>/libs/granite/ui/content/dumplibs.rebuild.html?back=true
   ```

1. 单击 **使缓存失效**.
1. 清理浏览器的缓存。

**父主题：**[&#x200B;下载并安装](download-install.md)


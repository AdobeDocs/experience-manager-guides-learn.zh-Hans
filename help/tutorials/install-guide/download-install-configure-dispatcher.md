---
title: 配置 Dispatcher
description: 了解如何配置Dispatcher
source-git-commit: 9fe396dcfd2e3570ec386c958d7d4efdb4d608e5
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 7%

---


# 配置 Dispatcher {#id213BCM0M05U}

如果您计划将AEM创作实例上的Dispatcher与AEM Guides结合使用，则需要执行以下其他配置以完成设置：

>[!NOTE]
>
> Dispatcher 是 Adobe Experience Manager 的缓存和/或负载平衡工具。有关使用Dispatcher的更多详细信息，请参阅 [Dispatcher概述](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=zh-Hans).

## 在URL中启用AllowEncodedSlases

默认情况下，AEM Dispatcher设置中未启用带编码斜杠的URL，但是当您在AEM Guides中工作时，需要启用此项。 要实现此目的，您需要在Apache配置中将AllowEncodedSlashes参数设置为On，如以下代码片段所示：

```XML
<VirtualHost *:80>
                ServerName www.geometrixx-outdoors.com
                **AllowEncodedSlashes On**
                <Directory />
                <IfModule disp_apache2.c>
                SetHandler dispatcher-handler
                </IfModule>
                Options FollowSymLinks
                AllowOverride None
                </Directory>
                </VirtualHost>
            
```

## 为DITA配置mime.types文件

在将Dispatcher与AEM Guides结合使用时，必须确保将DITA映射和主题文件呈现为HTML，以便作者按预期方式查看内容\（而不是原始文本格式\）。

执行以下步骤以更新mime.types文件：

1. 使用SSH连接到Dispatcher服务器并浏览到httpd.conf文件。

1. 检查“ mime.types”文件的路径。

1. 打开mime.types文件并搜索“ text/html ”。 “ text/html ”的默认映射为：

   `text/html html htm`

1. 通过添加ditamap和dita扩展来更新映射，如下所示：

   `text/html html htm ditamap dita`

1. 保存并关闭文件。


此配置更新确保Dispatcher渲染的DITA映射和主题文件在Assets UI中显示为HTML。

## 允许用户首选项请求URL

在将Dispatcher与AEM Guides结合使用时，如果您的创作实例前面有一个Dispatcher，则进行以下两项更改：

- 将POST请求URL列入白名单。 示例» `/filters`”规则如下所示 — 将此规则添加到Dispatcher配置文件：

```json
/xxxx {/type "allow" /method "POST" /url "/home/users/*/preferences"}
```

- 确保Author Dispatcher上未缓存URL模式“ /libs/cq/security/userinfo.json”，因此请在author\_dispatcher.any中添加规则\（如下所示\）

```json
/xxxx {
                /glob "/libs/cq/security/userinfo.json"
                /type "deny"
                }
```

**父主题：**[&#x200B;下载并安装](download-install.md)

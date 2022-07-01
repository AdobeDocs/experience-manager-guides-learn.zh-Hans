---
title: 创建全局键
description: 如何创建要在组织内容中使用的全局键
role: Admin
exl-id: b8e3a6d2-ea82-4fdb-bd16-3f4b6594af52
source-git-commit: b5e64512956f0a7f33c2021bc431d69239f2a088
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 0%

---

# 创建全局键

组织应当使用键，以防其出现一些可恢复且通用的文本（如产品名称或产品宣传），这些文本在许多地方都使用，但容易发生更改。 通过为此类可重用文本使用键，您可以在单个位置（如键值中）进行更改，从而在多个位置推送更新。

## 步骤1:创建用于存储密钥的全局映射

创建映射并添加 [!UICONTROL keyref] 元素。

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "technicalContent/dtd/map.dtd">
<mapid="map.ditamap_ffbdbf06-8658-4311-ad84-1c631bba904f">
  <title>global-keys-map</title>
  <keydefkeys="adobe">
    <topicmeta>
      <linktext>Adobe Systems</linktext>
    </topicmeta>
  </keydef>
  <keydefkeys="AEM">
    <topicmeta>
      <linktext>Adobe Experience Manager</linktext>
    </topicmeta>
  </keydef>
</map>
```

在此，您定义了两个定义（如上所示），提供了 [!UICONTROL keyref] as _AEM_ 对于 _Adobe Experience Manager_ 文本。

## 步骤2:将此映射添加到发布映射

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "technicalContent/dtd/map.dtd">
<mapid="map.ditamap_cbf4a96d-e382-4e8c-8830-bcc093fe6638">
  <title>sample-map</title>
  <topicrefhref="sample-topic-using-the-keys.dita"type="topic">
  </topicref>
  <maprefformat="ditamap"href="global-keys-map.ditamap"type="map">
  </mapref>
</map>
```

## 步骤3:使用键可引用全局键映射中定义的变量

+ 编辑主题并使用 [!UICONTROL keyref].
+ 如屏幕截图所示，将显示一个可从中选择关键词的小窗口。 在添加“关键字”元素时，将显示该内容。
   ![插入元素](assets/insert_element.png)
   ![关键参考](assets/key_ref.png)

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE topic PUBLIC "-//OASIS//DTD DITA Topic//EN" "technicalContent/dtd/topic.dtd">
<topicid="topic.dita_31b00e61-04b5-4193-af7a-68503e88b087">
  <title>sample-topic-using-the-keys</title>
  <shortdesc></shortdesc>
  <body>
    <p>This is a sample topic using the keys defined in the global map</p>
    <p>here i am using the key definition for AEM :<keywordkeyref="AEM"></keyword></p>
  </body>
</topic>
```

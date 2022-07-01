---
title: 从翻译中排除主题中的段落
description: 如何从翻译中排除主题中的段落
feature: Translation
role: User
exl-id: 21e41bb4-52f3-4352-92d9-4a60f636de99
source-git-commit: b5e64512956f0a7f33c2021bc431d69239f2a088
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# 如何从翻译中排除主题中的段落

最简单的方法是使用translation=no属性。

+ 作者可以将附加属性插入为 **translation=no** 不想翻译的段落。 翻译供应商需要得到通知，他们可以在末尾进行配置以忽略具有此属性的文本。
+ OOTB机器翻译(带有试用的Microsoft翻译连接器)表现出相同的行为。
+ 测试Microsoft翻译：如果定义 **translate=no** 属性，则不会翻译完整的段落。 此属性可在任何元素中定义，且该元素内的内容不会进行翻译。


以下是一些屏幕截图，可进一步说明这一点：

**源内容**

![源内容](assets/source-content.jpg)

**西班牙语翻译内容**

![西班牙语翻译内容](assets/trans-content.jpg)

---
title: Webeditor中的架构支持
description: 在Webeditor中使用Schematron
source-git-commit: 2a036ec628424f0dedfdb69a5e860906ca100cc6
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 0%

---


# 在Web编辑器中控制内容质量

本文概述了AEM指南Web编辑器中的验证可能性。
通过设计Web编辑器，可利用系统中的DITA架构设置来强制用户创建符合DITA规范的内容。 这样，系统中存储的所有内容都具有结构化、可重用且有效的DITA内容。

除了支持DITA规则外，Web编辑器还支持基于“*舍马特龙*”规则。

&quot;*舍马特龙*“”是指用于定义XML文件测试的基于规则的验证语言。 您可以导入架构文件，并在Web编辑器中对其进行编辑。 使用“架构”文件，您可以定义特定规则，然后验证这些规则以获取DITA主题或映射。 架构规则通过施加定义为规则的限制来确保XML结构的一致性。 这些限制是由拥有内容质量和一致性的中小企业推动的。

    注意：Web编辑器支持ISO架构。


## 了解Web编辑器中“架构”的工作原理

### 配置架构规则

请参阅 [用户指南](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_User-Guide_EN.pdf#page=148)


### 对文件保存强制执行验证规则

网络编辑器设置允许高级用户设置架构规则/文件，该规则/文件将在用户每次更新内容时执行。 有关更多详细信息，请参阅 [用户指南](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_User-Guide_EN.pdf#page=58)

![通过Web编辑器设置规则](../../../assets/authoring/schematron-editorsettings-validation-tab.png)


### 能否手动运行验证？

是，作为创建内容的作者/用户，您可以在编辑器中使用架构面板上传架构文件并对在编辑器中打开的文件运行验证。

    要使其正常工作，文件夹配置文件管理员必须允许所有用户在验证面板中添加架构文件。 请参阅编辑器设置（上面提供的屏幕截图）

![选择架构文件](../../../assets/authoring/schematron-rightpanel-validation-addsch.png)
![运行验证](../../../assets/authoring/schematron-rightpanel-validation-runsch.png)


### 支持的规则

AEM指南的当前版本仅支持使用基于“断言”的规则进行验证。 (请参阅 [资产与报表](https://schematron.com/document/205.html))尚不支持任何基于“报表”的规则。


### 有关架构规则的示例和更多帮助

#### 用例示例

- 检查链接是否为外部链接，以及其范围是否为“外部”

   ```
   <sch:pattern>
       <sch:rule context="xref[contains(@href, 'http') or contains(@href, 'https')]">
           <sch:assert test="@scope = 'external' and @format = 'html'">
               All external xref links must be with scope='external' and format='html'
           </sch:assert>
       </sch:rule>
   </sch:pattern>
   ```

- 检查地图中是否至少有一个“topicref”，或“ul”下是否至少有一个“li”

   ```
   <sch:pattern>
       <sch:rule context="map">
           <sch:assert test="count(topicref) > 0">
               There should be atleast one topicref in map
           </sch:assert>
       </sch:rule>
   
       <sch:rule context="ul">
           <sch:assert test="count(li) > 1" >
               A list must have more than one item.
           </sch:assert>
       </sch:rule>
   </sch:pattern>
   ```

- “indexterm”元素应始终显示在“prolog”中

   ```
   <sch:pattern>
       <sch:rule context="*[contains(@class, ' topic/indexterm ')]">
           <sch:assert test="ancestor::node()/local-name() = 'prolog'">
               The indexterm element should be in a prolog.
           </sch:assert>
       </sch:rule>
   </sch:pattern>
   ```

#### 资源

- 了解  [架构基础知识](https://da2022.xatapult.com/#what-is-schematron)
- 有关 [架构中的断言规则](https://www.xml.com/pub/a/2003/11/12/schematron.html#Assertions)
- [示例架构文件](../../../assets/authoring/sample_schematron.sch)
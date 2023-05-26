---
title: 使用 DOM 插入邮件合并地址块字段
linktitle: 使用 DOM 插入邮件合并地址块字段
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将邮件合并地址块字段插入到您的 Word 文档中。
type: docs
weight: 10
url: /zh/net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
---

这是一个分步指南，用于解释下面的 C# 源代码，它使用 Aspose.Words for .NET 的“插入邮件合并地址块字段”功能。确保仔细执行每个步骤以获得所需的结果。

## 第 1 步：文档目录设置

在提供的代码中，您必须指定文档的目录。将值“YOUR DOCUMENT DIRECTORY”替换为您的文档目录的适当路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：创建文档和 DocumentBuilder

我们首先创建一个新文档并初始化一个 DocumentBuilder。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第三步：移动光标到段落

我们使用 DocumentBuilder 的`MoveTo()`方法将光标移动到我们要插入邮件合并地址块字段的段落。

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## 第 4 步：插入邮件合并地址块字段

我们使用 DocumentBuilder 的`InsertField()`将邮件合并地址块字段插入段落的方法。

```csharp
FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, false);
```

然后我们配置地址块字段的属性，指定适当的选项，例如包括国家/地区名称、根据国家/地区格式化地址、排除的国家/地区名称、名称和地址格式以及语言标识符。

```csharp
field.IncludeCountryOrRegionName = "1";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "Test2";
field.NameAndAddressFormat = "Test3";
field.LanguageId = "Test 4";
```

最后，我们称`Update()`更新字段的方法。

```csharp
field. Update();
```

### 使用 Aspose.Words for .NET 插入邮件合并地址块字段的示例源代码

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Paragraph para = (Paragraph) doc.GetChildNodes(NodeType.Paragraph, true)[0];

builder. MoveTo(para);

//我们想像这样插入一个邮件合并地址块：
// { 地址块 \\c 1 \\d \\e Test2 \\f Test3 \\l \"测试 4\" }

FieldAddressBlock field = (FieldAddressBlock) builder.InsertField(FieldType.FieldAddressBlock, false);

// { 地址块 \\c 1" }
field.IncludeCountryOrRegionName = "1";

// { 地址块 \\c 1 \\d" }
field.FormatAddressOnCountryOrRegion = true;

// { 地址块 \\c 1 \\d \\e Test2 }
field.ExcludedCountryOrRegionName = "Test2";

// { 地址块 \\c 1 \\d \\e Test2 \\f Test3 }
field.NameAndAddressFormat = "Test3";

// { 地址块 \\c 1 \\d \\e Test2 \\f Test3 \\l \"测试 4\" }
field.LanguageId = "Test 4";

field. Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertMailMergeAddressBlockFieldUsingDOM.docx");
```

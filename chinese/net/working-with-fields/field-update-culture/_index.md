---
title: 现场更新文化
linktitle: 现场更新文化
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 更新 Word 文档中的字段区域性。
type: docs
weight: 10
url: /zh/net/working-with-fields/field-update-culture/
---

这是一个分步指南，用于解释下面的 C# 源代码，它使用 Aspose.Words for .NET 的“Field Culture Update”功能。确保仔细执行每个步骤以获得所需的结果。

## 第 1 步：文档目录设置

在提供的代码中，您必须指定文档的目录。将值“YOUR DOCUMENT DIRECTORY”替换为您的文档目录的适当路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：创建文档和文档生成器

我们首先创建一个新文档和一个文档生成器。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 3 步：插入时间字段

我们使用`InsertField()`将时间字段插入文档的方法。

```csharp
builder. InsertField(FieldType.FieldTime, true);
```

这将在文档中插入一个时间字段。

## 第 4 步：配置字段更新文化

我们配置字段选项以指定字段更新区域性应基于字段代码。

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();
```

这些选项确定用于更新字段的区域性。

### 使用 Aspose.Words for .NET 更新现场文化的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建文档和文档生成器。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//插入时间字段。
builder. InsertField(FieldType.FieldTime, true);

//配置字段更新文化。
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();

//保存文档。
doc.Save(dataDir + "UpdateCultureChamps.pdf");
```

在此示例中，我们创建了一个新文档，插入了一个时间字段，并配置了字段更新文化。然后我们用指定的文件名保存文档。

我们关于使用 Aspose.Words for .NET 的“更新字段文化”功能的指南到此结束。
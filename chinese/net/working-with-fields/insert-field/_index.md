---
title: 插入字段
linktitle: 插入字段
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将字段插入到您的 Word 文档中。使用动态字段个性化您的文档。
type: docs
weight: 10
url: /zh/net/working-with-fields/insert-field/
---

这是一个分步指南，用于解释下面的 C# 源代码，它使用 Aspose.Words for .NET 的“插入字段”功能。确保仔细执行每个步骤以获得所需的结果。

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

## 第 3 步：插入字段

我们使用`InsertField()`DocumentBuilder 的方法将字段插入到文档中。在此示例中，我们插入一个合并字段 (MERGEFIELD)，其字段名称为“MyFieldName”并采用合并格式。

```csharp
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");
```

### 使用 Aspose.Words for .NET 插入字段的源代码示例

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建文档和 DocumentBuilder。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//插入字段。
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");

doc.Save(dataDir + "InsertionField.docx");
```

在此示例中，我们创建了一个新文档，初始化了一个 DocumentBuilder，然后插入了一个字段名称为“MyFieldName”和合并格式的合并字段。然后以指定的文件名保存该文档。

我们关于使用 Aspose.Words for .NET 的“插入字段”功能的指南到此结束。

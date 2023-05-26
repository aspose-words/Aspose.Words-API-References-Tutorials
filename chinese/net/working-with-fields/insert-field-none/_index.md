---
title: 插入字段无
linktitle: 插入字段无
second_title: Aspose.Words for .NET API 参考
description: 了解如何在 Word avec Aspose.Words pour .NET 中插入 un champ AUCUN dans vos 文档。
type: docs
weight: 10
url: /zh/net/working-with-fields/insert-field-none/
---

这是一个分步指南，用于解释下面的 C# 源代码，它使用 Aspose.Words for .NET 的“Insert NONE Field”功能。确保仔细执行每个步骤以获得所需的结果。

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

## 第 3 步：插入 NONE 字段

我们使用`InsertField()`DocumentBuilder 的方法将 NONE 字段插入到文档中。

```csharp
FieldUnknown field = (FieldUnknown)builder.InsertField(FieldType.FieldNone, false);
```

### 使用 Aspose.Words for .NET 插入 NONE 字段的源代码示例

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建文档和 DocumentBuilder。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//插入无字段。
FieldUnknown field = (FieldUnknown)builder.InsertField(FieldType.FieldNone, false);

doc.Save(dataDir + "InsertionFieldNone.docx");
```

在此示例中，我们创建了一个新文档，初始化了一个 DocumentBuilder，然后插入了一个 NONE 字段。然后以指定的文件名保存该文档。

我们关于使用 Aspose.Words for .NET 的“Insert NONE Field”功能的指南到此结束。
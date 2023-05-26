---
title: 在没有文档生成器的情况下插入高级字段
linktitle: 在没有文档生成器的情况下插入高级字段
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将高级字段插入到您的 Word 文档中。
type: docs
weight: 10
url: /zh/net/working-with-fields/insert-advance-field-with-out-document-builder/
---

这是一个分步指南，用于解释下面的 C# 源代码，它使用 Aspose.Words for .NET 的“无需 DocumentBuilder 的高级字段插入”功能。确保仔细执行每个步骤以获得所需的结果。

## 第 1 步：文档目录设置

在提供的代码中，您必须指定文档的目录。将值“YOUR DOCUMENT DIRECTORY”替换为您的文档目录的适当路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：创建文档和段落

我们首先创建一个新文档并获取第一段。

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## 第 3 步：插入高级字段

我们使用`AppendField()`在段落中插入高级字段的方法。

```csharp
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);
```

然后，我们通过指定所需的值来配置高级字段的各种属性。

```csharp
field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";
```

最后，我们称`Update()`更新字段的方法。

```csharp
field. Update();
```

### 使用 Aspose.Words for .NET 在没有 DocumentBuilder 的情况下插入高级字段的源代码示例

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//文档创建。
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

//插入高级字段。
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);

field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";

field. Update();

doc.Save(dataDir + "InsertionFieldAdvanceWithoutDocumentBuilder.docx");
```

在此示例中，我们创建了一个新文档，在不使用 DocumentBuilder 的情况下插入了一个高级字段，配置了各种字段属性，并使用指定的文件名保存了该文档。

关于如何使用 Aspose.Words for .NET 的“不使用 DocumentBuilder 插入高级字段”功能的指南到此结束。


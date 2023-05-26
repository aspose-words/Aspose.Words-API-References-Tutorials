---
title: 在没有文档生成器的情况下插入 ASKField
linktitle: 在没有文档生成器的情况下插入 ASKField
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将 ASK 字段插入到您的 Word 文档中。
type: docs
weight: 10
url: /zh/net/working-with-fields/insert-askfield-with-out-document-builder/
---

这是一个分步指南，用于解释下面的 C# 源代码，它使用 Aspose.Words for .NET 的“不使用 DocumentBuilder 插入 ASK 字段”功能。确保仔细执行每个步骤以获得所需的结果。

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

## 第 3 步：插入 ASK 字段

我们使用`AppendField()`在段落中插入 ASK 字段的方法。

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

然后，我们通过指定所需的值来配置 ASK 字段的各种属性。

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

最后，我们称`Update()`更新字段的方法。

```csharp
field. Update();
```

### 使用 Aspose.Words for .NET 在没有 DocumentBuilder 的情况下插入 ASK 字段的源代码示例

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//文档创建。
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

//插入询问字段。
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

在这个例子中，我们创建了一个新的文档，在没有使用 DocumentBuilder 的情况下插入了一个 ASK 字段，配置了该字段的各种属性，并以指定的文件名保存了文档。

我们关于在 Aspose.Words for .NET 中使用“Insert ASK Field Without DocumentBuilder”功能的指南到此结束。
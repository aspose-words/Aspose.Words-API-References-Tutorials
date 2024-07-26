---
title: 不使用文档生成器插入高级字段
linktitle: 不使用文档生成器插入高级字段
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中插入高级字段。
type: docs
weight: 10
url: /zh/net/working-with-fields/insert-advance-field-with-out-document-builder/
---

以下是分步指南，用于解释下面的 C# 源代码，该代码使用了 Aspose.Words for .NET 的“无需 DocumentBuilder 的高级字段插入”功能。请务必仔细遵循每个步骤以获得所需的结果。

## 步骤 1：文档目录设置

在提供的代码中，您必须指定文档的目录。将值“YOUR DOCUMENT DIRECTORY”替换为您的文档目录的相应路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步骤 2：创建文档和段落

我们首先创建一个新文档并获取第一段。

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## 步骤 3：插入高级字段

我们使用`AppendField()`方法将高级字段插入段落。

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

最后，我们称`Update()`方法来更新字段。

```csharp
field. Update();
```

### 使用 Aspose.Words for .NET 插入高级字段（无需 DocumentBuilder）的源代码示例

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

在这个例子中，我们创建了一个新文档，插入了一个高级字段（没有使用 DocumentBuilder），配置了各种字段属性，并使用指定的文件名保存了该文档。

这就是我们关于如何使用 Aspose.Words for .NET 的“插入不带 DocumentBuilder 的高级字段”功能的指南。

### 常见问题解答

#### 问：Aspose.Words 中的高级字段是什么？

答：Aspose.Words 中的高级字段是一种特殊类型的字段，它允许您在 Word 文档中执行计算、包含条件和执行复杂操作。它为创建动态和自定义字段提供了极大的灵活性。

#### 问：如何在不使用 Aspose.Words 中的文档生成器的情况下在 Word 文档中插入高级字段？

答：要在不使用 Aspose.Words 中的 Document Builder 的情况下在 Word 文档中插入高级字段，您可以按照以下步骤操作：

1. 从 Aspose.Words.Fields 命名空间导入 Document 和 Field 类。
2. 通过加载现有文档来创建 Document 的实例。
3. 使用 InsertField 方法通过指定高级字段代码来插入高级字段。
4. 保存文档。

#### 问：如何获取Word文档中高级字段的结果？

答：要获取 Word 文档中高级字段的结果，可以使用 Field 类中的 Result 属性。此属性返回字段的计算结果。

#### 问：将高级字段插入到 Word 文档后，我可以修改其公式吗？

答：是的，您可以在将高级字段插入 Word 文档后编辑其公式。您可以通过访问 Field 类的 FieldCode 属性并通过修改公式文本来更新公式来实现此目的。
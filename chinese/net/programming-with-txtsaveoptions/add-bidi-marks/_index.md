---
title: 添加双向标记
linktitle: 添加双向标记
second_title: Aspose.Words for .NET API 参考
description: 学习使用 Aspose.Words for .NET 将双向标记添加到 Word 文档并创建专业的多语言文档。
type: docs
weight: 10
url: /zh/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words for .NET 是一个强大的库，用于在 C# 应用程序中创建、编辑和操作 Word 文档。 Aspose.Words 提供的功能之一是能够向文档添加 Bidi（双向）标记。在本指南中，我们将带您了解如何使用 Aspose.Words for .NET 的 C# 源代码为文档添加双向标记。

## 理解 Aspose.Words 库

在深入研究代码之前，了解 .NET 的 Aspose.Words 库很重要。 Aspose.Words 是一个流行的库，它使处理 Word 文档变得简单而高效。它提供了用于创建、编辑和操作 Word 文档的广泛功能，包括添加双向标记。

## 创建文档并添加内容

第一步是创建一个新文档并向其中添加内容。使用 Document 类创建一个新的文档实例。然后使用 DocumentBuilder 类向文档中添加文本。这是一个例子：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

在此示例中，我们创建一个新文档并使用 DocumentBuilder 添加文本。我们添加了三行文本：一行是英语，一行是希伯来语，一行是阿拉伯语，以演示添加不同语言的内容。

## 添加了双向标记

添加内容后，我们现在可以将双向标记添加到文档中。为此，我们使用 TxtSaveOptions 类并将 AddBidiMarks 属性设置为 true。就是这样：

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

在此示例中，我们创建了一个 TxtSaveOptions 实例并将 AddBidiMarks 属性设置为 true。接下来，我们使用 Document 类的 Save 方法来保存带有双向标记的文档。

### 使用 Aspose.Words for .NET 的“添加双向标记”功能的示例源代码

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建文档并添加内容
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

//添加双向标记
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## 结论

在本指南中，我们已经解释了如何使用 Aspose.Words for .NET 使用提供的 C# 源代码将双向标记添加到 Word 文档。按照提供的步骤，您可以在 C# 应用程序中轻松地将双向标记添加到 Word 文档。 Aspose.Words 为处理文本格式和语言管理提供了巨大的灵活性和强大的功能，使您能够专业地创建多语言文档。
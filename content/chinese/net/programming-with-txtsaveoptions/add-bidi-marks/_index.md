---
title: 在 Word 文档中添加双向标记
linktitle: 在 Word 文档中添加双向标记
second_title: Aspose.Words 文档处理 API
description: 学习使用 Aspose.Words for .NET 向 Word 文档添加 Bidi 标记并创建专业的多语言文档。
type: docs
weight: 10
url: /zh/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words for .NET 是一个功能强大的库，可用于在 C# 应用程序中创建、编辑和操作 Word 文档。Aspose.Words 提供的功能之一是能够向文档添加双向 (Bidi) 标记。在本指南中，我们将引导您了解如何使用 Aspose.Words for .NET 的 C# 源代码向文档添加双向标记。

## 了解 Aspose.Words 库

在深入研究代码之前，了解 .NET 的 Aspose.Words 库非常重要。Aspose.Words 是一个流行的库，它使 Word 文档的文字处理变得简单而高效。它提供了广泛的功能来创建、编辑和操作 Word 文档，包括添加双向标记。

## 创建文档并添加内容

第一步是创建一个新文档并向其中添加内容。使用 Document 类创建一个新的文档实例。然后使用 DocumentBuilder 类向文档添加文本。以下是示例：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

在此示例中，我们创建一个新文档并使用 DocumentBuilder 添加文本。我们添加了三行文本：一行英文、一行希伯来语和一行阿拉伯语，以演示如何添加不同语言的内容。

## 添加了 Bidi 标记

添加内容后，我们现在可以向文档添加 Bidi 标记。为此，我们使用 TxtSaveOptions 类并将 AddBidiMarks 属性设置为 true。操作方法如下：

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

在此示例中，我们创建 TxtSaveOptions 的一个实例，并将 AddBidiMarks 属性设置为 true。接下来，我们使用 Document 类的 Save 方法保存带有 Bidi 标记的文档。

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

//添加 Bidi 标记
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## 结论

在本指南中，我们解释了如何使用 Aspose.Words for .NET 使用提供的 C# 源代码将 Bidi 标记添加到 Word 文档。按照提供的步骤，您可以轻松地在 C# 应用程序中将 Bidi 标记添加到 Word 文档。Aspose.Words 通过文本格式和语言管理为文字处理提供了极大的灵活性和功能，使您能够专业地创建多语言文档。

### 经常问的问题

#### 问：Aspose.Words for .NET是什么？
Aspose.Words for .NET 是一个功能强大的库，用于在 C# 应用程序中创建、编辑和操作 Word 文档。它为 Word 文档的文字处理提供了许多功能，包括添加 Bidi（双向）标记。

#### 问：Aspose.Words for .NET 提供哪些功能？
Aspose.Words for .NET 提供了多种用于创建、编辑和操作 Word 文档的功能。这些功能包括创建文档、添加内容、格式化文本、管理表格、合并和拆分文档、转换文档等。

#### 问：如何使用 Aspose.Words for .NET 向 Word 文档添加双向标记？
您可以按照以下步骤将双向标记添加到 Word 文档：

使用创建一个新文档`Document`班级。

使用`DocumentBuilder`类来向文档添加内容。

添加内容后，使用`TxtSaveOptions`类并设置`AddBidiMarks`财产`true`.

使用`Save`方法`Document`班级。

#### 问：Aspose.Words 是否支持多种语言添加双向标记？
是的，Aspose.Words 支持多种语言添加双向标记。您可以使用 Aspose.Words for .NET 将双向标记添加到不同语言的文本中，例如英语、希伯来语和阿拉伯语。

#### 问：还有其他选项可以保存带有双向标记的文档吗？
是的，您可以在使用双向标记保存文档时指定其他选项`TxtSaveOptions`类。例如，您可以设置文档的保存格式、编码选项等。
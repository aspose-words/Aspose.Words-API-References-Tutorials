---
title: 更改目录级别的样式
linktitle: 更改目录级别的样式
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 轻松更改 Word 文档中目录级别的样式。
type: docs
weight: 10
url: /zh/net/programming-with-table-of-content/change-style-of-toc-level/
---

Aspose.Words for .NET 是一个功能强大的库，用于在 C# 应用程序中创建、编辑和操作 Word 文档。 Aspose.Words 提供的功能之一是能够更改文档目录特定级别的样式。在本指南中，我们将向您展示如何使用Aspose.Words for .NET的C#源代码来更改Word文档目录级别的样式。

## 了解 Aspose.Words 库

在深入研究代码之前，了解 .NET 的 Aspose.Words 库非常重要。 Aspose.Words 是一个流行的库，它使 Word 文档的处理变得简单而高效。它提供了广泛的用于创建、编辑和操作 Word 文档的功能，包括更改目录的样式。

## 创建新文档

第一步是创建一个要更改目录样式的新 Word 文档。使用 Document 类创建新文档。这是一个例子：

```csharp
Document doc = new Document();
```

在此示例中，我们将创建一个新的空文档。

## 更改目录级别的样式

创建文档后，您可以访问文档样式并更改用于特定级别目录的样式。在此示例中，我们将修改用于第一级目录的样式。就是这样：

```csharp
doc.Styles[StyleIdentifier.Toc1].Font.Bold = true;
```

在此示例中，我们使用 Document 类的 Styles 属性来访问文档样式。接下来，我们使用 StyleIdentifier.Toc1 样式标识符来访问用于第一级目录的样式。最后，我们修改样式的 Font.Bold 属性以使其变为粗体。

## 保存修改后的文档

对目录样式进行必要的修改后，可以使用 Document 类的 Save 方法保存修改后的文档。这是一个例子：

```csharp
doc.Save(dataDir + "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx");
```

在此示例中，我们将修改后的文档保存为“WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx”。

## 使用 Aspose.Words for .NET 的“更改目录级别的样式”功能的示例源代码

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建一个新文档
Document doc = new Document();

//修改第一级目录样式
doc.Styles[StyleIdentifier.Toc1].Font.Bold = true;

//保存修改后的文档
doc.Save(dataDir + "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx");
```

## 结论

在本指南中，我们解释了如何使用 Aspose.Words for .NET 使用提供的 C# 源代码更改 Word 文档目录级别的样式。通过按照提供的步骤操作，您可以轻松地在 C# 应用程序中自定义 Word 文档的目录样式。 Aspose.Words 提供了巨大的灵活性和强大的功能来处理文档的样式和格式，使您能够创建有吸引力且专业的 Word 文档。
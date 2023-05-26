---
title: 范围获取文本
linktitle: 范围获取文本
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 轻松地从 Word 文档中提取文本。
type: docs
weight: 10
url: /zh/net/programming-with-ranges/ranges-get-text/
---

Aspose.Words for .NET 是一个强大的库，用于在 C# 应用程序中创建、编辑和操作 Word 文档。 Aspose.Words 提供的功能之一是能够获取包含在文档特定范围内的文本。在本指南中，我们将带您了解如何使用 Aspose.Words for .NET 的 C# 源代码从 Word 文档中提取文本。

## 理解 Aspose.Words 库

在深入研究代码之前，了解 .NET 的 Aspose.Words 库很重要。 Aspose.Words 是一个流行的库，它使处理 Word 文档变得简单而高效。它为创建、编辑和操作 Word 文档提供了广泛的功能，包括从特定范围中提取文本。

## 载入Word文档

第一步是加载要从中提取文本的 Word 文档。使用 Document 类从源文件加载文档。这是一个例子：

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

在此示例中，我们加载位于文档目录中的文档“Document.docx”。

## 从特定范围中提取文本

加载文档后，您可以访问文档的不同范围并提取所需的文本。在此示例中，我们将从文档中提取所有文本。就是这样：

```csharp
string text = doc.Range.Text;
```

在此示例中，我们使用 Document 类的 Range 属性来访问文档的整个范围。然后我们使用 Text 属性获取该范围内包含的文本。

## 提取文本的显示

现在我们已经从指定范围中提取了文本，我们可以根据您的应用程序的需要显示或处理它。例如，您可以将其显示在屏幕上或将其保存到输出文件中。这是显示提取的文本的示例：

```csharp
Console.WriteLine(text);
```

在此示例中，我们使用 Console 类的 WriteLine 方法在控制台中显示提取的文本。

### 使用 Aspose.Words for .NET 的“从范围中获取文本”功能的示例源代码

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//载入Word文档
Document doc = new Document(dataDir + "Document.docx");

//从文档中提取文本
string text = doc.Range.Text;

//显示提取的文本
Console.WriteLine(text);
```

## 结论

在本指南中，我们介绍了如何使用 Aspose.Words for .NET 使用提供的 C# 源代码从 Word 文档中提取文本。按照提供的步骤操作，您可以在 C# 应用程序中轻松地从 Word 文档的特定范围中提取文本。 Aspose.Words 为处理文档内容提供了巨大的灵活性和强大的功能，允许您根据您的特定需求处理和使用文本。
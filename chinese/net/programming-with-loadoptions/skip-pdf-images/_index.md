---
title: 跳过 PDF 图片
linktitle: 跳过 PDF 图片
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 加载 PDF 文档而跳过加载 PDF 图像。
type: docs
weight: 10
url: /zh/net/programming-with-loadoptions/skip-pdf-images/
---

在 C# 应用程序中处理 PDF 文档时，出于性能或存储空间管理原因，可能需要跳过加载 PDF 图像。使用适用于 .NET 的 Aspose.Words 库，您可以使用 PdfLoadOptions 加载选项轻松跳过加载 PDF 图像。在这个循序渐进的指南中，我们将通过使用 PdfLoadOptions 加载选项跳过 PDF 图像的加载，引导您完成如何使用 Aspose.Words for .NET C# 源代码加载 PDF 文档。

## 理解 Aspose.Words 库

在深入研究代码之前，了解 .NET 的 Aspose.Words 库很重要。 Aspose.Words 是一个强大的库，可以在包括.NET 在内的不同平台上创建、编辑、转换和保护 Word 文档。它提供了许多用于操作文档的功能，例如插入文本、更改格式、添加部分等等。

## 配置加载选项

第一步是为我们的 PDF 文档配置加载选项。使用 PdfLoadOptions 类指定加载参数。在我们的例子中，我们需要将 SkipPdfImages 属性设置为 true 以跳过加载 PDF 图像。方法如下：

```csharp
PdfLoadOptions loadOptions = new PdfLoadOptions { SkipPdfImages = true };
```

我们创建一个新的 PdfLoadOptions 对象并将 SkipPdfImages 属性设置为 true 以跳过加载 PDF 图像。

## 加载 PDF 文档跳过 PDF 图像

现在我们已经配置了加载选项，我们可以使用 Document 类加载 PDF 文档并指定加载选项。这是一个例子：

```csharp
Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

在此示例中，我们使用指定的加载选项加载位于文档目录中的 PDF 文档“Pdf Document.pdf”。

### 使用 Aspose.Words for .NET 的具有“跳过 Pdf 图像”功能的 PdfLoadOptions 示例源代码

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//使用“跳过 Pdf 图像”功能配置加载选项
PdfLoadOptions loadOptions = new PdfLoadOptions { SkipPdfImages = true };

//跳过 PDF 图像加载 PDF 文档
Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

## 结论

在本指南中，我们解释了如何使用 .NET 的 Aspose.Words 库加载 PDF 文档而跳过 PDF 图像的加载。按照提供的步骤并使用提供的 C# 源代码，您可以轻松地将此功能应用到您的 C# 应用程序中。跳过 PDF 图像加载可以提高处理 PDF 文档时的性能和存储空间管理。
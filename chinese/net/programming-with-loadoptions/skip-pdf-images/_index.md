---
title: 跳过 Pdf 图像
linktitle: 跳过 Pdf 图像
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 加载 PDF 文档，跳过加载 PDF 图像的过程。
type: docs
weight: 10
url: /zh/net/programming-with-loadoptions/skip-pdf-images/
---

在 C# 应用程序中对 PDF 文档进行文字处理时，出于性能或存储空间管理原因，可能需要跳过加载 PDF 图像。借助适用于 .NET 的 Aspose.Words 库，您可以使用 PdfLoadOptions 加载选项轻松跳过加载 PDF 图像。在本分步指南中，我们将引导您了解如何使用 Aspose.Words for .NET C# 源代码通过使用 PdfLoadOptions 加载选项跳过 PDF 图像的加载来加载 PDF 文档。

## 了解 Aspose.Words 库

在深入研究代码之前，了解 .NET 的 Aspose.Words 库非常重要。 Aspose.Words 是一个功能强大的库，可在包括.NET 在内的不同平台上创建、编辑、转换和保护 Word 文档。它提供了许多用于操作文档的功能，例如插入文本、更改格式、添加部分等等。

## 配置加载选项

第一步是配置 PDF 文档的加载选项。使用 PdfLoadOptions 类指定加载参数。在我们的例子中，我们需要将 SkipPdfImages 属性设置为 true 以跳过加载 PDF 图像。操作方法如下：

```csharp
PdfLoadOptions loadOptions = new PdfLoadOptions { SkipPdfImages = true };
```

我们创建一个新的 PdfLoadOptions 对象并将 SkipPdfImages 属性设置为 true 以跳过加载 PDF 图像。

## 加载 PDF 文档并跳过 PDF 图像

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

//加载 PDF 文档，跳过 PDF 图像
Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

## 结论

在本指南中，我们解释了如何使用 .NET 的 Aspose.Words 库加载 PDF 文档，跳过 PDF 图像的加载。通过遵循提供的步骤并使用提供的 C# 源代码，您可以轻松地在 C# 应用程序中应用此功能。处理 PDF 文档时，跳过 PDF 图像加载可以提高性能和存储空间管理。
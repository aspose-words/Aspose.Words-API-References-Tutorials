---
title: 嵌入所有字体
linktitle: 嵌入所有字体
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 将所有字体嵌入 PDF 的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/embedded-all-fonts/
---

本文提供了有关如何使用 Aspose.Words for .NET 的嵌入式所有字体功能的分步指南。我们将遍历代码片段并详细解释每个部分。在本教程结束时，您将能够了解如何将所有字体嵌入到文档中，并使用 Aspose.Words for .NET 生成带有嵌入字体的 PDF。

在我们开始之前，请确保您已经在您的项目中安装并设置了 Aspose.Words for .NET 库。您可以在 Aspose 网站上找到库和安装说明。

## 第一步：定义文档目录路径

首先，您需要定义文档所在目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`使用文档目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：装入文档

接下来，我们需要加载要处理的文档。在此示例中，我们假设文档名为“Rendering.docx”并且位于指定的文档目录中。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 第 3 步：配置 PDF 保存选项

要在生成的 PDF 中嵌入所有字体，我们需要配置`PdfSaveOptions`对象与`EmbedFullFonts`属性设置为`true`.这可确保文档中使用的所有字体都包含在生成的 PDF 文件中。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = true };
```

## 第 4 步：将文档另存为带有嵌入字体的 PDF

最后，我们可以将文档另存为带有嵌入字体的 PDF 文件。指定输出文件名和`saveOptions`我们在上一步中配置的对象。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddedFontsInPdf.pdf", saveOptions);
```

就是这样！您已成功将所有字体嵌入到文档中，并使用 Aspose.Words for .NET 生成了包含嵌入字体的 PDF。

### 使用 Aspose.Words for .NET 的嵌入式所有字体的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//输出的 PDF 将嵌入文档中找到的所有字体。
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddedFontsInPdf.pdf", saveOptions);
  
```

## 结论

在本教程中，我们介绍了使用 Aspose.Words for .NET 的嵌入式所有字体功能的分步过程。我们学习了如何加载文档、配置 PDF 保存选项以及将文档保存为带有嵌入字体的 PDF 文件。通过遵循本指南，您可以确保您的 PDF 文档嵌入了所有必要的字体，从而在不同的设备和平台上提供一致和准确的呈现。

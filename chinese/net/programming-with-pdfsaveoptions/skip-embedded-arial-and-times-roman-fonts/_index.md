---
title: 跳过嵌入的 Arial 和 Times Roman 字体
linktitle: 跳过嵌入的 Arial 和 Times Roman 字体
second_title: Aspose.Words for .NET API 参考
description: 在不使用 Aspose.Words for .NET 嵌入 Arial 和 Times Roman 字体的情况下生成 PDF 的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

本文提供了有关如何使用 Aspose.Words for .NET 的功能将嵌入的 Arial 和 Times Roman 字体跳过到图元文件大小的分步指南。我们将详细解释代码的每一部分。在本教程结束时，您将能够了解如何在文档中配置字体嵌入模式选项并生成不嵌入 Arial 和 Times Roman 字体的 PDF。

在开始之前，请确保您已经在项目中安装并配置了 Aspose.Words for .NET 库。您可以在 Aspose 网站上找到库和安装说明。

## 第一步：定义文档目录

首先，您需要定义文档所在目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`使用文档目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第二步：上传文件

接下来，我们需要加载我们要处理的文档。在此示例中，我们假设文档名为“Rendering.docx”并且位于指定的文档目录中。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 第 3 步：使用嵌入字体配置另存为 PDF 选项

要跳过在生成的 PDF 中嵌入 Arial 和 Times Roman 字体，我们需要配置`PdfSaveOptions`对象并设置`FontEmbeddingMode`财产给`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## 步骤 4：将文档另存为不带嵌入字体的 PDF

最后，我们可以使用之前配置的保存选项将文档保存为 PDF 格式。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

就这样 ！您已经使用 Aspose.Words for .NET 成功生成了 PDF，但没有嵌入 Arial 和 Times Roman 字体。

### 使用 Aspose.Words for .NET 跳过图元文件大小的嵌入式 Arial 和 Times Roman 字体的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```

---
title: 嵌入式子集字体
linktitle: 嵌入式子集字体
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 在 PDF 中嵌入字体子集的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

本文提供了有关如何使用 Aspose.Words for .NET 的字体子集嵌入功能的分步指南。我们将详细解释代码的每一部分。在本教程结束时，您将能够了解如何在文档中嵌入字体子集并生成仅包含文档中使用的字形的 PDF。

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

## 第 3 步：配置另存为 PDF 选项

要创建仅包含文档中使用的字体子集的 PDF，我们需要配置`PdfSaveOptions`对象与`EmbedFullFonts`属性设置为`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## 第 4 步：将文档另存为带有字体子集的 PDF

最后，我们可以使用字体子集将文档保存为 PDF。指定输出文件名和`saveOptions`我们在上一步中配置的对象。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

就这样 ！您已经成功地将字体子集嵌入到文档中，并使用 Aspose.Words for .NET 生成了仅包含文档中使用的字形的 PDF。

### 使用 Aspose.Words for .NET 嵌入字体子集的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//输出 PDF 将包含文档中字体的子集。
	//只有文档中使用的字形包含在 PDF 字体中。
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```

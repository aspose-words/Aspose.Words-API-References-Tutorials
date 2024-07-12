---
title: 在 PDF 文档中嵌入子集字体
linktitle: 在 PDF 文档中嵌入子集字体
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 在 PDF 文档中嵌入字体子集的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

本文提供了有关如何使用 Aspose.Words for .NET 的字体子集嵌入功能的分步指南。我们将详细解释代码的每个部分。在本教程结束时，您将能够了解如何在文档中嵌入字体子集并生成仅包含文档中使用的字形的 PDF。

开始之前，请确保您已在项目中安装并配置了 Aspose.Words for .NET 库。您可以在 Aspose 网站上找到该库和安装说明。

## 步骤1：定义文档目录

首先，您需要定义文档所在目录的路径。替换`"YOUR DOCUMENT DIRECTORY"`使用您的文档目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：上传文件

接下来，我们需要加载要处理的文档。在此示例中，我们假设文档名为“Rendering.docx”，位于指定的文档目录中。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 步骤 3：配置另存为 PDF 选项

要创建仅包含文档中使用的字体子集的 PDF，我们需要配置`PdfSaveOptions`对象与`EmbedFullFonts`属性设置为`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## 步骤 4：将文档另存为包含字体子集的 PDF

最后，我们可以使用字体子集将文档保存为 PDF。指定输出文件名和`saveOptions`我们在上一步中配置的对象。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

就这样！您已成功将字体子集嵌入文档中，并使用 Aspose.Words for .NET 生成了仅包含文档中使用的字形的 PDF。

### 使用 Aspose.Words for .NET 嵌入字体子集的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//输出 PDF 将包含文档中字体的子集。
	// PDF 字体仅包含文档中使用的字形。
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```

## 结论

在本教程中，我们学习了如何使用 Aspose.Words for .NET 在 PDF 文档中嵌入字体子集。嵌入字体子集有助于减小 PDF 文件的大小，同时仅使用实际使用的字符来保留文档的外观。这可确保在查看和打印 PDF 时具有更好的兼容性和性能。请随意进一步探索 Aspose.Words for .NET 的功能，以优化使用嵌入字体子集的 PDF 文档的生成。

### 经常问的问题

#### 问：什么是在 PDF 文档中嵌入字体子集？
答：在 PDF 文档中嵌入字体子集是指仅包含文档中使用的字形，而不是包含所有完整字体的过程。通过仅包含显示文档中实际使用的字符所需的字体数据，可以减小 PDF 文件的大小。

#### 问：嵌入完整字体和嵌入字体子集有什么区别？
答：完全字体嵌入意味着将文档中使用的所有字体都包含在 PDF 文件中，这可确保文档按设计准确显示，但会增加 PDF 文件的大小。相比之下，嵌入字体子集仅包含文档中使用的字形，从而减小 PDF 文件的大小，但如果以后添加其他字符，则限制了准确复制文档外观的能力。

#### 问：如何使用 Aspose.Words for .NET 在 PDF 文档中嵌入字体子集？
答：要使用 Aspose.Words for .NET 在 PDF 文档中嵌入字体子集，请按照以下步骤操作：

通过替换来设置文档目录路径`"YOUR DOCUMENT DIRECTORY"`与您的文档目录的实际路径。

使用`Document`类和文档路径。

通过创建实例来配置 PDF 保存选项`PdfSaveOptions`类和设置`EmbedFullFonts`财产`false`这可确保只有文档中使用的字体子集才会包含在 PDF 文件中。

将文档保存为 PDF 格式，并使用嵌入的字体子集`Save`方法`Document`对象，指定输出文件的名称和之前配置的保存选项。

#### 问：在 PDF 文档中嵌入字体子集有什么好处？
答：在 PDF 文档中嵌入字体子集的好处是：

减小 PDF 文件大小：通过仅包含文档中使用的字形，与嵌入完整字体相比，PDF 文件大小有所减小。

保留文档的外观：PDF 文件中包含的字体子集使得仅使用实际使用的字符就可以重现文档的外观。

与许可证限制的兼容性：在由于许可限制而无法合法嵌入完整字体的情况下，可能优先嵌入字体子集。
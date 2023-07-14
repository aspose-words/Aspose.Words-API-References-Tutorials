---
title: 通过跳过嵌入的 Arial 和 Times Roman 字体优化 PDF 大小
linktitle: 通过跳过嵌入的 Arial 和 Times Roman 字体优化 PDF 大小
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 生成优化 PDF 且无需嵌入 Arial 和 Times Roman 字体的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

本文提供了有关如何使用该功能通过 Aspose.Words for .NET 将嵌入的 Arial 和 Times Roman 字体跳过到图元文件大小来优化 PDF 大小的分步指南。我们将详细解释代码的每一部分。在本教程结束时，您将能够了解如何在文档中配置字体嵌入模式选项并生成 PDF，而不嵌入 Arial 和 Times Roman 字体。

在开始之前，请确保您已在项目中安装并配置了 Aspose.Words for .NET 库。您可以在 Aspose 网站上找到库和安装说明。

## 第1步：定义文档目录

首先，您需要定义文档所在目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第2步：上传文件

接下来，我们需要加载我们想要处理的文档。在此示例中，我们假设文档名为“Rendering.docx”并且位于指定的文档目录中。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 步骤 3：配置带有字体嵌入的另存为 PDF 选项

要跳过在生成的 PDF 中嵌入 Arial 和 Times Roman 字体，我们需要配置`PdfSaveOptions`对象并设置`FontEmbeddingMode`财产给`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## 步骤 4：将文档另存为不嵌入字体的 PDF

最后，我们可以使用之前配置的保存选项将文档保存为 PDF 格式。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

就这样 ！您已使用 Aspose.Words for .NET 成功生成了 PDF，无需嵌入 Arial 和 Times Roman 字体。

### 使用 Aspose.Words for .NET 以图元文件大小跳过嵌入的 Arial 和 Times Roman 字体的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```

## 结论

在本教程中，我们解释了如何使用 Aspose.Words for .NET 在 PDF 文档中禁用 Arial 和 Times Roman 字体的嵌入。通过执行概述的步骤，您可以生成 PDF 文件，而无需嵌入这些特定字体，这有助于减小文件大小并确保文档在不同平台之间具有更好的兼容性。使用此功能时，请务必考虑禁用字体嵌入的后果。请随意探索 Aspose.Words for .NET 的更多功能来优化 PDF 文件的生成。

### 经常问的问题

#### 问：什么是禁用 PDF 文档中的 Arial 和 Times Roman 字体嵌入？为什么它很重要？
答：在 PDF 文档中禁用 Arial 和 Times Roman 字体的嵌入是指在生成的 PDF 文件中不包含这些字体的过程。通过避免包含 PDF 阅读器系统上已经常见的字体，这对于减小 PDF 文件的大小非常重要。它还可以帮助确保 PDF 文档在不同设备和平台上具有更好的兼容性和一致的外观。

#### 问：如何配置 Aspose.Words for .NET 不在 PDF 文档中嵌入 Arial 和 Times Roman 字体？
答：要将 Aspose.Words for .NET 配置为不在 PDF 文档中嵌入 Arial 和 Times Roman 字体，请按照以下步骤操作：

通过替换设置文档所在的目录路径`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

使用以下命令加载要处理的文档`Document`类和指定的文档路径。

创建一个实例`PdfSaveOptions`类并设置`FontEmbeddingMode`财产给`PdfFontEmbeddingMode.EmbedAll`。这将在生成的 PDF 文件中嵌入除 Arial 和 Times Roman 之外的所有字体。

使用`Save`的方法`Document`对象以 PDF 格式保存文档，指定之前配置的保存选项。

#### 问：在 PDF 文档中禁用 Arial 和 Times Roman 字体嵌入有什么好处？
答：在 PDF 文档中禁用 Arial 和 Times Roman 字体嵌入的好处是：

减小 PDF 文件大小：通过避免嵌入 Arial 和 Times Roman 等常用字体，可以减小 PDF 文件大小，从而更轻松地存储、共享和传输文件。

更好的兼容性：通过使用 PDF 阅读器系统上常用的字体，您可以确保文档在不同设备和平台上具有更好的兼容性和外观。

#### 问：在 PDF 文档中禁用 Arial 和 Times Roman 字体嵌入会产生什么后果？
答：在 PDF 文档中禁用 Arial 和 Times Roman 字体嵌入的后果如下：

外观不同：如果打开 PDF 的系统上没有 Arial 和 Times Roman 字体，则将使用替代字体，这可能会导致外观与预期不同。

可读性问题：使用的替代字体可能不如原始字体可读，这可能会影响文档的可读性。
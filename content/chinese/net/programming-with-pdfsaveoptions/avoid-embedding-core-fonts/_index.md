---
title: 通过不嵌入核心字体来减小 PDF 文件大小
linktitle: 通过不嵌入核心字体来减小 PDF 文件大小
second_title: Aspose.Words 文档处理 API
description: 了解如何在使用 Aspose.Words for .NET 将 Word 文档转换为 PDF 时通过不嵌入核心字体来减小 PDF 文件大小。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

在本教程中，我们将引导您完成如何使用 Aspose.Words for .NET 不嵌入核心字体来减小 PDF 文件大小的步骤。此功能允许您控制在转换 Word 文档时是否必须在 PDF 中嵌入基本字体（例如 Arial、Times New Roman 等）。请按照以下步骤操作：

## 步骤 1：加载文档

首先上传要转换为 PDF 的 Word 文档：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

确保指定 Word 文档的正确路径。

## 步骤 2：设置 PDF 转换选项

创建 PdfSaveOptions 类的实例并启用基本字体嵌入避免：

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

此选项控制是否应将基本字体嵌入 PDF。

## 步骤 3：将文档转换为 PDF

使用`Save`通过指定转换选项将 Word 文档转换为 PDF 的方法：

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

确保指定正确的路径来保存转换后的 PDF。

### 使用 Aspose.Words for .NET 避免嵌入核心字体的示例源代码

以下是使用该功能避免使用 Aspose.Words for .NET 嵌入核心字体的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//输出的 PDF 将不会嵌入核心字体，例如 Arial、Times New Roman 等。
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

通过遵循这些步骤，您可以轻松控制在使用 Aspose.Words for .NET 转换 Word 文档时是否应将基本字体嵌入 PDF 中。


## 结论

在本教程中，我们解释了如何使用 Aspose.Words for .NET 不嵌入基本字体来减小 PDF 文件的大小。此功能允许您控制在转换 Word 文档时是否应在 PDF 中嵌入基本字体。通过遵循概述的步骤，您可以轻松控制基本字体的嵌入或不嵌入，这有助于减小 PDF 文件大小并确保更好的兼容性以及文档在不同设备和平台上的一致外观。不要忘记考虑不嵌入基本字体的后果，并进行实验以确保文档按预期呈现。

### 经常问的问题

#### 问：在 PDF 文件中不嵌入基本字体的选项是什么？为什么这很重要？
答：不嵌入基本字体到 PDF 文件的选项控制在转换 Word 文档时是否必须嵌入基本字体（例如 Arial、Times New Roman 等）。通过避免包含 PDF 阅读器系统上常用的字体，这对于减小 PDF 文件的大小非常重要。它还可以帮助确保 PDF 文档在不同设备和平台上具有更好的兼容性和一致的外观。

#### 问：如何配置 Aspose.Words for .NET 以便不在 PDF 文件中嵌入基本字体？
答：要配置 Aspose.Words for .NET 以不在 PDF 文件中嵌入核心字体，请按照以下步骤操作：

通过替换来设置文档所在的目录路径`"YOUR DOCUMENTS DIRECTORY"`与您的文档目录的实际路径。

使用`Document`类和指定的文档路径。

创建一个实例`PdfSaveOptions`类并设置`UseCoreFonts`财产`true`。这将避免在生成的 PDF 文件中嵌入基本字体。

使用`Save`方法`Document`对象以 PDF 格式保存文档，指定之前配置的转换选项。

#### 问：在 PDF 文件中不嵌入基本字体有什么好处？
答：不在 PDF 文件中嵌入基础字体的好处是：

PDF 文件大小减小：通过避免嵌入常用字体（如 Arial、Times New Roman 等），可以减小 PDF 文件大小，从而更易于存储、共享和传输文件。

更好的兼容性：通过使用 PDF 阅读器系统上常用的基本字体，您可以确保在不同设备和平台上更好的兼容性和文档外观。

#### 问：如果 PDF 文件中没有嵌入基础字体会有什么后果？
答：PDF文件中不嵌入基础字体的后果如下：

不同的外观：如果打开 PDF 的系统上没有基本字体，则将使用替代字体，这可能会导致外观与预期不同。

可读性问题：使用的替代字体可能不如原始字体清晰易读，这可能会影响文档的可读性。
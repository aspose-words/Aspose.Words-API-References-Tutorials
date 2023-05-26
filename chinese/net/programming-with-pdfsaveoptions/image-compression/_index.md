---
title: 图像压缩
linktitle: 图像压缩
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 压缩图像的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/image-compression/
---

本文提供了有关如何使用 Aspose.Words for .NET 的图像压缩功能的分步指南。我们将详细解释代码的每一部分。在本教程结束时，您将能够了解如何压缩文档中的图像并生成具有适当图像压缩的 PDF。

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

## 第 3 步：配置带有图像压缩的另存为 PDF 选项

要在转换为 PDF 时压缩图像，我们需要配置`PdfSaveOptions`目的。如果需要，我们可以设置图像压缩类型、JPEG 质量和其他 PDF 合规性选项。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## 第 4 步：将文档另存为带图像压缩的 PDF

最后，我们可以使用之前配置的保存选项将文档保存为 PDF 格式。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## 第 5 步：配置使用图像压缩保存为 PDF/A-2u 的选项

如果要生成具有图像压缩的 PDF/A-2u 兼容 PDF，您可以配置其他保存选项。

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, //使用质量为 50% 的 JPEG 压缩来减小文件大小。
};
```

## 第 6 步：将文档另存为带图像压缩的 PDF/A-2u

使用之前配置的附加保存选项将文档保存为 PDF/A-2u 格式。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



就这样 ！您已经使用 Aspose.Words for .NET 成功地压缩了文档中的图像并生成了具有适当图像压缩的 PDF。

### 使用 Aspose.Words for .NET 压缩图像的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		ImageCompression = PdfImageCompression.Jpeg, PreserveFormFields = true
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);

	PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
	{
		Compliance = PdfCompliance.PdfA2u,
		ImageCompression = PdfImageCompression.Jpeg,
		JpegQuality = 100, //使用 50% 质量的 JPEG 压缩来减小文件大小。
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```

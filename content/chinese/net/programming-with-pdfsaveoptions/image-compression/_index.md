---
title: PDF 文档中的图像压缩
linktitle: PDF 文档中的图像压缩
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 压缩 PDF 文档中图像的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/image-compression/
---

本文提供了有关如何使用 Aspose.Words for .NET 的 PDF 文档图像压缩功能的分步指南。我们将详细解释代码的每个部分。在本教程结束时，您将能够了解如何压缩文档中的图像并生成具有适当图像压缩的 PDF。

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

## 步骤 3：配置使用图像压缩保存为 PDF 选项

要在转换为 PDF 时压缩图像，我们需要配置`PdfSaveOptions`对象。我们可以根据需要设置图像压缩类型、JPEG 质量和其他 PDF 合规选项。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## 步骤 4：使用图像压缩将文档保存为 PDF

最后，我们可以使用之前配置的保存选项将文档保存为 PDF 格式。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## 步骤 5：配置使用图像压缩保存为 PDF/A-2u 的选项

如果您想生成符合 PDF/A-2u 标准的带有图像压缩的 PDF，您可以配置额外的保存选项。

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, //使用 50% 质量的 JPEG 压缩来减小文件大小。
};
```

## 步骤 6：将文档保存为 PDF/A-2u 格式并进行图像压缩

使用之前配置的附加保存选项将文档保存为 PDF/A-2u 格式。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



就这样！您已成功压缩文档中的图像并使用 Aspose.Words for .NET 生成了具有适当图像压缩的 PDF。

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

## 结论

在本教程中，我们解释了如何使用 Aspose.Words for .NET 压缩 PDF 文档中的图像。按照所述步骤，您可以轻松减小 PDF 文档中图像的大小并生成具有适当图像压缩的 PDF。使用 Aspose.Words for .NET 的图像压缩功能可以优化 PDF 文档的大小，同时保持图像质量。

### 经常问的问题

#### 问：PDF 文档中的图像压缩是什么？
答：压缩 PDF 文档中的图片是为了减小 PDF 文档中包含的图片的大小，从而减小 PDF 文件的整体大小。这可以减少所需的存储空间并提高加载和查看 PDF 时的性能。

#### 问：如何使用 Aspose.Words for .NET 压缩 PDF 文档中的图像？
答：要使用 Aspose.Words for .NET 压缩 PDF 文档中的图像，请按照以下步骤操作：

创建一个实例`Document`指定 Word 文档路径的类。

创建一个实例`PdfSaveOptions`类并设置`ImageCompression`财产`PdfImageCompression.Jpeg`使用 JPEG 压缩。

您还可以根据需要设置其他图像压缩选项，例如 JPEG 质量。

使用`Save`方法`Document`通过指定保存选项将文档保存为 PDF 格式。

#### 问：标准图像压缩和 PDF/A-2u 图像压缩有什么区别？
答：标准图像压缩可减少 PDF 文档中图像的大小，同时保留表单字段。这可减少 PDF 文件的整体大小，而不会影响表单字段的功能。

PDF/A-2u 图像压缩是一个附加选项，允许您在应用图像压缩的同时生成符合 PDF/A-2u 标准的 PDF 文件。PDF/A-2u 是档案 PDF 文档的 ISO 标准，可确保文档的长期保存。

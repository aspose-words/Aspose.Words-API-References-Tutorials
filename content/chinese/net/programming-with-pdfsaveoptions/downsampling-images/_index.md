---
title: 通过降低图像采样率来减小 PDF 文档大小
linktitle: 通过降低图像采样率来减小 PDF 文档大小
second_title: Aspose.Words 文档处理 API
description: 了解如何在使用 Aspose.Words for .NET 转换为 PDF 时通过下采样图像来减小 pdf 文档大小。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/downsampling-images/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 转换为 PDF 时通过下采样图像来减小 PDF 文档大小的步骤。这会减小生成的 PDF 文件的大小。请按照以下步骤操作：

## 步骤 1：加载文档

首先上传您想要转换为 PDF 的文档：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

请确保指定文档的正确路径。

## 步骤 2：配置 PDF 保存选项

创建 PdfSaveOptions 类的实例并设置图像缩小选项：

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

这`Resolution`属性指定图像的目标分辨率和`ResolutionThreshold`属性指定图像不会缩小的最小分辨率。

## 步骤 3：将文档转换为 PDF

使用`Save`将文档转换为 PDF 的方法指定保存选项：

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

确保指定正确的路径来保存转换后的 PDF。

### 使用 Aspose.Words for .NET 进行图像下采样的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//我们可以设置下采样的最小阈值。
	//该值将阻止输入文档中的第二个图像被下采样。
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

通过遵循这些步骤，您可以在使用 Aspose.Words for .NET 转换为 PDF 时轻松降低图像分辨率。

## 结论

在本教程中，我们解释了如何在使用 Aspose.Words for .NET 转换为 PDF 时通过图像采样来减小 PDF 文档的大小。通过遵循所述步骤，您可以轻松降低图像的分辨率和生成的 PDF 文件的大小。请确保指定文档的正确路径并根据需要配置图像采样选项。减小 PDF 文件大小可以更轻松地在不同平台上共享、存储和快速加载文件。享受使用 Aspose.Words for .NET 通过图像采样减小 PDF 文档大小的好处。

### 经常问的问题

#### 问：如何使用图像采样来减小 PDF 文档的大小？
A：使用图像采样缩小 PDF 文档大小是指在转换为 PDF 时通过降低图像的分辨率来减小生成的 PDF 文件的大小。这可以优化存储空间的使用，并使 PDF 文件更易于共享和传输。

#### 问：如何使用 Aspose.Words for .NET 通过图像采样来减小 PDF 文档大小？
答：要使用 Aspose.Words for .NET 通过图像采样来减小 PDF 文档大小，请按照以下步骤操作：

通过替换来设置文档所在的目录路径`"YOUR DOCUMENTS DIRECTORY"`与您的文档目录的实际路径。

使用`Document`类并指定指定文档目录中文档的路径。

通过创建实例来配置另存为 PDF 选项`PdfSaveOptions`类并使用设置图像采样选项`DownsampleOptions`属性。您可以使用`Resolution`属性并设置一个最小分辨率阈值，高于该阈值的图像将不会使用`ResolutionThreshold`财产。

使用`Save`方法`Document`指定路径和保存选项的类。

#### 问：使用图像采样减少 PDF 文档大小有什么好处？
答：使用图像采样减少 PDF 文档大小的好处是：

减小 PDF 文件大小：图像采样可降低 PDF 文档中图像的分辨率，从而显著减小 PDF 文件大小。这样可轻松共享和传输文件，尤其是通过电子邮件或在线方式。

优化存储空间：减小 PDF 文件的大小有助于优化存储空间的使用，尤其是当您有许多包含高分辨率图像的 PDF 文件时。

性能改进：较小的 PDF 文件加载速度更快，并且可以在不同设备上更快地打开和查看。
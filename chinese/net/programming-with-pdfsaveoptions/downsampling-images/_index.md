---
title: 下采样图像
linktitle: 下采样图像
second_title: Aspose.Words for .NET API 参考
description: 了解如何在使用 Aspose.Words for .NET 转换为 PDF 时降低图像分辨率。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/downsampling-images/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 转换为 PDF 时降低图像分辨率的步骤。这会减小生成的 PDF 文件的大小。请按照以下步骤操作：

## 第 1 步：装入文档

首先上传要转换为 PDF 的文档：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

请务必指定文档的正确路径。

## 第 2 步：配置 PDF 保存选项

创建 PdfSaveOptions 类的实例并设置图像缩小选项：

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

这`Resolution`属性指定图像的目标分辨率和`ResolutionThreshold`属性指定图像不会按比例缩小的最小分辨率。

## 第 3 步：将文档转换为 PDF

使用`Save`指定保存选项将文档转换为 PDF 的方法：

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

确保指定正确的路径以保存转换后的 PDF。

### 使用 Aspose.Words for .NET 对图像进行下采样的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//我们可以设置下采样的最小阈值。
	//该值将防止输入文档中的第二个图像被缩减采样。
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

通过执行这些步骤，您可以在使用 Aspose.Words for .NET 转换为 PDF 时轻松降低图像分辨率。



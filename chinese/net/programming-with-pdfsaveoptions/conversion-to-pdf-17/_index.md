---
title: 转换为 PDF 17
linktitle: 转换为 PDF 17
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将文档转换为 PDF 1.7。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/conversion-to-pdf-17/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 转换为 PDF 1.7 的步骤。转换为 PDF 1.7 允许您生成符合 PDF 1.7 标准的 PDF 文件。请按照以下步骤操作：

## 第 1 步：装入文档

首先上传要转换为 PDF 的文档：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

请务必指定文档的正确路径。

## 第 2 步：设置 PDF 转换选项

创建 PdfSaveOptions 类的实例并指定要使用的 PDF 标准版本：

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };
```

该选项确保生成的 PDF 文件符合 PDF 1.7 标准。

## 第 3 步：将文档转换为 PDF

使用`Save`指定转换选项将文档转换为 PDF 的方法：

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);
```

确保指定正确的路径以保存转换后的 PDF。

### 使用 Aspose.Words for .NET 转换为 Pdf 17 的示例源代码

下面是使用 Aspose.Words for .NET 转换为 PDF 1.7 的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);

```

按照这些步骤，您可以使用 Aspose.Words for .NET 轻松转换为 PDF 1.7。


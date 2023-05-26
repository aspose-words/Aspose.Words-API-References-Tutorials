---
title: 加载加密的 PDF
linktitle: 加载加密的 PDF
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 加载加密 PDF 的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-pdfloadoptions/load-encrypted-pdf/
---

在 .NET 应用程序中处理 PDF 文档时，可能需要加载受密码保护的 PDF 文件。 Aspose.Words for .NET 是一个功能强大的库，提供加载加密 PDF 文档的功能。在本文中，我们将逐步引导您了解和使用该功能。

## 了解加载加密的 PDF 功能

Aspose.Words for .NET 的加载加密 PDF 功能允许您加载受密码保护的 PDF 文件。您可以在加载文档时指定密码，以便您可以访问其内容并根据需要对其进行操作。

## 第 1 步：加载加密的 PDF 文档

第一步是将加密的 PDF 文档加载到您的应用程序中。方法如下：

```csharp
//文档目录的路径。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Document.pdf");
```

请务必在`dataDir`多变的。

## 第 2 步：加密 PDF 文档

如果您还想加密您的 PDF 文档，您可以使用`PdfSaveOptions`类并指定加密细节：

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
};

```

这将在指定目录中创建 PDF 文档的加密版本。

## 第 3 步：保存加密的 PDF 文档

上传并可选择加密 PDF 文档后，您可以将其保存为其他格式或根据您的特定需要进一步处理。

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);
```

## 第 5 步：加载带密码的加密 PDF 文档

维护

但是，如果要加载带密码的加密 PDF 文档，则必须使用`PdfLoadOptions`类并在加载文档时指定密码：

```csharp
PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
```

请务必在`Password`多变的。

### 使用 Aspose.Words for .NET 加载加密 PDF 的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Pdf Document.pdf");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
	};

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);

	PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

	doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
        
```

## 结论

在本文中，我们探讨了如何使用 Aspose.Words for .NET 的加载加密 PDF 功能。您学习了如何上传加密的 PDF 文件、如何加密 PDF 文档、如何上传带密码的加密 PDF 以及如何生成 Markdown 格式的输出。在处理安全 PDF 文档时，此功能非常有用。



---
title: 加载加密 PDF
linktitle: 加载加密 PDF
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 加载加密 PDF 的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-pdfloadoptions/load-encrypted-pdf/
---

当您在 .NET 应用程序中对 PDF 文档进行文字处理时，可能需要加载受密码保护的 PDF 文件。Aspose.Words for .NET 是一个功能强大的库，可提供加载加密 PDF 文档的功能。在本文中，我们将逐步指导您了解和使用此功能。

## 了解加载加密 PDF 功能

Aspose.Words for .NET 的“加载加密 PDF”功能允许您加载受密码保护的 PDF 文件。您可以在加载文档时指定密码，以便访问其内容并根据需要对其进行操作。

## 步骤 1：加载加密的 PDF 文档

第一步是将加密的 PDF 文档加载到您的应用程序中。操作方法如下：

```csharp
//文档目录的路径。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Document.pdf");
```

确保在`dataDir`多变的。

## 步骤2：加密PDF文档

如果你还想加密 PDF 文档，你可以使用`PdfSaveOptions`类并指定加密细节：

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
};

```

这将在指定目录中创建 PDF 文档的加密版本。

## 步骤3：保存加密的PDF文档

上传并选择性加密 PDF 文档后，您可以将其保存为其他格式或根据您的特定需求进一步处理。

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);
```

## 步骤5：加载带密码的加密PDF文档

维护

但是，如果您想加载带有密码的加密 PDF 文档，则必须使用`PdfLoadOptions`类并在加载文档时指定密码：

```csharp
PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
```

确保在`Password`多变的。

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

在本文中，我们探讨了如何使用 Aspose.Words for .NET 的“加载加密 PDF”功能。您学习了如何上传加密 PDF 文件、如何加密 PDF 文档、如何使用密码上传加密 PDF 以及如何生成 Markdown 格式的输出。当使用安全的 PDF 文档进行文字处理时，此功能非常有用。



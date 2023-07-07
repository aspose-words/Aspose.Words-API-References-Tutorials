---
title: 加载 Pdf 的页面范围
linktitle: 加载 Pdf 的页面范围
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 加载特定 PDF 页面范围的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

在本教程中，我们将引导您了解如何使用 Aspose.Words for .NET 从 PDF 文档加载特定页面范围。请按照以下步骤操作：

## 第 1 步：加载一系列 PDF 页面

使用以下代码从 PDF 文档加载特定页面范围：

```csharp
//文档目录的路径。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

在此示例中，我们正在加载 PDF 文档的第一页。您可以更改以下值`PageIndex`和`PageCount`到所需的页面范围。

## 第 2 步：保存文档

最后，您可以使用以下命令保存包含特定页面范围的文档`Save`方法：

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

请务必指定正确的路径来保存编辑后的文档。

就这样 ！您现在已经使用 Aspose.Words for .NET 从 PDF 文档加载了特定页面范围。

### 使用 Aspose.Words for .NET 加载 Pdf 页面范围的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
请记住指定 PDF 文档目录的正确路径。




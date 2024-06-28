---
title: 加載 Pdf 的頁面範圍
linktitle: 加載 Pdf 的頁面範圍
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 載入特定 PDF 頁面範圍的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

在本教學中，我們將引導您了解如何使用 Aspose.Words for .NET 從 PDF 文件載入特定頁面範圍。請依照以下步驟操作：

## 第 1 步：載入一系列 PDF 頁面

使用以下程式碼從 PDF 文件載入特定頁面範圍：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

在此範例中，我們正在載入 PDF 文件的第一頁。您可以變更的值`PageIndex`和`PageCount`到所需的頁面範圍。

## 第 2 步：儲存文檔

最後，您可以使用以下命令儲存包含特定頁面範圍的文檔`Save`方法：

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

請務必指定正確的路徑來儲存編輯後的文件。

就這樣 ！您現在已經使用 Aspose.Words for .NET 從 PDF 文件載入了特定頁面範圍。

### 使用 Aspose.Words for .NET 載入 Pdf 頁面範圍的範例原始程式碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
請記得指定 PDF 文件目錄的正確路徑。




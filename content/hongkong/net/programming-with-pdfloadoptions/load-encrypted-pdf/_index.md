---
title: 載入加密的 PDF
linktitle: 載入加密的 PDF
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 載入加密 PDF 的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-pdfloadoptions/load-encrypted-pdf/
---

在 .NET 應用程式中對 PDF 文件進行文字處理時，可能需要載入受密碼保護的 PDF 檔案。 Aspose.Words for .NET 是一個功能強大的程式庫，提供載入加密 PDF 文件的功能。在本文中，我們將逐步引導您了解和使用此功能。

## 了解載入加密 PDF 功能

Aspose.Words for .NET 的載入加密 PDF 功能可讓您載入受密碼保護的 PDF 檔案。您可以在載入文件時指定密碼，以便您可以存取其內容並根據需要進行操作。

## 步驟1：載入加密的PDF文檔

第一步是將加密的 PDF 文件載入到您的應用程式中。操作方法如下：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Document.pdf");
```

請務必在中指定加密 PDF 檔案的正確路徑`dataDir`多變的。

## 步驟2：加密PDF文檔

如果您還想加密 PDF 文檔，可以使用`PdfSaveOptions`類別並指定加密詳細資訊：

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
};

```

這將在指定目錄中建立 PDF 文件的加密版本。

## 步驟3：儲存加密的PDF文檔

上傳並選擇加密 PDF 文件後，您可以將其儲存為其他格式或根據您的特定需求進一步處理。

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);
```

## 步驟5：載入帶有密碼的加密PDF文檔

維護

但是，如果您想載入帶有密碼的加密 PDF 文檔，則必須使用`PdfLoadOptions`類別並在載入文件時指定密碼：

```csharp
PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
```

請務必在密碼中提供正確的密碼`Password`多變的。

### 使用 Aspose.Words for .NET 載入加密 PDF 的範例原始程式碼

```csharp

	//文檔目錄的路徑。
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

## 結論

在本文中，我們探討如何使用 Aspose.Words for .NET 的載入加密 PDF 功能。您學習如何上傳加密的 PDF 文件、如何加密 PDF 文件、如何上傳帶有密碼的加密 PDF 以及如何產生 Markdown 格式的輸出。當對安全 PDF 文件進行文字處理時，此功能非常有用。



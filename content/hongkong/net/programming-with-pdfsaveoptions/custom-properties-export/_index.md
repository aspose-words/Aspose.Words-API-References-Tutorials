---
title: 匯出 PDF 文件中的自訂屬性
linktitle: 匯出 PDF 文件中的自訂屬性
second_title: Aspose.Words 文件處理 API
description: 了解如何在使用 Aspose.Words for .NET 將文件轉換為 PDF 時匯出自訂屬性。
type: docs
weight: 10
url: /zh-hant/net/programming-with-pdfsaveoptions/custom-properties-export/
---

在本教學中，我們將引導您完成使用 Aspose.Words for .NET 將文件的自訂屬性匯出到 PDF 文件中的步驟。匯出自訂屬性可讓您在產生的 PDF 文件中包含附加資訊。請依照以下步驟操作：

## 第 1 步：建立文件並新增自訂屬性

首先建立 Document 類別的實例：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## 第 2 步：新增自訂屬性
接下來，新增所需的自訂屬性。例如，若要新增值為“Aspose”的“Company”屬性，請使用`Add`CustomDocumentProperties 集合的方法：

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

您可以根據需要新增任意數量的自訂屬性。

## 第 3 步：設定 PDF 匯出選項

建立 PdfSaveOptions 類別的實例並指定如何匯出自訂屬性：

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

此選項控制轉換為 PDF 時自訂屬性的匯出。

## 步驟 4：將文件轉換為 PDF

使用`Save`將文件轉換為 PDF 的方法，指定轉換選項：

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

確保指定正確的路徑來儲存轉換後的 PDF。

### 使用 Aspose.Words for .NET 自訂屬性匯出的範例原始程式碼

以下是使用 Aspose.Words for .NET 從文件匯出自訂屬性的完整原始碼：


```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

透過執行下列步驟，您可以在使用 Aspose.Words for .NET 轉換為 PDF 時輕鬆匯出文件的自訂屬性。


## 結論

在本教學中，我們解釋如何使用 Aspose.Words for .NET 將自訂屬性從文件匯出到 PDF 文件。按照所述的步驟，您可以透過匯出文件的自訂屬性，輕鬆地在產生的 PDF 文件中包含附加資訊。利用 Aspose.Words for .NET 的功能，透過匯出自訂屬性來個人化和豐富您的 PDF 文件。

### 經常問的問題

#### Q：什麼是將自訂屬性匯出到 PDF 文件？
答：將自訂屬性匯出到 PDF 文件允許在產生的 PDF 文件中包含附加資訊。自訂屬性是特定於您的文件的元數據，例如標籤、關鍵字或憑證。透過匯出這些自訂屬性，您可以使用戶在查看 PDF 文件時可以使用它們。

#### Q：如何使用 Aspose.Words for .NET 將文件的自訂屬性匯出到 PDF 文件？
答：若要使用 Aspose.Words for .NET 將文檔的自訂屬性匯出至 PDF 文檔，請依照下列步驟操作：

建立一個實例`Document`班級。

使用以下命令新增所需的自訂屬性`CustomDocumentProperties`收藏。例如，使用`Add`方法新增值為“Aspose”的“Company”屬性。

建立一個實例`PdfSaveOptions`類別並指定如何使用匯出自訂屬性`CustomPropertiesExport`財產。這`PdfCustomPropertiesExport.Standard`value 根據預設設定匯出自訂屬性。

使用`Save`的方法`Document`用於將文件轉換為 PDF 的類，指定轉換選項。

#### Q：如何存取 PDF 文件的自訂屬性？
答：要存取 PDF 文件的自訂屬性，您可以使用支援檢視文件屬性的相容 PDF 閱讀器。最常見的 PDF 閱讀器（例如 Adobe Acrobat Reader）提供對 PDF 文件的元資料和屬性的存取。您通常可以在“文件”選單下找到這些選項，或者右鍵單擊文件並選擇“屬性”。
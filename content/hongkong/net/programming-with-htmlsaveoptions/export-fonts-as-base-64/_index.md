---
title: 將字體匯出為 Base 64
linktitle: 將字體匯出為 Base 64
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 儲存文件時匯出 Base 64 字體的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

在本教程中，我們將引導您完成 C# 原始程式碼，以使用 Aspose.Words for .NET 匯出 Base 64 字體。此功能可讓您在以 HTML 格式儲存文件時將字體匯出為 Base 64 資料。

## 第 1 步：項目設置

首先，在您最喜歡的 IDE 中建立一個新的 C# 專案。請確定您的專案中引用了 Aspose.Words for .NET 程式庫。

## 第 2 步：載入文檔

在此步驟中，我們將載入要匯出的文件。使用以下程式碼從指定目錄載入文件：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

這段程式碼創建了一個實例`Document`透過從指定目錄載入文件。

## 步驟 3：設定 HTML 備份選項

現在我們將配置 HTML 儲存選項以匯出 Base 64 字體。使用以下程式碼：

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

這段程式碼創建了一個實例`HtmlSaveOptions`和集`ExportFontsAsBase64`到`true`指定儲存為 HTML 時應將字體匯出為 Base 64 資料。

## 步驟 4：將文件轉換並儲存為 HTML

最後，我們將使用先前配置的 HTML 儲存選項將文件轉換為 HTML。使用以下程式碼：

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

此程式碼將文件轉換為 HTML 並將其儲存到文件中，其中字體匯出為 Base 64 資料。

### 使用 Aspose.Words for .NET 將字體匯出為 Base 64 的範例原始程式碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

請務必在檔案目錄中指定正確的路徑`dataDir`多變的。

現在您已經了解如何使用 Aspose.Words for .NET 將文件儲存為 HTML 時匯出 Base 64 字體。透過遵循本教學中提供的逐步指南，您可以輕鬆安全地匯出字體並將其嵌入到 HTML 文件中。
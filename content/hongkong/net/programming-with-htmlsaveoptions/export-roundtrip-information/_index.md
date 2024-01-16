---
title: 匯出往返資訊
linktitle: 匯出往返資訊
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 將文件儲存為 HTML 時匯出往返資訊的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

在本教程中，我們將引導您完成 C# 原始程式碼，以使用 Aspose.Words for .NET 從文件中匯出往返資訊。此功能可讓您在匯出的 HTML 檔案中包含往返訊息，從而更輕鬆地擷取對原始文件所做的變更。

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

現在我們將配置 HTML 儲存選項以匯出文件的往返資訊。使用以下程式碼：

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

這段程式碼創建了一個實例`HtmlSaveOptions`並設定`ExportRoundtripInformation`選項`true`導出時包含往返資訊。

## 步驟 4：將文件轉換並儲存為 HTML

最後，我們將使用先前配置的 HTML 儲存選項將文件轉換為 HTML。使用以下程式碼：

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

此程式碼將文件轉換為包含往返資訊的 HTML，並將匯出的 HTML 檔案儲存到指定目錄。

### 使用 Aspose.Words for .NET 匯出往返資訊的範例原始程式碼


```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

請務必在檔案目錄中指定正確的路徑`dataDir`多變的。
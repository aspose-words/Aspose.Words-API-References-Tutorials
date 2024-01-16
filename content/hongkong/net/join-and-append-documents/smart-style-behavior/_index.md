---
title: 聰明的風格行為
linktitle: 聰明的風格行為
second_title: Aspose.Words 文件處理 API
description: 了解如何在使用 Aspose.Words for .NET 加入和附加 Word 文件時保持智慧樣式行為。
type: docs
weight: 10
url: /zh-hant/net/join-and-append-documents/smart-style-behavior/
---

本教學將引導您完成使用 Aspose.Words for .NET 的智慧樣式行為功能的過程。此功能可讓您加入和附加 Word 文件，同時保持智慧樣式行為。

## 先決條件

在開始之前，請確保您具備以下條件：

1. Aspose.Words for .NET 已安裝。您可以從 Aspose 網站下載它或透過 NuGet 安裝它。
2. Visual Studio 或任何其他 C# 開發環境。

## 第 1 步：初始化文件目錄

首先，您需要設定文檔目錄的路徑。修改值`dataDir`變數到您的文件所在的路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：載入來源文檔和目標文檔

接下來，您需要使用 Aspose.Words 來載入來源文檔和目標文檔`Document`班級。更新檔名`Document`根據您的文檔名稱建構函數。

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 步驟 3：在目標文件中插入分頁符

為了確保附加的內容出現在目標文件的新頁面上，您可以使用`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## 第 4 步：設定智慧型樣式行為選項

若要在追加作業期間啟用智慧樣式行為，您需要建立一個實例`ImportFormatOptions`並設定`SmartStyleBehavior`財產給`true`.

```csharp
ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
```

## 步驟 5：將來源文檔附加到目標文檔

現在，您可以使用以下命令將來源文檔附加到目標文檔`InsertDocument`的方法`DocumentBuilder`班級。使用`ImportFormatMode.UseDestinationStyles`參數並傳遞`ImportFormatOptions`物件保持智慧風格行為。

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## 第 6 步：儲存最終文檔

最後，使用啟用的智慧型樣式行為功能儲存合併的文檔`Save`的方法`Document`班級。

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

### 使用 Aspose.Words for .NET 的智慧樣式行為的範例原始程式碼

以下是使用 Aspose.Words for .NET 在 C# 中實作「智慧樣式行為」功能的完整原始碼：
 
```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
	builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

就是這樣！您已使用 Aspose.Words for .NET 成功實現了智慧樣式行為功能。最終文件將包含合併的內容，並保持智慧樣式行為。
---
title: 使用生成器插入文檔
linktitle: 使用生成器插入文檔
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在另一個文件的末尾插入一個文件。
type: docs
weight: 10
url: /zh-hant/net/join-and-append-documents/insert-document-with-builder/
---

本教學課程說明如何使用 Aspose.Words for .NET 將一個文件插入到另一個文件中`DocumentBuilder`班級。提供的原始程式碼示範如何在另一個文檔的末尾插入一個文檔，同時保留來源格式。

## 第 1 步：設定項目

確保您具備以下先決條件：

- 已安裝 Aspose.Words for .NET 程式庫。您可以從以下位置下載：[Aspose.Releases]https://releases.aspose.com/words/net/ 或使用 NuGet 套件管理器來安裝它。
- 來源文檔和目標文檔所在的文檔目錄路徑。

## 步驟 2：開啟來源文檔和目標文檔

使用以下命令開啟來源文檔和目標文檔`Document`類別構造函數。代替`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 第 3 步：初始化 DocumentBuilder

建立一個新實例`DocumentBuilder`類別並將目標文件作為參數傳遞。

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## 第 4 步：定位 DocumentBuilder

移動`DocumentBuilder`到文件末尾，使用`MoveToDocumentEnd`方法。插入分頁符號以將現有內容與插入的文件分開。

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## 步驟5：插入來源文檔

使用`InsertDocument`的方法`DocumentBuilder`類別將來源文檔插入目標文件中。將匯入格式模式設定為`ImportFormatMode.KeepSourceFormatting`保留來源格式。

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 第六步：儲存修改後的文檔

最後，使用以下命令儲存修改後的目標文檔`Save`的方法`Document`目的。

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

這樣就完成了使用 Aspose.Words for .NET 將一個文件插入另一個文件的實作。

### 使用 Aspose.Words for .NET 插入文件與生成器的範例原始碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```
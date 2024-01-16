---
title: 將文件附加到空白
linktitle: 將文件附加到空白
second_title: Aspose.Words 文件處理 API
description: 了解如何將文件附加到 Aspose.Words for .NET 中的空白目標文件。
type: docs
weight: 10
url: /zh-hant/net/join-and-append-documents/append-document-to-blank/
---

本教學課程介紹如何使用 Aspose.Words for .NET 將一個文件的內容附加到空白目標文件。提供的原始程式碼示範如何建立新文件、刪除其內容，然後將來源文件附加到其中。

## 第 1 步：設定項目

確保您具備以下先決條件：

- 已安裝 Aspose.Words for .NET 程式庫。您可以從以下位置下載：[Aspose.Releases]https://releases.aspose.com/words/net/ 或使用 NuGet 套件管理器來安裝它。
- 來源文檔和目標文檔所在的文檔目錄路徑。

## 第 2 步：建立新的目標文檔

創建一個新的`Document`目標文檔的物件。

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## 步驟 3：從目標文件中刪除現有內容

為了確保目標文件乾淨，請使用以下命令從文件中刪除所有現有內容`RemoveAllChildren`方法。

```csharp
dstDoc.RemoveAllChildren();
```

## 步驟 4：將來源文檔附加到目標文檔

使用以下命令將來源文檔的內容附加到目標文檔`AppendDocument`方法與`ImportFormatMode.KeepSourceFormatting`選項。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 步驟 5：儲存目標文檔

最後，使用以下命令儲存修改後的目標文檔`Save`的方法`Document`目的。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

這樣就完成了使用 Aspose.Words for .NET 將文件附加到空白目標文件的實作。

### 使用 Aspose.Words for .NET 將文件追加到空白的範例原始碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	//目標文件不為空，通常會導致附加文件之前出現空白頁。
	//這是因為基礎文件有一個空白部分，而新文件從下一頁開始。
	//附加之前從目標文件中刪除所有內容。
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```
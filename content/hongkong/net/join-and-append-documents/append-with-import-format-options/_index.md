---
title: 新增導入格式選項
linktitle: 新增導入格式選項
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 附加具有匯入格式選項的文件。
type: docs
weight: 10
url: /zh-hant/net/join-and-append-documents/append-with-import-format-options/
---

本教學課程說明如何使用 Aspose.Words for .NET 透過匯入格式選項將一個文件的內容附加到另一個文件。提供的原始程式碼示範如何開啟來源文件和目標文件、指定匯入格式選項以及將來源文件附加到目標文件。

## 第 1 步：設定項目

確保您具備以下先決條件：

- 已安裝 Aspose.Words for .NET 程式庫。您可以從以下位置下載：[Aspose.Releases]https://releases.aspose.com/words/net/ 或使用 NuGet 套件管理器來安裝它。
- 來源文檔和目標文檔所在的文檔目錄路徑。

## 步驟 2：開啟來源文檔和目標文檔

使用以下命令開啟來源文檔和目標文檔`Document`類別構造函數。代替`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## 步驟 3：指定導入格式選項

建立一個實例`ImportFormatOptions`類別來指定導入格式選項。在這個例子中，我們使用`KeepSourceNumbering`屬性，以確保在與目標文件發生衝突時使用來源文件的編號。

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## 步驟 4：將來源文檔附加到目標文檔

使用`AppendDocument`目標文件附加來源文檔的方法。經過`ImportFormatMode.UseDestinationStyles`作為第二個參數來使用目標文件的樣式和格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## 步驟 5：儲存目標文檔

最後，使用以下命令儲存修改後的目標文檔`Save`的方法`Document`目的。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

這樣就完成了使用 Aspose.Words for .NET 附加具有導入格式選項的文件的實作。

### 使用 Aspose.Words for .NET 附加導入格式選項的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	//指定如果來源文件和目標文件中的編號衝突，
	//然後將使用來源文檔中的編號。
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```
---
title: 附加文檔
linktitle: 附加文檔
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將一個文件的內容附加到另一個文件。
type: docs
weight: 10
url: /zh-hant/net/join-and-append-documents/append-document/
---

本教學課程介紹如何使用 Aspose.Words for .NET 將一個文件的內容附加到另一個文件。提供的原始程式碼示範如何開啟來源文檔和目標文檔，將來源文檔中的部分匯入並附加到目標文檔。

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

## 步驟 3：將來源文檔中的部分附加到目標文檔

循環遍歷來源文件中的所有部分，並使用以下命令將每個部分匯入目標文件中`ImportNode`方法。然後，將匯入的部分附加到目標文件。

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## 步驟 4：儲存目標文檔

最後，使用以下命令儲存修改後的目標文檔`Save`的方法`Document`目的。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

這樣就完成了使用 Aspose.Words for .NET 附加文件的實作。

### 使用 Aspose.Words for .NET 追加文件的範例原始碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//循環瀏覽來源文檔中的所有部分。
	//節節點是文檔節點的直接子節點，因此我們可以列舉文件。
	foreach (Section srcSection in srcDoc)
	{
		//因為我們要將一個文檔的一部分複製到另一個文檔，
		//需要將Section節點匯入到目標文件中。
		//這會調整任何特定於文件的樣式、清單等引用。
		//
		//導入節點會建立原始節點的副本，但該副本
		//ss 準備插入到目標文件中。
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		//現在可以將新的節節點附加到目標文件。
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```
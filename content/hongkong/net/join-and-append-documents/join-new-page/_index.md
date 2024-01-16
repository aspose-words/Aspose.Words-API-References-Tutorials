---
title: 加入新頁面
linktitle: 加入新頁面
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在新頁面上合併兩個文檔，同時保留格式。
type: docs
weight: 10
url: /zh-hant/net/join-and-append-documents/join-new-page/
---

本教學課程說明如何使用 Aspose.Words for .NET 在新頁面上連接兩個文件。提供的原始程式碼示範如何將一個文件附加到另一個文件的結尾，同時在新頁面上啟動附加文件。

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

## 第 3 步：設定新頁面部分開始

若要在新頁面上開始附加文檔，請設置`SectionStart`來源文檔中第一部分的屬性`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## 第 4 步：附加來源文檔

使用以下命令將來源文檔附加到目標文檔`AppendDocument`的方法`Document`班級。將匯入格式模式設定為`ImportFormatMode.KeepSourceFormatting`保留來源文檔中的原始樣式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 第五步：儲存修改後的文檔

最後，使用以下命令儲存修改後的目標文檔`Save`的方法`Document`目的。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```

這樣就完成了使用 Aspose.Words for .NET 在新頁面上連接兩個文件的實作。

### 使用 Aspose.Words for .NET 加入新頁面的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//將附加文件設定為從新頁面開始。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	//使用來源文件中找到的原始樣式附加來源文件。
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```
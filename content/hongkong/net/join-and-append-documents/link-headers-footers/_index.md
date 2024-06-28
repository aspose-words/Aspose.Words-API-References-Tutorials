---
title: 連結頁眉頁腳
linktitle: 連結頁眉頁腳
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 連接和附加 Word 文件時連結頁首和頁尾。
type: docs
weight: 10
url: /zh-hant/net/join-and-append-documents/link-headers-footers/
---

本教學將引導您完成使用 Aspose.Words for .NET 的連結頁首頁尾功能的過程。此功能可讓您合併和附加多個 Word 文檔，同時將來源文檔的頁首和頁尾連結到目標文件中的上一部分。

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

接下來，您需要使用 Aspose.Words 載入來源文件和目標文件。`Document`班級。更新檔名`Document`根據您的文檔名稱建構函數。

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 步驟 3：將附加文件設定為顯示在新頁面上

為了確保來源文件的內容顯示在目標文件的新頁面上，您需要設定`SectionStart`來源文檔中第一部分的屬性`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## 步驟 4：將頁首和頁尾連結到上一節

若要將來源文件的頁首和頁尾連結到目標文件中的上一部分，您可以使用`LinkToPrevious`的方法`HeadersFooters`收藏。透過傳遞`true`作為參數，您可以覆寫來源文件中任何現有的頁首或頁尾。

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## 步驟 5：將來源文檔附加到目標文檔

現在，您可以使用以下命令將來源文檔附加到目標文檔`AppendDocument`的方法`Document`班級。這`ImportFormatMode.KeepSourceFormatting`參數確保在追加操作期間保留來源格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 第 6 步：儲存最終文檔

最後，使用連結的頁首和頁尾保存合併的文檔`Save`的方法`Document`班級。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### 使用 Aspose.Words for .NET 的連結頁首頁腳的範例原始碼 

以下是使用 Aspose.Words for .NET 在 C# 中實作「連結頁首頁尾」功能的完整原始碼：


```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//將附加文件設定為顯示在新頁面上。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	//將來源文件中的頁首和頁尾連結到上一部分。
	//這將覆蓋來源文件中已找到的任何頁首或頁尾。
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

就是這樣！您已使用 Aspose.Words for .NET 成功實現了連結頁首頁尾功能。最終文件將包含合併的內容，其中來源文件的頁首和頁尾連結到目標文件中的上一部分。
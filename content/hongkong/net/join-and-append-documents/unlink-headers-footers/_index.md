---
title: 取消連結頁眉頁腳
linktitle: 取消連結頁眉頁腳
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 合併和追加 Word 文件，同時取消頁首和頁尾的連結。
type: docs
weight: 10
url: /zh-hant/net/join-and-append-documents/unlink-headers-footers/
---

本教學將引導您完成使用 Aspose.Words for .NET 的取消連結頁首頁尾功能的過程。此功能可讓您加入和附加 Word 文件，同時取消頁首和頁尾與來源文檔的連結。

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

## 步驟 3：取消連結來源文件中的頁首和頁尾

要取消來源文件中的頁首和頁尾與目標文件的頁首和頁尾的鏈接，您需要設置`LinkToPrevious`的財產`HeadersFooters`來源文檔第一部分中的集合`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## 步驟 4：將來源文檔附加到目標文檔

現在，您可以使用以下命令將來源文檔附加到目標文檔`AppendDocument`的方法`Document`班級。這`ImportFormatMode.KeepSourceFormatting`參數確保在追加操作期間保留來源格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 第 5 步：儲存最終文檔

最後，使用啟用的取消連結頁眉頁腳功能儲存合併的文檔`Save`的方法`Document`班級。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### 使用 Aspose.Words for .NET 取消連結頁首頁腳的範例原始碼

以下是使用 Aspose.Words for .NET 在 C# 中實作「取消連結頁首頁尾」功能的完整原始碼：

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//取消連結來源文件中的頁首和頁尾以阻止此行為
	//繼續目標文件的頁首和頁尾。
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

就是這樣！您已使用 Aspose.Words for .NET 成功實現了取消連結頁首頁尾功能。最終文件將包含合併的內容，其中來源文件的頁首和頁尾與目標文件取消連結。
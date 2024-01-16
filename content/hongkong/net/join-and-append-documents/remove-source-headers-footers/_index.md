---
title: 刪除來源頁首頁腳
linktitle: 刪除來源頁首頁腳
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 加入和附加 Word 文件時刪除頁首和頁尾。
type: docs
weight: 10
url: /zh-hant/net/join-and-append-documents/remove-source-headers-footers/
---

本教學將引導您完成使用 Aspose.Words for .NET 的刪除來源頁首頁尾功能的流程。此功能可讓您加入和附加 Word 文檔，同時從來源文件中刪除頁首和頁尾。

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

## 步驟 3：從來源文件部分刪除頁首和頁尾

若要從來源文件中的每個部分中刪除頁首和頁腳，您可以使用`foreach`循環並調用`ClearHeadersFooters`方法。

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## 步驟 4：停用 HeadersFooters 的「LinkToPrevious」設置

即使從來源文件中清除頁首和頁尾後，「LinkToPrevious」設定也有可能`HeadersFooters`仍然可以設定。為了避免這種行為，您需要將其明確設定為`false`對於第一部分的`HeadersFooters`財產。

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## 步驟 5：將來源文檔附加到目標文檔

現在，您可以使用以下命令將來源文檔附加到目標文檔`AppendDocument`的方法`Document`班級。這`ImportFormatMode.KeepSourceFormatting`參數確保在追加操作期間保留來源格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 第 6 步：儲存最終文檔

最後，使用啟用的刪除來源頁首頁尾功能儲存合併的文檔`Save`的方法`Document`班級。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### 使用 Aspose.Words for .NET 刪除來源頁首頁腳的範例原始碼 

以下是使用 Aspose.Words for .NET 在 C# 中「刪除來源頁首頁尾」功能的完整原始碼：


```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//從來源文件的每個部分中刪除頁首和頁尾。
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	//即使從來源文件清除頁首和頁尾後，「LinkToPrevious」設置
	//對於 headersfooters 仍然可以設定。這將導致頁首和頁尾從目標繼續
	//文件.這應該設定為 false 以避免這種行為。
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
就是這樣！您已使用 Aspose.Words for .NET 成功實作了刪除來源頁首頁尾功能。最終文件將包含合併的內容，並從來源文件中刪除了頁首和頁尾。
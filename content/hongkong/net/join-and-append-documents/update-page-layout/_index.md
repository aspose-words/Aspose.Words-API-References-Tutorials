---
title: 更新頁面佈局
linktitle: 更新頁面佈局
second_title: Aspose.Words 文件處理 API
description: 了解如何在使用 Aspose.Words for .NET 加入和附加 Word 文件時更新頁面佈局。
type: docs
weight: 10
url: /zh-hant/net/join-and-append-documents/update-page-layout/
---

本教學將引導您完成使用 Aspose.Words for .NET 的更新頁面佈局功能的過程。此功能可確保在加入和附加 Word 文件時正確更新頁面佈局。

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

## 步驟 3：更新目標文件的頁面佈局

為了確保在附加來源文件之前正確更新頁面佈局，您可以調用`UpdatePageLayout`目標文件上的方法。

```csharp
dstDoc.UpdatePageLayout();
```

## 步驟 4：將來源文檔附加到目標文檔

現在，您可以使用以下命令將來源文檔附加到目標文檔`AppendDocument`的方法`Document`班級。這`ImportFormatMode.KeepSourceFormatting`參數確保在追加操作期間保留來源格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 步驟5：再次更新頁面佈局

附加來源文件後，您需要調用`UpdatePageLayout`再次在目標文件上呼叫方法，以確保追加操作後所做的任何更改都反映在渲染的輸出中。

```csharp
dstDoc.UpdatePageLayout();
```

## 第 6 步：儲存最終文檔

最後，使用啟用的更新頁面佈局功能儲存合併的文檔`Save`的方法`Document`班級。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### 使用 Aspose.Words for .NET 更新頁面佈局的範例原始程式碼

以下是使用 Aspose.Words for .NET 在 C# 中「更新頁面佈局」功能的完整原始程式碼：

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//如果目標文件呈現為 PDF、圖像等。
	//或在來源文檔之前呼叫 UpdatePageLayout。附上，
	//那麼之後所做的任何更改都不會反映在渲染輸出中
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	//為了將變更更新到呈現的輸出，必須再次呼叫 UpdatePageLayout。
	//如果不再調用，附加文件將不會出現在下一次渲染的輸出中。
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

就是這樣！您已使用 Aspose.Words for .NET 成功實作了更新頁面佈局功能。最終文件將包含合併的內容以及正確更新的頁面佈局。
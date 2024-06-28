---
title: 使用目標樣式
linktitle: 使用目標樣式
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 套用目標文件樣式時加入和追加 Word 文件。
type: docs
weight: 10
url: /zh-hant/net/join-and-append-documents/use-destination-styles/
---

本教學將引導您完成使用 Aspose.Words for .NET 的「使用目標樣式」功能的流程。此功能可讓您在套用目標文件的樣式的同時加入和附加 Word 文件。

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

## 步驟 3：附加帶有目標樣式的來源文檔

若要在套用目標文檔的樣式時將來源文檔附加到目標文檔，您可以使用`AppendDocument`的方法`Document`類與`ImportFormatMode.UseDestinationStyles`參數。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## 第 4 步：儲存最終文檔

最後，使用啟用的「使用目標樣式」功能儲存合併的文檔`Save`的方法`Document`班級。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

### 使用 Aspose.Words for .NET 使用目標樣式的範例原始程式碼

以下是 C# 中使用 Aspose.Words for .NET 的「使用目標樣式」功能的完整原始碼：

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//使用目標文件的樣式附加來源文件。
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

就是這樣！您已使用 Aspose.Words for .NET 成功實現了「使用目標樣式」功能。最終文件將包含合併的內容以及套用的目標文件的樣式。
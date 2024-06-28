---
title: 重新開始頁碼編號
linktitle: 重新開始頁碼編號
second_title: Aspose.Words 文件處理 API
description: 了解如何在使用 Aspose.Words for .NET 加入和附加 Word 文件時重新開始頁碼編號。
type: docs
weight: 10
url: /zh-hant/net/join-and-append-documents/restart-page-numbering/
---

本教學將引導您完成使用 Aspose.Words for .NET 的重新啟動頁碼功能的過程。此功能可讓您在來源文件中重新啟動頁碼編號的同時加入和附加 Word 文件。

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

## 步驟 3：設定來源文件以重新開始頁碼編號

若要在來源文件中重新開始頁碼編號，您需要設定`SectionStart`來源文檔中第一部分的屬性`SectionStart.NewPage`並設定`RestartPageNumbering`財產給`true`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
```

## 步驟 4：將來源文檔附加到目標文檔

現在，您可以使用以下命令將來源文檔附加到目標文檔`AppendDocument`的方法`Document`班級。這`ImportFormatMode.KeepSourceFormatting`參數確保在追加操作期間保留來源格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 第 5 步：儲存最終文檔

最後，使用啟用重新啟動頁碼編號功能儲存合併的文檔`Save`的方法`Document`班級。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

### 使用 Aspose.Words for .NET 重新啟動頁碼的範例原始碼

以下是使用 Aspose.Words for .NET 在 C# 中實作「重新啟動頁碼編號」功能的完整原始碼：
 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

就是這樣！您已使用 Aspose.Words for .NET 成功實作了重新啟動頁碼編號功能。最終文件將包含合併的內容，並在來源文件中重新啟動頁碼。
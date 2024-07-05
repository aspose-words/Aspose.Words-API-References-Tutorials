---
title: 文檔頁面設定
linktitle: 文檔頁面設定
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 設定文件佈局的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-document-options-and-settings/document-page-setup/
---

在本教學中，我們將引導您完成 C# 原始程式碼，以使用 Aspose.Words for .NET 設定文件佈局。此功能可讓您設定佈局模式、每行字元數和每頁行數。

## 第 1 步：項目設置

首先，在您最喜歡的 IDE 中建立一個新的 C# 專案。請確定您的專案中引用了 Aspose.Words for .NET 程式庫。

## 第 2 步：載入文檔

在此步驟中，我們將載入要設定的Word文件。使用以下程式碼載入文件：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

代替`"YOUR DOCUMENTS DIRECTORY"`與文件所在目錄的實際路徑。

## 第 3 步：設定佈局

現在讓我們來配置文檔佈局。使用以下程式碼設定佈局模式、每行字元數和每頁行數：

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

此程式碼將佈局模式設為“Grid”，然後指定每行的字元數和每頁的行數。

### 使用 Aspose.Words for .NET 進行文件頁面設定的範例原始碼


```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	//設定允許定義文件網格行為的部分的佈局模式。
	//請注意，「文件網格」標籤在 MS Word 的「頁面設定」對話方塊中變得可見
	//是否將任何亞洲語言定義為編輯語言。
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

請務必在中指定正確的文件路徑`dataDir`多變的。

現在您已經了解如何使用 Aspose.Words for .NET 設定文件的佈局。透過遵循本教學中提供的逐步指南，您可以輕鬆自訂自己的文件的佈局。
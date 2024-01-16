---
title: 設定頁面設定和部分格式
linktitle: 設定頁面設定和部分格式
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 設定文件佈局和部分格式的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

在本教程中，我們將引導您完成 C# 原始程式碼，以使用 Aspose.Words for .NET 設定佈局和部分格式。此功能可讓您設定頁面方向、邊距和紙張尺寸。

## 第 1 步：項目設置

首先，在您最喜歡的 IDE 中建立一個新的 C# 專案。請確定您的專案中引用了 Aspose.Words for .NET 程式庫。

## 第 2 步：建立文檔

在此步驟中，我們將建立一個新文件。使用以下程式碼建立文件並初始化建構函式：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

代替`"YOUR DOCUMENTS DIRECTORY"`與要儲存文件的目錄的實際路徑。

## 步驟 3：設定佈局並儲存文檔

現在讓我們來配置文檔佈局。使用以下代碼設定方向、邊距和紙張尺寸：

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

此程式碼將頁面方向設定為橫向，左邊距設定為 50，紙張尺寸設定為 10x14。

### 使用 Aspose.Words for .NET 設定頁面設定和節格式的範例原始碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.PageSetup.Orientation = Orientation.Landscape;
	builder.PageSetup.LeftMargin = 50;
	builder.PageSetup.PaperSize = PaperSize.Paper10x14;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
  
```

請務必指定要儲存文件的目錄的正確路徑`dataDir`多變的。

現在您已經了解如何使用 Aspose.Words for .NET 設定文件的佈局和部分格式。透過遵循本教學中提供的逐步指南，您可以輕鬆自訂自己文件的佈局和格式。
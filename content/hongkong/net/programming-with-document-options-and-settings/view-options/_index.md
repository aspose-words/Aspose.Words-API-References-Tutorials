---
title: 查看選項
linktitle: 查看選項
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 設定文件顯示選項的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-document-options-and-settings/view-options/
---

在本教學中，我們將引導您完成 C# 原始程式碼，以使用 Aspose.Words for .NET 設定顯示選項。此功能可讓您自訂文件中的檢視模式和縮放等級。

## 第 1 步：項目設置

首先，在您最喜歡的 IDE 中建立一個新的 C# 專案。請確定您的專案中引用了 Aspose.Words for .NET 程式庫。

## 第 2 步：載入文檔

在此步驟中，我們將載入要配置顯示選項的 Word 文件。使用以下程式碼載入文件：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

代替`"YOUR DOCUMENTS DIRECTORY"`與文件所在目錄的實際路徑。

## 步驟 3：配置顯示選項

現在我們將配置文檔顯示選項。使用以下程式碼設定顯示模式和縮放等級：

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

此程式碼將視圖模式設為“PageLayout”，並將縮放等級設為 50%。

### 使用 Aspose.Words for .NET 檢視選項的範例原始碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

請務必在中指定正確的文件路徑`dataDir`多變的。

現在您已經了解如何使用 Aspose.Words for .NET 設定文件顯示選項。透過遵循本教學中提供的逐步指南，您可以輕鬆自訂自己文件的顯示。
---
title: 顯示語法和拼字錯誤
linktitle: 顯示語法和拼字錯誤
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 在文件中顯示語法和拼字錯誤的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-document-options-and-settings/show-grammatical-and-spelling-errors/
---

在本教程中，我們將引導您完成 C# 原始程式碼，以便使用 Aspose.Words for .NET 顯示語法和拼字錯誤。此功能可讓您查看文件中的語法和拼字錯誤。

## 第 1 步：項目設置

首先，在您最喜歡的 IDE 中建立一個新的 C# 專案。請確定您的專案中引用了 Aspose.Words for .NET 程式庫。

## 第 2 步：載入文檔

在此步驟中，我們將載入要顯示語法和拼字錯誤的 Word 文件。使用以下程式碼載入文件：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

代替`"YOUR DOCUMENTS DIRECTORY"`與文件所在目錄的實際路徑。

## 步驟 3：啟用錯誤顯示

現在我們將啟用文件中語法和拼字錯誤的顯示。使用以下程式碼啟用錯誤顯示：

```csharp
doc. ShowGrammaticalErrors = true;
doc. ShowSpellingErrors = true;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
```

此程式碼可以顯示語法錯誤（`ShowGrammaticalErrors`）和拼字錯誤（`ShowSpellingErrors`）在文檔中。

### 使用 Aspose.Words for .NET 顯示語法和拼字錯誤的範例原始程式碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.ShowGrammaticalErrors = true;
	doc.ShowSpellingErrors = true;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");

```

請務必在中指定正確的文件路徑`dataDir`多變的。

現在您已經了解如何使用 Aspose.Words for .NET 在文件中顯示語法和拼字錯誤。透過遵循本教學中提供的逐步指南，您可以在自己的文件中輕鬆啟用此功能。
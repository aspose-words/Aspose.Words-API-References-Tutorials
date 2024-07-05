---
title: 清理重複樣式
linktitle: 清理重複樣式
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 清理文件中重複樣式的逐步指南。包括完整的源代碼。
type: docs
weight: 10
url: /zh-hant/net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

在本教學中，我們將引導您逐步完成 C# 原始程式碼，以使用 Aspose.Words for .NET 清理重複的樣式。此功能有助於從文件中刪除重複的樣式。

## 第 1 步：項目設置

首先，在您最喜歡的 IDE 中建立一個新的 C# 專案。請確定您的專案中引用了 Aspose.Words for .NET 程式庫。

## 第 2 步：載入文檔

在此步驟中，我們將載入要清理的Word文件。使用以下程式碼載入文件：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

代替`"YOUR DOCUMENTS DIRECTORY"`與文件所在目錄的實際路徑。

## 第 3 步：清潔前清點款式

在進行清理之前，我們將計算文件中存在的樣式數量。使用以下程式碼顯示樣式計數：

```csharp
Console.WriteLine(doc.Styles.Count);
```

此語句顯示文件中存在的樣式數量。

## 第四步：清理重複的樣式

現在讓我們清理文件中的重複樣式。使用以下程式碼執行清理：

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

此程式碼使用指定的選項清除文件中的重複樣式。在這個例子中，我們啟用了`DuplicateStyle`清理重複樣式的選項。

## 第五步：清點清潔後的款式

清理完畢後，我們會再次清點款式數量，看看是否減少了。使用以下程式碼顯示新樣式計數：

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

此語句顯示清潔後剩餘的款式數量。

### 使用 Aspose.Words for .NET 清理重複樣式的範例原始程式碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	//清理前的樣式計數。
	Console.WriteLine(doc.Styles.Count);

	//清除文件中的重複樣式。
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	//清理後的樣式數量減少。
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```
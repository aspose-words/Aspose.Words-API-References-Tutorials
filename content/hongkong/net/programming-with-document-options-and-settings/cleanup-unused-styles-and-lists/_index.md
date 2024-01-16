---
title: 清理未使用的樣式和列表
linktitle: 清理未使用的樣式和列表
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 清理文件中未使用的樣式和清單的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

在本教程中，我們將引導您完成 C# 原始程式碼，以使用 Aspose.Words for .NET 清理未使用的樣式和清單。此功能可讓您刪除文件中未使用的樣式和清單。

## 第 1 步：項目設置

首先，在您最喜歡的 IDE 中建立一個新的 C# 專案。請確定您的專案中引用了 Aspose.Words for .NET 程式庫。

## 第 2 步：載入文檔

在此步驟中，我們將載入包含我們要清理的未使用樣式和清單的 Word 文件。使用以下程式碼載入文件：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

代替`"YOUR DOCUMENTS DIRECTORY"`與文件所在目錄的實際路徑。

## 第 3 步：清理前清點樣式和列表

在清理之前，我們將計算文件中存在的樣式和清單的數量。使用以下程式碼顯示計數器：

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

這些說明顯示清潔前文件中存在的樣式數量和清單。

## 步驟 4：清理未使用的樣式和列表

現在讓我們清理文件中未使用的樣式和清單。使用以下程式碼執行清理：

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

此程式碼使用指定的選項清除文件中未使用的樣式和清單。在這個例子中，我們啟用了`UnusedStyles`選項刪除未使用的樣式並停用`UnusedLists`即使不使用列表，也可以選擇保留列表。

## 第五步：統計清理後的樣式和列表

完成清理後，我們將再次計算樣式和清單以檢查它們是否已折疊。使用以下程式碼顯示新計數器：

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

這些說明顯示清潔後剩餘的款式數量和清單。

### 使用 Aspose.Words for .NET 清理未使用的樣式和清單的範例原始程式碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	//與內建樣式結合，該文件現在有八種樣式。
	//當文件中存在任何文字時，自訂樣式會被標記為“已使用”
	//以那種風格格式化。這表示我們新增的 4 種樣式目前未使用。
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	//根據給定的 CleanupOptions 從文件中清除未使用的樣式和清單。
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

請務必在中指定正確的文件路徑`dataDir`多變的。

現在您已經了解如何使用 Aspose.Words for .NET 清理文件中未使用的樣式和清單。透過遵循本教學中提供的逐步指南，您可以輕鬆地將此功能套用到您自己的文件中。


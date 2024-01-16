---
title: 比較 Word 文件中的選項
linktitle: 比較 Word 文件中的選項
second_title: Aspose.Words 文件處理 API
description: 逐步指南說明使用 Aspose.Words for .NET 在 Word 文件功能中比較選項的 C# 原始碼。
type: docs
weight: 10
url: /zh-hant/net/compare-documents/compare-options/
---
在本教學中，我們將說明如何透過 Aspose.Words for .NET 使用 Word 文件中的比較選項功能。請按照以下步驟了解原始程式碼並套用變更。

## 第 1 步：將文件與自訂選項進行比較

首先，載入兩個文檔進行比較。在此範例中，我們將使用`Clone()`方法建立原始文件的副本。就是這樣：

```csharp
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();
```

## 第 2 步：配置比較選項

我們現在將透過建立一個來配置比較選項`CompareOptions`對象並根據需要設定各種屬性。就是這樣：

```csharp
CompareOptions options = new CompareOptions
{
IgnoreFormatting = true,
IgnoreHeadersAndFooters = true,
IgnoreCaseChanges = true,
IgnoreTables = true,
IgnoreFields = true,
IgnoreComments = true,
IgnoreTextboxes=true,
IgnoreFootnotes=true
};
```

## 第 3 步：將文件與自訂選項進行比較

我們現在將使用`Compare()`方法傳遞自訂選項來比較兩個文件。此方法會標記原始文檔中的變更。就是這樣：

```csharp
//將文件與自訂選項進行比較
docA.Compare(docB, "user", DateTime.Now, options);

//檢查文件是否相同
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal": "Documents are not equal");
```

### 使用 Aspose.Words for .NET 的比較選項的範例原始程式碼

以下是 Aspose.Words for .NET 的比較選項功能的完整原始碼：

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();

	CompareOptions options = new CompareOptions
	{
		IgnoreFormatting = true,
		IgnoreHeadersAndFooters = true,
		IgnoreCaseChanges = true,
		IgnoreTables = true,
		IgnoreFields = true,
		IgnoreComments = true,
		IgnoreTextboxes = true,
		IgnoreFootnotes = true
	};

	docA.Compare(docB, "user", DateTime.Now, options);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

透過此程式碼，您可以使用自訂選項來比較兩個文檔，以在與 Aspose.Words for .NET 進行比較時忽略特定元素。

## 結論

在本教學中，我們學習如何在比較兩個文件時使用 Aspose.Words for .NET 中的比較選項來自訂比較過程。透過指定不同的選項，您可以忽略特定元素並使比較過程更加靈活。此功能可讓您更好地控制比較過程，並根據您的特定要求進行自訂。 Aspose.Words for .NET 提供強大的文件比較功能，可輕鬆識別文件之間的差異，同時根據需要忽略某些元素。

### 常見問題解答

#### Q：在 Aspose.Words for .NET 中使用比較選項的目的為何？

答：Aspose.Words for .NET 中的比較選項可讓您在比較兩個文件時自訂比較過程。使用這些選項，您可以指定在比較過程中忽略哪些元素，例如格式變更、頁首和頁尾、表格、欄位、註解、文字方塊和腳註。

#### Q：如何在 Aspose.Words for .NET 中使用比較選項？

答：若要在 Aspose.Words for .NET 中使用比較選項，請依照下列步驟操作：
1. 將要比較的兩個文件載入到單獨的 Document 物件中。
2. 使用`Clone()`方法建立原始文件的副本。
3. 創建一個`CompareOptions`物件並設定其屬性來自訂比較過程。您可以指定在比較過程中忽略哪些元素。
4. 使用`Compare()`方法在其中一個文件上並傳遞另一個文件和`CompareOptions`對像作為參數。此方法將根據指定的選項對文件進行比較，並標記原始文件中的變更。
5. 檢查`Revisions`原始文檔的屬性。如果計數為零，則表示考慮到指定的選項，文件是相同的。

#### Q：CompareOptions 中有哪些常用選項？

答：CompareOptions 中可用的常見選項包括：
- `IgnoreFormatting`：忽略格式變更。
- `IgnoreHeadersAndFooters`：忽略頁首和頁尾的變更。
- `IgnoreCaseChanges`：忽略大小寫變更（大寫/小寫）。
- `IgnoreTables`：忽略表中的變更。
- `IgnoreFields`：忽略字段的變化。
- `IgnoreComments`：忽略註釋中的變更。
- `IgnoreTextboxes`：忽略文字方塊中的變更。
- `IgnoreFootnotes`：忽略腳註的更改。

#### Q：在文件比較過程中，我可以對特定元素使用自訂選項嗎？

答：是的，您可以在文件比較過程中對特定元素使用自訂選項。透過設定屬性`CompareOptions`相應地，您可以選擇在比較過程中忽略哪些元素以及考慮哪些元素。
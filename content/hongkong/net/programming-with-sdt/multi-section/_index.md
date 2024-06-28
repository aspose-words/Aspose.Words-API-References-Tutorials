---
title: 多節
linktitle: 多節
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 擷取和處理 Word 文件中的多部分結構化文件標籤。
type: docs
weight: 10
url: /zh-hant/net/programming-with-sdt/multi-section/
---

本教學課程介紹如何使用 Aspose.Words for .NET 在 Word 文件中處理多部分結構化文件標籤。您可以檢索和處理文件中存在的部分標籤。

## 先決條件
要學習本教程，您需要具備以下條件：

- 已安裝 Aspose.Words for .NET 程式庫。
- C# 和 Word 文件文字處理的基礎知識。

## 第 1 步：設定文檔目錄
首先設定文檔目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與文件所在目錄的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：載入文件並檢索多節標籤
使用以下命令載入 Word 文檔`Document`建構函數，將文檔的路徑作為參數傳遞。使用下列命令檢索文件中所有結構化文件標記範圍起始節點`GetChildNodes`方法。

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## 步驟 3：處理多節標籤
迭代結構化文件標記範圍起始節點的集合。在此範例中，我們只需將每個標籤的標題列印到控制台。您可以根據您的要求進行進一步的處理。

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### 使用 Aspose.Words for .NET 的多部分範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

就是這樣！您已使用 Aspose.Words for .NET 成功擷取並處理了 Word 文件中的多節結構化文件標籤。
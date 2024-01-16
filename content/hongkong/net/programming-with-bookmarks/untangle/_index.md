---
title: 解開Word文件中的纏結
linktitle: 解開Word文件中的纏結
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 理清 Word 文件中相鄰表格行中的巢狀書籤。
type: docs
weight: 10
url: /zh-hant/net/programming-with-bookmarks/untangle/
---

在本文中，我們將探索上面的 C# 原始程式碼，以了解如何使用 Aspose.Words for .NET 函式庫中的 Untangle 函數。此函數可解開相鄰表行中的巢狀書籤。

## 先決條件

- C# 語言的基礎知識。
- 安裝了 Aspose.Words 函式庫的 .NET 開發環境。

## 第 1 步：瀏覽文件書籤

我們使用 foreach 迴圈來遍歷文件中存在的所有書籤：

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     //此處處理書籤的程式碼
}
```

## 步驟 2：從書籤中取得父行

我們使用`GetAncestor`檢索書籤開始和結束節點的父行的方法：

```csharp
Row row1 = (Row)bookmark.BookmarkStart.GetAncestor(typeof(Row));
Row row2 = (Row)bookmark.BookmarkEnd.GetAncestor(typeof(Row));
```

## 第 3 步：解開嵌套書籤

如果找到兩個父行並且書籤在相鄰行中開始和結束，我們將書籤的結束節點移動到頂行最後一個單元格的最後一段的末尾：

```csharp
if (row1 != null && row2 != null && row1.NextSibling == row2)
     row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
```

### 使用 Aspose.Words for .NET 進行 Untangle 的範例原始碼

以下是使用 Aspose.Words for .NET 解開巢狀書籤的完整原始碼範例：

```csharp

	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		//取得書籤和書籤結束節點的父行。
		Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
		Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

		//如果發現兩行都正常，且書籤開頭和結尾包含在相鄰行中，
		//將書籤結束節點移到頂行最後一個儲存格中最後一段的結尾。
		if (row1 != null && row2 != null && row1.NextSibling == row2)
			row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
	}

```

## 結論

在本文中，我們探索了 C# 原始程式碼，以了解如何使用 Aspose.Words for .NET 的 Untangle 功能。我們按照逐步指南來解開相鄰表格行中的巢狀書籤。

### 常見問題解答

#### Q：Untangle 功能是否僅適用於相鄰表格行中的巢狀書籤？

答：是的，「解開」功能專門用於解開相鄰表格行中的巢狀書籤。如果書籤不在相鄰行中，則此功能不適用。

#### Q：如何識別 Word 文件中的巢狀書籤？

答：您可以透過循環瀏覽文件中的書籤並檢查起始書籤和結束書籤是否位於相鄰的表格行中來識別巢狀書籤。您可以使用本文中提供的原始程式碼作為實現此功能的起點。

#### Q：解密功能是否會修改原始文件的內容？

答：是的，Untangle 功能透過將書籤的結束節點移動到頂行最後一個單元格的最後一段的末尾來修改原始文件。在套用此功能之前，請確保已儲存文件的備份副本。

#### Q：如何解開其他類型文件元素（例如節或段落）中的巢狀書籤？

答：本文介紹的 Untangle 函數專門用來解開相鄰表格行中的巢狀書籤。如果您想要解開其他文件元素中的巢狀書籤，則需要相應地調整程式碼並使用適當的方法來存取所需的元素。

#### Q：是否有其他方法可以使用 Aspose.Words for .NET 來解開 Word 文件中的巢狀書籤？

答：本文介紹的方法是解開相鄰表格行中嵌套書籤的常用方法。但是，根據專案的具體需求，可能還有其他方法或技術。您可以查看[Aspose.Words for .NET API 參考](https://reference.aspose.com/words/net/)進一步探索可用的功能。
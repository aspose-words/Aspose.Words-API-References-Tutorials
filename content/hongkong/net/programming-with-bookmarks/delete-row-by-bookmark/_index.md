---
title: 在Word文件中按書籤刪除行
linktitle: 在Word文件中按書籤刪除行
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 根據 Word 文件中的特定書籤刪除表格行。
type: docs
weight: 10
url: /zh-hant/net/programming-with-bookmarks/delete-row-by-bookmark/
---

在本文中，我們將探索上述 C# 原始程式碼，以了解如何使用 Aspose.Words for .NET 程式庫中的按書籤刪除行功能。此功能可讓您根據Word文件中的特定書籤刪除表格行。

## 先決條件

- C# 語言的基礎知識。
- 安裝了 Aspose.Words 函式庫的 .NET 開發環境。

## 第一步：取得書籤

我們使用`Bookmarks`文檔範圍的屬性來取得我們要用來刪除表格行的特定書籤：

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## 步驟 2：刪除表格行

我們使用`GetAncestor`方法得到`Row`輸入書籤的父元素。接下來，我們使用`Remove`刪除表格行的方法：

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### 使用 Aspose.Words for .NET 按書籤刪除行的範例原始程式碼

以下是完整的範例原始程式碼，示範使用 Aspose.Words for .NET 刪除基於特定書籤的表格行：

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## 結論

在本文中，我們探索了 C# 原始程式碼，以了解如何使用 Aspose.Words for .NET 的按書籤刪除行功能。我們按照逐步指南根據文件中的特定書籤刪除表格行。

### Word文件中逐行刪除書籤的常見問題解答

#### Q：我可以使用同一書籤刪除多行嗎？

答：是的，您可以使用同一書籤刪除多行。但是，您需要處理程式碼中的邏輯以確定要刪除的行數並對提供的程式碼片段進行必要的調整。

#### Q：如果文件中不存在書籤會怎樣？

答：如果文件中不存在指定的書籤，則程式碼片段將為書籤物件傳回空值。因此，您需要在嘗試刪除表行之前透過新增適當的檢查來在程式碼中處理這種情況。

#### Q：Aspose.Words 函式庫可以免費使用嗎？

答：Aspose.Words 庫是一個商業庫，您可能需要有效的許可證才能在專案中使用它。您可以訪問[Aspose.Words for .NET API 參考](https://reference.aspose.com/words/net/)了解有關其許可選項和定價的更多資訊。

#### Q：我可以從 Word 文件特定部分的表格中刪除行嗎？

答：是的，您可以從 Word 文件特定部分的表格中刪除行。您可以透過使用該部分中的適當範圍或書籤來修改提供的程式碼片段以定位特定部分。
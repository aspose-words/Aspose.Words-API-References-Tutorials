---
title: 在 Word 文件中為表格列新增書籤
linktitle: 在 Word 文件中為表格列新增書籤
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中為表格列新增書籤。
type: docs
weight: 10
url: /zh-hant/net/programming-with-bookmarks/bookmark-table-columns/
---

在本文中，我們將探索上面的 C# 原始程式碼，以了解如何使用 Aspose.Words for .NET 程式庫中的書籤表格列功能。此功能可讓您為 Word 文件中表格的特定欄位新增書籤並存取該列的內容。

## 先決條件

- C# 語言的基礎知識。
- 安裝了 Aspose.Words 函式庫的 .NET 開發環境。

## 第 1 步：建立表

在表列上建立書籤之前，我們必須先使用`DocumentBuilder`目的。在我們的範例中，我們建立一個包含兩行和兩列的表：

```csharp
builder. StartTable();

builder. InsertCell();

builder. StartBookmark("MyBookmark");

builder.Write("This is cell 1 of row 1");

builder. InsertCell();
builder.Write("This is cell 2 of row 1");

builder. EndRow();

builder. InsertCell();
builder.Writeln("This is cell 1 of row 2");

builder. InsertCell();
builder.Writeln("This is cell 2 of row 2");

builder. EndRow();
builder. EndTable();
```

## 第 2 步：建立列書籤

我們使用`StartBookmark`方法在表格的特定列上建立書籤。在我們的範例中，我們使用名稱「MyBookmark」作為書籤：

```csharp
builder. StartBookmark("MyBookmark");
```

## 步驟 3：存取列內容

我們瀏覽文件中的所有書籤並顯示它們的名稱。如果書籤是一列，我們使用列索引和`GetText`方法：

```csharp
foreach (Bookmark

  bookmark in doc.Range.Bookmarks)
{
Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn?" (Column)": "");

if (bookmark.IsColumn)
{
if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
}
}
```

### 使用 Aspose.Words for .NET 的書籤表格列的範例原始程式碼

以下是完整的範例原始程式碼，示範使用 Aspose.Words for .NET 在表格列上建立書籤：

```csharp

	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartTable();
	
	builder.InsertCell();

	builder.StartBookmark("MyBookmark");

	builder.Write("This is row 1 cell 1");

	builder.InsertCell();
	builder.Write("This is row 1 cell 2");

	builder.EndRow();

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 1");

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 2");

	builder.EndRow();
	builder.EndTable();
	
	builder.EndBookmark("MyBookmark");
	

	
	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn ? " (Column)" : "");

		if (bookmark.IsColumn)
		{
			if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
				Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
		}
	}
	
        
```

## 結論

在本文中，我們探索了 C# 原始程式碼，以了解如何使用 Aspose.Words for .NET 的書籤表格列功能。我們按照逐步指南為 Word 文件中表格的特定欄位新增書籤，並跳到該列的內容。

### Word 文件中書籤表列的常見問題解答

#### Q：使用 Aspose.Words for .NET 中的「表格書籤」功能有哪些先決條件？

答：要使用 Aspose.Words for .NET 中的「表格列書籤」功能，您需要具備 C# 語言的基本知識。您還需要一個安裝了 Aspose.Words 函式庫的 .NET 開發環境。

#### Q：如何使用 Aspose.Words for .NET 在 Word 文件中建立包含列的表格？

答：要使用 Aspose.Words for .NET 在 Word 文件中建立包含列的表格，您可以使用`DocumentBuilder`物件將儲存格和內容插入表中。這是範例程式碼：

```csharp
builder. StartTable();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 1");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 2");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. EndTable();
```

#### Q：如何使用 Aspose.Words for .NET 為表格列新增書籤？

答：要使用 Aspose.Words for .NET 在表格列上建立書籤，您可以使用`StartBookmark`的方法`DocumentBuilder`物件在特定表列上啟動書籤。這是範例程式碼：

```csharp
builder.StartBookmark("MyBookmark");
```

#### Q：如何使用 Aspose.Words for .NET 從書籤存取表格列內容？

答：要使用 Aspose.Words for .NET 從書籤存取表格列的內容，您可以循環遍歷文件中的所有書籤，檢查書籤是否為列，然後使用列的索引來存取該欄位。這是範例程式碼：

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     if (bookmark.IsColumn)
     {
         if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
         {
             string content = row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar);
             //對列的內容做一些事情......
         }
     }
}
```

#### Q：在有列書籤的表中可以建立的列數是否有限制？

答：使用 Aspose.Words for .NET 在有列書籤的表格中建立的列數沒有具體限制。此限制主要取決於系統上的可用資源以及您所使用的 Word 文件格式的規格。但是，建議不要建立過多的列，因為這可能會影響最終文件的效能和可讀性。
---
title: 在 Word 文档中为表格列添加书签
linktitle: 在 Word 文档中为表格列添加书签
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 为 Word 文档中的表格列添加书签。
type: docs
weight: 10
url: /zh/net/programming-with-bookmarks/bookmark-table-columns/
---

在本文中，我们将探索上面的 C# 源代码，以了解如何使用 Aspose.Words for .NET 库中的“为表格列添加书签”功能。此功能允许您为 Word 文档中表格的特定列添加书签并访问该列的内容。

## 先决条件

- C# 语言的基本知识。
- 安装了 Aspose.Words 库的.NET 开发环境。

## 步骤 1：创建表

在表列上创建书签之前，我们必须首先使用`DocumentBuilder`对象。在我们的示例中，我们创建一个有两行两列的表格：

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

## 步骤 2：创建列书签

我们使用`StartBookmark`方法在表的特定列上创建书签。在我们的示例中，我们使用名称“MyBookmark”作为书签：

```csharp
builder. StartBookmark("MyBookmark");
```

## 步骤 3：访问列内容

我们浏览文档中的所有书签并显示它们的名称。如果书签是一列，则我们使用列索引和`GetText`方法：

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

### 使用 Aspose.Words for .NET 的书签表列的示例源代码

以下是完整的示例源代码，演示如何使用 Aspose.Words for .NET 在表列上创建书签：

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

## 结论

在本文中，我们探索了 C# 源代码，以了解如何使用 Aspose.Words for .NET 的“为表列添加书签”功能。我们按照分步指南为 Word 文档中表的特定列添加书签，并跳转到该列的内容。

### Word 文档中书签表格列的常见问题解答

#### 问：使用 Aspose.Words for .NET 中的“表格列书签”功能的先决条件是什么？

答：要使用 Aspose.Words for .NET 中的“表格列书签”功能，您需要具备 C# 语言的基础知识。您还需要一个安装了 Aspose.Words 库的 .NET 开发环境。

#### 问：如何使用 Aspose.Words for .NET 在 Word 文档中创建带有列的表格？

答：要使用 Aspose.Words for .NET 在 Word 文档中创建带有列的表格，您可以使用`DocumentBuilder`对象将单元格和内容插入到表中。以下是示例代码：

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

#### 问：如何使用 Aspose.Words for .NET 为表格列添加书签？

答：要使用 Aspose.Words for .NET 在表列上创建书签，您可以使用`StartBookmark`方法`DocumentBuilder`对象在特定表列上启动书签。以下是示例代码：

```csharp
builder.StartBookmark("MyBookmark");
```

#### 问：如何使用 Aspose.Words for .NET 从书签访问表格列内容？

答：要使用 Aspose.Words for .NET 从书签访问表格列的内容，您可以循环遍历文档中的所有书签，检查书签是否为列，然后使用列的索引访问该列的内容。以下是示例代码：

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     if (bookmark.IsColumn)
     {
         if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
         {
             string content = row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar);
             //对列的内容进行一些处理......
         }
     }
}
```

#### 问：我在表格中使用列书签可以创建的列数是否有限制？

答：使用 Aspose.Words for .NET 在带有列书签的表格中可以创建的列数没有特定限制。限制主要取决于系统上可用的资源以及您使用的 Word 文件格式的规格。但是，建议不要创建过多的列，因为这会影响最终文档的性能和可读性。
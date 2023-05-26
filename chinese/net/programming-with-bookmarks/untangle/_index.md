---
title: 解开纠结
linktitle: 解开纠结
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 解开相邻表格行中的嵌套书签。
type: docs
weight: 10
url: /zh/net/programming-with-bookmarks/untangle/
---

在本文中，我们将探索上面的 C# 源代码，以了解如何使用 Aspose.Words for .NET 库中的 Untangle 函数。此函数解开相邻表格行中的嵌套书签。

## 先决条件

- C# 语言的基础知识。
- 安装了 Aspose.Words 库的 .NET 开发环境。

## 第 1 步：浏览文档书签

我们使用 foreach 循环遍历文档中存在的所有书签：

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     //此处处理书签的代码
}
```

## 第 2 步：从书签中获取父行

我们使用`GetAncestor`检索书签的开始和结束节点的父行的方法：

```csharp
Row row1 = (Row)bookmark.BookmarkStart.GetAncestor(typeof(Row));
Row row2 = (Row)bookmark.BookmarkEnd.GetAncestor(typeof(Row));
```

## 第 3 步：解开嵌套书签

如果找到两个父行并且书签在相邻行中开始和结束，我们将书签的结束节点移动到顶行最后一个单元格的最后一段的末尾：

```csharp
if (row1 != null && row2 != null && row1.NextSibling == row2)
     row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
```

### 使用 Aspose.Words for .NET 的 Untangle 示例源代码

下面是使用 Aspose.Words for .NET 解开嵌套书签的完整源代码示例：

```csharp

	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		//获取书签和书签结束节点的父行。
		Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
		Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

		//如果两行都没有问题，并且书签的开始和结束包含在相邻的行中，
		//将书签结束节点移动到顶行最后一个单元格中最后一段的末尾。
		if (row1 != null && row2 != null && row1.NextSibling == row2)
			row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
	}

```

## 结论

在本文中，我们探索了 C# 源代码以了解如何使用 Aspose.Words for .NET 的 Untangle 功能。我们已按照分步指南解开相邻表格行中的嵌套书签。
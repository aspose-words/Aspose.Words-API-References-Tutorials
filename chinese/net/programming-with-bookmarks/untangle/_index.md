---
title: 解开Word文档中的缠结
linktitle: 解开Word文档中的缠结
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 理清 Word 文档中相邻表格行中的嵌套书签。
type: docs
weight: 10
url: /zh/net/programming-with-bookmarks/untangle/
---

在本文中，我们将探索上面的 C# 源代码，以了解如何使用 Aspose.Words for .NET 库中的 Untangle 函数。此函数可解开相邻表行中的嵌套书签。

## 先决条件

- C# 语言的基础知识。
- 安装了 Aspose.Words 库的 .NET 开发环境。

## 第 1 步：浏览文档书签

我们使用 foreach 循环来遍历文档中存在的所有书签：

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     //此处处理书签的代码
}
```

## 步骤 2：从书签中获取父行

我们使用`GetAncestor`检索书签开始和结束节点的父行的方法：

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

### 使用 Aspose.Words for .NET 进行 Untangle 的示例源代码

以下是使用 Aspose.Words for .NET 解开嵌套书签的完整源代码示例：

```csharp

	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		//获取书签和书签结束节点的父行。
		Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
		Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

		//如果发现两行都正常，并且书签开头和结尾包含在相邻行中，
		//将书签结束节点移动到顶行最后一个单元格中最后一段的末尾。
		if (row1 != null && row2 != null && row1.NextSibling == row2)
			row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
	}

```

## 结论

在本文中，我们探索了 C# 源代码，以了解如何使用 Aspose.Words for .NET 的 Untangle 功能。我们按照分步指南来解开相邻表格行中的嵌套书签。

### 常见问题解答

#### 问：Untangle 功能是否仅适用于相邻表格行中的嵌套书签？

答：是的，“解开”功能专门用于解开相邻表格行中的嵌套书签。如果书签不在相邻行中，则此功能不适用。

#### 问：如何识别 Word 文档中的嵌套书签？

答：您可以通过循环浏览文档中的书签并检查起始书签和结束书签是否位于相邻的表格行中来识别嵌套书签。您可以使用本文中提供的源代码作为实现此功能的起点。

#### 问：解密功能是否会修改原始文档的内容？

答：是的，Untangle 功能通过将书签的结束节点移动到顶行最后一个单元格的最后一段的末尾来修改原始文档。在应用此功能之前，请确保保存文档的备份副本。

#### 问：如何解开其他类型文档元素（例如节或段落）中的嵌套书签？

答：本文中介绍的 Untangle 函数专门用于解开相邻表格行中的嵌套书签。如果您想要解开其他文档元素中的嵌套书签，则需要相应地调整代码并使用适当的方法来访问所需的元素。

#### 问：是否有其他方法可以使用 Aspose.Words for .NET 来解开 Word 文档中的嵌套书签？

答：本文介绍的方法是解开相邻表格行中嵌套书签的常用方法。但是，根据项目的具体需求，可能还有其他方法或技术。您可以查看官方 Aspose.Words 文档以进一步探索可用功能。
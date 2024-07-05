---
title: 解开 Word 文档中的行书签
linktitle: 解开 Word 文档中的行书签
second_title: Aspose.Words 文档处理 API
description: 了解如何解开 Word 文档中嵌套的行书签以删除特定行而不影响其他书签。
type: docs
weight: 10
url: /zh/net/programming-with-bookmarks/untangle-row-bookmarks/
---

在本文中，我们将探索上面的 C# 源代码，以了解如何使用 Aspose.Words for .NET 库中的 Untangle Row Bookmarks 函数。该函数可以将行书签的末尾与书签的开头放在同一行。

## 先决条件

- C# 语言的基本知识。
- 安装了 Aspose.Words 库的.NET 开发环境。

## 步骤 1：加载文档

我们使用`Document`类从文件加载现有文档：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## 第 2 步：解开线书签

我们使用`Untangle`函数将书签从行中解开。此函数执行自定义任务，将书签行的结尾与书签的开始放在同一行中：

```csharp
Untangle(doc);
```

## 步骤 3：通过书签删除行

我们使用`DeleteRowByBookmark`通过书签删除特定行的函数：

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## 步骤 4：检查其他书签的完整性

我们通过检查书签末尾是否仍然存在来验证其他书签是否未被损坏：

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### 使用 Aspose.Words for .NET 解开行书签的示例源代码

以下是使用 Aspose.Words for .NET 从行中解开书签的完整示例源代码：


```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	//这将执行将行书签结束与书签开始放入同一行的自定义任务。
	Untangle(doc);

	//现在我们可以轻松地通过书签删除行而不会损坏任何其他行的书签。
	DeleteRowByBookmark(doc, "ROW2");

	//这只是为了检查其他书签没有损坏。
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

#### 解开源代码
```csharp

private void Untangle(Document doc)
        {
            foreach (Bookmark bookmark in doc.Range.Bookmarks)
            {
                //获取书签和书签结束节点的父行。
                Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
                Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

                //如果两行均正确，且书签的开始和结束位于相邻行中，
                //将书签结束节点移动到顶行最后一个单元格中最后一段的末尾。
                if (row1 != null && row2 != null && row1.NextSibling == row2)
                    row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
            }
        }

```

#### DeleteRowByBookmark 源代码
```csharp

 private void DeleteRowByBookmark(Document doc, string bookmarkName)
        {
            Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

            Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
            row?.Remove();
        }

```
## 结论

在本文中，我们探索了 C# 源代码，以了解如何使用 Aspose.Words for .NET 的“解开行书签”功能。我们按照分步指南解开行书签并删除特定行，而不会损坏其他书签。

### Word 文档中解开行书签的常见问题解答

#### 问：Unscramble Row Bookmarks 只适用于表格中的行书签吗？

答：是的，解开行书签功能专门用于解开表格中的行书签。此功能可用于处理数组中的行书签，并确保书签结尾与书签开头位于同一行。

#### 问：解乱行书签功能会修改原文档的内容吗？

答：是的，“解除行书签”功能会修改原始文档，方法是移动行书签的末尾，使其与书签的开头位于同一行。请确保在应用此功能之前保存文档的备份副本。

#### 问：如何识别 Word 文档中的行书签？

答：行书签通常用于表格中标记特定部分。您可以通过浏览文档中的书签并检查书签是否位于表格行中来识别行书签。

#### 问：是否可以解开非相邻表中的行书签？

答：本文介绍的“解开行书签”功能旨在解开相邻表格中的行书签。要解开非相邻表格中的行书签，可能需要根据文档的结构对代码进行额外调整。

#### 问：解开行书签后，我还能对其进行哪些操作？

答：一旦解开行书签，您就可以根据需要执行不同的操作。这可能包括编辑、删除或向已加书签的行添加内容。请务必小心处理行书签，以免对文档的其余部分造成任何不必要的影响。
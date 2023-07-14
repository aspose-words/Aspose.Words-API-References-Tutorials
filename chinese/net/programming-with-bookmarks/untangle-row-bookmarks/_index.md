---
title: 解开Word文档中的行书签
linktitle: 解开Word文档中的行书签
second_title: Aspose.Words 文档处理 API
description: 了解如何解开 Word 文档中的嵌套行书签以删除特定行而不影响其他书签。
type: docs
weight: 10
url: /zh/net/programming-with-bookmarks/untangle-row-bookmarks/
---

在本文中，我们将探索上面的 C# 源代码，以了解如何使用 Aspose.Words for .NET 库中的 Untangle Row Bookmarks 功能。此功能可以将行书签的末尾与书签的开头放在同一行中。

## 先决条件

- C# 语言的基础知识。
- 安装了 Aspose.Words 库的 .NET 开发环境。

## 第 1 步：加载文档

我们使用`Document`类从文件加载现有文档：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## 第 2 步：解开线书签

我们使用`Untangle`函数从行中解开书签。此函数执行将书签行尾与书签开头放在同一行的自定义任务：

```csharp
Untangle(doc);
```

## 步骤 3：按书签删除行

我们使用`DeleteRowByBookmark`通过书签删除特定行的函数：

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## 步骤 4：检查其他书签的完整性

我们通过检查书签末尾是否仍然存在来验证其他书签没有损坏：

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### 使用 Aspose.Words for .NET 解开行书签的示例源代码**

以下是使用 Aspose.Words for .NET 从行中解开书签的完整示例源代码：


```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	//这将执行将行书签结尾放入与书签开头相同的行中的自定义任务。
	Untangle(doc);

	//现在我们可以轻松地删除书签所在的行，而不会损坏任何其他行的书签。
	DeleteRowByBookmark(doc, "ROW2");

	//这只是为了检查另一个书签是否损坏。
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

## 结论

在本文中，我们探索了 C# 源代码，以了解如何使用 Aspose.Words for .NET 的 Untangle Row Bookmarks 功能。我们按照分步指南来解开行书签并删除特定行而不损坏其他书签。

### 解开 Word 文档中的行书签的常见问题解答

#### 问：Unscramble Row Bookmarks 是否仅适用于表中的行书签？

答：是的，解开行书签功能专门用于解开表中的行书签。该函数可用于处理数组中的行书签，并确保书签结尾与书签开头位于同一行。

#### 问：解读行书签功能是否会修改原始文档的内容？

答：是的，解读行书签功能通过移动行书签的末尾以将它们放置在与书签开头相同的行中来修改原始文档。在应用此功能之前，请确保保存文档的备份副本。

#### 问：如何识别 Word 文档中的行书签？

答：行书签通常在表格中用于标记特定部分。您可以通过浏览文档中的书签并检查书签是否位于表行中来识别行书签。

#### 问：是否可以解开非相邻表中的行书签？

答：本文中介绍的解开行书签功能旨在解开相邻表中的行书签。要解开不相邻表格中的行书签，可能需要根据文档的结构对代码进行额外的调整。

#### 问：解开行书签后，我还可以对其执行哪些其他操作？

答：线书签解开后，您可以根据需要执行不同的操作。这可能包括编辑、删除内容或将内容添加到已添加书签的行。请务必小心处理行书签，以避免对文档的其余部分产生任何不必要的影响。
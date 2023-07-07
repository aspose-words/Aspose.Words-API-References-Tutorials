---
title: 解开行书签
linktitle: 解开行书签
second_title: Aspose.Words for .NET API 参考
description: 了解如何解开嵌套行书签以删除特定行而不影响其他书签。
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
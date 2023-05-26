---
title: 附加书签文本
linktitle: 附加书签文本
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 从 Word 文档中的书签添加文本。
type: docs
weight: 10
url: /zh/net/programming-with-bookmarks/append-bookmarked-text/
---

在本文中，我们将探索上述 C# 源代码，以了解如何在 Aspose.Words for .NET 库中使用 Append Bookmarked Text 功能。此功能允许您将 Word 文档的特定书签中包含的文本添加到另一个文档。

## 先决条件

- C# 语言的基础知识。
- 安装了 Aspose.Words 库的 .NET 开发环境。

## 第 1 步：从书签中获取段落

在开始添加书签文本之前，我们需要获取包含书签开头和结尾的段落。这可以通过访问`BookmarkStart`和`BookmarkEnd`书签的属性：

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## 第 2 步：检查父段落

我们检查开始和结束段落是否有有效的父级，也就是说，它们是否真的属于一个段落。如果不是，我们生成一个异常：

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## 第 3 步：检查段落的父项

我们检查开始和结束段落是否具有相同的父级。如果不是，则意味着这些段落不包含在同一节或文档中，我们将抛出异常：

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## 第 4 步：复制段落

我们遍历从开始段落到结束段落的节点（段落）。对于每个节点，我们创建一个副本并将其导入到目标文档的上下文中：

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### 使用 Aspose.Words for .NET 添加书签文本的示例源代码

以下是演示使用 Aspose.Words for .NET 从书签添加文本的完整示例源代码：

```csharp

	//这是包含书签开头的段落。
	Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

	//这是包含书签结尾的段落。
	Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

	if (startPara == null || endPara == null)
		throw new InvalidOperationException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

	//将我们自己限制在一个相当简单的场景中。
	if (startPara.ParentNode != endPara.ParentNode)
		throw new InvalidOperationException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");

	//我们要复制从开始段落到（包括）结束段落的所有段落，
	//因此我们停止的节点是结束段落之后的节点。
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		//这将创建当前节点的副本并将其导入（使其有效）在上下文中
		//目标文件。导入意味着正确调整样式和列表标识符。
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## 结论

在本文中，我们探索了 C# 源代码以了解如何使用 Aspose.Words for .NET 的附加书签文本功能。我们已按照分步指南从书签中获取段落、验证父级以及将段落复制到另一个文档。
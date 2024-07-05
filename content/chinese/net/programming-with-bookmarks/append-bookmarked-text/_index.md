---
title: 在 Word 文档中附加书签文本
linktitle: 在 Word 文档中附加书签文本
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 从 Word 文档中的书签添加文本。
type: docs
weight: 10
url: /zh/net/programming-with-bookmarks/append-bookmarked-text/
---

在本文中，我们将探索上述 C# 源代码，以了解如何使用 Aspose.Words for .NET 库中的“附加书签文本”功能。此功能允许您将 Word 文档特定书签中包含的文本添加到另一个文档。

## 先决条件

- C# 语言的基本知识。
- 安装了 Aspose.Words 库的.NET 开发环境。

## 步骤 1：从书签获取段落

在开始添加书签文本之前，我们需要获取包含书签开始和结束的段落。这可以通过访问`BookmarkStart`和`BookmarkEnd`书签的属性：

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## 第 2 步：检查父段落

我们检查开始和结束段落是否有有效的父级，即它们是否真的属于一个段落。如果没有，我们将生成一个异常：

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## 步骤 3：检查段落的父级

我们检查开始和结束段落是否有相同的父级。如果没有，则意味着段落不包含在同一部分或文档中，并且我们会抛出异常：

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## 步骤 4：复制段落

我们从起始段落到结束段落遍历节点（段落）。对于每个节点，我们创建一个副本并将其导入到目标文档的上下文中：

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### 使用 Aspose.Words for .NET 添加书签文本的示例源代码

以下是完整的示例源代码，演示如何使用 Aspose.Words for .NET 从书签添加文本：

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

	//我们希望复制从起始段落到结束段落（包括结束段落）的所有段落，
	//因此我们停止的节点是最后一段之后的一个节点。
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		//这将创建当前节点的副本并将其导入上下文中（使其有效）
		//目标文档。导入意味着正确调整样式和列表标识符。
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## 结论

在本文中，我们探索了 C# 源代码，以了解如何使用 Aspose.Words for .NET 的附加书签文本功能。我们按照分步指南从书签中获取段落、验证父级以及将段落复制到另一个文档。

### 在 Word 文档中附加书签文本的常见问题解答

#### 问题 1：使用 Aspose.Words for .NET 中的“添加带有书签的文本”功能有哪些先决条件？

A：要使用 Aspose.Words for .NET 中的“添加带书签的文本”功能，您需要具备 C# 语言的基础知识。您还需要一个安装了 Aspose.Words 库的 .NET 开发环境。

#### Q2：如何获取Word文档中包含书签开始和结束的段落？

答：要获取 Word 文档中包含书签开始和结束的段落，您可以访问`BookmarkStart`和`BookmarkEnd`书签的属性。以下是示例代码：

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### Q3：如果开始和结束段落没有有效的父级会发生什么？

答：如果开始和结束段落没有有效的父级，即它们不是真正的段落，则会抛出异常。目前无法处理这种情况。

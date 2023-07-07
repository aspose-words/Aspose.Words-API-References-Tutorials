---
title: 显示隐藏书签内容
linktitle: 显示隐藏书签内容
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 显示或隐藏书签内容。
type: docs
weight: 10
url: /zh/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

在本文中，我们将探索上述 C# 源代码，以了解如何在 Aspose.Words for .NET 库中使用“显示隐藏书签内容”功能。此功能允许您在合并数据时根据特定条件显示或隐藏书签的内容。

## 先决条件

- C# 语言的基础知识。
- 安装了 Aspose.Words 库的 .NET 开发环境。

## 第一步：获取书签

我们使用`Bookmarks`文档范围的属性来获取我们要显示或隐藏内容的特定书签：

```csharp
Bookmark bm = doc.Range.Bookmarks[bookmarkName];
```

## 步骤 2：插入合并字段

我们使用文档生成器`DocumentBuilder`插入必要的合并字段。这些合并字段将设置一个条件来显示或隐藏书签内容，具体取决于`showHide`多变的：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToDocumentEnd();

Field field = builder. InsertField("IF \"", null);
builder. MoveTo(field. Start. NextSibling);
builder. InsertField("MERGEFIELD " + bookmarkName + "", null);
builder. Write("\" = \"true\" ");
builder. Write("\"");
builder. Write("\"");
builder. Write(" \"\"");
```

## 步骤 3：移动书签内容

我们循环浏览书签的内容并移动它以使其出现

isse 在书签之前。这将根据指定条件控制显示或隐藏内容：

```csharp
Node currentNode = field. Start;
bool flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.Run)
         if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
             flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
     currentNode = nextNode;
}
```

## 步骤 4：移动书签的其余内容

我们将书签的其余内容移动到书签之后，使用书签的结束节点作为插入点：

```csharp
Node endNode = bm.BookmarkEnd;
flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.FieldEnd)
         flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
     endNode = currentNode;
     currentNode = nextNode;
}
```

## 第 5 步：执行合并

我们使用`Execute`文档方法`s `邮件合并` object to execute the merge using the bookmark name and the value of the `显示隐藏`变量：

```csharp
doc. MailMerge. Execute(new[] { bookmarkName }, new object[] { showHide });
```

### 使用 Aspose.Words for .NET 显示隐藏书签内容的示例源代码

以下是源代码的完整示例，演示使用 Aspose.Words for .NET 显示或隐藏书签内容：

```csharp

	Bookmark bm = doc.Range.Bookmarks[bookmarkName];

	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.MoveToDocumentEnd();

	// {IF "{MERGEFIELD 书签}" = "true" "" ""}
	Field field = builder.InsertField("IF \"", null);
	builder.MoveTo(field.Start.NextSibling);
	builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
	builder.Write("\" = \"true\" ");
	builder.Write("\"");
	builder.Write("\"");
	builder.Write(" \"\"");

	Node currentNode = field.Start;
	bool flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.Run)
			if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
				flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
		currentNode = nextNode;
	}

	Node endNode = bm.BookmarkEnd;
	flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.FieldEnd)
			flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
		endNode = currentNode;
		currentNode = nextNode;
	}

	doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });

```

## 结论

在本文中，我们探索了 C# 源代码，以了解如何使用 Aspose.Words for .NET 的显示隐藏书签内容功能。我们按照分步指南在合并数据时根据特定条件显示或隐藏书签的内容。
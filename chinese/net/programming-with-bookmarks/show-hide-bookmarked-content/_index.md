---
title: 在 Word 文档中显示隐藏书签内容
linktitle: 在 Word 文档中显示隐藏书签内容
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中显示或隐藏书签内容。
type: docs
weight: 10
url: /zh/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

在本文中，我们将探索上述 C# 源代码，以了解如何在 Aspose.Words for .NET 库中使用“显示隐藏书签内容”功能。此功能允许您在合并数据时根据特定条件显示或隐藏 Word 文档中书签的内容。

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

### 有关在 Word 文档中显示隐藏书签内容的常见问题解答

#### 问：我可以对同一文档中的多个书签使用相同的条件吗？

答：是的，您可以对同一文档中的多个书签使用相同的条件。只需对每个书签重复步骤 2-5，调整书签名称以及可选的值`showhide`根据需要可变。

#### 问：如何添加更多条件来显示或隐藏书签内容？

 A：要添加更多条件，您可以使用逻辑运算符，例如`AND`和`OR`在步骤 2 中插入合并字段的代码中。编辑以下代码中的条件以添加其他条件：

```csharp
builder. Write("\" = \"true\" ");
```

#### 问：如何使用 Aspose.Words for .NET 删除 Word 文档中的书签？

答：要使用 Aspose.Words for .NET 删除 Word 文档中的书签，您可以使用`Remove`方法从`Bookmarks`文档范围的集合。以下是删除特定书签的示例代码：

```csharp
doc.Range.Bookmarks.Remove(bookmarkName);
```

#### 问：Aspose.Words 库是免费的吗？

答：Aspose.Words 库是一个商业库，需要有效的许可证才能在您的项目中使用。您可以查看 Aspose 的官方网站，了解有关许可选项和定价的更多信息。

#### 问：是否还有其他库可用于在 .NET 中对 Word 文档进行文字处理？

答：是的，还有其他库可用于在 .NET 中对 Word 文档进行文字处理，例如 Open XML SDK 和 GemBox.Document。您可以根据您的特定需求和偏好探索这些库作为 Aspose.Words 的替代品。
---
title: 在跟踪文档中移动节点
linktitle: 在跟踪文档中移动节点
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 在跟踪文档中移动节点。
type: docs
weight: 10
url: /zh/net/working-with-revisions/move-node-in-tracked-document/
---

在本分步指南中，我们将向您介绍如何使用 Aspose.Words for .NET 在跟踪的 Word 文档中移动节点。我们将为您提供完整的源代码，并向您展示如何格式化降价输出。

## 第 1 步：创建文档

第一步是创建一个新文档并添加段落。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Number of paragraphs: {0}", body.Paragraphs.Count);
```

## 第 2 步：跟踪修订

我们将在文档中启用修订跟踪。

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## 第 3 步：移动节点

我们将在生成修订时将节点（段落）从一个位置移动到另一个位置。

```csharp
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
     Node nextNode = node. NextSibling;
     body. InsertBefore(node, referenceNode);
     node = nextNode;
}
```

## 第 4 步：停止跟踪评论

我们将停止跟踪文档中的修订。

```csharp
doc.StopTrackRevisions();
```

## 第 5 步：保存文档

插入文本输入表单域后，使用`Save`方法。确保提供适当的文件路径：

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### 使用 Aspose.Words for .NET 在跟踪文档中移动节点的示例源代码

以下是使用 Aspose.Words for .NET 在跟踪文档中移动节点的完整源代码：


```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.Writeln("Paragraph 1");
	builder.Writeln("Paragraph 2");
	builder.Writeln("Paragraph 3");
	builder.Writeln("Paragraph 4");
	builder.Writeln("Paragraph 5");
	builder.Writeln("Paragraph 6");
	Body body = doc.FirstSection.Body;
	Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);

	//开始跟踪修订。
	doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));

	//将节点从一个位置移动到另一个位置时生成修订。
	Node node = body.Paragraphs[3];
	Node endNode = body.Paragraphs[5].NextSibling;
	Node referenceNode = body.Paragraphs[0];
	while (node != endNode)
	{
		Node nextNode = node.NextSibling;
		body.InsertBefore(node, referenceNode);
		node = nextNode;
	}

	//停止跟踪修订的过程。
	doc.StopTrackRevisions();

	//移出范围中还有 3 个附加段落。
	Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
	doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
            
```


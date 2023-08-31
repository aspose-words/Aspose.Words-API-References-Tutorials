---
title: 在跟踪文档中移动节点
linktitle: 在跟踪文档中移动节点
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 移动跟踪文档中的节点。
type: docs
weight: 10
url: /zh/net/working-with-revisions/move-node-in-tracked-document/
---

在本分步指南中，我们将引导您了解如何使用 Aspose.Words for .NET 在跟踪的 Word 文档中移动节点。我们将为您提供完整的源代码，并向您展示如何格式化 Markdown 输出。

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

## 步骤 3：移动节点

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

插入文本输入表单字段后，使用以下命令将文档保存到所需位置`Save`方法。确保提供适当的文件路径：

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

//移出范围中有 3 个附加段落。
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

## 结论

在本教程中，我们学习了如何使用 Aspose.Words for .NET 移动跟踪的 Word 文档中的节点。通过遵循创建文档、启用修订跟踪、移动节点和停止修订跟踪的步骤，我们能够成功执行此操作。 Aspose.Words for .NET 是一款功能强大的 Word 文档文字处理工具，并提供管理修订的高级功能。现在，您可以利用这些知识在您自己的 Word 文档中移动节点，同时使用 Aspose.Words for .NET 跟踪修订。

### 常见问题解答

#### 问：如何在 Aspose.Words for .NET 文档中启用修订跟踪？

答：要在 Aspose.Words for .NET 文档中启用修订跟踪，您可以使用`StartTrackRevisions`的方法`Document`目的。该方法将修订的作者姓名和后续修订的开始日期作为参数。

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

#### 问：如何移动跟踪文档中的节点而不生成修订？

答：如果您想移动跟踪文档中的节点而不生成修订，您可以使用`Remove`和`InsertAfter`或者`InsertBefore`的方法`Node`目的。例如，要将一个段落移到另一个段落之后，可以使用以下代码：

```csharp
Node nodeToMove = document.FirstSection.Body.Paragraphs[0];
Node referenceNode = document.FirstSection.Body.Paragraphs[1];
nodeToMove.Remove();
document.FirstSection.Body.InsertAfter(nodeToMove, referenceNode);
```

#### 问：如何停止 Aspose.Words for .NET 文档中的修订跟踪？

答：要停止跟踪 Aspose.Words for .NET 文档中的修订，您可以使用`StopTrackRevisions`的方法`Document`目的。

```csharp
doc.StopTrackRevisions();
```
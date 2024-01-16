---
title: 在追蹤文件中移動節點
linktitle: 在追蹤文件中移動節點
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 移動追蹤文件中的節點。
type: docs
weight: 10
url: /zh-hant/net/working-with-revisions/move-node-in-tracked-document/
---

在本逐步指南中，我們將引導您了解如何使用 Aspose.Words for .NET 在追蹤的 Word 文件中移動節點。我們將為您提供完整的原始程式碼，並向您展示如何格式化 Markdown 輸出。

## 第 1 步：建立文檔

第一步是建立一個新文件並新增段落。

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

## 第 2 步：追蹤修訂

我們將在文件中啟用修訂追蹤。

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## 步驟 3：移動節點

我們將在產生修訂時將節點（段落）從一個位置移動到另一個位置。

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

## 第 4 步：停止追蹤評論

我們將停止追蹤文件中的修訂。

```csharp
doc.StopTrackRevisions();
```

## 第 5 步：儲存文檔

插入文字輸入表單欄位後，使用以下命令將文件儲存到所需位置`Save`方法。確保提供適當的文件路徑：

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### 使用 Aspose.Words for .NET 在追蹤文件中移動節點的範例原始碼

以下是使用 Aspose.Words for .NET 在追蹤文件中移動節點的完整原始碼：


```csharp
//文檔目錄的路徑。
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

//開始追蹤修訂。
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));

//將節點從一個位置移動到另一個位置時產生修訂。
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
	Node nextNode = node.NextSibling;
	body.InsertBefore(node, referenceNode);
	node = nextNode;
}

//停止追蹤修訂的過程。
doc.StopTrackRevisions();

//移出範圍中有 3 個附加段落。
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

## 結論

在本教學中，我們學習如何使用 Aspose.Words for .NET 行動追蹤的 Word 文件中的節點。透過遵循建立文件、啟用修訂追蹤、移動節點和停止修訂追蹤的步驟，我們能夠成功執行此操作。 Aspose.Words for .NET 是一款功能強大的 Word 文件文字處理工具，並提供管理修訂的進階功能。現在，您可以利用這些知識在您自己的 Word 文件中移動節點，同時使用 Aspose.Words for .NET 追蹤修訂。

### 常見問題解答

#### Q：如何在 Aspose.Words for .NET 文件中啟用修訂追蹤？

答：要在 Aspose.Words for .NET 文件中啟用修訂跟踪，您可以使用`StartTrackRevisions`的方法`Document`目的。此方法將修訂的作者姓名和後續修訂的開始日期作為參數。

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

#### Q：如何移動追蹤文件中的節點而不產生修訂？

答：如果您想移動追蹤文件中的節點而不產生修訂，您可以使用`Remove`和`InsertAfter`或者`InsertBefore`的方法`Node`目的。例如，要將一個段落移到另一個段落之後，可以使用以下程式碼：

```csharp
Node nodeToMove = document.FirstSection.Body.Paragraphs[0];
Node referenceNode = document.FirstSection.Body.Paragraphs[1];
nodeToMove.Remove();
document.FirstSection.Body.InsertAfter(nodeToMove, referenceNode);
```

#### Q：如何停止 Aspose.Words for .NET 文件中的修訂追蹤？

答：要停止追蹤 Aspose.Words for .NET 文件中的修訂，您可以使用`StopTrackRevisions`的方法`Document`目的。

```csharp
doc.StopTrackRevisions();
```
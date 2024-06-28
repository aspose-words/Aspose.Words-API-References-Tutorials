---
title: 接受评论
linktitle: 接受评论
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 接受对 Word 文档的修订
type: docs
weight: 10
url: /zh/net/working-with-revisions/accept-revisions/
---

在本教程中，我们将引导您使用 Aspose.Words for .NET 的接受修订功能接受对 Word 文档的修订。请按照以下步骤了解源代码并接受对文档的更改。

## 第1步：添加和编辑文档内容

在此示例中，我们将创建一个文档并添加内容。我们用几个段落来说明变化和修订。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

//将文本添加到第一个段落，然后再添加两个段落。
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## 第 2 步：跟踪评论并添加评论

我们启用修订跟踪并向文档添加修订。就是这样：

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

//该段落是修订版，并且将设置相应的“IsInsertRevision”标志。
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## 第 3 步：删除段落并管理修订

我们删除一个段落并检查已保存的修订。就是这样：

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

//由于我们正在跟踪修订，该段落仍然存在于文档中，将设置“IsDeleteRevision”标志
//并将在 Microsoft Word 中显示为评论，直到我们接受或拒绝所有评论。
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## 第 4 步：接受更改

我们接受对文档的所有更改。就是这样：

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## 第 5 步：停止跟踪评论

我们将停止跟踪修订，以便对文档的更改不再显示为修订。就是这样：

```csharp
doc.StopTrackRevisions();
```
## 第 6 步：保存文档

插入文本输入表单字段后，使用以下命令将文档保存到所需位置`Save`方法。确保提供适当的文件路径：

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### 使用 Aspose.Words for .NET 接受修订的示例源代码

以下是使用 Aspose.Words for .NET 接受文档更改的完整源代码：


```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

//将文本添加到第一个段落，然后再添加两个段落。
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

//我们有三个段落，其中没有一个被注册为任何类型的修订
//如果我们在跟踪修订时添加/删除文档中的任何内容，
//它们将在文档中显示并可以接受/拒绝。
doc.StartTrackRevisions("John Doe", DateTime.Now);

//本段是修订版，并将设置相应的“IsInsertRevision”标志。
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

//获取文档的段落集合并删除段落。
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

//由于我们正在跟踪修订，该段落仍然存在于文档中，将设置“IsDeleteRevision”
//并将在 Microsoft Word 中显示为修订版本，直到我们接受或拒绝所有修订版本。
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

//一旦我们接受更改，已删除的修订段落就会被删除。
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

//停止跟踪修订会使该文本显示为普通文本。
//文档更改时不计算修订版本。
doc.StopTrackRevisions();

//保存文档。
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## 结论

在本教程中，我们学习了如何使用 Aspose.Words for .NET 的接受修订功能接受 Word 文档中的修订。我们已按照以下步骤添加和编辑文档内容、跟踪修订、删除修订的段落、接受所有更改以及停止跟踪修订。现在，您可以使用 Aspose.Words for .NET 应用这些知识来有效管理您自己的 Word 文档中的修订。

### 常见问题解答

#### 问：如何在 Aspose.Words for .NET 中启用修订跟踪？

#### 解决方案一：

答：要在 Aspose.Words for .NET 中启用修订跟踪，请使用`StartTrackRevisions`的方法`Document`对象并指定作者姓名和修订跟踪的开始日期。

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### 解决方案2：

答：您还可以使用以下命令启用修订跟踪`Document`接受的构造函数`trackRevisions`和`author`参数。

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### 问：如何使用 Aspose.Words for .NET 接受文档中的所有更改？

答：使用`AcceptAllRevisions`的方法`Document`反对接受对文档所做的所有更改。

```csharp
doc.AcceptAllRevisions();
```

#### 问：如何保存已接受修订的修改文档？

使用`Save`的方法`Document`对象保存已接受修订的修改后的文档。请务必提供正确的文件路径。

```csharp
doc.Save("path/to/the/document.docx");
```

#### 问：如何停止跟踪 Aspose.Words for .NET 中的修订？

答：使用`StopTrackRevisions`的方法`Document`反对停止跟踪修订。

```csharp
doc.StopTrackRevisions();
```

#### 问：如何使用 Aspose.Words for .NET 删除文档中修改的段落？

答：要删除文档中修改的段落，您可以使用`Remove`段落收集方法。

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```
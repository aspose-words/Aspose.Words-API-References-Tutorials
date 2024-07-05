---
title: 接受修订
linktitle: 接受修订
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 接受对 Word 文档的修订
type: docs
weight: 10
url: /zh/net/working-with-revisions/accept-revisions/
---

在本教程中，我们将引导您使用 Aspose.Words for .NET 的“接受修订”功能接受对 Word 文档的修订。按照以下步骤了解源代码并接受对文档的更改。

## 步骤 1：添加和编辑文档内容

在此示例中，我们正在创建文档并添加内容。我们使用几个段落来说明更改和修订。操作方法如下：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

//在第一段添加文本，然后再添加两段。
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## 第 2 步：跟踪评论并添加评论

我们启用修订跟踪并向文档添加修订。操作如下：

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

//此段落是修订版，将设置相应的“IsInsertRevision”标志。
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## 步骤 3：删除段落并管理修订

我们删除一个段落并检查已保存的修订。操作如下：

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

//由于我们正在跟踪修订，该段落仍存在于文档中，因此将设置“IsDeleteRevision”标志
//并将作为评论显示在 Microsoft Word 中，直到我们接受或拒绝所有评论。
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## 步骤 4：接受更改

我们接受对文档的所有更改。方法如下：

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## 第 5 步：停止跟踪评论

我们将停止跟踪修订，这样对文档的更改将不再显示为修订。具体方法如下：

```csharp
doc.StopTrackRevisions();
```
## 步骤 6：保存文档

插入文本输入表单字段后，使用`Save`方法。请确保提供适当的文件路径：

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

//在第一段添加文本，然后再添加两段。
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

//我们有三个段落，其中没有一个被登记为任何类型的修订
//如果我们在跟踪修订时添加或删除文档中的任何内容，
//它们将会在文档中显示，并且可以被接受/拒绝。
doc.StartTrackRevisions("John Doe", DateTime.Now);

//此段落是一次修订，并将设置相应的“IsInsertRevision”标志。
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

//获取文档的段落集合并删除一个段落。
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

//由于我们正在跟踪修订，该段落仍存在于文档中，将设置“IsDeleteRevision”
//并将在 Microsoft Word 中显示为修订，直到我们接受或拒绝所有修订。
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

//一旦我们接受更改，删除修订段落就会被删除。
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

//停止修订跟踪会使该文本显示为普通文本。
//当文档发生更改时，修订不被计算在内。
doc.StopTrackRevisions();

//保存文档。
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## 结论

在本教程中，我们学习了如何使用 Aspose.Words for .NET 的“接受修订”功能接受 Word 文档中的修订。我们按照以下步骤添加和编辑文档内容、跟踪修订、删除修订段落、接受所有更改以及停止跟踪修订。现在，您可以应用这些知识，使用 Aspose.Words for .NET 有效地管理您自己的 Word 文档中的修订。

### 常见问题解答

#### 问：如何在 Aspose.Words for .NET 中启用修订跟踪？

#### 解决方案 1：

答：要在 Aspose.Words for .NET 中启用修订跟踪，请使用`StartTrackRevisions`方法`Document`对象并指定修订跟踪的作者姓名和开始日期。

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### 解决方案 2：

答：您还可以使用`Document`接受的构造函数`trackRevisions`和`author`参数。

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### 问：如何使用 Aspose.Words for .NET 接受文档中的所有更改？

答：使用`AcceptAllRevisions`方法`Document`对象接受对文档所做的所有更改。

```csharp
doc.AcceptAllRevisions();
```

#### 问：如何保存已接受修订的修改文档？

使用`Save`方法`Document`对象保存修改后的文档并接受修订。请确保提供正确的文件路径。

```csharp
doc.Save("path/to/the/document.docx");
```

#### 问：如何停止跟踪 Aspose.Words for .NET 中的修订？

答：使用`StopTrackRevisions`方法`Document`反对停止跟踪修订。

```csharp
doc.StopTrackRevisions();
```

#### 问：如何使用 Aspose.Words for .NET 删除文档中修订的段落？

答：要删除文档中修订的段落，您可以使用`Remove`段落收集的方法。

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```
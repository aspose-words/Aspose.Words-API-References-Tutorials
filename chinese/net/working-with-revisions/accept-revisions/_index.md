---
title: 接受修订
linktitle: 接受修订
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 接受对 Word 文档的修订
type: docs
weight: 10
url: /zh/net/working-with-revisions/accept-revisions/
---

在本教程中，我们将引导您使用 Aspose.Words for .NET 的接受修订功能接受对 Word 文档的修订。按照以下步骤了解源代码并接受对文档的更改。

## 第 1 步：添加和编辑文档内容

在此示例中，我们正在创建文档并添加内容。我们使用几个段落来说明更改和修订。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

//向第一段添加文本，然后再添加两段。
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## 第 2 步：跟踪评论并添加评论

我们启用修订跟踪并向文档添加修订。就是这样：

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

//本段是修订版，将设置相应的“IsInsertRevision”标志。
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## 第 3 步：删除段落并管理修订

我们删除一个段落并检查保存的修订。就是这样：

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
## 第 6 步：保存文件

插入文本输入表单域后，使用`Save`方法。确保提供适当的文件路径：

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

//向第一段添加文本，然后再添加两段。
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

//我们有三个段落，其中没有一个被注册为任何类型的修订
//如果我们在跟踪修订时添加/删除文档中的任何内容，
//它们将按原样显示在文档中，并且可以被接受/拒绝。
doc.StartTrackRevisions("John Doe", DateTime.Now);

//本段是修订版，将设置相应的“IsInsertRevision”标志。
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

//获取文档的段落集合并删除一个段落。
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

//由于我们正在跟踪修订，该段落仍然存在于文档中，将设置“IsDeleteRevision”
//并将在 Microsoft Word 中显示为修订版，直到我们接受或拒绝所有修订版。
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

//一旦我们接受更改，删除修订段落将被删除。
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

//停止跟踪修订会使该文本显示为普通文本。
//更改文档时不计算修订。
doc.StopTrackRevisions();

//保存文档。
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

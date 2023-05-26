---
title: 锚评论
linktitle: 锚评论
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将评论回复锚定到 Word 文档中的特定文本。
type: docs
weight: 10
url: /zh/net/working-with-comments/anchor-comment/
---

在这个综合教程中，您将学习如何使用 Aspose.Words for .NET 将评论回复锚定到 Word 文档中的特定文本。我们将指导您完成整个过程，并为您提供必要的 C# 代码片段。在本指南结束时，您将能够将注释与文档中的特定文本相关联。

## 先决条件
在我们开始之前，请确保您具备以下先决条件：
- Aspose.Words for .NET 库安装在您的系统上。

## 第 1 步：创建新文档并添加文本
首先，使用 Document 类创建一个新文档并添加所需的文本：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);
```

## 第 2 步：创建评论并添加评论范围
接下来，使用 CommentRangeStart 和 CommentRangeEnd 对象创建评论并将其与特定文本相关联：

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);
```

## 第 3 步：保存文档
将评论锚定到特定文本后，使用 Document 类的 Save 方法将文档保存到文件：

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### 使用 Aspose.Words for .NET 的锚评论回复示例源代码
以下是使用 Aspose.Words for .NET 锚定评论回复的完整源代码：

```csharp

    //创建文档的实例。
	string dataDir = "YOUR DOCUMENT DIRECTORY";        
	Document doc = new Document();

    //创建三个运行对象。
    //前两个运行一些文本，而第三个运行评论

	Paragraph para1 = new Paragraph(doc);
	Run run1 = new Run(doc, "Some ");
	Run run2 = new Run(doc, "text ");
	para1.AppendChild(run1);
	para1.AppendChild(run2);
	doc.FirstSection.Body.AppendChild(para1);

	Paragraph para2 = new Paragraph(doc);
	Run run3 = new Run(doc, "is ");
	Run run4 = new Run(doc, "added ");
	para2.AppendChild(run3);
	para2.AppendChild(run4);
	doc.FirstSection.Body.AppendChild(para2);

	Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
	comment.Paragraphs.Add(new Paragraph(doc));
	comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

	//每个 Run 对象都有一个关联的 CommentRangeStart 和 CommentRangeEnd 对象。

	CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
	CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

	run1.ParentNode.InsertAfter(commentRangeStart, run1);
	run3.ParentNode.InsertAfter(commentRangeEnd, run3);
	commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

	doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
            
```

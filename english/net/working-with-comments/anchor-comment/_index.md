---
title: Anchor Comment
linktitle: Anchor Comment
second_title: Aspose.Words for .NET API Reference
description: Learn how to anchor comment replies to specific text in Word documents using Aspose.Words for .NET. 
type: docs
weight: 10
url: /net/working-with-comments/anchor-comment/
---

In this comprehensive tutorial, you will learn how to anchor comment replies to specific text in a Word document using Aspose.Words for .NET. We will guide you through the process and provide you with the necessary C# code snippets. By the end of this guide, you will be able to associate comments with specific text in your documents.

## Prerequisites
Before we begin, ensure that you have the following prerequisites:
- Aspose.Words for .NET library installed on your system.

## Step 1: Create a New Document and Add Text
To start, create a new document using the Document class and add the desired text:

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

## Step 2: Create a Comment and Add Comment Range
Next, create a comment and associate it with specific text using CommentRangeStart and CommentRangeEnd objects:

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

## Step 3: Save the Document
After anchoring the comment to specific text, save the document to a file using the Save method of the Document class:

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### Example Source Code for Anchor Comment Reply using Aspose.Words for .NET
Here is the complete source code for anchoring a comment reply using Aspose.Words for .NET:

```csharp
// Create an instance of the Document.
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// Create three Run objects.
// The first two run some text, while the third runs a Comment

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

// Each of the Run objects has an associated CommentRangeStart and CommentRangeEnd object.

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```

### FAQ's

#### Q: What is a comment anchor in Aspose.Words for .NET?

A: In Aspose.Words for .NET, a comment anchor is a marker that connects a comment to a specific location in a document.

#### Q: How can I add a comment anchor in an Aspose.Words for .NET document?

A: To add a comment anchor in an Aspose.Words for .NET document, follow the steps mentioned in the tutorial.

#### Q: How do I access an existing comment anchor in Aspose.Words for .NET?

A: You can access an existing comment anchor in Aspose.Words for .NET using the `Comment.Anchor` property.

#### Q: Can I supprime a comment anchor in Aspose.Words for .NET?

A: Yes, you can remove a comment anchor in Aspose.Words for .NET using the `Comment.Remove` method.

#### Q: How can I edit the text of a comment linked to a comment anchor in Aspose.Words for .NET?

A: To modify the text of a comment bound to a comment anchor in Aspose.Words for .NET, you can access the `Comment.Text` property of the corresponding `Comment` object and modify the text as needed.



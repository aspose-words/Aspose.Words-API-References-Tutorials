---
title: Add Comments
linktitle: Add Comments
second_title: Aspose.Words Document Processing API
description: Learn how to add comments to Word documents using Aspose.Words for .NET. 
type: docs
weight: 10
url: /net/working-with-comments/add-comments/
---

In this comprehensive tutorial, you will learn how to add comments to a Word document using Aspose.Words for .NET. We will guide you through the process and provide you with the necessary C# code snippets. By the end of this guide, you will be able to insert comments and customize their content in your documents.

## Prerequisites
Before we begin, ensure that you have the following prerequisites:
- Aspose.Words for .NET library installed on your system.

## Step 1: Create a New Document and DocumentBuilder
To start, create a new document using the Document class and initialize a DocumentBuilder object:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Add Content to the Document
Next, add the desired content to the document using the DocumentBuilder object. In this example, we add some text:

```csharp
builder.Write("Some text is added.");
```

## Step 3: Create a Comment and Add Contents
To add a comment, create an instance of the Comment class, passing the Document object, author name, author initials, and the current date:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

Next, append the comment to the current paragraph:

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

Add contents to the comment, such as a paragraph and text:

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## Step 4: Save the Document
After adding the comment and its contents, save the document to a file using the Save method of the Document class:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Example Source Code for Add Comments using Aspose.Words for .NET
Here is the complete source code for adding comments using Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text is added.");

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
builder.CurrentParagraph.AppendChild(comment);

comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Conclusion
Congratulations! You have successfully learned how to add comments to a Word document using Aspose.Words for .NET. By following the step-by-step guide and utilizing the provided source code, you can now insert comments and customize their content in your documents.

Comments are useful for collaboration, providing additional information, or making notes within a document. Experiment with different author names, initials, and comment contents to meet your specific requirements.

### FAQ's

#### Q: How can I add a comment in an Aspose.Words for .NET document?

A: To add a comment in an Aspose.Words for .NET document, you need to follow the steps mentioned in the tutorial.

#### Q: Can I format comment text in Aspose.Words for .NET?

A: Yes, you can format comment text in Aspose.Words for .NET using the formatting properties available.

#### Q: How can I retrieve all the comments present in a document?

A: You can retrieve all comments present in a document using the `Document.Comments` property.

#### Q: Can I delete a specific comment in Aspose.Words for .NET?

A: Yes, you can remove a specific comment in Aspose.Words for .NET using the `Comment.Remove` method.

#### Q: How can I modify the text of an existing comment in Aspose.Words for .NET?

A: To modify the text of an existing comment in Aspose.Words for .NET, you can access the `Comment.Text` property of the corresponding `Comment` object and modify the text as needed.

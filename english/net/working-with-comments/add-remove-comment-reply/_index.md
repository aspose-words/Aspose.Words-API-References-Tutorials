---
title: Add Remove Comment Reply
linktitle: Add Remove Comment Reply
second_title: Aspose.Words for .NET API Reference
description: Learn how to add and remove comment replies in Word documents using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-comments/add-remove-comment-reply/
---

In this comprehensive tutorial, you will learn how to add and remove comment replies in a Word document using Aspose.Words for .NET. We will guide you through the process and provide you with the necessary C# code snippets. By the end of this guide, you will be able to manage comment replies and customize them according to your requirements.

## Prerequisites
Before we begin, ensure that you have the following prerequisites:
- Aspose.Words for .NET library installed on your system.

## Step 1: Load the Document
To start, load the document that contains the comments using the Document class:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## Step 2: Access the Comment and Manage Replies
Next, access the comment from the document using the GetChild method with the NodeType.Comment parameter:

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

To remove a reply from the comment, use the RemoveReply method and provide the desired reply index:

```csharp
comment.RemoveReply(comment.Replies[0]);
```

To add a new reply to the comment, use the AddReply method and provide the author name, author initials, date and time, and reply text:

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## Step 3: Save the Document
After adding or removing comment replies, save the document to a file using the Save method of the Document class:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

### Example Source Code for Add and Remove Comment Replies using Aspose.Words for .NET
Here is the complete source code for adding and removing comment replies using Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);

comment.RemoveReply(comment.Replies[0]);

comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");

doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## Conclusion
Congratulations! You have successfully learned how to add and remove comment replies in a Word document using Aspose.Words for .NET. By following the step-by-step guide and utilizing the provided source code, you can now manage comment replies and customize them as per your requirements.

Comment replies allow for collaborative discussions and feedback within a document. Experiment with different reply authors, initials, dates, and texts to enhance collaboration and communication within your documents.

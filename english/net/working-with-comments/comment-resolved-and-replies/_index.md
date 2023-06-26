---
title: Comment Resolved And Replies
linktitle: Comment Resolved And Replies
second_title: Aspose.Words for .NET API Reference
description: Learn how to resolve comments and their replies in Word documents using Aspose.Words for .NET. 
type: docs
weight: 10
url: /net/working-with-comments/comment-resolved-and-replies/
---

In this comprehensive tutorial, you will learn how to resolve comments and their replies in a Word document using Aspose.Words for .NET. We will guide you through the process and provide you with the necessary C# code snippets. By the end of this guide, you will be able to manage comment resolution and update the status of comments and their replies.

## Prerequisites
Before we begin, ensure that you have the following prerequisites:
- Aspose.Words for .NET library installed on your system.

## Step 1: Load the Document and Access Comments
To start, load the document that contains the comments using the Document class and access the comments collection:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## Step 2: Resolve Comments and Their Replies
Next, iterate through the comments and their replies to mark them as resolved:

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

In the above code, we access the parent comment and iterate through its replies. We can retrieve the parent comment ID and its resolution status. Then, we update the "Done" mark of each comment reply to indicate resolution.

## Step 3: Save the Document
After resolving the comments and updating their status, save the modified document to a file using the Save method of the Document class:

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### Example Source Code for Resolving Comments and Their Replies using Aspose.Words for .NET
Here is the complete source code for resolving comments and their replies using Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}

doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```
Remember to adjust the code according to your specific requirements, including the document file path and additional customization

## Conclusion
Congratulations! You have successfully learned how to resolve comments and their replies in a Word document using Aspose.Words for .NET. By following the step-by-step guide and utilizing the provided source code, you can now manage comment resolution and update the status of comments and their replies according to your requirements.

Comment resolution helps in tracking and managing feedback within a document. Experiment with different comment statuses and customize them to improve collaboration and review processes in your documents.

### FAQ's

#### Q: How do I resolve a comment in Aspose.Words for .NET?

A: To resolve a comment in Aspose.Words for .NET, you can use the `Comment.Resolve` method specifying the `Comment` object you want to resolve. This will mark the comment as resolved and hide it in the final document.

#### Q: How do I add a reply to a resolved comment in Aspose.Words for .NET?

A: Although resolved comments are hidden by default in the final document, you can still add a reply to a resolved comment using the `Comment.AddReply` method specifying the reply text and where you want to add it .

#### Q: How do I view resolved comments in Aspose.Words for .NET?

A: By default, resolved comments are hidden in the final document. However, you can show them by using the `CommentOptions.ShowResolvedComments` property of the `Document` object and setting it to `true`.

#### Q: How can I hide all comments, including replies, in Aspose.Words for .NET?

A: To hide all comments, including replies, in Aspose.Words for .NET, you can use the `CommentOptions.CommentDisplayMode` property of the `Document` object and set it to `CommentDisplayMode.None`.

#### Q: Can I edit the text of a resolved comment in Aspose.Words for .NET?

A: Yes, you can edit the text of a resolved comment in Aspose.Words for .NET by accessing the `Comment.Text` property of the corresponding `Comment` object and modifying the text as needed.

---
title: Show Hide Bookmarked Content In Word Document
linktitle: Show Hide Bookmarked Content In Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to dynamically show or hide bookmarked content in Word documents using Aspose.Words for .NET with this comprehensive step-by-step guide.
type: docs
weight: 10
url: /net/programming-with-bookmarks/show-hide-bookmarked-content/
---

## Introduction

Hey there! Have you ever wanted to control the visibility of specific content within a Word document based on certain conditions? With Aspose.Words for .NET, you can dynamically show or hide bookmarked content with just a few lines of code. In this tutorial, I'll walk you through the process step-by-step, ensuring you understand each part of the code. By the end, you'll be a pro at manipulating bookmarks in Word documents. Let's get started!

## Prerequisites

Before we dive into the tutorial, let's make sure you have everything you need:

1. Basic Knowledge of C#: You should be comfortable with C# syntax and concepts.
2. Aspose.Words for .NET: Download it [here](https://releases.aspose.com/words/net/). If you're not ready to purchase, you can start with a [free trial](https://releases.aspose.com/).
3. Visual Studio: Any recent version will work, but using the latest version is recommended.
4. .NET Framework: Ensure it's installed on your machine.

Ready to get started? Great! Let's begin by importing the necessary namespaces.

## Import Namespaces

To use Aspose.Words for .NET, we need to import the required namespaces. This step ensures we have access to all the classes and methods we'll be using.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

These namespaces are crucial for working with Word documents and manipulating their content.

## Step 1: Setting Up the Document

First, let's create a new Word document and a document builder. The document builder helps us easily add and manipulate content within the document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

In this step, we initialize a new document and a document builder. This sets up our environment for further operations.

## Step 2: Adding Bookmarked Content

Next, we'll add some content to the document and create a bookmark around it. This bookmark will help us identify and manipulate the content.

```csharp
builder.Write("This is some text before the bookmark.");
builder.StartBookmark("MyBookmark");
builder.Write("This is the bookmarked content.");
builder.EndBookmark("MyBookmark");
builder.Write("This is some text after the bookmark.");
```

Here, we add some text before and after the bookmarked content. The `StartBookmark` and `EndBookmark` methods define the boundaries of the bookmark.

## Step 3: Inserting a Conditional Field

To control the visibility of the bookmarked content, we'll use a conditional field. This field will check a condition and display or hide the content accordingly.

```csharp
builder.MoveToDocumentEnd();
Field field = builder.InsertField("IF \"", null);
builder.MoveTo(field.Start.NextSibling);
builder.InsertField("MERGEFIELD MyBookmark", null);
builder.Write("\" = \"true\" \"Visible\" \"Hidden\"");
```

In this step, we insert an IF field that checks the value of the bookmark. If the value is "true", it will display "Visible"; otherwise, it will display "Hidden".

## Step 4: Rearranging Nodes

Next, we need to rearrange the nodes to ensure the conditional logic applies correctly to the bookmarked content.

```csharp
Bookmark bm = doc.Range.Bookmarks["MyBookmark"];
Node currentNode = field.Start;
bool flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.Run && currentNode.ToString(SaveFormat.Text).Trim() == "\"")
        flag = false;

    Node nextNode = currentNode.NextSibling;
    bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
    currentNode = nextNode;
}

Node endNode = bm.BookmarkEnd;
flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.FieldEnd)
        flag = false;

    Node nextNode = currentNode.NextSibling;
    bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
    endNode = currentNode;
    currentNode = nextNode;
}
```

Here, we move nodes around to make sure the condition properly encompasses the bookmarked content.

## Step 5: Executing Mail Merge

Finally, we'll execute a mail merge to set the value of the bookmark and determine whether the content should be shown or hidden.

```csharp
doc.MailMerge.Execute(new[] { "MyBookmark" }, new object[] { "true" });
```

This step sets the bookmark value to "true", which will make the content visible based on our condition.

## Step 6: Saving the Document

After all the manipulations, the last step is to save the modified document.

```csharp
doc.Save("ShowHideBookmarkedContent.docx");
```

Here, we save the document with a descriptive file name to indicate the changes.

## Conclusion

And that's it! You've successfully learned how to show or hide bookmarked content in a Word document using Aspose.Words for .NET. This tutorial covered creating a document, adding bookmarks, inserting conditional fields, rearranging nodes, and executing a mail merge. Aspose.Words offers a plethora of features, so don't hesitate to explore the [API documentation](https://reference.aspose.com/words/net/) for more advanced capabilities.

## FAQs

### 1. What is Aspose.Words for .NET?

Aspose.Words for .NET is a powerful library that allows developers to create, modify, and convert Word documents programmatically. It's widely used for document automation tasks.

### 2. Can I use Aspose.Words for .NET for free?

You can try Aspose.Words for .NET using a [free trial](https://releases.aspose.com/). For long-term use, you'll need to purchase a license.

### 3. How do I modify other properties of a bookmark?

Aspose.Words allows you to manipulate various properties of a bookmark, such as its text and location. Refer to the [API documentation](https://reference.aspose.com/words/net/) for detailed instructions.

### 4. How do I get support for Aspose.Words for .NET?

You can get support by visiting the [Aspose support forum](https://forum.aspose.com/c/words/8).

### 5. Can I manipulate other types of content with Aspose.Words for .NET?

Yes, Aspose.Words for .NET supports various types of content manipulation, including text, images, tables, and more.

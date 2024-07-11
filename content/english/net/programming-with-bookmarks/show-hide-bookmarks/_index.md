---
title: Show Hide Bookmarks In Word Document
linktitle: Show Hide Bookmarks In Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to dynamically show or hide bookmarks in a Word document using Aspose.Words for .NET with our step-by-step guide. Perfect for developers.
type: docs
weight: 10
url: /net/programming-with-bookmarks/show-hide-bookmarks/
---
## Introduction

Ever found yourself needing to hide or show certain parts of your Word document dynamically? Well, you're in luck! With Aspose.Words for .NET, you can easily manage the visibility of bookmarked content in your documents. This tutorial will walk you through the process of showing and hiding bookmarks in a Word document using Aspose.Words for .NET. We'll break down the code step by step, so whether you're a seasoned developer or a newbie, you'll find this guide easy to follow.

## Prerequisites

Before we dive into the code, let's make sure you have everything you need:

1. Aspose.Words for .NET: Ensure you have the Aspose.Words for .NET library installed. If not, you can download it [here](https://releases.aspose.com/words/net/).
2. Development Environment: An IDE like Visual Studio.
3. Basic Knowledge of C#: Familiarity with C# programming will be beneficial.
4. A Word Document: A sample Word document with bookmarks.

## Import Namespaces

Before starting with the code, you need to import the necessary namespaces. Add the following at the beginning of your C# file:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
using Aspose.Words.Tables;
```

## Step 1: Load Your Document

First things first, you need to load the Word document that contains the bookmarks. Here’s how you can do it:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

### Explanation

- dataDir: This is the directory path where your Word document is located.
- Document doc: This initializes a new instance of the `Document` class with your specified file.

## Step 2: Show or Hide Bookmarked Content

Next, we’ll define a method to show or hide the bookmarked content. Here's the complete method:

```csharp
public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool showHide)
{
    Bookmark bm = doc.Range.Bookmarks[bookmarkName];

    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.MoveToDocumentEnd();

    // {IF "{MERGEFIELD bookmark}" = "true" "" ""}
    Field field = builder.InsertField("IF \"", null);
    builder.MoveTo(field.Start.NextSibling);
    builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
    builder.Write("\" = \"true\" ");
    builder.Write("\"");
    builder.Write("\"");
    builder.Write(" \"\"");

    Node currentNode = field.Start;
    bool flag = true;
    while (currentNode != null && flag)
    {
        if (currentNode.NodeType == NodeType.Run)
            if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
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

    doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });
}
```

### Explanation

- Bookmark bm: Fetches the bookmark from the document.
- DocumentBuilder builder: Helps in navigating and modifying the document.
- Field field: Inserts an IF field to check the condition of the bookmark.
- Node currentNode: Traverses through the nodes to find the field start and end.

## Step 3: Execute the Show/Hide Function

Now, you need to call the `ShowHideBookmarkedContent` method, passing the document, bookmark name, and the visibility flag:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

### Explanation

- doc: Your document object.
- "MyBookmark1": The name of the bookmark you want to show/hide.
- false: The visibility flag (true for showing, false for hiding).

## Step 4: Save Your Document

Finally, save the modified document:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### Explanation

- dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx": The path and name of the new document where changes will be saved.

## Conclusion

And there you have it! You’ve successfully learned how to show and hide bookmarks in a Word document using Aspose.Words for .NET. This technique can be incredibly useful for dynamically generating documents with conditional content.

## FAQ's

### What is Aspose.Words for .NET?
Aspose.Words for .NET is a powerful document processing library that allows developers to create, modify, and convert Word documents programmatically.

### How do I get Aspose.Words for .NET?
You can download Aspose.Words for .NET from [here](https://releases.aspose.com/words/net/). A free trial is also available.

### Can I use this method for other types of bookmarks?
Yes, this method can be adapted to manage visibility for any bookmarks in your Word document.

### What if my document does not contain the specified bookmark?
If the bookmark does not exist, the method will throw an error. Ensure the bookmark exists before attempting to show/hide it.

### How can I get support if I encounter issues?
You can get support from the Aspose community [here](https://forum.aspose.com/c/words/8).

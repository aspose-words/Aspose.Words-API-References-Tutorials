---
title: Document Builder Insert Bookmark
linktitle: Document Builder Insert Bookmark
second_title: Aspose.Words Document Processing API
description: Learn how to insert bookmarks in Word documents using DocumentBuilder in Aspose.Words for .NET. Step-by-step guide.
type: docs
weight: 10
url: /net/add-content-using-documentbuilder/document-builder-insert-bookmark/
---

In this comprehensive example, you will learn how to insert bookmarks into a Word document using the DocumentBuilder class in Aspose.Words for .NET. We will guide you through the process and provide you with the necessary C# code snippets. By the end of this guide, you will be able to create and manage bookmarks within your documents.

## Prerequisites
Before we begin, ensure that you have the following prerequisites:
- Aspose.Words for .NET library installed on your system.

## Step 1: Create a New Document and DocumentBuilder
To start, create a new document using the Document class and initialize a DocumentBuilder object:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Insert a Bookmark
Next, use the StartBookmark and EndBookmark methods of the DocumentBuilder class to insert a bookmark into the document. Provide a unique name for the bookmark as a parameter:

```csharp
builder.StartBookmark("FineBookmark");
builder.Writeln("This is just a fine bookmark.");
builder.EndBookmark("FineBookmark");
```

## Step 3: Save the Document
After inserting the bookmark, save the document to a file using the Save method of the Document class:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.DocumentBuilderInsertBookmark.docx");
```

### Example Source Code for DocumentBuilder Insert Bookmark using Aspose.Words for .NET
Here is the complete source code for inserting a bookmark using the DocumentBuilder class in Aspose.Words for .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartBookmark("FineBookmark");
builder.Writeln("This is just a fine bookmark.");
builder.EndBookmark("FineBookmark");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.DocumentBuilderInsertBookmark.docx");
```

## Conclusion
Congratulations! You have successfully learned how to insert bookmarks into a Word document using the DocumentBuilder class in Aspose.Words for .NET. By following the step-by-step guide and utilizing the provided source code, you can now create and manage bookmarks within your documents.

Bookmarks are useful for various scenarios, such as navigating through large documents, referencing specific sections, or programmatically manipulating content within bookmarked areas.

Remember to adjust the code according to your specific requirements and enhance it with additional functionality as needed.



---
title: Link
linktitle: Link
second_title: Aspose.Words for .NET API Reference
description: Learn how to insert links with Aspose.Words for .NET. Step-by-step guide.
type: docs
weight: 10
url: /net/working-with-markdown/link/
---

In this example, we will walk you through how to use the links feature with Aspose.Words for .NET. Links are used to create clickable references to websites or other documents.

## Step 1: Using a document generator

First, we'll use a document generator to add content to our document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Step 2: Inserting a link

We can insert a link using the `Insertlink` method of the document generator. We need to specify the link text, here "Aspose", as well as the destination URL.

```csharp
builder.Insertlink("Aspose", "https://www.aspose.com", false);
```

### Example source code for links with Aspose.Words for .NET


```csharp
// Use a document builder to add content to the document.
DocumentBuilder builder = new DocumentBuilder();

// Insert link.
builder.Insertlink("Aspose", "https://www.aspose.com", false);
```
Congratulation ! You have now learned how to use the links feature with Aspose.Words for .NET.



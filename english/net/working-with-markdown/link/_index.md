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


### FAQ's

#### Q: How can I link to a URL in Aspose.Words?

A: To link to a URL address in Aspose.Words, you can use the `<a>` tag with the `href` attribute containing the URL address. For example, you can use `<a href="https://www.aspose.com">Click Here</a>` to hyperlink to the URL "https://www.example.com " with the display text "Click here".

#### Q: Is it possible to link to an internal bookmark in Aspose.Words?

A: Yes, it is possible to link to an internal bookmark in Aspose.Words. You can use the `<a>` tag with the `href` attribute containing the name of the bookmark preceded by a hash (#). For example, `<a href="#bookmark1">Go to bookmark 1</a>` will link to the bookmark named "bookmark1" in the document.

#### Q: How can I customize the display text of a link in Aspose.Words?

A: To customize the display text of a link in Aspose.Words, you can modify the content between the `<a>` tags. For example, `<a href="https://www.aspose.com">Click here</a>` will display the text "Click here" as a hyperlink.

#### Q: Can I specify a target for a link in Aspose.Words?

A: Yes, you can specify a target for a link in Aspose.Words using the `target` attribute of the `<a>` tag. For example, `<a href="https://www.aspose.com" target="_blank">Open in new window</a>` will open the link in a new window or tab.

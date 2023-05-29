---
title: Move To Headers Footers
linktitle: Move To Headers Footers
second_title: Aspose.Words for .NET API Reference
description: Learn how to use Aspose.Words for .NET to navigate and modify headers and footers in Word documents with this step-by-step guide.
type: docs
weight: 10
url: /net/add-content-using-documentbuilder/move-to-headers-footers/
---

In this example, we will explore the Move To Headers Footers feature of Aspose.Words for .NET. Aspose.Words is a powerful document manipulation library that allows developers to create, modify, and convert Word documents programmatically. The Move To Headers/Footers feature enables us to navigate to different headers and footers within a document and add content to them.

Let's go through the source code step by step to understand how to use the Move To Headers/Footers feature using Aspose.Words for .NET.



## Step 1: Initializing the document and document builder

First, initialize the Document and DocumentBuilder objects:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Configuring headers and footers

Specify the header/footer settings for the document. In this example, we set the headers and footers to be different for the first page and for odd/even pages:

```csharp
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;
```

## Step 3: Creating headers for different pages

Move to each header type and add content to them. In this example, we create headers for the first page, even pages, and all other pages:

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");
```

## Step 4: Creating pages in the document
Add content to the document to create multiple pages. For example:

```csharp
// Create two pages in the document.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
```
## Step 5: Saving the document

Save the modified document to a desired location:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

Make sure to specify the appropriate file path and format (e.g., DOCX).

### Example source code for Move To Headers/Footers using Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Specify that we want headers and footers different for first, even and odd pages.
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

// Create the headers.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

// Create two pages in the document.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```


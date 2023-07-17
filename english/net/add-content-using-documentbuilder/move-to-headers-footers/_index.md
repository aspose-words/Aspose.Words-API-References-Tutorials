---
title: Move To Headers Footers In Word Document
linktitle: Move To Headers Footers In Word Document
second_title: Aspose.Words Document Processing API
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

## Conclusion

In this example, we explored the Move To Headers/Footers feature of Aspose.Words for .NET. We learned how to navigate to different headers and footers within a Word document and add content to them using the DocumentBuilder class. This feature allows developers to customize headers and footers for specific pages or sections, providing flexibility in creating professional and structured documents. Aspose.Words for .NET provides a powerful set of tools for programmatically manipulating Word documents, making it an essential library for document processing applications.

### FAQ's for move to headers footers in word document

#### Q: What is the purpose of the Move To Headers/Footers feature in Aspose.Words for .NET?

A: The Move To Headers/Footers feature in Aspose.Words for .NET allows developers to navigate to different headers and footers within a Word document and add content to them programmatically. It is useful when you need to customize headers and footers for different pages or sections in the document.

#### Q: Can I have different headers and footers for different pages in the document?

A: Yes, you can specify different headers and footers for the first page, even pages, and odd pages using the PageSetup.DifferentFirstPageHeaderFooter and PageSetup.OddAndEvenPagesHeaderFooter properties, respectively.

#### Q: How can I add content to specific headers and footers?

A: To add content to specific headers and footers, use the MoveToHeaderFooter method of the DocumentBuilder class. You can move to the HeaderFirst, HeaderEven, and HeaderPrimary headers or the FooterFirst, FooterEven, and FooterPrimary footers based on your requirement.

#### Q: Can I create headers and footers for a specific section in the document?

A: Yes, you can use the MoveToSection method of the DocumentBuilder class to move to a specific section in the document and then create headers and footers within that section.

#### Q: How can I save the modified document to a file using Aspose.Words for .NET?

A: You can save the modified document to a desired location and format using the Save method of the Document class. Make sure to specify the appropriate file path and file format (e.g., DOCX).

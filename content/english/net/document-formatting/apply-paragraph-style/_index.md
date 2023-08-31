---
title: Apply Paragraph Style In Word Document
linktitle: Apply Paragraph Style In Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to apply a paragraph style in word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/document-formatting/apply-paragraph-style/
---
In this tutorial, we will walk you through how to apply a paragraph style using Aspose.Words for .NET. Follow the steps below to understand the source code and apply the paragraph style.

## Step 1: Creating and configuring the document

To begin, create a new document and an associated DocumentBuilder object. Here's how:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Configuring the paragraph style

We will now configure the paragraph style using the built-in style identifier. Here's how:

```csharp
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
```

## Step 3: Add content

We are going to add content to the paragraph. Here's how:

```csharp
builder.Write("Hello");
doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
```

### Example source code for Apply Paragraph Style using Aspose.Words for .NET

Here is the complete source code for the Apply Paragraph Style feature with Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
	builder.Write("Hello");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
	
```

With this code you will be able to apply a paragraph style using Aspose.Words for .NET.

## Conclusion

In this tutorial, we explored how to apply a paragraph style in a Word document using Aspose.Words for .NET. By setting the `StyleIdentifier` property of the `ParagraphFormat`, we were able to apply a built-in style to the paragraph. Aspose.Words for .NET provides a wide range of formatting options, including the ability to create and apply custom styles, allowing you to achieve professional-looking documents with ease.

### FAQ's

#### Q: How do I apply a paragraph style in a Word document using Aspose.Words for .NET?

A: To apply a paragraph style in a Word document using Aspose.Words for .NET, follow these steps:
1. Create a new document and a `DocumentBuilder` object.
2. Configure the paragraph style by setting the `StyleIdentifier` property of the `ParagraphFormat` to the desired style identifier (e.g., `StyleIdentifier.Title`, `StyleIdentifier.Heading1`, etc.).
3. Add content to the paragraph using the `Write` method of the `DocumentBuilder`.
4. Save the document using the `Save` method.

#### Q: What are style identifiers in Aspose.Words for .NET?

A: Style identifiers in Aspose.Words for .NET are predefined constants that represent built-in paragraph styles. Each style identifier corresponds to a specific style such as "Title," "Heading1," "Heading2," etc. By setting the `StyleIdentifier` property of the `ParagraphFormat`, you can apply the corresponding style to the paragraph.

#### Q: Can I create and apply custom paragraph styles using Aspose.Words for .NET?

A: Yes, using Aspose.Words for .NET, you can create and apply custom paragraph styles. You can define your own styles with specific formatting properties such as font, alignment, indentation, etc., and apply them to paragraphs in your document. This allows you to achieve consistent and customized formatting throughout your document.

---
title: Move To Paragraph
linktitle: Move To Paragraph
second_title: Aspose.Words for .NET API Reference
description: Learn how to use Aspose.Words for .NET's Move To Paragraph feature to navigate and manipulate paragraphs in Word documents programmatically.
type: docs
weight: 10
url: /net/add-content-using-documentbuilder/move-to-paragraph/
---

In this step-by-step example, we will explore the Move To Paragraph feature of Aspose.Words for .NET. This feature allows developers to navigate and manipulate paragraphs within a Word document programmatically. By following this guide, you will learn how to implement and utilize the Move To Paragraph feature effectively.

The above code demonstrates the usage of the Move To Paragraph feature. Let's understand each step in detail:

## Step 1: Loading the Document

We start by loading the Word document into an instance of the `Document` class. The `MyDir` variable represents the directory path where the document is located. You should replace it with the actual directory path or modify the code accordingly.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");
```

## Step 2: Initializing the DocumentBuilder

Next, we create a `DocumentBuilder` object and associate it with the loaded document. The `DocumentBuilder` class provides various methods and properties to manipulate the document's content.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 3: Moving to a Specific Paragraph

The `MoveToParagraph` method is used to position the document builder at a specific paragraph within the document. It takes two parameters: the index of the target paragraph and the character position within that paragraph (0 represents the start of the paragraph).

In the provided example, we are moving to the third paragraph (index 2) of the document:

```csharp
builder.MoveToParagraph(2, 0);
```

## Step 4: Modifying the Paragraph Content

Once the builder is positioned at the desired paragraph, we can use the `Writeln` method to add or modify the content of that paragraph. In this case, we are adding the text "This is the 3rd paragraph."

```csharp
builder.Writeln("This is the 3rd paragraph.");
```

### Example Source Code for Move To Paragraph using Aspose.Words for .NET

Below is the complete example source code for implementing the Move To Paragraph feature using Aspose.Words for .NET:

```csharp

	Document doc = new Document(MyDir + "Paragraphs.docx");
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.MoveToParagraph(2, 0);
	builder.Writeln("This is the 3rd paragraph.");
	
```

By following this guide and utilizing the Move To Paragraph feature, you can programmatically manipulate paragraphs within Word documents using Aspose.Words for .NET.



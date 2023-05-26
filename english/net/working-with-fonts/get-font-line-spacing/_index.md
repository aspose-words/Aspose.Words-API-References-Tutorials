---
title: Get Font Line Spacing
linktitle: Get Font Line Spacing
second_title: Aspose.Words for .NET API Reference
description: In this tutorial, learn how to get font line spacing in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fonts/get-font-line-spacing/
---
In this tutorial, we are going to tell you how to get the font line spacing in a Word document using the Aspose.Words library for .NET. The font line spacing defines the vertical space between lines of text. We'll take you step-by-step to help you understand and implement the code in your .NET project.

## Prerequisites
Before you begin, make sure you have the following items:
- A working knowledge of the C# programming language
- The Aspose.Words library for .NET installed in your project

## Step 1: Create a new document and document generator
First, we will create a new document by instantiating the `Document` class and a document builder by instantiating the `DocumentBuilder` class.

```csharp
// Create a new document
Document doc = new Document();

// Create a document generator
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Configure the font
Next, we will configure the font by setting the `Name` property of the document generator.

```csharp
// Configure the font
builder.Font.Name = "Calibri";
```

## Step 3: Add text to the document
We will now use the document generator to add formatted text to the document.

```csharp
// Add text to the document
builder. Writen("qText");
```

## Step 4: Get Font Line Spacing
Now we will access the `Font` object of the first paragraph of the document and retrieve the value of the `LineSpacing` property.

```csharp
// Get the line spacing of the font
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

### Sample source code for Get Font Line Spacing using Aspose.Words for .NET 
```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Calibri";
builder.Writeln("qText");
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## Conclusion
In this tutorial, we saw how to get the font line spacing in a Word document with Aspose.Words for .NET. Font line spacing is important for controlling the vertical spacing between lines of text. Feel free to use this feature to customize the appearance of your text in your documents.


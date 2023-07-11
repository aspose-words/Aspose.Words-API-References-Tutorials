---
title: Get Font Line Spacing
linktitle: Get Font Line Spacing
second_title: Aspose.Words Document Processing API
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

### FAQ's

#### Q: How can I change the line spacing of specific text in a Word document?

A: With Aspose.Words, you can easily change the line spacing of specific text in a Word document. Use the API to select the desired text and adjust the spacing between lines by specifying the appropriate value.

#### Q: Is it possible to apply exact spacing between lines in a Word document?

A: Yes, Aspose.Words allows you to apply exact spacing between lines in a Word document. You can specify a precise value for line spacing using the API.

#### Q: How can I adjust the line spacing for the whole Word document?

A: With Aspose.Words, you can easily adjust line spacing for the entire Word document. Use the methods provided by the API to specify the desired line spacing for the entire document.

#### Q: Does Aspose.Words support multiple line spacing?

A: Yes, Aspose.Words supports multiple line spacing in Word documents. You can set multiple spacing, such as 1.5 times or 2 times normal spacing, for the lines of your text.

#### Q: How can I avoid line overlapping issues when adjusting line spacing?

A: To avoid line overlapping issues when adjusting the spacing between lines, be sure to choose appropriate spacing values. Also test the final rendering of your document to ensure that the text remains readable and well formatted.

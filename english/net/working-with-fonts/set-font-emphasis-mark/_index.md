---
title: Set Font Emphasis Mark
linktitle: Set Font Emphasis Mark
second_title: Aspose.Words for .NET API Reference
description: Learn how to set the font emphasis style in a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fonts/set-font-emphasis-mark/
---

In this tutorial, we will show you how to set the font emphasis style in a Word document using Aspose.Words for .NET. Font emphasis is used to highlight certain words or phrases in text.

## Prerequisites
Before you begin, make sure you have the following items:
- A working knowledge of the C# programming language
- The Aspose.Words library for .NET installed in your project

## Step 1: Define the document directory
Start by setting the directory path to the location of your Word document. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Create and customize the document
Create an instance of the `Document` class and an associated `DocumentBuilder` to build the document content. Use the `Font.EmphasisMark` property to set the font emphasis style to `EmphasisMark.UnderSolidCircle`. Then use the `Write` and `Writeln` methods of the `DocumentBuilder` to add text with the specified font emphasis.

```csharp
Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasized text");
builder. Writen();
builder.Font.ClearFormatting();
builder.Write("Simple text");
```

## Step 3: Save the document
Save the document using the `Save` method of the `Document` with the appropriate path and filename.

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### Sample source code for Set Font Emphasis Mark using Aspose.Words for .NET 

```csharp
// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## Conclusion
In this tutorial, you learned how to set the font emphasis style in a Word document using Aspose.Words for .NET. Experiment with different styles of emphasis and use this feature to highlight words or phrases in your documents.


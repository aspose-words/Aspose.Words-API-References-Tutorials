---
title: Set Font Formatting
linktitle: Set Font Formatting
second_title: Aspose.Words for .NET API Reference
description: Learn how to set font formatting in Word document using Aspose.Words for .NET and create attractive documents.
type: docs
weight: 10
url: /net/working-with-fonts/set-font-formatting/
---
In this tutorial, we will show you how to set font formatting in a Word document using Aspose.Words for .NET. You will learn how to apply styles such as bold, color, italics, font, size, spacing, and underlining.

## Prerequisites
Before you begin, make sure you have the following items:
- A working knowledge of the C# programming language
- The Aspose.Words library for .NET installed in your project

## Step 1: Define the document directory
Start by setting the directory path to the location of your Word document. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Create and format the document
Create an instance of the `Document` class and the `DocumentBuilder` class to build the document. Use the `Font` property of the `DocumentBuilder` to access font formatting properties.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font. Bold = true;
font.Color = Color.DarkBlue;
font. Italic = true;
font.Name = "Arial";
font.Size = 24;
font. Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nicely formatted string.");
```

## Step 3: Save the document
Use the `Save` method to save the document with the font formatting applied. Replace `"WorkingWithFonts.SetFontFormatting.docx"` with the desired filename.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");
```

### Sample source code for Set Font Formatting using Aspose.Words for .NET 
```csharp

// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font.Bold = true;
font.Color = Color.DarkBlue;
font.Italic = true;
font.Name = "Arial";
font.Size = 24;
font.Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nice formatted string.");
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");

```

## Conclusion
Congratulation ! You now know how to set font formatting in a Word document using Aspose.Words for .NET. You can explore more font formatting options and create personalized and attractive Word documents.

### FAQ's

#### Q: How can I apply the bold style to a font in a Word document using Aspose.Words?

A: To apply the bold style to a font in a Word document using Aspose.Words, you can use the API to navigate to the desired font and set its style to "bold". This will apply the bold style to the specified font.

#### Q: Is it possible to apply italic style to a specific part of text in a Word document with Aspose.Words?

A: Yes, with Aspose.Words you can apply the italic style to a specific part of text in a Word document. You can use the API to select the desired text range and set its style to "italic".

#### Q: How can I change the font color in a Word document using Aspose.Words?

A: To change the font color in a Word document using Aspose.Words, you can access the desired font using the API and set its color to the desired color. This will change the font color in the document.

#### Q: Is it possible to change the font size in a Word document using Aspose.Words?

A: Yes, you can change the font size in a Word document using Aspose.Words. The API lets you access the font and set its size in points or scale points, depending on your needs.

#### Q: Can I apply multiple font formats, such as bold and italic, to the same text in a Word document?

A: Yes, with Aspose.Words you can apply multiple font formats, such as bold and italic, to the same text in a Word document. You can use the API to set the different font styles you want for different parts of the text.

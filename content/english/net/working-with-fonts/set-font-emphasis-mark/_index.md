---
title: Set Font Emphasis Mark
linktitle: Set Font Emphasis Mark
second_title: Aspose.Words Document Processing API
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

### FAQ's

#### Q: How can I add accent marks to a specific font in a Word document using Aspose.Words?

A: To add accent marks to a specific font in a Word document using Aspose.Words, you can use the API to navigate to the desired font and apply the appropriate accent marks. This will add accent marks to the text with the selected font.

#### Q: Is it possible to change the style of accent marks in a Word document with Aspose.Words?

A: Yes, with Aspose.Words you can change the style of accent marks in a Word document. The API allows you to adjust style properties such as color, size, linetype, etc., to customize the appearance of accent marks.

#### Q: How can I remove all accent marks from a Word document using Aspose.Words?

A: To remove all accent marks from a Word document using Aspose.Words, you can use the API to browse the document, detect existing accent marks and remove them using the appropriate methods. This will remove all emphasis marks from the document.

#### Q: Can I add accent marks to a specific part of text in a Word document?

A: Yes, you can add accent marks to a specific part of text in a Word document using Aspose.Words. You can select the desired range of text using the API and add appropriate emphasis marks to that part of the text.

#### Q: Can the accent marks be customized to my needs?

A: Yes, accent marks can be customized to your needs using Aspose.Words. You can adjust the style properties of accent marks, such as color, size, linetype, and more, to match your formatting preferences.

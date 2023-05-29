---
title: Setext Heading
linktitle: Setext Heading
second_title: Aspose.Words for .NET API Reference
description: Learn how to use Setext headings to format your documents with Aspose.Words for .NET Step-by-step guide.
type: docs
weight: 10
url: /net/working-with-markdown/setext-heading/
---

In this tutorial, we will walk you through how to use the Setext Heading feature with Aspose.Words for .NET. Setext Heading are an alternative method of formatting titles in Markdown documents.

## Step 1: Using a document generator

First, we'll use a document generator to add content to our document.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## Step 2: Using the Setext heading style

We are going to use the default "Heading 1" paragraph style to create a level 1 heading in our document.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## Step 3: Resetting Styles

We reset previously applied font styles to avoid any unwanted combination of styles between paragraphs.

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## Step 4: Customizing Setext Heading Levels

We can customize Setext heading levels by adding new paragraph styles based on existing heading styles. In this example, we are creating a "SetextHeading1" style based on the "Heading 1" style to represent a level 1 heading in the Setext format.

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## Step 5: Saving the document

Finally, we can save the document in the desired format.

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### Example source code for Setext titles with Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Use a document builder to add content to the document.
DocumentBuilder builder = new DocumentBuilder();

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");

// Reset styles from the previous paragraph to not combine styles between paragraphs.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Setext Heading level 1");

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
builder.Writeln("This is an H3 tag");

// Reset styles from the previous paragraph to not combine styles between paragraphs.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
builder.ParagraphFormat.Style = setexHeading2;
builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

// Setex heading level will be reset to 2 if the base paragraph has a Heading level greater than 2.
builder.Writeln("Setext Heading level 2");


builder.Document.Save(dataDir + "Test.md");
```





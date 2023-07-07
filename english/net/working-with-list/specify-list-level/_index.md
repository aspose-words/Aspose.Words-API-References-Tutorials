---
title: Specify List Level
linktitle: Specify List Level
second_title: Aspose.Words for .NET API Reference
description: Learn how to specify the list level in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-list/specify-list-level/
---

In this step-by-step tutorial, we will show you how to specify the list level in a Word document using Aspose.Words for .NET. We'll explain the provided C# source code and show you how to implement it in your own projects.

To get started, make sure you have Aspose.Words for .NET installed and configured in your development environment. If you haven't already, download and install the library from the official site.

## Step 1: Creating the Document and Document Generator

First, create a new document and an associated document generator:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Creating and Applying a Numbered List

Next, create a numbered list based on one of Microsoft Word's list templates and apply it to the current paragraph in the document builder:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## Step 3: List Level Specification

Use the document builder's `ListLevelNumber` property to specify the list level and add text to the paragraph:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

Repeat these steps to specify list levels and add text at each level.

## Step 4: Creating and Applying a Bulleted List

You can also create and apply a bulleted list using one of Microsoft Word's list templates:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## Step 5: Adding Text to Bulleted List Levels

Use the `ListLevelNumber` property again to specify the bulleted list level and add text:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## Step 6: Stop Formatting List

To stop list formatting, set `null` to the `List` property of the document generator:

```csharp
builder. ListFormat. List = null;
```

## Step 7: Saving the modified document

Save the modified document:

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

So ! You have successfully specified the list level in a Word document using Aspose.Words for .NET.

### Sample source code to specify list level

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Create a numbered list based on one of the Microsoft Word list templates
// and apply it to the document builder's current paragraph.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

// There are nine levels in this list, let's try them all.
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Create a bulleted list based on one of the Microsoft Word list templates
// and apply it to the document builder's current paragraph.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);

for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// This is a way to stop list formatting.
builder.ListFormat.List = null;

builder.Document.Save(dataDir + "WorkingWithList.SpecifyListLevel.docx");
            
```

### FAQ's

#### Q: How can I specify list level in Aspose.Words?

A: To specify the list level in Aspose.Words, you need to create an instance of the `List` class and give it a numbered list. Then you can use the `Paragraph.ListFormat.ListLevelNumber` property to specify the level of each list item. You can associate this list with a section of your document so that the list items have the desired level.

#### Q: Is it possible to change the numbering format of list items in Aspose.Words?

A: Yes, you can change the numbering format of list items in Aspose.Words. The `ListLevel` class offers several properties for this, such as `ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`, etc. You can use these properties to set the numbering format for list items, such as Arabic numerals, Roman numerals, letters, etc.

#### Q: Can I add additional levels to a numbered list in Aspose.Words?

A: Yes, it is possible to add additional levels to a numbered list in Aspose.Words. The `ListLevel` class allows you to set formatting properties for each level of the list. You can set options like prefix, suffix, alignment, indent, etc. This allows you to create lists with multiple levels of hierarchy.




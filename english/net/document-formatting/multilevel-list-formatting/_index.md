---
title: Multilevel List Formatting
linktitle: Multilevel List Formatting
second_title: Aspose.Words Document Processing API
description: Learn how to create a multilevel list and apply custom formatting with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/document-formatting/multilevel-list-formatting/
---

In this tutorial, we are going to show you how to use the multilevel list formatting feature with Aspose.Words for .NET. Follow the steps below to understand the source code and apply the changes.

## Step 1: Creating and configuring the document

To begin, create a new document and an associated DocumentBuilder object. Here's how:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Formatting the multilevel list

We will now apply the multilevel list formatting using the methods available in the DocumentBuilder object. Here's how:

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## Step 3: Saving the document

After inserting the text input form field, save the document to the desired location using the `Save` method. Make sure to provide the appropriate file path:

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### Example source code for Multilevel List Formatting using Aspose.Words for .NET

Here is the complete source code for the multilevel list formatting feature with Aspose.Words for .NET:


```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ListFormat.ApplyNumberDefault();
	builder.Writeln("Item 1");
	builder.Writeln("Item 2");

	builder.ListFormat.ListIndent();
	builder.Writeln("Item 2.1");
	builder.Writeln("Item 2.2");
	
	builder.ListFormat.ListIndent();
	builder.Writeln("Item 2.2.1");
	builder.Writeln("Item 2.2.2");

	builder.ListFormat.ListOutdent();
	builder.Writeln("Item 2.3");

	builder.ListFormat.ListOutdent();
	builder.Writeln("Item 3");

	builder.ListFormat.RemoveNumbers();
	
	doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

With this code you will be able to create a multi-level list and apply proper formatting to each level using Aspose.Words for .NET.

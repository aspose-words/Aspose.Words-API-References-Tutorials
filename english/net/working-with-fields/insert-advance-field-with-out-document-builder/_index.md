---
title: Insert Advance Field Without Document Builder
linktitle: Insert Advance Field Without Document Builder
second_title: Aspose.Words for .NET API Reference
description: Learn how to insert an advanced field into your Word documents with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fields/insert-advance-field-with-out-document-builder/
---

Here is a step-by-step guide to explain the C# source code below, which uses the "Advanced Field Insertion without DocumentBuilder" feature of Aspose.Words for .NET. Make sure to follow each step carefully to get the desired results.

## Step 1: Document Directory Setup

In the code provided, you must specify the directory of your documents. Replace the value "YOUR DOCUMENT DIRECTORY" with the appropriate path to your documents directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Creating the Document and Paragraph

We start by creating a new document and fetching the first paragraph.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Step 3: Inserting the advanced field

We use the `AppendField()` method to insert an advanced field into the paragraph.

```csharp
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);
```

We then configure the various properties of the advanced field by specifying the desired values.

```csharp
field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";
```

Finally, we call the `Update()` method to update the field.

```csharp
field. Update();
```

### Example of the source code for inserting an advanced field without DocumentBuilder with Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Document creation.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Insert the advanced field.
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);

field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";

field. Update();

doc.Save(dataDir + "InsertionFieldAdvanceWithoutDocumentBuilder.docx");
```

In this example, we created a new document, inserted an advanced field without using DocumentBuilder, configured the various field properties, and saved the document with a specified filename.

This concludes our guide on how to use the "Insert Advanced Field Without DocumentBuilder" feature with Aspose.Words for .NET.



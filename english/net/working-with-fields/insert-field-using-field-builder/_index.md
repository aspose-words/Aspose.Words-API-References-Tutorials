---
title: Insert Field Using Field Builder
linktitle: Insert Field Using Field Builder
second_title: Aspose.Words for .NET API Reference
description: Learn how to Insert custom fields into your Word documents with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fields/insert-field-using-field-builder/
---

Here is a step-by-step guide to explain the C# source code below, which uses the "Insert a Field using FieldBuilder" feature of Aspose.Words for .NET. Make sure to follow each step carefully to get the desired results.

## Step 1: Document Directory Setup

In the code provided, you must specify the directory of your documents. Replace the value "YOUR DOCUMENT DIRECTORY" with the appropriate path to your documents directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Creating the document

We start by creating a new document.

```csharp
Document doc = new Document();
```

## Step 3: Building the IF field using FieldBuilder

We use the FieldBuilder class to construct an IF field with two nested MERGEFIELD fields. In this example, the IF field displays first and last name based on a condition.

```csharp
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));
```

## Step 4: Inserting the IF field into the document

We use the `BuildAndInsert()` method to build and insert the IF field at a specific location in the document.

```csharp
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();
```

### Example source code for inserting a field using FieldBuilder with Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Document creation.
Document doc = new Document();

// Construction of the IF field using FieldBuilder.
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));

// Insert the IF field into the document.
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

In this example, we created a new document, constructed an IF field with nested MERGEFIELD fields, and then inserted that field into the document at a specified location. The document is then saved with a specific file name.


---
title: Insert Merge Field Using DOM
linktitle: Insert Merge Field Using DOM
second_title: Aspose.Words for .NET API Reference
description: Learn how to insert custom field merge fields into your Word documents with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fields/insert-merge-field-using-dom/
---

Here is a step by step guide to explain the C# source code below which uses the "Insert Field Merge Field" feature of Aspose.Words for .NET. Make sure to follow each step carefully to get the desired results.

## Step 1: Document Directory Setup

In the code provided, you must specify the directory of your documents. Replace the value "YOUR DOCUMENT DIRECTORY" with the appropriate path to your documents directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Creating the Document and DocumentBuilder

We start by creating a new document and initializing a DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 3: Moving cursor to paragraph

We use the `MoveTo()` method of the DocumentBuilder to move the cursor to the paragraph where we want to insert the field merge field.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Step 4: Inserting the field merge field

We use the DocumentBuilder's `InsertField()` method to insert a field merge field into the paragraph.

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

We then configure the field merge field properties by specifying the appropriate options, such as the field name, text before and after the field, and vertical formatting options.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

Finally, we call the `Update()` method to update the field.

```csharp
field. Update();
```

### Sample source code for inserting a field merge field with Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Create the document and the DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Move cursor to paragraph.
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

// Insert field merge field.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

// Update the field.
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

In this example, we created a new document, moved the cursor to the desired paragraph, and then inserted a field merge field into the document.
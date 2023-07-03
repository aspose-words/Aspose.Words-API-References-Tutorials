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

### FAQ's

#### Q: How can I insert a merge field in a Word document using Aspose.Words for .NET with the DOM?

A: To insert a merge field in a Word document using Aspose.Words for .NET with DOM, you can follow these steps:

1. Navigate to the paragraph where you want to insert the merge field.
2. Create a `FieldMergeField` object.
3. Set the merge field properties, such as field name and formatting options.
4. Add the merge field to the paragraph using the `Paragraph.AppendChild` method.

#### Q: How can I specify source data for merge field in Aspose.Words for .NET?

A: To specify the source data for the merge field in Aspose.Words for .NET, you can use the `FieldMergeField.FieldName` method to set the merge field name, which is the name of a field in a data source external such as a CSV file, database, etc. You can also use the `FieldMergeField.Text` method to set the merge field value directly.

#### Q: Can I customize the appearance of the merge field in a Word document with Aspose.Words for .NET?

A: Yes, you can customize the appearance of the merge field in a Word document with Aspose.Words for .NET. You can set the formatting options like case, font, color, etc. using the properties of the `FieldMergeField` object.

#### Q: How can I check if a merge field was successfully inserted in a Word document with Aspose.Words for .NET?

A: To check if a merge field was inserted successfully, you can browse the document content and search for merge field instances. You can use the methods and properties of the `Document` object to access paragraphs, fields, and other elements of the document.

#### Q: Does inserting a merge field using DOM affect Word document structure with Aspose.Words for .NET?

A: Inserting a merge field using the DOM does not directly affect the structure of the Word document. However, it adds a new field element to the document content. You can manipulate the document structure by adding, deleting or modifying the existing elements according to your needs.

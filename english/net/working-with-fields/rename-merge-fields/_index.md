---
title: Rename Merge Fields
linktitle: Rename Merge Fields
second_title: Aspose.Words for .NET API Reference
description: In this tutorial, you will learn how to rename merge fields in a document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fields/rename-merge-fields/
---

Here is a step by step guide to explain the C# source code below which uses the merge field renaming feature of Aspose.Words for .NET. Follow each step carefully to get the desired results.

## Step 1: Document Directory Setup

In the code provided, you must specify the directory of your documents. Replace the value "YOUR DOCUMENT DIRECTORY" with the appropriate path to your documents directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Creating the document and inserting the merge fields

We start by creating a new document and using a `DocumentBuilder` to insert the merge fields.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## Step 3: Renaming Merge Fields

We loop through each field in the document range, and if it's a merge field, we rename the field by adding the "_Renamed" suffix.

```csharp
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}
```

## Step 4: Saving the document

Finally, we call the `Save()` method to save the modified document.

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### Source code example for renaming merge fields with Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Create the document and insert the merge fields.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");

// Rename merge fields.
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}

// Save the document.
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

Follow these steps to rename merge fields in your document using Aspose.Words for .NET.

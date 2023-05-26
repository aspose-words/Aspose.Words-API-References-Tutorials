---
title: Remove Field
linktitle: Remove Field
second_title: Aspose.Words for .NET API Reference
description: In this guide, you will learn how to delete a specific field in a document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fields/remove-field/
---
Here is a step-by-step guide to explain the C# source code below, which uses the "Field Removal" functionality of Aspose.Words for .NET. Follow each step carefully to get the desired results.

## Step 1: Document Directory Setup

In the code provided, you must specify the directory of your documents. Replace the value "YOUR DOCUMENT DIRECTORY" with the appropriate path to your documents directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Loading the document

We start by loading the existing document from the specified file.

```csharp
Document doc = new Document(dataDir + "Various fields.docx");
```

## Step 3: Deleting the field

We select the first field in the document range and use the `Remove()` method to remove it.

```csharp
Field field = doc.Range.Fields[0];
field. Remove();
```

## Step 4: Saving the document

Finally, we call the `Save()` method to save the modified document.

```csharp
doc.Save(dataDir + "WorkingWithFields.RemoveField.docx");
```

### Example source code for field deletion with Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the document.
Document doc = new Document(dataDir + "Various fields.docx");

// Selection of the field to delete.
Field field = doc.Range.Fields[0];
field. Remove();

// Save the document.
doc.Save(dataDir + "WorkingWithFields.RemoveField.docx");
```

Follow these steps to delete a specific field in your document using Aspose.Words for .NET.


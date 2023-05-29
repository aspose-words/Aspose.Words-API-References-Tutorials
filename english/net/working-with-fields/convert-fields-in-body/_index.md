---
title: Convert Fields In Body
linktitle: Convert Fields In Body
second_title: Aspose.Words for .NET API Reference
description: Learn how to use Aspose.Words for .NET to convert Page fields to text in the body of a Word document.
type: docs
weight: 10
url: /net/working-with-fields/convert-fields-in-body/
---

In this step-by-step tutorial, we will walk you through how to use the ConvertFieldsInBody feature of Aspose.Words for .NET using the provided C# source code. This feature allows you to convert specific fields in the body of your document to plain text, making your documents easier to process. Follow the steps below to use this feature effectively.

## Step 1: Prerequisites

Before you start, make sure you have installed Aspose.Words for .NET and have a document ready to process. Also make sure you have the directory path to your documents.

## Step 2: Load the document

Start by declaring a variable for the path to your documents directory, then use that variable to initialize a Document object from the specified document. In our example, the document is called "Linked fields.docx".

```csharp
// The path to your documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the document
Document doc = new Document(dataDir + "Linked fields.docx");
```

## Step 3: Convert Page Fields to Plain Text

Now that the document is loaded, we can move on to the conversion steps. To convert the page fields to plain text in the body of the first section, you can use the `Range.Fields` method to get all fields in the specified range, and then filter out fields of type `FieldType.FieldPage`. Then you can use the `ForEach` method to loop through each field and call the `Unlink()` method to convert it to plain text.

```csharp
// Pass the appropriate parameters to convert the page fields to plain text in the body of the first section.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.Unlink());
```

## Step 4: Save the modified document

Once you have converted the page fields to plain text, you can save the modified document using the `Save()` method and specifying the path and name of the output file. In our example, we save it as "WorkingWithFields.ConvertFieldsInBody.docx".

```csharp
// Save the modified document
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### Example source code for converting fields in body with Aspose.Words for .NET

Here is the full source code example for converting fields into the body using Aspose.Words for .NET:

```csharp
// The path to your documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the document
Document doc = new Document(dataDir + "Linked fields.docx");

// Pass the appropriate parameters to convert the page fields to plain text in the body of the first section.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.A
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```
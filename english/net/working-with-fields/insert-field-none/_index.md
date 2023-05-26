---
title: Insert Field None
linktitle: Insert Field None
second_title: Aspose.Words for .NET API Reference
description: Learn how to Insérez un champ AUCUN dans vos documents Word avec Aspose.Words pour .NET. 
type: docs
weight: 10
url: /net/working-with-fields/insert-field-none/
---

Here is a step-by-step guide to explain the C# source code below, which uses the "Insert NONE Field" feature of Aspose.Words for .NET. Make sure to follow each step carefully to get the desired results.

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

## Step 3: Inserting the NONE field

We use the `InsertField()` method of the DocumentBuilder to insert a NONE field into the document.

```csharp
FieldUnknown field = (FieldUnknown)builder.InsertField(FieldType.FieldNone, false);
```

### Source code example for inserting a NONE field with Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Create the document and the DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insert the NONE field.
FieldUnknown field = (FieldUnknown)builder.InsertField(FieldType.FieldNone, false);

doc.Save(dataDir + "InsertionFieldNone.docx");
```

In this example, we've created a new document, initialized a DocumentBuilder, and then inserted a NONE field. The document is then saved with a specified file name.

This concludes our guide on using the "Insert NONE Field" feature with Aspose.Words for .NET.

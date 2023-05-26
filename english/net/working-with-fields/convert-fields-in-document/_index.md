---
title: Convert Fields In Document
linktitle: Convert Fields In Document
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to convert document fields to text using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fields/convert-fields-in-document/
---

In this tutorial, We will guide you step by step guide using ConvertFieldsInDocument function of Aspose.Words for .NET software. We'll explain in detail the C# source code needed for this feature and provide sample markdown output formats.

## Step 1: Prerequisites
Before you begin, make sure you have the following:

- Aspose.Words for .NET installed on your development machine.
- A Word document containing linked fields that you want to convert to text.
- A document directory where you can save the transformed document.

## Step 2: Setting up the environment
Make sure you have properly configured your development environment to use Aspose.Words for .NET. Import the necessary namespaces and set the path to your documents directory.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 3: Load the document
Use the `Document` class of Aspose.Words to load the Word document containing the linked fields you want to convert.

```csharp
Document doc = new Document(MyDir + "Linked fields.docx");
```

## Step 4: Convert bound fields to text
Use the `Unlink()` method to convert all "IF" type fields encountered in the document to text. This method is used to transform linked fields into their textual content.

```csharp
doc.Range.Fields.Where(f => f.Type == FieldType.FieldIf).ToList().ForEach(f => f.Unlink());
```

## Step 5: Save the transformed document
Use the `Save()` method to save the document with the fields converted to text in the specified document directory.

```csharp
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInDocument.docx");
```

## Sample source code for ConvertFieldsInDocument using Aspose.Words for .NET

Here is the complete source code for the ConvertFieldsInDocument function:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(MyDir + "Linked fields.docx");

// Pass the appropriate parameters to convert all IF fields encountered in the document (including headers and footers) to text.
doc.Range.Fields.Where(f => f.Type == FieldType.FieldIf).ToList().ForEach(f => f.Unlink());

// Save the document with fields transformed to disk
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInDocument.docx");
```

## Conclusion
Aspose.Words for .NET's ConvertFieldsInDocument function is a powerful tool for converting linked fields in a Word document to text. 

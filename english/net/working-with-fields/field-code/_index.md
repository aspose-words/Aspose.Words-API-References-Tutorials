---
title: Field Code
linktitle: Field Code
second_title: Aspose.Words for .NET API Reference
description: Step by step guide to get field code and field result in your Word documents with Aspose.Words for .NET.  
type: docs
weight: 10
url: /net/working-with-fields/field-code/
---

Here is a step-by-step guide to explain the C# source code below, which uses the "Get Field Code" feature of Aspose.Words for .NET. Make sure to follow each step carefully to get the desired results.

## Step 1: Document Directory Setup

In the code provided, you must specify the directory of your documents. Replace the value "YOUR DOCUMENT DIRECTORY" with the appropriate path to your documents directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Loading the document

The first step is to upload the document where you want to get the field codes.

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

Be sure to replace "Hyperlinks.docx" with the name of your own file.

## Step 3: Browse Document Fields

We use a `foreach` loop to loop through all the fields present in the document.

```csharp
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;
}
```

On each iteration of the loop, we get the field code using the `GetFieldCode()` method. We also store the result of the field in a variable.

### Source Code Example for Get Field Code with Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the document.
Document doc = new Document(dataDir + "Hyperlinks.docx");

// Loop through document fields.
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;

     // Do something with the field's code and result.
}
```

In this example, we loaded a document and then cycled through all the fields present in the document. At each iteration, we got the code and the result of the field. You can add your own logic to process the code and result fields as needed.

This concludes our guide on using the "Get Field Code" feature with Aspose.Words for .NET.

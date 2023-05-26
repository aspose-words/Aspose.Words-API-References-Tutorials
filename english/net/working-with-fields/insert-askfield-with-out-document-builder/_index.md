---
title: Insert ASKField Without Document Builder
linktitle: Insert ASKField Without Document Builder
second_title: Aspose.Words for .NET API Reference
description: Learn how to insert an ASK field into your Word documents with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fields/insert-askfield-with-out-document-builder/
---

Here is a step-by-step guide to explain the C# source code below, which uses the "Insert an ASK field without DocumentBuilder" feature of Aspose.Words for .NET. Make sure to follow each step carefully to get the desired results.

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

## Step 3: Inserting the ASK field

We use the `AppendField()` method to insert an ASK field into the paragraph.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

We then configure the various properties of the ASK field by specifying the desired values.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

Finally, we call the `Update()` method to update the field.

```csharp
field. Update();
```

### Example of the source code for inserting an ASK field without DocumentBuilder with Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Document creation.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Insert the ASK field.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

In this example, we created a new document, inserted an ASK field without using DocumentBuilder, configured the various properties of the field, and saved the document with a specified filename.

This concludes our guide on using the "Insert ASK Field Without DocumentBuilder" feature with Aspose.Words for .NET.

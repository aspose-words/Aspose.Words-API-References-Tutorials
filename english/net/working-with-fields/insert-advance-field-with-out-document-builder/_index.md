---
title: Insert Advance Field Without Document Builder
linktitle: Insert Advance Field Without Document Builder
second_title: Aspose.Words for .NET API Reference
description: Learn how to insert an advanced field into your Word documents with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fields/insert-advance-field-with-out-document-builder/
---

Here is a step-by-step guide to explain the C# source code below, which uses the "Advanced Field Insertion without DocumentBuilder" feature of Aspose.Words for .NET. Make sure to follow each step carefully to get the desired results.

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

## Step 3: Inserting the advanced field

We use the `AppendField()` method to insert an advanced field into the paragraph.

```csharp
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);
```

We then configure the various properties of the advanced field by specifying the desired values.

```csharp
field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";
```

Finally, we call the `Update()` method to update the field.

```csharp
field. Update();
```

### Example of the source code for inserting an advanced field without DocumentBuilder with Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Document creation.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Insert the advanced field.
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);

field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";

field. Update();

doc.Save(dataDir + "InsertionFieldAdvanceWithoutDocumentBuilder.docx");
```

In this example, we created a new document, inserted an advanced field without using DocumentBuilder, configured the various field properties, and saved the document with a specified filename.

This concludes our guide on how to use the "Insert Advanced Field Without DocumentBuilder" feature with Aspose.Words for .NET.

### FAQ's

#### Q: What is an advanced field in Aspose.Words?

A: An Advance Field in Aspose.Words is a special type of field that allows you to perform calculations, include conditions and perform complex operations in a Word document. It offers great flexibility to create dynamic and custom fields.

#### Q: How to insert an advanced field in a Word document without using Document Builder in Aspose.Words?

A: To insert an advanced field in a Word document without using Document Builder in Aspose.Words, you can follow these steps:

1. Import Document and Field class from Aspose.Words.Fields namespace.
2. Create an instance of Document by loading your existing document.
3. Use the InsertField method to insert an advanced field by specifying the advanced field code.
4. Save the document.

#### Q: How to get the result of an advanced field in a Word document?

A: To get the result of an advanced field in a Word document, you can use the Result property available in the Field class. This property returns the calculated result of the field.

#### Q: Can I modify the formula of an advanced field after inserting it in a Word document?

A: Yes, you can edit the formula of an advanced field after inserting it into a Word document. You can do this by accessing the FieldCode property of the Field class and updating the formula by modifying the formula text.

---
title: Insert Author Field
linktitle: Insert Author Field
second_title: Aspose.Words Document Processing API
description: Learn how to Insert an AUTHOR field in your Word documents with Aspose.Words for .NET. Specify the author's name to personalize your documents.
type: docs
weight: 10
url: /net/working-with-fields/insert-author-field/
---


Here is a step-by-step guide to explain the C# source code below, which uses the "Insert an AUTHOR field" feature of Aspose.Words for .NET. Make sure to follow each step carefully to get the desired results.

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

## Step 3: Insert AUTHOR field

We use the `AppendField()` method to insert an AUTHOR field into the paragraph.

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

We then configure the field's `AuthorName` property to specify the author's name.

```csharp
field. AuthorName = "Test1";
```

Finally, we call the `Update()` method to update the field.

```csharp
field. Update();
```

### Example of the source code for inserting an AUTHOR field with Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Document creation.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Insert the AUTHOR field.
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);

field. AuthorName = "Test1";

field. Update();

doc.Save(dataDir + "InsertionAuthorField.docx");
```

In this example, we created a new document, inserted an AUTHOR field, configured the author name, and saved the document with a specified filename.

This concludes our guide on using the "Insert AUTHOR Field" feature with Aspose.Words for .NET.

### FAQ's

#### Q: What is an author field in Aspose.Words?

A: An Author Field in Aspose.Words is a special field that automatically inserts and updates the author's name in a Word document. It is often used to indicate who created or modified the document.

#### Q: How to update the author field in a Word document with Aspose.Words?

A: The author field in a Word document can be updated to reflect the current author's name. For this, you can use the UpdateFields method available in the Document class. This method will update all fields in the document, including the author field.

#### Q: Is it possible to customize the format of the author field in a Word document?

A: Yes, it is possible to customize the format of the author field in a Word document. By default, the author field simply displays the author's name. However, you can add additional information such as date and time of modification using the formatting options available in Aspose.Words.

#### Q: Is the author field sensitive to subsequent changes to the author's name?

A: Yes, the author field is sensitive to subsequent changes to the author name. If you change the author name in the document properties, the author field will automatically update with the new name when updating document fields.

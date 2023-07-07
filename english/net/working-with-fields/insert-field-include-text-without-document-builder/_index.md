---
title: Insert Field Include Text Without Document Builder
linktitle: Insert FieldIncludeText Without Document Builder
second_title: Aspose.Words for .NET API Reference
description: Learn how to insert a FieldIncludeText field in your Word documents with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fields/insert-field-include-text-without-document-builder/
---

Here is a step-by-step guide to explain the C# source code below, which uses the "Insert a FieldIncludeText field" functionality of Aspose.Words for .NET. Make sure to follow each step carefully to get the desired results.

## Step 1: Document Directory Setup

In the code provided, you must specify the directory of your documents. Replace the value "YOUR DOCUMENT DIRECTORY" with the appropriate path to your documents directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Creating the Document and Paragraph

We start by creating a new document and initializing a paragraph.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Step 3: Inserting the FieldIncludeText field

We use the `AppendField()` method to insert an FieldIncludeText field into the paragraph.

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

We then configure the properties of the FieldIncludeText field by specifying the name of the bookmark and the name of the source file.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

Next, we add the paragraph to the body of the document.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

Finally, we call the `Update()` method to update the field.

```csharp
fieldIncludeText.Update();
```

### Example of the source code for inserting a FieldIncludeText field with Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Create the document and the paragraph.
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Insert FieldIncludeText field.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

In this example, we created a new document, initialized a paragraph, inserted a FieldIncludeTexten specifying the bookmark name and source file name, and saved the document with a specified file name.

This concludes our guide on using the "Insert a FieldIncludeText" feature with Aspose.Words for .NET.

### FAQ's

#### Q: How can I specify the source file for text inclusion field in Aspose.Words for .NET?

A: To specify the source file for the text inclusion field in Aspose.Words for .NET, you can use the `FieldIncludeText.SourceFullName` property to set the full path of the source file. Make sure the source file is accessible and contains the content you want to include in the text inclusion field.

#### Q: Can I include text from a macro in the text inclusion field with Aspose.Words for .NET?

A: Yes, you can include text from a macro in the text inclusion field with Aspose.Words for .NET. You can use the `FieldIncludeText.IncludeText` property to specify the name of the macro whose content should be included in the field.

#### Q: Does inserting a text include field without the document builder affect the Word document structure with Aspose.Words for .NET?

A: Inserting a text include field without the document builder does not directly affect the structure of the Word document. However, it adds a new field element to the document content. You can manipulate the document structure by adding, deleting or modifying the existing elements according to your needs.

#### Q: Can I customize the appearance of the text inclusion field in a Word document with Aspose.Words for .NET?

A: The text inclusion field does not directly customize its appearance in a Word document. However, you can format the included text using the paragraph properties, font properties, and other formatting objects available in Aspose.Words for .NET.

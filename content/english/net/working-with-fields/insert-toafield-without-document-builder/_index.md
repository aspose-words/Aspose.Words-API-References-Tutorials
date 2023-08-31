---
title: Insert TOA Field Without Document Builder
linktitle: Insert TOA Field Without Document Builder
second_title: Aspose.Words Document Processing API
description: Step by step guide to insert TOA field without Document Builder using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fields/insert-toafield-without-document-builder/
---

Here is a step-by-step guide to explain the C# source code below, which uses the "TOA Field Insertion" feature of Aspose.Words for .NET. Follow each step carefully to get the desired results.

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

## Step 3: Inserting the TA field

We use the FieldTA class to insert a TA field into the paragraph.

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## Step 4: Adding the paragraph to the body of the document

We add the paragraph containing the TA field to the body of the document.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Step 5: Creating the paragraph for the TOA field

We create a new paragraph for the TOA field.

```csharp
para = new Paragraph(doc);
```

## Step 6: Inserting the TOA field

We use the FieldToa class to insert a TOA field into the paragraph.

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## Step 7: Adding the paragraph to the body of the document

We add the paragraph containing the TOA field to the body of the document.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Step 8: Update TOA Field

Finally, we call the `Update()` method to update the TOA field.

```csharp
fieldToa.Update();
```

### Source code example for TOA field insertion without Document Builder with Aspose.Words for .NET

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// We want to insert TA and TOA fields like this:
// { TA \c 1 \l "Value 0" }
// { TOA \c 1 }

FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);

para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);

fieldToa.Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

### FAQ's

#### Q: How to customize the appearance of the TOA field inserted in the Word document with Aspose.Words for .NET?

A: You can customize the appearance of the inserted TOA field by using the properties of the `FieldTOA` object to specify formatting options.

#### Q: Can I add multiple TOA fields in a single Word document using Aspose.Words for .NET?

A: Yes, you can add multiple TOA fields in a single Word document using Aspose.Words for .NET. Just repeat the insert steps for each field.

#### Q: How can I check if a TOA field was successfully inserted into a Word document with Aspose.Words for .NET?

A: To check if a TOA field was successfully inserted, you can browse the document content and search for TOA field instances.

#### Q: Does inserting a TOA field without using DocumentBuilder affect Word document formatting with Aspose.Words for .NET?

A: Inserting a TOA field without using DocumentBuilder does not directly affect the formatting of the Word document. However, the TOA field formatting options can impact the overall formatting of the document.

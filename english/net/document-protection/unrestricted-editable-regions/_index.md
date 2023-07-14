---
title: Unrestricted Editable Regions In Word Document
linktitle: Unrestricted Editable Regions In Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to create unrestricted editable areas in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/document-protection/unrestricted-editable-regions/
---
In this tutorial, we will guide you through the steps to use the unrestricted editable areas feature of Aspose.Words for .NET. This feature lets you define areas in a Word document where content can be edited without restriction, even if the rest of the document is read-only. Follow the steps below:

## Step 1: Loading the document and setting protection

Start by loading the existing document:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

Protect the document by setting read-only protection type and password

## Step 2: Creating an editable area

Start by creating an editable area using the EditableRangeStart and EditableRangeEnd objects:

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
// An EditableRange object is created for the EditableRangeStart that we just made.
EditableRange editableRange = edRangeStart.EditableRange;

// Put something inside the editable range.
builder.Writeln("Paragraph inside first editable range");

// An editable range is well-formed if it has a start and an end.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## Step 3: Add content outside of editable areas

You can add content outside of the editable areas, which will remain read-only:

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## Step 4: Save the document

Finally, save the modified document:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

Be sure to specify the correct path and filename to save the document with editable areas.

### Example source code for Unrestricted Editable Regions using Aspose.Words for .NET

Here is the complete source code for unrestricted editable areas using Aspose.Words for .NET:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Upload a document and make it as read-only.
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

doc.Protect(ProtectionType.ReadOnly, "MyPassword");

builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

// Start an editable range.
EditableRangeStart edRangeStart = builder.StartEditableRange();
// An EditableRange object is created for the EditableRangeStart that we just made.
EditableRange editableRange = edRangeStart.EditableRange;

// Put something inside the editable range.
builder.Writeln("Paragraph inside first editable range");

// An editable range is well-formed if it has a start and an end.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
By following these steps, you can easily create unrestricted editable areas in your Word document with Aspose.Words for .NET.

## Conclusion
In this tutorial, we learned how to create unrestricted editable regions in a Word document using Aspose.Words for .NET. By following the provided steps, you can define specific areas within the document where users can freely edit the content while keeping the rest of the document read-only. Aspose.Words for .NET offers powerful features for document protection and customization, providing you with control over the editing capabilities of your Word documents.

### FAQ's for unrestricted editable regions in word document

#### Q: What are unrestricted editable regions in Aspose.Words for .NET?

A: Unrestricted editable regions in Aspose.Words for .NET are areas within a Word document where content can be edited without any restrictions, even if the rest of the document is set as read-only. These regions provide a way to define specific parts of the document that users can modify while maintaining the overall document protection.

#### Q: How can I create unrestricted editable regions using Aspose.Words for .NET?

A: To create unrestricted editable regions in a Word document using Aspose.Words for .NET, you can follow these steps:
1. Load the existing document using the `Document` class.
2. Set the document protection to read-only using the `Protect` method of the `Document` object.
3. Use the `DocumentBuilder` class to create an editable range by adding an `EditableRangeStart` object and an `EditableRangeEnd` object.
4. Add content within the editable range using the `DocumentBuilder`.
5. Save the modified document using the `Save` method of the `Document` object.

#### Q: Can I have multiple unrestricted editable regions in a Word document?

A: Yes, you can have multiple unrestricted editable regions in a Word document. To achieve this, you can create multiple sets of `EditableRangeStart` and `EditableRangeEnd` objects using the `DocumentBuilder` class. Each set of objects will define a separate editable region where users can modify the content without any restrictions.

#### Q: Can I nest editable regions within each other?

A: No, you cannot nest editable regions within each other using Aspose.Words for .NET. Each editable region defined by an `EditableRangeStart` and `EditableRangeEnd` pair should be independent and not overlap or be nested within another editable region. Nested editable regions are not supported.

#### Q: Can I remove the read-only protection from the document within an editable region?

A: No, you cannot remove the read-only protection from the document within an editable region. The read-only protection is applied to the entire document, and it cannot be selectively removed within specific editable regions. The purpose of the editable regions is to allow content modification while keeping the overall document read-only.

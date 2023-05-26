---
title: Unrestricted Editable Regions
linktitle: Unrestricted Editable Regions
second_title: Aspose.Words for .NET API Reference
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




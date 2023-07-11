---
title: Unrestricted Section
linktitle: Unrestricted Section
second_title: Aspose.Words Document Processing API
description: Learn how to define unrestricted sections in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/document-protection/unrestricted-section/
---

In this tutorial, we will guide you through the steps to use the unrestricted section feature of Aspose.Words for .NET. This feature allows you to define specific sections in a Word document that are not protected, even if the rest of the document is protected. Follow the steps below:

## Step 1: Creating the Document and Sections

Start by creating an instance of the Document class and a DocumentBuilder object:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Add content to the document
Use the DocumentBuilder object to add content to the document and insert section breaks:

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## Step 3: Protect Document and Sections

Section protection only works when document protection is enabled and only editing in form fields is allowed. You can protect the document using the Protect() method of the Document object:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Be sure to specify the correct type of protection and set the desired password.

## Step 4: Disabling protection for a specific section

By default, all sections are protected, but you can selectively disable protection for a specific section using the ProtectedForForms property of the Section object:

```csharp
doc.Sections[0].ProtectedForForms = false;
```

In this example, protection is disabled for the first section.

## Step 5: Save the document

Finally, save the modified document:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

Be sure to specify the correct path and filename to save the document with unrestricted sections.

### Example source code for Unrestricted Section using Aspose.Words for .NET

Here is the complete source code for the unrestricted section using Aspose.Words for .NET:


```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Insert two sections with some text.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1. Unprotected.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");

// Section protection only works when document protection is turned and only editing in form fields is allowed.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// By default, all sections are protected, but we can selectively turn protection off.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

By following these steps, you will be able to easily define unrestricted sections in your Word document with Aspose.Words for .NET.



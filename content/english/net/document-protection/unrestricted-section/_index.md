---
title: Unrestricted Section In Word Document
linktitle: Unrestricted Section In Word Document
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

## Conclusion

In this tutorial, we explored the unrestricted section feature of Aspose.Words for .NET, which allows specific sections in a Word document to remain unprotected while the rest of the document is protected. By following the steps provided, you can easily define sections within your document where users can freely edit the content while maintaining protection for other sections. Aspose.Words for .NET offers powerful capabilities for document protection and customization, giving you control over the editing permissions within your Word documents.

### FAQ's for unrestricted section in word document

#### Q: What are unrestricted sections in Aspose.Words for .NET?

A: Unrestricted sections in Aspose.Words for .NET are specific sections within a Word document that are not protected, even if the rest of the document is protected. These sections allow users to modify the content within them while maintaining protection for the remaining parts of the document.

#### Q: How can I create unrestricted sections using Aspose.Words for .NET?

A: To create unrestricted sections in a Word document using Aspose.Words for .NET, you can follow these steps:
1. Create an instance of the `Document` class and a `DocumentBuilder` object.
2. Use the `DocumentBuilder` to add content to the document and insert section breaks.
3. Protect the document using the `Protect` method of the `Document` object, specifying the desired protection type and password.
4. Disable protection for a specific section by setting the `ProtectedForForms` property of the corresponding `Section` object to `false`.
5. Save the modified document.

#### Q: Can I have multiple unrestricted sections within a Word document?

A: Yes, you can have multiple unrestricted sections within a Word document. By selectively disabling protection for specific sections using the `ProtectedForForms` property of the `Section` object, you can define multiple sections where users can freely modify the content while keeping other sections protected.

#### Q4. Can I remove protection from a section that was initially protected?
Yes, you can remove protection from a section that was initially protected by setting the `ProtectedForForms` property of the corresponding `Section` object to `false`. This allows users to edit the content within that specific section without any restrictions.

#### Q: What protection types can be applied to a Word document?

A: Aspose.Words for .NET provides various protection types that can be applied to a Word document, including:
- NoProtection: No protection is applied.
- AllowOnlyRevisions: Users can only make revisions to the document.
- AllowOnlyComments: Users can only add comments to the document.
- AllowOnlyFormFields: Users can only edit form fields in the document.
- ReadOnly: The document is read-only, and no editing is allowed.




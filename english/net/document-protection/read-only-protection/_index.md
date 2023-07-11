---
title: Read Only Protection
linktitle: Read Only Protection
second_title: Aspose.Words Document Processing API
description: Learn how to protect your read-only Word documents with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/document-protection/read-only-protection/
---
In this tutorial, we will guide you through the steps to use the read-only protection feature of Aspose.Words for .NET. This feature allows you to make a Word document read-only to prevent unauthorized modification. Follow the steps below:

## Step 1: Creating the Document and Applying Protection

Start by creating an instance of the Document class and a DocumentBuilder object:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Write content to the document
Use the DocumentBuilder object to write content to the document:

```csharp
builder.Write("Open document as read-only");
```

## Step 3: Set password and make document read-only

Set a password for the document using the SetPassword() property of the WriteProtection object:

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

Be sure to replace "MyPassword" with the actual password you want to use.

## Step 4: Apply read-only document

Make the document read-only by setting the ReadOnlyRecommended property to true:

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## Step 5: Apply read-only protection and save the document

Finally, apply read-only protection using the Protect() method of the Document object:

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Be sure to specify the correct path and filename to save the protected document.

### Example source code for Read Only Protection using Aspose.Words for .NET

Here is the complete source code for read-only protection using Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Open document as read-only");

	// Enter a password that's up to 15 characters long.
	doc.WriteProtection.SetPassword("MyPassword");

	// Make the document as read-only.
	doc.WriteProtection.ReadOnlyRecommended = true;

	// Apply write protection as read-only.
	doc.Protect(ProtectionType.ReadOnly);
	doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

By following these steps, you can easily protect your documents



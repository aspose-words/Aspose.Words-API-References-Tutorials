---
title: Creating And Signing New Signature Line
linktitle: Creating And Signing New Signature Line
second_title: Aspose.Words Document Processing API
description: Learn how to create and sign a new signature line in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---

In this tutorial, we will walk you through the steps to use the create and sign a new signature line feature with Aspose.Words for .NET. This feature allows you to insert a signature line in a Word document, set custom options and sign the document. Follow the steps below:

## Step 1: Creating the Document and Generator

Start by creating an instance of the Document class and a DocumentBuilder object:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Inserting the signature line

Use the InsertSignatureLine() method of the DocumentBuilder object to insert a new signature line into the document:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Step 3: Save the document

Save the modified document:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

Be sure to specify the correct path and filename to save the document.

## Step 4: Signing the document

To sign the document, you need to set the signature options and use the DigitalSignatureUtil class:

```csharp
SignOptions signOptions = new SignOptions
{
	SignatureLineId = signatureLine.Id,
	SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
	dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

Be sure to specify the correct paths for the document, signature line image, and signed document.

### Example source code for Creating And Signing New Signature Line using Aspose.Words for .NET

Here is the complete source code to create and sign a new signature line with Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
	
	doc.Save(dataDir + "SignDocuments.SignatureLine.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
		dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);

```

By following these steps, you will be able to easily create and sign a new signature line in your Word document with Aspose.Words for .NET.



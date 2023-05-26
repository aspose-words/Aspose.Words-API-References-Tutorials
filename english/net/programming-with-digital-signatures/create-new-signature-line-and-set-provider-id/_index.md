---
title: Create New Signature Line And Set Provider Id
linktitle: Create New Signature Line And Set Provider Id
second_title: Aspose.Words for .NET API Reference
description: Learn how to create a new signature line and set provider ID in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---

In this tutorial, we'll walk you through the steps to use the Create New Signature Line and Set Provider ID feature with Aspose.Words for .NET. This feature allows you to insert a signature line in a Word document, set custom options and sign the document. Follow the steps below:

## Step 1: Creating the Document and Generator

Start by creating an instance of the Document class and a DocumentBuilder object:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Setting Signature Line Options

Create an instance of the SignatureLineOptions class and set the desired options:

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
Sign = "vderyushev",
SignerTitle = "QA",
Email = "vderyushev@aspose.com",
ShowDate=true,
Default Instructions = false,
Instructions = "Please sign here.",
AllowComments = true
};
```

## Step 3: Inserting the signature line

Use the InsertSignatureLine() method of the DocumentBuilder object to insert the signature line into the document:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## Step 4: Set Provider ID

Set the provider ID for the signature line using the ProviderId property:

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

Be sure to specify the correct provider ID for your use case.

## Step 5: Save the Document

Save the modified document:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Be sure to specify the correct path and filename to save the document.

## Step 6: Signing the document

To sign the document, you need to set the signature options and use the DigitalSignatureUtil class:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
ProviderId = signatureLine.ProviderId,
Comments = "Document was signed by vderyushev",
SignTime = DateTime.Now
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
	dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions)
```

Be sure to specify the correct paths for the document, certificate, and signed document.

### Example source code for Create New Signature Line And Set Provider Id using Aspose.Words for .NET

Here is the complete source code to create a new signature line and set the provider ID with Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLineOptions signatureLineOptions = new SignatureLineOptions
	{
		Signer = "vderyushev",
		SignerTitle = "QA",
		Email = "vderyushev@aspose.com",
		ShowDate = true,
		DefaultInstructions = false,
		Instructions = "Please sign here.",
		AllowComments = true
	};

	SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
	signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
	
	doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		ProviderId = signatureLine.ProviderId,
		Comments = "Document was signed by vderyushev",
		SignTime = DateTime.Now
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
		dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);

```

By following these steps, you can easily create a new signature line and set the provider ID in your Word document with Aspose.Words for .NET.



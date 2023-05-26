---
title: Signing Existing Signature Line
linktitle: Signing Existing Signature Line
second_title: Aspose.Words for .NET API Reference
description: Learn how to sign an existing signature line in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-digital-signatures/signing-existing-signature-line/
---

In this tutorial, we'll walk you through the steps to use the signature feature of an existing signature line with Aspose.Words for .NET. This feature allows you to digitally sign a signature line already present in a Word document. Follow the steps below:

## Step 1: Loading the document and accessing the signature line

Start by uploading the document containing the existing signature line:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Step 2: Setting Signature Options

Create an instance of the SignOptions class and set the signature options, including signature line ID and signature line image:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

Be sure to specify the correct path to the signature line image.

## Step 3: Loading the certificate

Start by loading the signing certificate using the CertificateHolder class:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Be sure to specify the correct path to your certificate and associated password.

## Step 4: Signing the existing signature line

Use the DigitalSignatureUtil class to sign the existing signature line:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

Be sure to specify the correct paths for the source document, signed document, and certificate.

### Example source code for Signing Existing Signature Line using Aspose.Words for .NET

Here is the complete source code to sign an existing signature line with Aspose.Words for .NET:


```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");
	
	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
	

```

By following these steps, you can easily sign an existing signature line in a Word document with Aspose.Words for .NET.



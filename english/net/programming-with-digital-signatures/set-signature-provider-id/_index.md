---
title: Set Signature Provider Id
linktitle: Set Signature Provider Id
second_title: Aspose.Words Document Processing API
description: Learn how to set the signature provider ID in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-digital-signatures/set-signature-provider-id/
---

In this tutorial, we'll walk you through the steps to use the Set Signature Provider ID feature with Aspose.Words for .NET. This feature allows you to specify the signature provider ID for a signature line in a Word document. Follow the steps below:

## Step 1: Loading the document and accessing the signature line

Start by uploading the document containing the signature line:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Step 2: Setting Signature Options

Create an instance of the SignOptions class and set the signing options, including the provider ID:

```csharp
SignOptions signOptions = new SignOptions
{
ProviderId = signatureLine.ProviderId,
 SignatureLineId = signatureLine.Id
};
```

## Step 3: Signing the document

To sign the document, you must use the DigitalSignatureUtil class and specify the signing certificate:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

Be sure to specify the correct paths for the document, certificate, and signed document.

### Example source code for Set Signature Provider Id using Aspose.Words for .NET

Here is the complete source code to set the signature provider ID with Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");

	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		ProviderId = signatureLine.ProviderId, SignatureLineId = signatureLine.Id
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);

```

Finish the Signature Provider ID in your Word document with Aspose.Words for .NET.



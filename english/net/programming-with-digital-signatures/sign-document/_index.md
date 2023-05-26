---
title: Sign Document
linktitle: Sign Document
second_title: Aspose.Words for .NET API Reference
description: Learn how to digitally sign a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-digital-signatures/sign-document/
---

In this tutorial, we'll walk you through the steps to use the document signing feature with Aspose.Words for .NET. This feature allows you to digitally sign a Word document using a certificate. Follow the steps below:

## Step 1: Loading the certificate

Start by loading the signing certificate using the CertificateHolder class:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Be sure to specify the correct path to your certificate and associated password.

## Step 2: Signing the document

Use the DigitalSignatureUtil class to sign the document:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

Be sure to specify the correct paths for the source document and the signed document.

### Example source code for Sign Document using Aspose.Words for .NET

Here is the complete source code to sign a document with Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

By following these steps, you can easily sign a Word document with Aspose.Words for .NET.





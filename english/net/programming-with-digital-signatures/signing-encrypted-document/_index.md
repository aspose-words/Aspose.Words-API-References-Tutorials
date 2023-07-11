---
title: Signing Encrypted Document
linktitle: Signing Encrypted Document
second_title: Aspose.Words Document Processing API
description: Learn how to digitally sign an encrypted document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-digital-signatures/signing-encrypted-document/
---

In this tutorial, we will guide you through the steps to use the feature of signing an encrypted document with Aspose.Words for .NET. This feature allows you to digitally sign a Word document that is encrypted using a decryption password. Follow the steps below:

## Step 1: Setting Signature Options

Create an instance of the SignOptions class and set the decryption password:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionpassword" };
```

Be sure to specify the correct decryption password for your encrypted document.

## Step 2: Loading the certificate

Start by loading the signing certificate using the CertificateHolder class:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Be sure to specify the correct path to your certificate and associated password.

## Step 3: Signing the encrypted document

Use the DigitalSignatureUtil class to sign the encrypted document:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
	certHolder, signOptions);
```

Be sure to specify the correct paths for the encrypted document, signed document, and certificate.

### Example source code for Signing Encrypted Document using Aspose.Words for .NET

Here is the complete source code to sign an encrypted document with Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
		certHolder, signOptions);
	

```
By following these steps, you can easily sign an encrypted Word document with Aspose.Words for .NET.



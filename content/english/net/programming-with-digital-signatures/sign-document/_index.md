---
title: Sign Word Document
linktitle: Sign Word Document
second_title: Aspose.Words Document Processing API
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

## Conclusion

In this tutorial, we explored the document signing feature in Aspose.Words for .NET. By loading a signing certificate and using the `DigitalSignatureUtil.Sign` method, we can digitally sign a Word document. Document signing provides authentication and ensures the integrity of the document's contents, making it a valuable feature for secure and trustworthy document management.

### FAQ's for sign word document

#### Q: What is document signing in Aspose.Words for .NET?

A: Document signing in Aspose.Words for .NET refers to the process of digitally signing a Word document using a certificate. This feature adds a digital signature to the document, providing authenticity, integrity, and non-repudiation of the document's contents.

#### Q: How can I load the signing certificate in Aspose.Words for .NET?

A: To load the signing certificate in Aspose.Words for .NET, you can use the `CertificateHolder` class. Create an instance of `CertificateHolder` by providing the path to the certificate file and the associated password. Here's an example:

```csharp
CertificateHolder certHolder = CertificateHolder.Create("path/to/certificate.pfx", "password");
```

Make sure to provide the correct path to your certificate and the associated password.

#### Q: How do I sign a Word document using Aspose.Words for .NET?

A: To sign a Word document using Aspose.Words for .NET, you can use the `DigitalSignatureUtil` class. Call the `Sign` method, providing the path to the source document, the path to the signed document (output), and the `CertificateHolder` object. Here's an example:

```csharp
DigitalSignatureUtil.Sign("path/to/source/document.docx", "path/to/signed/document.docx", certHolder);
```

Ensure that you provide the correct paths for the source document and the signed document (output).

#### Q: What is the purpose of document signing?

A: Document signing serves as a method of ensuring the authenticity and integrity of a document. By digitally signing a document, you can provide proof of its origin, verify its contents haven't been altered, and establish non-repudiation. Document signing is commonly used for legal, financial, and sensitive documents.

#### Q: Can I use any certificate for document signing in Aspose.Words for .NET?

A: For document signing in Aspose.Words for .NET, you need to use a valid X.509 certificate. This certificate can be obtained from a trusted certificate authority (CA) or a self-signed certificate can be used for testing purposes.

#### Q: What file format does Aspose.Words for .NET support for document signing?

A: Aspose.Words for .NET supports document signing for Word documents in the DOCX file format. You can sign DOCX files using the `DigitalSignatureUtil` class and the appropriate certificate.

#### Q: Can I sign multiple Word documents using the same certificate?

A: Yes, you can sign multiple Word documents using the same certificate. Once you have loaded the certificate using the `CertificateHolder` class, you can reuse it to sign multiple documents by calling the `DigitalSignatureUtil.Sign` method with different source and signed document paths.

#### Q: Does document signing modify the original document?

A: Document signing with Aspose.Words for .NET does not modify the original document. Instead, it creates a digitally signed copy of the document, leaving the original document intact. The digitally signed copy contains the added digital signature, ensuring the integrity of the document's contents.

#### Q: Can I verify the digital signature of a signed document using Aspose.Words for .NET?

A: Yes, Aspose.Words for .NET provides functionality to verify the digital signature of a signed document. You can use the `DigitalSignatureUtil.Verify` method to check the validity and authenticity of the digital signature.

---
title: Set Signature Provider Id In Word Document
linktitle: Set Signature Provider Id In Word Document
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


## Conclusion

In this tutorial, we learned how to set the signature provider ID for a signature line in a Word document using Aspose.Words for .NET. By following the provided steps, you can easily load the document, access the signature line, set the provider ID, and sign the document. The ability to set the signature provider ID helps establish the identity and trustworthiness of the signer, enhancing the security and integrity of your Word documents. Aspose.Words for .NET provides a robust API for working with digital signatures, allowing you to customize and manage the signature process with ease.

### FAQ's for set signature provider id in word document

#### Q: What is a signature provider ID in a Word document?

A: A signature provider ID in a Word document is a unique identifier that specifies the provider of a digital signature. It helps identify the entity or organization responsible for creating and managing the digital signature.

#### Q: How can I set the signature provider ID for a signature line in a Word document using Aspose.Words for .NET?

A: To set the signature provider ID for a signature line in a Word document using Aspose.Words for .NET, you can follow these steps:
1. Load the document using the `Document` class and specify the path to the document file.
2. Access the signature line using the appropriate method or property. For example, you can use `GetChild` method to retrieve the signature line shape.
3. Retrieve the provider ID from the signature line.
4. Create an instance of the `SignOptions` class and set the `ProviderId` property to the retrieved provider ID.
5. Use the `DigitalSignatureUtil.Sign` method to sign the document, providing the necessary parameters including the `SignOptions` object.

#### Q: How do I access the signature line in a Word document using Aspose.Words for .NET?

A: To access the signature line in a Word document using Aspose.Words for .NET, you can use the appropriate method or property to retrieve the signature line shape from the document's structure. For example, you can use the `GetChild` method with the appropriate parameters to get the desired signature line shape.

#### Q: Can I set the signature provider ID for multiple signature lines in a Word document?

A: Yes, you can set the signature provider ID for multiple signature lines in a Word document. You can iterate through the collection of signature lines in the document and set the provider ID for each signature line individually using the `SignOptions.ProviderId` property.

#### Q: What is the purpose of the signature provider ID in a Word document?

A: The signature provider ID in a Word document serves the purpose of identifying the entity or organization responsible for creating and managing the digital signature. It helps establish the authenticity and trustworthiness of the digital signature by associating it with a specific provider.

#### Q: What type of digital certificates can be used for setting the signature provider ID in a Word document?

A: You can use X.509 digital certificates with appropriate provider information to set the signature provider ID in a Word document. The digital certificate should be issued by a trusted certificate authority (CA) and contain the necessary metadata to identify the provider.

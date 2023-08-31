---
title: Signing Existing Signature Line In Word Document
linktitle: Signing Existing Signature Line In Word Document
second_title: Aspose.Words Document Processing API
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

## Conclusion

In this tutorial, we learned how to sign an existing signature line in a Word document using Aspose.Words for .NET. By following the provided steps, you can easily load the document, access the existing signature line, set the signing options, and sign the document. The ability to sign an existing signature line provides a convenient way to add digital signatures to predefined areas in your Word documents, ensuring document integrity and authentication. Aspose.Words for .NET offers a powerful API for Words Processing with digital signatures, allowing you to customize the signing process and enhance the security of your Word documents.

### FAQ's

#### Q: What is an existing signature line in a Word document?

A: An existing signature line in a Word document is a predefined area where a signature can be placed. It is typically represented by a shape or object in the document and serves as a designated space for the signer to add their digital signature.

#### Q: How can I sign an existing signature line in a Word document using Aspose.Words for .NET?

A: To sign an existing signature line in a Word document using Aspose.Words for .NET, you can follow these steps:
1. Load the document using the `Document` class and specify the path to the document file.
2. Access the existing signature line using the appropriate method or property. For example, you can use `GetChild` method to retrieve the signature line shape.
3. Create an instance of the `SignOptions` class and set the `SignatureLineId` property to the ID of the existing signature line.
4. Set the `SignatureLineImage` property of the `SignOptions` class to the image representing the digital signature.
5. Load the signing certificate using the `CertificateHolder` class and provide the necessary certificate and password.
6. Use the `DigitalSignatureUtil.Sign` method to sign the document, providing the necessary parameters including the `SignOptions` object.

#### Q: How do I access the existing signature line in a Word document using Aspose.Words for .NET?

A: To access the existing signature line in a Word document using Aspose.Words for .NET, you can use the appropriate method or property to retrieve the signature line shape from the document's structure. For example, you can use the `GetChild` method with the appropriate parameters to get the desired signature line shape.

#### Q: Can I customize the appearance of the digital signature in an existing signature line?

A: Yes, you can customize the appearance of the digital signature in an existing signature line by providing an image file representing the signature. The image can be a logo, handwritten signature, or any other graphical representation of the signature. You can set the `SignatureLineImage` property of the `SignOptions` class to the bytes of the image file.

#### Q: Can I sign multiple existing signature lines in a Word document?
A: Yes, you can sign multiple existing signature lines in a Word document. You need to follow the steps for each signature line individually, setting the appropriate `SignatureLineId` and `SignatureLineImage` values in the `SignOptions` object for each signature line.

#### Q: What format should the image file be for the digital signature in an existing signature line?

A: The image file for the digital signature in an existing signature line can be in various formats, such as PNG, JPEG, BMP, or GIF. You can specify the file path or read the bytes of the image file and assign it to the `SignatureLineImage` property of the `SignOptions` class.


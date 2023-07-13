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

## Conclusion

In this tutorial, we learned how to create and sign a new signature line in a Word document using Aspose.Words for .NET. By following the steps provided, you can easily insert a signature line into your document, customize its options, and sign the document using a digital certificate. Adding signature lines and digital signatures to your documents enhances their authenticity and integrity, making them more secure and trustworthy. Aspose.Words for .NET provides a powerful API for working with signatures and digital certificates in Word documents, allowing you to automate the signing process and ensure the validity of your documents.

### FAQ's

#### Q: What is a signature line in a Word document?

A: A signature line in a Word document is a placeholder that indicates where a signature should be placed. It typically includes the name, title, and date, and provides space for a handwritten or digital signature.

#### Q: How can I create a signature line in a Word document using Aspose.Words for .NET?

A: To create a signature line in a Word document using Aspose.Words for .NET, you can follow these steps:
1. Create an instance of the `Document` class and a `DocumentBuilder` object.
2. Use the `InsertSignatureLine` method of the `DocumentBuilder` object to insert a new signature line into the document.
3. Save the modified document.

#### Q: Can I customize the signature line options, such as name, title, and date?

A: Yes, you can customize the signature line options. The `SignatureLineOptions` class provides properties to set the desired options, such as `Signer`, `SignerTitle`, `ShowDate`, etc. You can modify these properties before inserting the signature line.

#### Q: How can I sign the document after creating a signature line?

A: To sign the document after creating a signature line, you need to set the signature options and use the `DigitalSignatureUtil` class. Here are the steps:
1. Set the `SignatureLineId` property in the `SignOptions` object to the ID of the signature line.
2. Set the `SignatureLineImage` property in the `SignOptions` object to the image of the signature you want to use.
3. Load the signing certificate using the `CertificateHolder` class.
4. Use the `DigitalSignatureUtil.Sign` method to sign the document, providing the necessary parameters.

#### Q: Can I use a digital signature image to sign the document?

A: Yes, you can use a digital signature image to sign the document. To do this, you need to provide the image file in the `SignOptions` object using the `SignatureLineImage` property. The image can be in any supported image format, such as JPEG, PNG, or EMF.

#### Q: What is the purpose of creating and signing a new signature line in a Word document?

A: Creating and signing a new signature line in a Word document using Aspose.Words for .NET allows you to add a placeholder for a signature and then sign the document using a digital certificate. This process ensures the authenticity and integrity of the document, providing evidence of approval or agreement.

#### Q: Can I create and sign multiple signature lines in a Word document using Aspose.Words for .NET?

A: Yes, you can create and sign multiple signature lines in a Word document using Aspose.Words for .NET. Each signature line can have its own unique ID and options. You can repeat the steps to create and sign additional signature lines in the document.

#### Q: Can I modify the signature line or add additional information after it has been signed?

A: Once a signature line has been signed, it becomes part of the document's content and cannot be modified separately. However, you can add additional information or content after the signed signature line.

#### Q: Can I verify the digital signature of a document that contains a signature line?

A: Yes, Aspose.Words for .NET provides functionality to verify the digital signature of a document that contains a signature line. You can use the `DigitalSignatureUtil.Verify` method to check the validity and authenticity of the digital signature.

#### Q: What file format does Aspose.Words for .NET support for creating and signing signature lines?

A: Aspose.Words for .NET supports creating and signing signature lines in the DOCX file format. You can create and sign signature lines in DOCX files using the provided methods and classes.

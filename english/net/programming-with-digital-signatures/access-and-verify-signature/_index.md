---
title: Access And Verify Signature In Word Document
linktitle: Access And Verify Signature In Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to access and verify digital signatures in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-digital-signatures/access-and-verify-signature/
---
In this tutorial, we will guide you through the steps to use the access and signature verification feature of Aspose.Words for .NET. This feature allows you to access digital signatures in a Word document and verify their validity. Follow the steps below:

## Step 1: Loading the document and accessing signatures

Start by uploading the document containing digital signatures:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

## Step 2: Browse Digital Signatures

Use a loop to loop through all the digital signatures in the document:

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
	// Access signature information
	Console.WriteLine("* Signature Found *");
	Console.WriteLine("Is valid: " + signature.IsValid);
	// This property is available in MS Word documents only.
	Console.WriteLine("Reason for signing: " + signature.Comments); 
	Console.WriteLine("Time of signing: " + signature.SignTime);
	Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
	Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
	Console.WriteLine();
}
```

Be sure to customize the display messages according to your needs.

### Example source code for Access And Verify Signature using Aspose.Words for .NET

Here is the complete source code for access and signature verification using Aspose.Words for .NET:

```csharp
	
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Digitally signed.docx");

	foreach (DigitalSignature signature in doc.DigitalSignatures)
	{
		Console.WriteLine("* Signature Found *");
		Console.WriteLine("Is valid: " + signature.IsValid);
		// This property is available in MS Word documents only.
		Console.WriteLine("Reason for signing: " + signature.Comments); 
		Console.WriteLine("Time of signing: " + signature.SignTime);
		Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
		Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
		Console.WriteLine();
	}

```

By following these steps, you will be able to easily access and verify the digital signatures in your Word document with Aspose.Words for .NET.

## Conclusion

In this tutorial, we explored the feature of accessing and verifying digital signatures in a Word document using Aspose.Words for .NET. By following the steps provided, you can easily load a document, access its digital signatures, and verify their validity. The ability to access and verify digital signatures provides a way to ensure the integrity and authenticity of your Word documents. Aspose.Words for .NET offers a powerful API for Words Processing with digital signatures, allowing you to automate the verification process and enhance the security of your documents.

### FAQ's

#### Q: What are digital signatures in a Word document?

A: Digital signatures in a Word document are electronic signatures that provide a way to authenticate the integrity and origin of the document. They are created using digital certificates and cryptographic algorithms, allowing recipients to verify that the document has not been altered and that it comes from a trusted source.

#### Q: How can I access digital signatures in a Word document using Aspose.Words for .NET?

A: To access digital signatures in a Word document using Aspose.Words for .NET, you can follow these steps:
1. Load the document using the `Document` class and specify the path to the document file.
2. Use a loop to iterate through the `DigitalSignatures` collection of the document. Each iteration represents a digital signature.

#### Q: What information can I access from a digital signature in a Word document?

A: From a digital signature in a Word document, you can access various information, such as:
- Validity: Check if the signature is valid.
- Comments: Get the reason for signing specified by the signer.
- Sign Time: Obtain the time when the document was signed.
- Subject Name: Retrieve the name of the signer or certificate subject.
- Issuer Name: Get the name of the certificate issuer.

#### Q: Can I verify the validity of a digital signature in a Word document using Aspose.Words for .NET?

A: Yes, you can verify the validity of a digital signature in a Word document using Aspose.Words for .NET. By accessing the `IsValid` property of the `DigitalSignature` object, you can determine if the signature is valid or not.

#### Q: How can I verify the validity of digital signatures in a Word document using Aspose.Words for .NET?

A: To verify the validity of digital signatures in a Word document using Aspose.Words for .NET, you can follow these steps:
1. Access the `DigitalSignatures` collection of the document.
2. Iterate through each `DigitalSignature` object in the collection.
3. Use the `IsValid` property of the `DigitalSignature` object to check if the signature is valid.

#### Q: Can I retrieve the signer's comments or reason for signing from a digital signature in a Word document?

A: Yes, you can retrieve the signer's comments or reason for signing from a digital signature in a Word document. The `Comments` property of the `DigitalSignature` object provides access to the comments specified by the signer during the signing process.

#### Q: What type of documents does the signature verification feature support in Aspose.Words for .NET?

A: The signature verification feature in Aspose.Words for .NET supports the verification of digital signatures in Word documents with the DOCX file format. You can use this feature to verify signatures in DOCX files.

#### Q: How can I access the certificate details of a digital signature in a Word document using Aspose.Words for .NET?

A: To access the certificate details of a digital signature in a Word document using Aspose.Words for .NET, you can access the `CertificateHolder` property of the `DigitalSignature` object. From the `CertificateHolder` object, you can retrieve various details of the certificate, such as the subject name and issuer name.

#### Q: Can I customize the display or processing of digital signatures in a Word document using Aspose.Words for .NET?

A: Yes, you can customize the display or processing of digital signatures in a Word document using Aspose.Words for .NET. By accessing the properties and methods of the `DigitalSignature` object, you can extract the desired information, perform additional validations, or integrate the signature verification process into your application's workflow.

#### Q: Is it possible to verify multiple digital signatures in a Word document using Aspose.Words for .NET?

A: Yes, it is possible to verify multiple digital signatures in a Word document using Aspose.Words for .NET. By iterating through the `DigitalSignatures` collection of the document, you can access and verify each digital signature individually.



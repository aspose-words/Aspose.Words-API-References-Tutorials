---
title: Create New Signature Line And Set Provider Id
linktitle: Create New Signature Line And Set Provider Id
second_title: Aspose.Words Document Processing API
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

## Conclusion

In this tutorial, we explored the feature of creating a new signature line and setting the provider ID in a Word document using Aspose.Words for .NET. By following the steps provided, you can easily insert a signature line with custom options and associate it with a specific provider using the provider ID. Adding signature lines and customizing the provider information enhances the authenticity and trustworthiness of your documents. Aspose.Words for .NET provides a powerful API for Words Processing with signature lines and digital certificates in Word documents, enabling you to automate the signing process and ensure the validity of your documents.

### FAQ's

#### Q: What is a provider ID in a signature line?

A: A provider ID in a signature line is a unique identifier that represents the provider of the digital signature. It helps identify the source or organization responsible for the signature.

#### Q: How can I create a new signature line in a Word document using Aspose.Words for .NET?

A: To create a new signature line in a Word document using Aspose.Words for .NET, you can follow these steps:
1. Create an instance of the `Document` class and a `DocumentBuilder` object.
2. Create an instance of the `SignatureLineOptions` class and set the desired signature line options.
3. Use the `InsertSignatureLine` method of the `DocumentBuilder` object to insert the signature line into the document.

#### Q: Can I customize the options of the signature line, such as signer name, title, and instructions?

A: Yes, you can customize the options of the signature line. The `SignatureLineOptions` class provides properties to set the desired options, such as `Signer`, `SignerTitle`, `Instructions`, `AllowComments`, etc. You can modify these properties before inserting the signature line.

#### Q: What is the purpose of setting the provider ID for a signature line?

A: Setting the provider ID for a signature line helps identify the source or organization responsible for the digital signature. It allows you to associate the signature with a specific provider or entity, providing additional information about the origin and trustworthiness of the signature.

#### Q: How can I set the provider ID for a signature line using Aspose.Words for .NET?

A: To set the provider ID for a signature line using Aspose.Words for .NET, you can follow these steps:
1. After inserting the signature line, access the `ProviderId` property of the `SignatureLine` object.
2. Set the `ProviderId` property to the desired provider ID value using the `Guid` data type.

#### Q: Can I sign the document after creating a new signature line and setting the provider ID?

A: Yes, after creating a new signature line and setting the provider ID, you can sign the document. To sign the document, you need to set the signature options, including the signature line ID, provider ID, comments, and sign time. Then, use the `DigitalSignatureUtil.Sign` method to sign the document using a digital certificate.

#### Q: Can I specify a specific provider ID for each signature line in a Word document?

A: Yes, you can specify a specific provider ID for each signature line in a Word document. After inserting each signature line, you can set the provider ID for that particular signature line by accessing the `ProviderId` property of the respective `SignatureLine` object.

#### Q: How can I save the modified document after creating a new signature line and setting the provider ID?

A: To save the modified document after creating a new signature line and setting the provider ID, you can use the `Save` method of the `Document` object. Specify the correct path and filename to save the document.

#### Q: What file format does Aspose.Words for .NET support for creating and signing signature lines?

A: Aspose.Words for .NET supports creating and signing signature lines in the DOCX file format. You can create and sign signature lines in DOCX files using the provided methods and classes.

#### Q: Can I modify the provider ID or other options of a signature line after it has been signed?

A: Once a signature line has been signed, it becomes part of the document's content and cannot be modified separately. Any modifications to the signature line, such as changing the provider ID or other options, would require removing the existing signature and creating a new signature line.

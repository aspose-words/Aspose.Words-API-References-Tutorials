---
title: Access And Verify Signature
linktitle: Access And Verify Signature
second_title: Aspose.Words for .NET API Reference
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
	Console.WriteLine("*** Signature Found ***");
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
		Console.WriteLine("*** Signature Found ***");
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




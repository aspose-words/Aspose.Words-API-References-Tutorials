---
title: Add Digital Signature to PDF using Certificate Holder
linktitle: Add Digital Signature to PDF using Certificate Holder
second_title: Aspose.Words Document Processing API
description: Learn how to add Digital Signature to PDF using Certificate Holder with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

In this tutorial, we'll walk you through the steps to add digital signature to PDF using certificate holder with Aspose.Words for .NET. The digital signature adds a layer of security and integrity to the PDF document. Follow the steps below:

## Step 1: Creating the document and adding content

Start by creating an instance of the Document class:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Add content to the document

Then use the `DocumentBuilder` to add content to the document. For example, to add a paragraph containing the text "Test Signed PDF", use the `Writeln` method:

```csharp
builder.Writeln("Test Signed PDF.");
```

You can add other content items as needed.

## Step 3: Set PDF save options

Create an instance of the PdfSaveOptions class and specify the digital signature details:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
	DigitalSignatureDetails = new PdfDigitalSignatureDetails(
		CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
		DateTime.Now)
};
```

Be sure to specify the correct path to your certificate and associated password. You can also customize the signature reason and location.

## Step 4: Save Document as Digitally Signed PDF

Use the `Save` method to save the document as a PDF by specifying the save options:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

Make sure to specify the correct path to save the digitally signed PDF.

By following these steps, you can easily create a digitally signed PDF with a certificate using Aspose.Words for .NET.

### Example source code for Digitally Signed Pdf Using Certificate Holder using Aspose.Words for .NET

Here is the complete source code to digitally signed Pdf using certificate holder from a document using Aspose.Words for .NET:

```csharp

            // The path to the documents directory.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            
            builder.Writeln("Test Signed PDF.");

            PdfSaveOptions saveOptions = new PdfSaveOptions
            {
                DigitalSignatureDetails = new PdfDigitalSignatureDetails(
                    CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
                    DateTime.Now)
            };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
            
        
```
## Conclusion

In this tutorial, we explored the steps to add a digital signature to a PDF document using a certificate with Aspose.Words for .NET. The digital signature adds a layer of security and integrity to the document, thus guaranteeing its authenticity and making it possible to detect any subsequent modification. By following the given steps, you can easily create a digitally signed PDF using a certificate with Aspose.Words for .NET.

### Frequently Asked Questions

#### Q: What is a digital signature and why is it important in a PDF document?
A: A digital signature is a security technique that helps ensure the authenticity, integrity, and non-repudiation of an electronic document, such as a PDF file. It uses a digital certificate to add a layer of security to the document, which helps verify the identity of the author and detect any subsequent changes to the content.

#### Q: How can I add a digital signature to a PDF document using a certificate with Aspose.Words for .NET?
A: To add a digital signature to a PDF document using a certificate with Aspose.Words for .NET, follow these steps:

Create an instance of the `Document` class to represent the document.

Use the `DocumentBuilder` class to add the desired content to the document.

Create an instance of the `PdfSaveOptions` class and specify the digital signature details using the `PdfDigitalSignatureDetails` class. You will need to provide the path to the certificate (`CertificateHolder.Create`), the associated password, and the signing reason and location.

Use the `Save` method to save the document in PDF format specifying the save options.

#### Q: How do I get a certificate to add a digital signature to a PDF document?
A: To obtain a certificate to add a digital signature to a PDF document, you can usually contact a certificate authority (CA) or a trust service provider. These entities issue digital certificates after verifying your identity and validating your request. Once you have obtained a certificate, you can use it in your application to add digital signatures to PDF documents.

#### Q: Is it possible to customize the details of the digital signature, such as reason and location?
A: Yes, you can customize the digital signature details by specifying the reason and location of the signature. In the example code provided, you can modify the values of the `reason` and `location` parameters when creating the `PdfDigitalSignatureDetails` object. Be sure to provide appropriate information for each parameter to reflect the reason and location of the signature in your PDF document.
---
title: Digitally Signed Pdf Using Certificate Holder
linktitle: Digitally Signed Pdf Using Certificate Holder
second_title: Aspose.Words for .NET API Reference
description: Learn how to digitally sign a PDF using a certificate holder with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

In this tutorial, we'll walk you through the steps to create a digitally signed PDF using a certificate with Aspose.Words for .NET. The digital signature adds a layer of security and integrity to the PDF document. Follow the steps below:

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


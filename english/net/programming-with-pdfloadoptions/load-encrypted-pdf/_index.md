---
title: Load Encrypted Pdf
linktitle: Load Encrypted Pdf
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to load an encrypted PDF using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfloadoptions/load-encrypted-pdf/
---

When working with PDF documents in your .NET application, it may be necessary to load PDF files that are password protected. Aspose.Words for .NET is a powerful library that provides functionality for loading encrypted PDF documents. In this article, we will guide you step by step to understand and use this feature.

## Understanding Load Encrypted PDF Feature

The Load Encrypted PDF feature of Aspose.Words for .NET allows you to load PDF files that are password protected. You can specify the password when loading the document so that you can access its content and manipulate it as needed.

## Step 1: Loading the Encrypted PDF Document

The first step is to load the encrypted PDF document into your application. Here's how to do it:

```csharp
// Path to the documents directory.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Document.pdf");
```

Be sure to specify the correct path to the encrypted PDF file in the `dataDir` variable.

## Step 2: Encrypting the PDF Document

If you also want to encrypt your PDF document, you can do so using the `PdfSaveOptions` class and specifying the encryption details:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
};

```

This will create an encrypted version of the PDF document in the specified directory.

## Step 3: Saving the Encrypted PDF Document

After uploading and optionally encrypting the PDF document, you can save it in another format or process it further according to your specific needs.

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);
```

## Step 5: Loading the Encrypted PDF Document with Password

Maint

However, if you want to load the encrypted PDF document with a password, you must use the `PdfLoadOptions` class and specify the password when loading the document:

```csharp
PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
```

Be sure to provide the correct password in the `Password` variable.

### Example Source Code for Load Encrypted PDF using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Pdf Document.pdf");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
	};

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);

	PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

	doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
        
```

## Conclusion

In this article, we explored how to use the Load Encrypted PDF feature of Aspose.Words for .NET. You learned how to upload encrypted PDF files, how to encrypt a PDF document, how to upload an encrypted PDF with a password, and how to generate output in Markdown format. This feature is extremely useful when working with secure PDF documents.




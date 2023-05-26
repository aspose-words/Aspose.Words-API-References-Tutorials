---
title: Load Page Range Of Pdf
linktitle: Load Page Range Of Pdf
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to load a specific PDF page range with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

In this tutorial, we will walk you through how to load a specific page range from a PDF document using Aspose.Words for .NET. Follow the steps below:

## Step 1: Loading a Range of PDF Pages

Use the following code to load a specific page range from a PDF document:

```csharp
// Path to the documents directory.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

In this example, we are loading the first page of the PDF document. You can change the values of `PageIndex` and `PageCount` to the desired page range.

## Step 2: Saving the document

Finally, you can save the document containing the specific page range using the `Save` method:

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

Be sure to specify the correct path to save the edited document.

That's all ! You have now loaded a specific page range from a PDF document using Aspose.Words for .NET.

### Example source code for Load Page Range Of Pdf using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
Remember to specify the correct path to the directory of your PDF documents.





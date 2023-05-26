---
title: Update Last Printed Property
linktitle: Update Last Printed Property
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to update "Last Printed" property when converting to PDF with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/update-last-printed-property/
---

This article provides a step-by-step guide on how to use the "Last Printing" property update feature with Aspose.Words for .NET. We will explain each part of the code in detail. At the end of this tutorial, you will be able to understand how to configure the option to update the "Last printed" property when converting to PDF.

Before you start, make sure you have installed and configured the Aspose.Words for .NET library in your project. You can find the library and installation instructions on the Aspose website.

## Step 1: Define the document directory

To start, you need to define the path to the directory where your documents are located. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your documents directory.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Upload the document

Next, we need to load the document we want to process. In this example, we assume the document is called "Rendering.docx" and is located in the specified documents directory.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Step 3: Configure Save as PDF Options with Updated "Last Printed" Property

To enable updating the "Last Printed" property when converting to PDF, we need to configure the `PdfSaveOptions` object and set the `UpdateLastPrintedProperty` property to `true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## Step 4: Save the document as a PDF with the update of the "Last printed" property

Finally, we can save the document in PDF format using the save options configured previously.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
```

That's all ! You have successfully enabled updating the "Last Printed" property when converting a document to PDF using Aspose.Words for .NET.

### Example Source Code for Updating "Last Printed" Property with Aspose.Words for .NET


```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);

```


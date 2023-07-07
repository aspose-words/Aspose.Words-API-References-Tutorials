---
title: Update Last Printed Property in PDF Document
linktitle: Update Last Printed Property in PDF Document
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to update "Last Printed" property when converting to PDF with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/update-last-printed-property/
---

This article provides a step-by-step guide on how to use the "Last Printing" property in PDF Document update feature with Aspose.Words for .NET. We will explain each part of the code in detail. At the end of this tutorial, you will be able to understand how to configure the option to update the "Last printed" property when converting to PDF.

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
## Conclusion

In this tutorial, we explained how to update the "Last Printed" property in a PDF document using Aspose.Words for .NET. By following the given steps, you can easily configure the option to update the "Last Printed" property when converting a document to PDF. Use this feature to keep track of document usage and related information.

### Frequently Asked Questions

#### Q: What is the "Last Printed" property in a PDF document?
A: The "Last Printed" property in a PDF document refers to the date and time when the document was last printed. This property can be useful for tracking information about document usage and management.

#### Q: How can I update the "Last Printed" property in a PDF document with Aspose.Words for .NET?
A: To update the "Last Printed" property in a PDF document with Aspose.Words for .NET, follow these steps:

Create an instance of the `Document` class specifying the path to the Word document.

Create an instance of the `PdfSaveOptions` class and set the `UpdateLastPrintedProperty` property to `true` to enable updating the "Last Printed" property.

Use the `Save` method of the `Document` class to save the document in PDF format by specifying save options.

#### Q: How can I check if the "Last Printed" property has been updated in the generated PDF document?
A: You can check if the "Last Printed" property has been updated in the generated PDF document by opening the PDF file with a compatible PDF viewer, such as Adobe Acrobat Reader, and viewing the document information. The date and time of the last printing should correspond to the date and time of the generation of the PDF document.


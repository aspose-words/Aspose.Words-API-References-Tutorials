---
title: Export Word Document Structure to PDF Document
linktitle: Export Word Document Structure to PDF Document
second_title: Aspose.Words for .NET API Reference
description: Step by step guide to Export Word Document Structure to PDF Document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/export-document-structure/
---

This article provides a step-by-step guide on how to use the Export Word Document Structure to PDF Document feature with Aspose.Words for .NET. We will explain each part of the code in detail. At the end of this tutorial, you will be able to understand how to export the structure of a document and generate a PDF with the structure of the document visible.

Before you start, make sure you have installed and configured the Aspose.Words for .NET library in your project. You can find the library and installation instructions on the Aspose website.

## Step 1: Define the document directory

To start, you need to define the path to the directory where your documents are located. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your documents directory.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Upload the document

Next, we need to load the document we want to process. In this example, we assume the document is called "Paragraphs.docx" and is located in the specified documents directory.

```csharp
Document doc = new Document(dataDir + "Paragraphs.docx");
```

## Step 3: Configure save as PDF options

To export the document structure and make the structure visible in Adobe Acrobat Pro's "Content" navigation pane while editing the PDF file, we need to configure the `PdfSaveOptions` object with the `ExportDocumentStructure` property set to `true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };
```

## Step 4: Save the document as a PDF with the document structure

Finally, we can save the document in PDF format using the save options configured previously.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
```

That's all ! You have successfully exported a document structure and generated a PDF with the document structure visible using Aspose.Words for .NET.

### Sample source code for exporting document structure with Aspose.Words for .NET


```csharp

            // The path to the documents directory.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "Paragraphs.docx");

            // The file size will be increased and the structure will be visible in the "Content" navigation pane
            // of Adobe Acrobat Pro, while editing the .pdf.
            PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
        
```


## Conclusion

In this tutorial, we have explained how to export the structure of a Word document to a PDF document using Aspose.Words for .NET. By following the steps outlined, you can easily generate a PDF with your document structure visible, making it easier to navigate and search through the document. Use the features of Aspose.Words for .NET to export the structure of your Word documents and create well-structured PDFs.

### Frequently Asked Questions

#### Q: What is exporting the structure of a Word document to a PDF document?
A: Exporting the structure of a Word document to a PDF document creates a PDF with a visible document structure. Document structure usually includes things like headings, sections, paragraphs, and other structured elements of the document. This structure can be useful for navigation and searching in the PDF document.

#### Q: How can I export the structure of a Word document to a PDF document using Aspose.Words for .NET?
A: To export the structure of a Word document to a PDF document using Aspose.Words for .NET, follow these steps:

Create an instance of the `Document` class specifying the path to the Word document.

Create an instance of the `PdfSaveOptions` class and set the `ExportDocumentStructure` property to `true`. This will export the document structure and make it visible in Adobe Acrobat Pro's "Content" navigation pane when editing the PDF file.

Use the `Save` method of the `Document` class to save the document in PDF format by specifying save options.

#### Q: How can I view the structure of a PDF document with Adobe Acrobat Pro?
A: To view the structure of a PDF document with Adobe Acrobat Pro, follow these steps:

Open the PDF document in Adobe Acrobat Pro.

In the left navigation bar, click the "Content" icon to display the "Content" navigation pane.

In the "Content" navigation pane, you will see the document structure with headings, sections, and other structured elements.

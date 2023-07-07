---
title: Render 3D DML 3DEffects in a PDF Document
linktitle: Render 3D DML 3DEffects in a PDF Document
second_title: Aspose.Words for .NET API Reference
description: Learn how to enable rendering of 3D DML effects when converting to PDF with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/dml-3deffects-rendering/
---

In this tutorial, we will walk you through the steps to enable 3D DML effect rendering when converting to PDF with Aspose.Words for .NET. This keeps the 3D effects in the generated PDF document. Follow the steps below:

## Step 1: Loading the document

Start by uploading the document you want to convert to PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Be sure to specify the correct path to your document.

## Step 2: Configure PDF save options

Create an instance of the PdfSaveOptions class and enable advanced rendering of 3D DML effects:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };
```

This option keeps the 3D effects in the generated PDF document.

## Step 3: Convert Document to PDF

Use the `Save` method to convert the document to PDF specifying save options:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
```

Make sure to specify the correct path to save the converted PDF.

### Example source code for Dml 3DEffects Rendering using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
	 
```

By following these steps, you can easily enable rendering of 3D DML effects when converting to PDF with Aspose.Words for .NET.

## Conclusion

In this tutorial, we explained how to enable rendering of 3D DML effects when converting to PDF with Aspose.Words for .NET. By following the described steps, you can easily keep the 3D effects in the generated PDF document. Use this feature to preserve the important visual effects of your original document.


### Frequently Asked Questions

#### Q: What is rendering 3D DML effects in a PDF document?
A: Rendering 3D DML effects in a PDF document refers to the ability to retain 3D effects when converting a document to PDF format. This preserves the visual effects and ensures that the generated PDF document looks like the original document.

#### Q: How can I enable rendering of 3D DML effects when converting to PDF with Aspose.Words for .NET?
A: To enable rendering of 3D DML effects when converting to PDF with Aspose.Words for .NET, follow these steps:

Create an instance of the `Document` class specifying the path to the Word document.

Create an instance of the `PdfSaveOptions` class and set the `Dml3DEffectsRenderingMode` property to `Dml3DEffectsRenderingMode.Advanced` to enable advanced rendering of 3D DML effects.

Use the `Save` method of the `Document` class to save the document in PDF format by specifying save options.

#### Q: How can I check if 3D DML effects have been rendered in the generated PDF document?
A: To check if the 3D DML effects have been rendered in the generated PDF document, open the PDF file with a compatible PDF viewer, such as Adobe Acrobat Reader, and examine the document. You should see the 3D effects as they appear in the original document.





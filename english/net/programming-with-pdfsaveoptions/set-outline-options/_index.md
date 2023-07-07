---
title: Set Outline Options in a PDF Document
linktitle: Set Outline Options in a PDF Document
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to set outline options in a PDF document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/set-outline-options/
---

This article provides a step-by-step guide on how to use the set outline options to metafile size feature with Aspose.Words for .NET. We will explain each part of the code in detail. At the end of this tutorial, you will be able to understand how to set outline options in a document and generate a PDF with the corresponding outline options.

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

## Step 3: Configure save as PDF options with plan options

To set outline options in the generated PDF, we need to configure the `PdfSaveOptions` object. We can set the number of heading outline levels (`HeadingsOutlineLevels`) and the number of expanded outline levels (`ExpandedOutlineLevels`).

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## Step 4: Save document as PDF with outline options

Finally, we can save the document in PDF format using the save options configured previously.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

That's all ! You have successfully set outline options in a document and generated a PDF with corresponding outline options using Aspose.Words for .NET.

### Example source code to set plan options to metafile size with Aspose.Words for .NET


```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
	saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
   
```

## Conclusion

In this tutorial, we explained how to set outline options in a PDF document using Aspose.Words for .NET. Using the steps described, you can easily specify heading and outline levels in your document and generate a PDF file with corresponding outline options. Enjoy the benefits of the outline option to improve structure and navigation in your PDF documents using Aspose.Words for .NET.

### Frequently Asked Questions

#### Q: What is the outline option in a PDF document?
A: The outline option in a PDF document refers to the hierarchical structure of the document content. It allows you to create an interactive table of contents and facilitates navigation in the document. Outline options determine the title and subtitle levels to include in the outline and the level of detail to display in the generated outline.

#### Q: How can I set outline options in a PDF document using Aspose.Words for .NET?
A: To set outline options in a PDF document using Aspose.Words for .NET, follow these steps:

Set the directory path where your documents are located by replacing `"YOUR DOCUMENT DIRECTORY"` with the actual path of your documents directory.

Load the document you want to convert to PDF using the `Document` class and specify the path to the document in the specified documents directory.

Configure save as PDF options by creating an instance of the `PdfSaveOptions` class and using the `OutlineOptions` property to set the outline options. You can specify the number of heading levels to include in the outline using the `HeadingsOutlineLevels` property and the number of expanded outline levels using the `ExpandedOutlineLevels` property.

Save the document in PDF format using the `Save` method of the `Document` class specifying the path and saving options.

#### Q: What is the plan option for in a PDF document?
A: The outline option in a PDF document allows you to create a hierarchical structure of the content, which makes it easier to navigate the document and access different sections. This allows users to quickly jump to specific parts of the document by clicking entries in the table of contents or outline. The outline option also enhances the reading experience by providing an overview of the overall document structure.


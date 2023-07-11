---
title: Set Page Setup And Section Formatting
linktitle: Set Page Setup And Section Formatting
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to setting up a document's layout and section formatting with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

In this tutorial, we will walk you through the C# source code to set up layout and section formatting with Aspose.Words for .NET. This feature lets you set the page orientation, margins, and paper size.

## Step 1: Project Setup

To get started, create a new C# project in your favorite IDE. Make sure the Aspose.Words for .NET library is referenced in your project.

## Step 2: Creating the document

In this step, we will create a new document. Use the following code to create the document and initialize the constructor:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Replace `"YOUR DOCUMENTS DIRECTORY"` with the actual path of the directory where you want to save the document.

## Step 3: Setting up the layout and save document

Now let's configure the document layout. Use the following code to set the orientation, margins, and paper size:

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

This code will set the page orientation to landscape, the left margin to 50, and the paper size to 10x14.

### Example source code for Set Page Setup And Section Formatting using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.PageSetup.Orientation = Orientation.Landscape;
	builder.PageSetup.LeftMargin = 50;
	builder.PageSetup.PaperSize = PaperSize.Paper10x14;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
  
```

Be sure to specify the correct path to the directory where you want to save the document in the `dataDir` variable.

You have now learned how to configure the layout and section formatting of a document using Aspose.Words for .NET. By following the step-by-step guide provided in this tutorial, you can easily customize the layout and formatting of your own documents.

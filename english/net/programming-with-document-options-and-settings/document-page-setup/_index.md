---
title: Document Page Setup
linktitle: Document Page Setup
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to setting up a document layout with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-document-options-and-settings/document-page-setup/
---

In this tutorial, we will walk you through the C# source code to configure document layout with Aspose.Words for .NET. This feature allows you to set the layout mode, the number of characters per line and the number of lines per page.

## Step 1: Project Setup

To get started, create a new C# project in your favorite IDE. Make sure the Aspose.Words for .NET library is referenced in your project.

## Step 2: Loading the document

In this step, we will load the Word document that we want to configure. Use the following code to load the document:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

Replace `"YOUR DOCUMENTS DIRECTORY"` with the actual path of the directory where your document is located.

## Step 3: Setting up the layout

Now let's configure the document layout. Use the following code to set the layout mode, number of characters per line, and number of lines per page:

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

This code sets the layout mode to "Grid" and then specifies the number of characters per line and the number of lines per page.

### Example source code for Document Page Setup using Aspose.Words for .NET


```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Set the layout mode for a section allowing to define the document grid behavior.
	// Note that the Document Grid tab becomes visible in the Page Setup dialog of MS Word
	// if any Asian language is defined as editing language.
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

Be sure to specify the correct document path in the `dataDir` variable.

You have now learned how to configure the layout of a document using Aspose.Words for .NET. By following the step-by-step guide provided in this tutorial, you can easily customize the layout of your own documents.

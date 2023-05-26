---
title: View Options
linktitle: View Options
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to configure document display options with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-document-options-and-settings/view-options/
---

In this tutorial, we will walk you through the C# source code to configure display options with Aspose.Words for .NET. This feature allows you to customize the view mode and zoom level in a document.

## Step 1: Project Setup

To get started, create a new C# project in your favorite IDE. Make sure the Aspose.Words for .NET library is referenced in your project.

## Step 2: Loading the document

In this step, we will load the Word document for which we want to configure the display options. Use the following code to load the document:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

Replace `"YOUR DOCUMENTS DIRECTORY"` with the actual path of the directory where your document is located.

## Step 3: Configuring display options

Now we will configure the document display options. Use the following code to set the display mode and zoom level:

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

This code sets the view mode to "PageLayout" and the zoom level to 50%.

### Example source code for View Options using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

Be sure to specify the correct document path in the `dataDir` variable.

You have now learned how to configure document display options using Aspose.Words for .NET. By following the step-by-step guide provided in this tutorial, you can easily customize the display of your own documents.

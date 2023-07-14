---
title: Export Cid Urls For Mhtml Resources
linktitle: Export Cid Urls For Mhtml Resources
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to export CID URLs of MHTML resources when saving a document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---

In this tutorial, we will walk you through the C# source code to export CID URLs for MHTML resources with Aspose.Words for .NET. This feature allows you to export CID URLs of MHTML resources when saving a document in MHTML format.

## Step 1: Project Setup

To get started, create a new C# project in your favorite IDE. Make sure the Aspose.Words for .NET library is referenced in your project.

## Step 2: Loading the document

In this step, we will load the document to export. Use the following code to load the document from a specified directory:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Content-ID.docx");
```

This code creates an instance of `Document` by loading the document from the specified directory.

## Step 3: Configuring HTML backup options

Now we will configure HTML save options to export CID URLs of MHTML resources. Use the following code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
PrettyFormat = true,
ExportCidUrlsForMhtmlResources = true
};
```

This code creates an instance of `HtmlSaveOptions` with the save format set to MHTML. It also enables the export of CID URLs of MHTML resources by setting `ExportCidUrlsForMhtmlResources` to `true`.

## Step 4: Converting and saving the document to MHTML

Finally, we will convert the document to MHTML using the HTML saving options configured earlier. Use the following code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

This code converts the document to MHTML and saves it to a file with the CID URLs of the exported MHTML resources.

### Example source code for Export Cid Urls For Mhtml Resources using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Content-ID.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
	{
		PrettyFormat = true, ExportCidUrlsForMhtmlResources = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);

```

Be sure to specify the correct path to the documents directory in the `dataDir` variable.

You have now learned how to export CID URLs of MHTML resources when saving a document in MHTML format using Aspose.Words for .NET. By following the step-by-step guide provided in this tutorial, you can easily manage CID URLs in your exported MHTML documents.



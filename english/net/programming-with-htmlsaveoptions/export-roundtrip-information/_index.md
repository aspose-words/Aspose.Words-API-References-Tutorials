---
title: Export Roundtrip Information
linktitle: Export Roundtrip Information
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to export roundtrip information when saving a document as HTML with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

In this tutorial, we will walk you through the C# source code to export roundtrip information from a document with Aspose.Words for .NET. This feature allows you to include roundtrip information in the exported HTML file, making it easier to retrieve changes made to the original document.

## Step 1: Project Setup

To get started, create a new C# project in your favorite IDE. Make sure the Aspose.Words for .NET library is referenced in your project.

## Step 2: Loading the document

In this step, we will load the document to export. Use the following code to load the document from a specified directory:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

This code creates an instance of `Document` by loading the document from the specified directory.

## Step 3: Configuring HTML backup options

Now we will configure the HTML save options to export the document's roundtrip information. Use the following code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

This code creates an instance of `HtmlSaveOptions` and sets the `ExportRoundtripInformation` option to `true` to include roundtrip information when exporting.

## Step 4: Converting and saving the document to HTML

Finally, we will convert the document to HTML using the HTML saving options configured earlier. Use the following code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

This code converts the document to HTML including the roundtrip information, and saves the exported HTML file to the specified directory.

### Example source code for Export Roundtrip Information using Aspose.Words for .NET


```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

Be sure to specify the correct path to the documents directory in the `dataDir` variable.

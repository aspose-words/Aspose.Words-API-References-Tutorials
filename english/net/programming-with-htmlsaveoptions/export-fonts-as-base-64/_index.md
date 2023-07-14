---
title: Export Fonts As Base 64
linktitle: Export Fonts As Base 64
second_title: Aspose.Words Document Processing API
description: Step by step guide to export base 64 fonts when saving a document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

In this tutorial, we will walk you through the C# source code to export base 64 fonts with Aspose.Words for .NET. This feature allows you to export fonts as base 64 data when saving a document in HTML format.

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

Now we will configure the HTML save options to export base 64 fonts. Use the following code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

This code creates an instance of `HtmlSaveOptions` and sets `ExportFontsAsBase64` to `true` to specify that fonts should be exported as base 64 data when saving as HTML.

## Step 4: Converting and saving the document to HTML

Finally, we will convert the document to HTML using the HTML saving options configured earlier. Use the following code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

This code converts the document to HTML and saves it to a file with the fonts exported as base 64 data.

### Example source code for Export Fonts As Base 64 using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

Be sure to specify the correct path to the documents directory in the `dataDir` variable.

You have now learned how to export base 64 fonts when saving a document as HTML using Aspose.Words for .NET. By following the step-by-step guide provided in this tutorial, you can easily export fonts securely and embedded in your HTML documents.

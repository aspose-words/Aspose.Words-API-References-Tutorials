---
title: Export Resources
linktitle: Export Resources
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to export document resources when saving as HTML with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-htmlsaveoptions/export-resources/
---

In this tutorial, we will walk you through the C# source code to export document resources with Aspose.Words for .NET. This feature allows you to export resources, such as fonts, as external files when saving a document in HTML format.

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

Now we will configure the HTML save options to export the document resources. Use the following code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
CssStyleSheetType = CssStyleSheetType.External,
ExportFontResources=true,
ResourceFolder = ArtifactsDir + "Resources",
ResourceFolderAlias = "http://example.com/resources"
};
```

This code creates an instance of `HtmlSaveOptions` and sets the following options:

- `CssStyleSheetType` is set to `CssStyleSheetType.External` to export the CSS style sheet to an external file.
- `ExportFontResources` is set to `true` to export font resources.
- `ResourceFolder` specifies the destination directory where the resources will be saved.
- `ResourceFolderAlias` specifies the URL alias that will be used to access resources.

## Step 4: Converting and saving the document to HTML

Finally, we will convert the document to HTML using the HTML saving options configured earlier. Use the following code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

This code converts the document to HTML and saves the resources to the specified directory, using the specified URL alias.

### Example source code for Export Resources using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External,
		ExportFontResources = true,
		ResourceFolder = ArtifactsDir + "Resources",
		ResourceFolderAlias = "http://example.com/resources"
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
  
```

Be sure to specify the correct path to the documents directory in the `dataDir` variable.

---
title: Export Text Input Form Field As Text
linktitle: Export Text Input Form Field As Text
second_title: Aspose.Words Document Processing API
description: Step by step guide to export text input form fields as plain text with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---

In this tutorial, we will walk you through the C# source code to export text input form fields as plain text with Aspose.Words for .NET. This feature allows you to export text input form fields as readable text, rather than exporting them as HTML input elements.

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

Now we will configure HTML save options to export text input form fields as plain text. Use the following code:

```csharp
string imagesDir = Path. Combine(ArtifactsDir, "Images");

// The specified folder must exist and be empty.
if (Directory.Exists(imagesDir))
Directory. Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
ExportTextInputFormFieldAsText = true,
ImagesFolder = imagesDir
};
```

This code creates an instance of `HtmlSaveOptions` and sets the `ExportTextInputFormFieldAsText` option to `true` to export text input form fields as plain text. Moreover, it specifies the folder where the extracted images will be saved.

## Step 4: Converting and saving the document to HTML

Finally, we will convert the document to HTML using the HTML saving options configured earlier. Use the following code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```

This code converts the document to HTML by exporting text input form fields as plain text, and saves the exported HTML file to the specified directory.

### Example source code for Export Text Input Form Field As Text using Aspose.Words for .NET


```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	string imagesDir = Path.Combine(ArtifactsDir, "Images");

	// The folder specified needs to exist and should be empty.
	if (Directory.Exists(imagesDir))
		Directory.Delete(imagesDir, true);

	Directory.CreateDirectory(imagesDir);

	// Set an option to export form fields as plain text, not as HTML input elements.
	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		ExportTextInputFormFieldAsText = true, ImagesFolder = imagesDir
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);

```

Be sure to specify the correct path to the documents directory in the `dataDir` variable.

---
title: Resolve Font Names
linktitle: Resolve Font Names
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to resolve missing font names when converting to HTML with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-htmlsaveoptions/resolve-font-names/
---

In this tutorial, we will walk you through the C# source code to resolve missing font names with Aspose.Words for .NET. This feature allows you to automatically resolve missing font names when converting a document to HTML.

## Step 1: Project Setup

To get started, create a new C# project in your favorite IDE. Make sure the Aspose.Words for .NET library is referenced in your project.

## Step 2: Loading the document

In this step, we will load the document to be processed. Use the following code to load the document from a specified directory:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

This code creates an instance of `Document` by loading the document from the specified directory.

## Step 3: Configuring HTML backup options

Now we will configure HTML save options to resolve missing font names during conversion. Use the following code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

This code creates an instance of `HtmlSaveOptions` and sets the `ResolveFontNames` option to `true` to resolve missing font names when converting to HTML. Also, the `PrettyFormat` option is set to `true` to get nicely formatted HTML code.

## Step 4: Converting and saving the document to HTML

Finally, we will convert the document to HTML using the HTML saving options configured earlier. Use the following code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

This code converts the document to HTML by automatically resolving missing font names, and saves the converted HTML file to the specified directory.

### Example source code for Resolve Font Names using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Missing font.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		PrettyFormat = true, ResolveFontNames = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);

```

Be sure to specify the correct path to the documents directory in the `dataDir` variable.

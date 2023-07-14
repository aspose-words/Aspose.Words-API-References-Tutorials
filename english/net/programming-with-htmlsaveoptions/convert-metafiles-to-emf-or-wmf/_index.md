---
title: Convert Metafiles To Emf Or Wmf
linktitle: Convert Metafiles To Emf Or Wmf
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to converting metafiles to EMF or WMF formats when converting a document to HTML with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

In this tutorial, we will walk you through the C# source code to convert metafiles to EMF or WMF format with Aspose.Words for .NET. This feature allows you to convert images in metafile format to more compatible formats such as EMF or WMF when converting a document to HTML.

## Step 1: Project Setup

To get started, create a new C# project in your favorite IDE. Make sure the Aspose.Words for .NET library is referenced in your project.

## Step 2: Inserting an image into the document

In this step, we will insert an image into the document to be converted. Use the following code to insert an image from a data source using an HTML tag:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an image as is: ");
builder.InsertHtml(
	@"<img src=""data:image/png;base64,
		iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
		C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
		AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
		REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
		ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
		vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");
```

This code creates an instance of `Document` and `DocumentBuilder` to build the document. It inserts an `<img>` tag into the document with a base64 encoded image.

## Step 3: Set HTML save options

Now we'll set the HTML save options, including the metafile format to use for images. Use the following code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

This code creates an instance of `HtmlSaveOptions` and sets `MetafileFormat` to `HtmlMetafileFormat.EmfOrWmf` to specify that metafiles should be converted to EMF or WMF format when converting to HTML.

## Step 4: Converting and saving the document to HTML

Finally we will convert the document to HTML using the save HTML options previously defined. Use the following code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

This code converts the document to HTML and saves it to a file with the converted metafiles in EMF or WMF format depending on the save options set.

### Example source code for Convert Metafiles To Emf Or Wmf using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Here is an image as is: ");
	builder.InsertHtml(
		@"<img src=""data:image/png;base64,
			iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
			C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
			AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
			REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
			ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
			vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);

```

Be sure to specify the correct path to the documents directory in the `dataDir` variable.

You have now learned how to convert metafiles to EMF or WMF formats when converting a document to HTML using Aspose.Words for .NET. By following the step-by-step guide provided in this tutorial, you can easily manage metafiles in your converted HTML documents.

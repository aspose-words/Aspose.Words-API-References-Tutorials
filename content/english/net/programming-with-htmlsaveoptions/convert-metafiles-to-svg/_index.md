---
title: Convert Metafiles To Svg
linktitle: Convert Metafiles To Svg
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to converting metafiles to SVG format when converting a document to HTML with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

In this tutorial, we will walk you through the C# source code to convert metafiles to SVG format with Aspose.Words for .NET. This feature allows you to convert metafiles to SVG format when converting a document to HTML.

## Step 1: Project Setup

To get started, create a new C# project in your favorite IDE. Make sure the Aspose.Words for .NET library is referenced in your project.

## Step 2: Inserting an SVG image into the document

In this step, we will insert an SVG image into the document to be converted. Use the following code to insert an SVG image using an HTML tag:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an SVG image: ");
builder.InsertHtml(
	@"<svg height='210' width='500'>
	<polygon points='100,10 40,198 190,78 10,78 160,198' 
		style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
</svg> ");
```

This code creates an instance of `Document` and `DocumentBuilder` to build the document. It inserts a `<svg>` tag containing a `<polygon>` element with attributes to define the shape and style of the SVG image.

## Step 3: Set HTML save options

Now we'll set the HTML save options, specifying that metafiles should be converted to SVG format. Use the following code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

This code creates an instance of `HtmlSaveOptions` and sets `MetafileFormat` to `HtmlMetafileFormat.Svg` to specify that metafiles should be converted to SVG format when converting to HTML.

## Step 4: Converting and saving the document to HTML

Finally, we'll convert the document to HTML using the HTML save options defined earlier. Use the following code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

This code converts the document to HTML and saves it to a file with the metafiles converted to SVG.

### Example source code for Convert Metafiles To Svg using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Write("Here is an SVG image: ");
	builder.InsertHtml(
		@"<svg height='210' width='500'>
		<polygon points='100,10 40,198 190,78 10,78 160,198' 
			style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
	</svg> ");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
	
```


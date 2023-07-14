---
title: Add Css Class Name Prefix
linktitle: Add Css Class Name Prefix
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to add a CSS class name prefix when converting a document to HTML with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

In this tutorial, we will walk you through the C# source code to add a CSS class name prefix with Aspose.Words for .NET. This feature allows you to add a custom prefix to generated CSS class names when converting a document to HTML.

## Step 1: Project Setup

To get started, create a new C# project in your favorite IDE. Make sure the Aspose.Words for .NET library is referenced in your project.

## Step 2: Loading the document

In this step, we will load the Word document that we want to convert to HTML. Use the following code to load the document:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Replace `"YOUR DOCUMENTS DIRECTORY"` with the actual path of the directory where your document is located.

## Step 3: Set HTML save options

Now let's set the HTML save options, including CSS stylesheet type and CSS class name prefix. Use the following code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

This code creates an instance of `HtmlSaveOptions` and sets `CssStyleSheetType` to `CssStyleSheetType.External` to generate an external CSS style sheet, and `CssClassNamePrefix` to `"pfx_"` to prefix `"pfx_"` to names CSS class.

## Step 4: Converting and saving the document to HTML

Finally, we'll convert the document to HTML using the HTML save options defined earlier. Use the following code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

This code converts the document to HTML and saves it to a file with the CSS class name prefix added.

### Example source code for Add Css Class Name Prefix using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External, CssClassNamePrefix = "pfx_"
	};
	
	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);

```

Be sure to specify the correct document path in the `dataDir` variable.

You have now learned how to add a CSS class name prefix when converting a document to HTML using Aspose.Words for .NET. Following the step-by-step guide step provided in this tutorial, you can customize the CSS class names in your converted HTML documents.

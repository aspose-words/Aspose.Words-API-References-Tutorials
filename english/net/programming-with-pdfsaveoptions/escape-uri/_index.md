---
title: Escape Uri
linktitle: Escape Uri
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to escaping Uri with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/escape-uri/
---

This article provides a step by step guide on how to use the Uri escape feature with Aspose.Words for .NET. We will explain each part of the code in detail. At the end of this tutorial, you will be able to understand how to insert hyperlinks with escaped Uri in a document.

Before you start, make sure you have installed and configured the Aspose.Words for .NET library in your project. You can find the library and installation instructions on the Aspose website.

## Step 1: Define the document directory

To start, you need to define the path to the directory where your documents are located. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your documents directory.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Create a document and a DocumentBuilder

Next, we need to create a new `Document` object and a `DocumentBuilder` object to build the document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 3: Insert hyperlinks with escaped Uri

Use the `InsertHyperlink` method of the `DocumentBuilder` object to insert hyperlinks into the document. Uri must be escaped using the `Uri.EscapeUriString` function to avoid format errors.

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), false);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"),
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), false);
```

## Step 4: Save the document as a PDF

Finally, we can save the document as a PDF using the `Save` method of the `Document` object. Specify the output file name.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

That's all ! You have successfully inserted hyperlinks with escaped Uri's in a document using Aspose.Words for .NET.

### Sample source code for Uri escaping with Aspose.Words for .NET


```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search?q=%2Fthe%20test", false);
	builder.Writeln();
	builder.InsertHyperlink("https://www.google.com/search?q=%2Fthe%20test", 
		"https://www.google.com/search?q=%2Fthe%20test", false);

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```


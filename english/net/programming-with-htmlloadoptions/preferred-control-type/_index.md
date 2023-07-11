---
title: Preferred Control Type
linktitle: Preferred Control Type
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to specifying the preferred control type when loading an HTML document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-htmlloadoptions/preferred-control-type/
---

This article provides a step-by-step guide on how to use the preferred control type feature with Aspose.Words for .NET. We will explain each part of the code in detail. At the end of this tutorial, you will be able to understand how to specify the preferred control type when loading an HTML document.

Before you start, make sure you have installed and configured the Aspose.Words for .NET library in your project. You can find the library and installation instructions on the Aspose website.

## Step 1: Define the HTML code

To start, you need to define the HTML code you want to load as a document. In this example, we have defined an `html` variable containing the HTML code of a selector with options.

```csharp
const string html=@"
<html>
<select name='ComboBox' size='1'>
<option value='val1'>item1</option>
<option value='val2'></option>
</select>
</html>
";
```

## Step 2: Set HTML loading options

Next, we create an `HtmlLoadOptions` object and set the `PreferredControlType` property to `HtmlControlType.StructuredDocumentTag`. This tells Aspose.Words to use StructuredDocumentTags to represent HTML when loading.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## Step 3: Load and save the document

We use the `Document` class to load HTML code from a memory stream with the load options defined earlier. Then we save the document in the specified directory with the `.docx` file format.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### Example source code for preferred control type with Aspose.Words for .NET

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

That's all ! You have successfully specified the preferred control type when loading an HTML document with Aspose.Words for .NET.
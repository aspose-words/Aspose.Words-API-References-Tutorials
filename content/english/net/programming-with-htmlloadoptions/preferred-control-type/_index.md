---
title: Preferred Control Type In Word Document
linktitle: Preferred Control Type In Word Document
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to specifying the preferred control type in word document when loading an HTML document with Aspose.Words for .NET.
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

## Conclusion

By following this step-by-step guide, you have learned how to use the "Preferred Control Type" feature in Aspose.Words for .NET to specify the desired control type when loading an HTML document. Setting the `PreferredControlType` property to `HtmlControlType.StructuredDocumentTag` allows Aspose.Words to use StructuredDocumentTags (SDT) for better representation and processing of HTML content. You can explore other control types as well to suit your specific requirements. Using this feature helps ensure accurate and efficient handling of HTML documents in your C# application with Aspose.Words.

### FAQ's for preferred control type in word document

#### Q: What is the "Preferred Control Type" feature in Aspose.Words for .NET?

A: The "Preferred Control Type" feature allows you to specify the preferred type of control to represent HTML elements when loading an HTML document. It helps in selecting the appropriate control type for better representation and processing of the HTML content.

#### Q: How do I set the preferred control type when loading an HTML document?

A: To set the preferred control type, you need to create an `HtmlLoadOptions` object and set its `PreferredControlType` property to the desired `HtmlControlType`. In the provided example, `HtmlControlType.StructuredDocumentTag` is used.

#### Q: What is the significance of using StructuredDocumentTags (SDT) as the preferred control type?

A: StructuredDocumentTags (SDT) are XML-based elements that can be used to represent complex content and controls in a Word document. Using SDTs as the preferred control type can provide better compatibility and representation of HTML content.

#### Q: How can I ensure that Aspose.Words uses the preferred control type when loading the HTML document?

A: By setting the `PreferredControlType` property to `HtmlControlType.StructuredDocumentTag`, as shown in the example source code, Aspose.Words will use SDTs to represent HTML elements when loading the document.

#### Q: Can I use other control types as the preferred option?

A: Yes, apart from `HtmlControlType.StructuredDocumentTag`, Aspose.Words for .NET supports other control types such as `HtmlControlType.ContentControl` and `HtmlControlType.CustomXmlMarkup`.
